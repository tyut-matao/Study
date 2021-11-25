### 基础知识梳理

---

1. Java 数据类型分为两大类：基本类型和引用类型

   | 类型     | 具体                                               |
   | :------- | -------------------------------------------------- |
   | 基本类型 | 数值类型（整数类型、浮点类型、字符类型）、布尔类型 |
   | 引用类型 | 类、接口、数组                                     |

2. 类型转换：强类型转换和自动类型转换 （运算中不同类型先转换为同一类型然后再进行运算）

   - 强类型转换： byte > short > char > int > long > float > double
   - 自动类型转换
   
3. 变量：变量名、变量类型、作用域

4. 位运算符（二进制）

   - 左移：相当于乘以2
   - 右移：相当于除以2
   
5. 条件运算符（？ ：）

   x ? y : z    意思是如果X为真（true），则计算结果为y，反之则为z
   
   x可以为表达式，如：    score > 60  ?  "及格"："不及格";

6. Java的包机制：类似于命名空间，不同的包中的相同类名不冲突
7. JavaDoc生成文档： javadoc -encoding UTF-8  -charset  UTF-8   xxx.java



### Java 流程控制

***

1. 用户交互（Scanner）

   - Package   java.util.Scanner
   
   - 基本语法：
   
     Scanner s = new Scanner ( System.in )
     
   - 通过 Scanner 类的 next( ) 与 nextLine( ) 方法获取输入的字符串，在读取前我们一般需要使用 hasNext( ) 与 hasNextLine( ) 判断时候还有输入的数据
   
   - ```java
     import java.util.Scanner;
     
     Public class Demo1{
         public static void main(String[] args){
             //创建一个扫描枪对象，用于获取键盘的输入
             Scanner scanner = new Scanner(System.in);
             System.out.println("使用 next 方式接收：");
             //判断用户有没有输入字符串
             if(scanner.hasNext()){
                 //使用 next 方式接收用户的输入
                 String str = scanner.next();
                 System.out.println(" 输入的内容为：" + str);
             }
             //关闭IO流
             scanner.close();
         }
     }
     
     Public class Demo2{
         public static void main(String[] args){
             //创建一个扫描枪对象，用于获取键盘的输入
             Scanner scanner = new Scanner(System.in);
             System.out.println("使用 nextLine 方式接收：");
             //判断用户有没有输入字符串
             if(scanner.hasNextLine()){
                 //使用 next 方式接收用户的输入
                 String str = scanner.nextLine();
                 System.out.println(" 输入的内容为：" + str);
             }
             //关闭IO流
             scanner.close();
         }
     }
     ```
   
   - 上面的例子： （输入为 Hello World！） 
   
       - hasNext( ) 方式输出为：   Hello
       - hasNextLine( ) 方式输出为：   Hello World!
       - next( ) 和 nextLine( ) 的区别
         - next( ) 
           1. 一定要读取到有效字符后才可以结束输入
           2. 对输入有效字符之前遇到的空白，next( ) 方法会自动将其去掉
           3. 只有输入有效字符后才将其后面输入的空白作为分隔符或者结束符
           4. next( ) 不能得到带有空格的字符串  
         - nextLine( )
           1. 以 enter 为结束符，也就是说 nextLine( ) 方法返回的是输入回车之前的所有字符
           2. 可以获得空白
   
2. Scanner 进阶使用

   - 判断不同数据类型的数据输入

     ```java
     Public class Demo3{
         public static void main(String[] args){
              //创建一个扫描枪对象，用于获取键盘的输入
             Scanner scanner = new Scanner(System.in);
             int i = 0;
             float f = 0.0f;
             System.out.println("请输入整数：");
             //判断用户有没有输入整数,若果是整数，就执行，反之执行else
             if(scanner.hasNextInt()){
                 i = scanner.nextInt();
                 System.out.println(" 输入的整数为：" + i);
             }else{
                 System.out.println(" 输入的不是整数");
             }
             
             //输入的是小数的情况就不写了 scanner.nextFloat( )
             //double 类型
             //......
             //关闭IO流
             
             scanner.close();
         }
     }
     ```

3. for循环增强版

   ```java
   Public class Demo4{
       Public static void main(String[] args){
           int[] numbers=[1,2,3,4,5,6];
           //把numbers数组中的数值赋值给x，然后输出
           for(int x:numbers){
               System.out.println(x);
           }
       }
   }
   ```



### Java方法 ###

---

1. 这是今天的测试数据

