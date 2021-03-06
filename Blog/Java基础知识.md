 * [一、Java 简介](#一java-简介)
   * [Java 的三个体系](#java-的三个体系)
   * [Java 的主要特性](#java-的主要特性)
   * [二、Java 基础语法](#二java-基础语法)
      * [基础语法](#基础语法)
      * [标识符](#标识符)
      * [数组](#数组)
      * [枚举](#枚举)
   * [三、Java 数据类型](#三java-数据类型)
      * [基本数据类型](#基本数据类型)
      * [引用数据类型](#引用数据类型)
      * [Number类](#number类)
      * [自动拆装箱](#自动拆装箱)
         * [主要的发生情况](#主要的发生情况)
         * [带来的问题](#带来的问题)
         * [对象比较(缓存池问题)](#对象比较缓存池问题)
      * [类型转换](#类型转换)
         * [自动类型转换](#自动类型转换)
         * [强制类型转换](#强制类型转换)
         * [类型提升](#类型提升)
   * [四、Java 变量类型](#四java-变量类型)
      * [局部变量](#局部变量)
      * [实例变量](#实例变量)
      * [类变量](#类变量)
   * [五、Java 修饰符](#五java-修饰符)
      * [访问控制修饰符](#访问控制修饰符)
      * [访问控制与继承](#访问控制与继承)
      * [非访问修饰符](#非访问修饰符)
         * [static修饰符](#static修饰符)
         * [final修饰符](#final修饰符)
         * [abstract修饰符](#abstract修饰符)
         * [synchronized修饰符](#synchronized修饰符)
         * [volatile修饰符](#volatile修饰符)
         * [transient修饰符](#transient修饰符)
   * [六、Java 运算符](#六java-运算符)
      * [算术运算符](#算术运算符)
      * [关系运算符](#关系运算符)
      * [位运算符](#位运算符)
      * [逻辑运算符](#逻辑运算符)
      * [赋值运算符](#赋值运算符)
      * [条件运算符（?:）](#条件运算符)
      * [instanceOf 运算符](#instanceof-运算符)
      * [运算符优先级](#运算符优先级)
   * [七、Java String 类](#七java-string-类)



# 一、Java 简介

> 1. Java是一门面向对象编程语言，不仅吸收了C++语言的各种优点，还摒弃了C++里难以理解的多继承、指针等概念，因此Java语言具有功能强大和简单易用两个特征。Java语言作为静态面向对象编程语言的代表，极好地实现了面向对象理论，允许程序员以优雅的思维方式进行复杂的编程。
>
> 2. Java具有简单性、面向对象、分布式、健壮性、安全性、平台独立与可移植性、多线程、动态性等特点。Java可以编写桌面应用程序、Web应用程序、分布式系统和嵌入式系统应用程序等。

## Java 的三个体系

- **Java SE（Java Platform，Standard Edition）**：Java SE 以前称为 J2SE。它允许开发和部署在桌面、服务器、嵌入式环境和实时环境中使用的 Java 应用程序。Java SE 包含了支持 Java Web 服务开发的类，并为 Java Platform，Enterprise Edition（Java EE）提供基础。
- **Java EE（Java Platform，Enterprise Edition）：**Java EE 以前称为 J2EE。企业版本帮助开发和部署可移植、健壮、可伸缩且安全的服务器端 Java 应用程序。Java EE 是在 Java SE 的基础上构建的，它提供 Web 服务、组件模型、管理和通信 API，可以用来实现企业级的面向服务体系结构（service-oriented architecture，SOA）和 Web 2.0 应用程序。
- **Java ME（Java Platform，Micro Edition）：**Java ME以前称为 J2ME。Java ME 为在移动设备和嵌入式设备（比如手机、PDA、电视机顶盒和打印机）上运行的应用程序提供一个健壮且灵活的环境。Java ME 包括灵活的用户界面、健壮的安全模型、许多内置的网络协议以及对可以动态下载的连网和离线应用程序的丰富支持。基于 Java ME 规范的应用程序只需编写一次，就可以用于许多设备，而且可以利用每个设备的本机功能。

## Java 的主要特性

- **Java语言是简单的：**

  Java语言的语法与C语言和C++语言很接近，使得大多数程序员很容易学习和使用。另一方面，Java丢弃了C++中很少使用的、很难理解的、令人迷惑的那些特性，如操作符重载、多继承、自动的强制类型转换。特别地，Java语言不使用指针，而是引用。并提供了自动的废料收集，使得程序员不必为内存管理而担忧。

- **Java语言是面向对象的：**

  Java语言提供类、接口和继承等面向对象的特性，为了简单起见，只支持类之间的单继承，但支持接口之间的多继承，并支持类与接口之间的实现机制（关键字为implements）。Java语言全面支持动态绑定，而C++语言只对虚函数使用动态绑定。总之，Java语言是一个纯的面向对象程序设计语言。

- **Java语言是分布式的：**

  Java语言支持Internet应用的开发，在基本的Java应用编程接口中有一个网络应用编程接口（java net），它提供了用于网络应用编程的类库，包括URL、URLConnection、Socket、ServerSocket等。Java的RMI（远程方法激活）机制也是开发分布式应用的重要手段。

- **Java语言是健壮的：**

  Java的强类型机制、异常处理、垃圾的自动收集等是Java程序健壮性的重要保证。对指针的丢弃是Java的明智选择。Java的安全检查机制使得Java更具健壮性。

- **Java语言是安全的：**

  Java通常被用在网络环境中，为此，Java提供了一个安全机制以防恶意代码的攻击。除了Java语言具有的许多安全特性以外，Java对通过网络下载的类具有一个安全防范机制（类ClassLoader），如分配不同的名字空间以防替代本地的同名类、字节代码检查，并提供安全管理机制（类SecurityManager）让Java应用设置安全哨兵。

- **Java语言是体系结构中立的：**

  Java程序（后缀为java的文件）在Java平台上被编译为体系结构中立的字节码格式（后缀为class的文件），然后可以在实现这个Java平台的任何系统中运行。这种途径适合于异构的网络环境和软件的分发。

- **Java语言是可移植的：**

  这种可移植性来源于体系结构中立性，另外，Java还严格规定了各个基本数据类型的长度。Java系统本身也具有很强的可移植性，Java编译器是用Java实现的，Java的运行环境是用ANSI C实现的。

- **Java语言是解释型的：**

  如前所述，Java程序在Java平台上被编译为字节码格式，然后可以在实现这个Java平台的任何系统中运行。在运行时，Java平台中的Java解释器对这些字节码进行解释执行，执行过程中需要的类在联接阶段被载入到运行环境中。

- **Java是高性能的：**

  与那些解释型的高级脚本语言相比，Java的确是高性能的。事实上，Java的运行速度随着JIT(Just-In-Time）编译器技术的发展越来越接近于C++。

- **Java语言是多线程的：**

  在Java语言中，线程是一种特殊的对象，它必须由Thread类或其子（孙）类来创建。通常有两种方法来创建线程：其一，使用型构为Thread(Runnable)的构造子类将一个实现了Runnable接口的对象包装成一个线程，其二，从Thread类派生出子类并重写run方法，使用该子类创建的对象即为线程。值得注意的是Thread类已经实现了Runnable接口，因此，任何一个线程均有它的run方法，而run方法中包含了线程所要运行的代码。线程的活动由一组方法来控制。Java语言支持多个线程的同时执行，并提供多线程之间的同步机制（关键字为synchronized）。

- **Java语言是动态的：**

  Java语言的设计目标之一是适应于动态变化的环境。Java程序需要的类能够动态地被载入到运行环境，也可以通过网络来载入所需要的类。这也有利于软件的升级。另外，Java中的类有一个运行时刻的表示，能进行运行时刻的类型检查。

# 二、Java 基础语法

## 基础语法

- **大小写敏感**：Java是大小写敏感的，这就意味着标识符Hello与hello是不同的。
- **类名**：对于所有的类来说，类名的首字母应该大写。如果类名由若干单词组成，那么每个单词的首字母应该大写，例如 MyFirstJavaClass 。
- **方法名**：所有的方法名都应该以小写字母开头。如果方法名含有若干单词，则后面的每个单词首字母大写。
- **源文件名**：源文件名必须和类名相同。当保存文件的时候，你应该使用类名作为文件名保存（切记Java是大小写敏感的），文件名的后缀为.java。（如果文件名和类名不相同则会导致编译错误）。
- **主方法入口**：所有的Java 程序由**public static void main(String args[])**方法开始执行。

## 标识符

> Java所有的组成部分都需要名字。类名、变量名以及方法名都被称为标识符。

**注意：**

1. 所有的标识符都应该以字母（A-Z或者a-z）,美元符（$）、或者下划线（_）开始
2. 首字符之后可以是任何字符的组合
3. 关键字不能用作标识符
4. 标识符是大小写敏感的

**Example:**

- 合法标识符举例：age、$salary、_value、_1_value
- 非法标识符举例：123abc、-salary

## 数组

> 数组是储存在堆上的对象，可以保存多个同类型变量，这些变量类型既可以存储基本数据类型，也可以存储引用数据类型。

### **一维数组**

**数组的格式**

```java
int[] a；     定义了一个int类型的数组a；
int a[];      定义了一个int类型的a数组；
//推荐使用第一种定义方式。
```

**数组的初始化**

所谓初始化：就是为数组中的数组元素分配内存空间，并为每个数组元素赋值。Java中的数组必须先初始化,然后才能使用。

- **动态初始化：** 只指定长度，由系统给出初始化值。
- **静态初始化：** 给出初始化值，不用new关键字完成，由系统决定长度。
- **默认初始化：**数组是引用类型，它的元素相当于类的成员变量，因此数组分配空间后，每个元素也被按照成员变量的规则被隐士初始化。

### **二维数组**

**定义格式**

```java
int[][] arr = new int[3][2];
//定义了一个二维数组arr
//这个二维数组有3个一维数组，名称是arr[0],arr[1],arr[2]
//每个一维数组有2个元素，可以通过arr[m][n]来获取,表示获取第m+1个一维数组的第n+1个元素
```
## 枚举

> Java 5.0引入了枚举，枚举限制变量只能是预先设定好的值。使用枚举可以减少代码中的bug。



# 三、Java 数据类型

## 基本数据类型

> Java语言内置了八种基本类型。六种数字类型（四个整数型，两个浮点型），一种字符类型，还有一种布尔型。

| 类型    | 最小值       | 最大值            | 默认值 | 说明                                   |
| ------- | ------------ | ----------------- | ------ | -------------------------------------- |
| byte    | -128（-2^7） | 127（2^7-1）      | 0      | 8位、有符号的，以二进制补码表示的整数  |
| short   | -2^15        | 2^15 - 1          | 0      | 16位、有符号的以二进制补码表示的整数   |
| int     | -2^31        | 2^31 - 1          | 0      | 32位、有符号的以二进制补码表示的整数   |
| long    | -2^63        | 2^63 -1           | 0L     | 64位、有符号的以二进制补码表示的整数   |
| float   |              |                   | 0.0f   | 单精度、32位、符合IEEE 754标准的浮点数 |
| double  |              |                   | 0.0d   | 双精度、64位、符合IEEE 754标准的浮点数 |
| boolean |              |                   | false  | 表示一位的信息                         |
| char    | '\u0000' (0) | '\uffff' (65,535) |        | 一个单一的16位Unicode字符              |

- 浮点数的默认类型为double类型，不能用来表示精确的值，如货币。但float在储存大型浮点数组的时候可节省内存空间。

- [Primitive Data Types](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html)

## 引用数据类型

> java为每种基本类型都提供了对应的封装类型，分别为：Byte、Short、Integer、Long、Float、Double、Character、Boolean。引用类型是一种对象类型,它的值是指向内存空间的引用，就是地址。

- 在Java中，引用类型的变量非常类似于C/C++的指针。引用类型指向一个对象，指向对象的变量是引用变量。这些变量在声明时被指定为一个特定的类型，变量一旦声明后，类型就不能被改变了。
- 基本数据类型的变量是存储在栈内存中，而引用类型变量存储在栈内存中，保存的是实际对象在堆内存中的地址，实际对象中保存这内容。
- 对象、String、数组都是引用数据类型。
- 所有引用类型的默认值都是null。
- 一个引用变量可以用来引用任何与之兼容的类型。

## Number类

> 在实际开发过程中，我们经常会遇到需要使用对象，而不是内置数据类型的情形。为了解决这个问题，Java语言为每一个内置数据类型提供了对应的包装类。所有的包装类（Integer、Long、Byte、Double、Float、Short）都是抽象类Number的子类。

![](https://7n.w3cschool.cn/attachments/image/20160401/1459506097805010.jpg)

**Math类**

Java 的 Math 包含了用于执行基本数学运算的属性和方法，如初等指数、对数、平方根和三角函数。

Math 的方法都被定义为 static 形式，通过 Math 类可以在主函数中直接调用。

## 自动拆装箱

> Java 从 jdk1.5 开始引入自动装箱和拆箱,使得基本数据类型与引用类型之间相互转换变得简单。

- **自动装箱：**java自动将原始类型转化为引用类型的过程，自动装箱时编译器会调用valueOf()方法,将原始类型转化为对象类型。
- **自动拆箱：**java自动将引用类型转化为原始类型的过程，自动拆箱时编译器会调用intValue(),doubleValue()这类的方法将对象转换成原始类型值。

### 主要的发生情况

一是赋值时: 

```java
Integer a = 3; //自动装箱
int b = a; //自动拆箱
```

二是方法调用：

```java
public Integer query(Integer a){
   return a;
}
query(3); //自动装箱
int result = query(3); //自动拆箱
```

### 带来的问题

- **程序性能：**由于装箱会隐式地创建对象创建，因此千万不要在一个循环中进行自动装箱的操作，下面就是一个循环中进行自动装箱的例子，会额外创建多余的对象,增加GC的压力,影响程序的性能。

```java
Integer sum = 0;
 for(int i=0; i<1000; i++){
   sum+=i;
}
```

- **空指针异常：**

```java
Object obj = null;
int i = (Integer)obj;
```

### 对象比较(缓存池问题)

```java
Integer a = 120;
int b= 120;
Integer c = 120;
Integer d = new Integer(120);
System.out.println(a == b);   //true    t1
System.out.println(a == c);   //true    t2
System.out.println(a == d);   //false   t3

Integer e = 128;
Integer f = 128;
System.out.println(e == f);   //false   t4
```

1. t1产生的原因是编译器编译时会调用intValue()自动的将a进行了拆箱，结果肯定是true; 
2. t3结果无论如何都不会相等的，因为new Integer(120)构造器会创建新的对象。
3. 对于t2和t4，查看jdk的源码：

```java
public static Integer valueOf(int i) {
    assert IntegerCache.high >= 127;
    if (i >= IntegerCache.low && i <= IntegerCache.high)
        return IntegerCache.cache[i + (-IntegerCache.low)];
    return new Integer(i);
}
```

发现在 Java 8 中，Integer 缓存池的大小默认为 -128\~127，对于-128~127之间的值会取缓存中的引用,通过缓存经常请求的值而显著提高空间和时间性能。 这就能解释t2结果返回true，而t4由于128不在缓存区间内，编译器调用valueOf方法会重新创建新的对象，两个不同的对象返回false。

**基本类型对应的缓冲池**

- boolean values true and false
- all byte values
- short  and int values between -128 and 127
- char in the range \u0000 to \u007F

## 类型转换

> 整型、实型(常量)、字符型数据可以混合运算。运算中，不同类型的数据先转化为同一类型，然后进行运算。

### 自动类型转换

> 数字表示范围小的数据类型可以自动转换成范围大的数据类型。

```java
int i = 200;
long l = i;
```

自动转换关系图：

[![Java-Snipaste-2019-03-19-21-39-43.png](https://i.postimg.cc/HLhHSCkf/Java-Snipaste-2019-03-19-21-39-43.png)](https://postimg.cc/4KVrdqt5)

实线表示自动转换时不会造成数据丢失，虚线则可能会出现数据丢失问题。

**注意：**

- 自动转换也要小心数据溢出问题

```java
int count = 100000000;
int price = 1999;
long totalPrice = count * price;

//编译没任何问题，但结果却输出的是负数，
//这是因为两个 int 相乘得到的结果是 int, 相乘的结果超出了 int 的代表范围。
//这种情况，一般把第一个数据转换成范围大的数据类型再和其他的数据进行运算。

int count = 100000000;
int price = 1999;
long totalPrice = (long) count * price;
```

- **向下转换**时可以直接将 int 常量字面量赋值给 byte、short、char 等数据类型，而不需要强制转换，只要该常量值不超过该类型的表示范围都能自动转换。

### 强制类型转换

```java
short s = 199;
int i = s;// 199

double d = 10.24;
long ll = (long) d;// 10

//以上的转换结果都在我们的预期之内，属于正常的转换和丢失精度的情况，下面的例子就一样属于数据溢出的情况。

int ii = 300;
byte b = (byte)ii;
//300 已经超出了 byte 类型表示的范围，所以会转换成一个毫无意义的数字。
```

### 类型提升

> 所谓类型提升就是指在多种不同数据类型的表达式中，类型会自动向范围表示大的值的数据类型提升。

```java
long count = 100000000;
int price = 1999;
long totalPrice = price * count;

//price 为 int 型，count 为 long 型，运算结果为 long 型，运算结果正常，没有出现溢出的情况。
```

## 参数传递

Java 的参数是以值传递的形式传入方法中，而不是引用传递。在将一个参数传入一个方法时，本质上是将对象的地址以值的方式传递到形参中。因此在方法中使指针引用其它对象，那么这两个指针此时指向的是完全不同的对象，在一方改变其所指向对象的内容时对另一方没有影响。

- 基本类型作为参数传递时，是传递值的拷贝，无论你怎么改变这个拷贝，原值是不会改变的。

  ```java
  public class Test {
         public static void main(String[] args) {
             int n = 3;
             
             System.out.println("Before change, n = " + n);     
             //Before change, n = 3
             
             changeData(n);
             System.out.println("After changeData(n), n = " + n);
             //After changeData(n), n = 3
         }
      
         public static void changeData(int nn) {
             n = 10;
         }
  }
  ```

- 对象作为参数传递时，是把对象在内存中的地址拷贝了一份传给了参数。

  ```java
  public class Test1 {
      public static void main(String[] args) {
          StringBuffer sb = new StringBuffer("Hello ");
          System.out.println("Before change, sb = " + sb);
          //Before change, sb = Hello
          
          changeData(sb);
          System.out.println("After changeData(n), sb = " + sb);
          //After changeData(n), sb = Hi World!
      }
      public static void changeData(StringBuffer strBuf) {
          strBuf.append("World!");
      }
  }
  
  public class Test2 {
      public static void main(String[] args) {
          StringBuffer sb = new StringBuffer("Hello ");
          System.out.println("Before change, sb = " + sb);
          //Before change, sb = Hello
          
          changeData(sb);
          System.out.println("After changeData(n), sb = " + sb);
          //After changeData(n), sb = Hello
      }
      public static void changeData(StringBuffer strBuf) {
          strBuf = new StringBuffer("Hi ");
          strBuf.append("World!");
      }
  }
  ```

[StackOverflow: Is Java “pass-by-reference” or “pass-by-value”?](https://stackoverflow.com/questions/40480/is-java-pass-by-reference-or-pass-by-value)

# 四、Java 变量类型

> 在Java语言中，所有的变量在使用前必须声明。声明变量的基本格式如下：
>
> ```java
> //type identifier [ = value][, identifier [= value] ...] ;
> 
> int a, b, c;         // 声明三个int型整数：a、b、c。
> int d = 3, e, f = 5; // 声明三个整数并赋予初值。
> ```

## 局部变量

> 类的方法中的变量

- 局部变量声明在方法、构造方法或者语句块中；
- 局部变量在方法、构造方法、或者语句块被执行的时候创建，当它们执行完成后，变量将会被销毁；
- 访问修饰符不能用于局部变量；
- 局部变量只在声明它的方法、构造方法或者语句块中可见；
- 局部变量是在栈上分配的;
- 局部变量没有默认值，所以局部变量被声明后，必须经过初始化，才可以使用。

## 实例变量

> 独立于方法之外的变量，不过没有 static 修饰。

- 实例变量声明在一个类中，但在方法、构造方法和语句块之外；
- 当一个对象被实例化之后，每个实例变量的值就跟着确定；
- 实例变量在对象创建的时候创建，在对象被销毁的时候销毁；
- 实例变量的值应该至少被一个方法、构造方法或者语句块引用，使得外部能够通过这些方式获取实例变量信息；
- 实例变量可以声明在使用前或者使用后；
- 访问修饰符可以修饰实例变量；
- 实例变量对于类中的方法、构造方法或者语句块是可见的。一般情况下应该把实例变量设为私有。通过使用访问修饰符可以使实例变量对子类可见；
- 实例变量具有默认值。数值型变量的默认值是0，布尔型变量的默认值是false，引用类型变量的默认值是null。变量的值可以在声明时指定，也可以在构造方法中指定；
- 实例变量可以直接通过变量名访问。但在静态方法以及其他类中，就应该使用完全限定名：ObejectReference.VariableName。

## 类变量

> 亦称静态变量，独立于方法之外的变量，用 static 修饰。

- 类变量也称为静态变量，在类中以static关键字声明，但必须在方法、构造方法和语句块之外；
- 无论一个类创建了多少个对象，类只拥有类变量的一份拷贝；
- 静态变量除了被声明为常量外很少使用。常量是指声明为public/private，final和static类型的变量。常量初始化后不可改变；
- 静态变量储存在静态存储区。经常被声明为常量，很少单独使用static声明变量；
- 静态变量在程序开始时创建，在程序结束时销毁；
- 与实例变量具有相似的可见性。但为了对类的使用者可见，大多数静态变量声明为public类型；
- 默认值和实例变量相似。数值型变量默认值是0，布尔型默认值是false，引用类型默认值是null。变量的值可以在声明的时候指定，也可以在构造方法中指定。此外，静态变量还可以在静态语句块中初始化；
- 类变量被声明为public static final类型时，类变量名称必须使用大写字母。如果静态变量不是public和final类型，其命名方式与实例变量以及局部变量的命名方式一致；
- 静态变量可以通过：*ClassName.VariableName*的方式访问。

# 五、Java 修饰符

> 像其他语言一样，Java可以使用修饰符来修饰类中方法和属性。主要有两类修饰符：
>
> 1. **访问控制修饰符 :** default, public , protected, private
> 2. **非访问控制修饰符 :** final, abstract, static，synchronized 和 volatile

## 访问控制修饰符

- **默认访问控制修饰符**
  1. 使用默认访问修饰符声明的变量和方法，对同一个包内的类是可见的。
  2. 接口里的变量都隐式声明为public static final,而接口里的方法默认情况下访问权限为public。
- **私有访问控制修饰符**
  1. 私有访问修饰符是最严格的访问级别，所以被声明为private的方法、变量和构造方法只能被所属类访问，并且类和接口不能声明为private。
  2. 声明为私有访问类型的变量只能通过类中公共的getter方法被外部类访问。
  3. Private访问修饰符的使用主要用来隐藏类的实现细节和保护类的数据。
- **公有访问修饰符：**
  1. 被声明为public的类、方法、构造方法和接口能够被任何其他类访问。
  2. 类所有的公有方法和变量都能被其子类继承。
  3. Java程序的main() 方法必须设置成公有的，否则，Java解释器将不能运行该类。

- **受保护的访问修饰符**
  1. 被声明为protected的变量、方法和构造器能被同一个包中的任何其他类访问，也能够被不同包中的子类访问。

## 访问控制与继承

- 父类中声明为public的方法在子类中也必须为public。
- 父类中声明为protected的方法在子类中要么声明为protected，要么声明为public。不能声明为private。
- 父类中默认修饰符声明的方法，能够在子类中声明为private。
- 父类中声明为private的方法，不能够被继承。

## 非访问修饰符

> 为了实现一些其他的功能，Java也提供了许多非访问修饰符。

### static修饰符

> static修饰符，用来创建类方法和类变量。

- **静态变量：**static关键字用来声明独立于对象的静态变量，无论一个类实例化多少对象，它的静态变量只有一份拷贝。静态变量也被称为类变量。局部变量不能被声明为static变量。
- **静态方法：**static关键字用来声明独立于对象的静态方法。静态方法不能使用类的非静态变量。静态方法从参数列表得到数据，然后计算这些数据。

### final修饰符

> 用来修饰类、方法和变量，final修饰的类不能够被继承，修饰的方法不能被继承类重新定义，修饰的变量为常量，是不可修改的。

- **final变量：**

  1. final变量能被显式地初始化并且只能初始化一次。被声明为final的对象的引用不能指向不同的对象。
  2. 但是final对象里的数据可以被改变。也就是说final对象的引用不能改变，但是里面的值可以改变。

- **final方法：**

  1. 类中的Final方法可以被子类继承，但是不能被子类修改。

  2. 声明final方法的主要目的是防止该方法的内容被修改。

- **final类：**

  1. final类不能被继承，没有类能够继承final类的任何特性。

### abstract修饰符

- **抽象类：**
  1. 抽象类不能用来实例化对象，声明抽象类的唯一目的是为了将来对该类进行扩充。
  2. 一个类不能同时被abstract和final修饰。如果一个类包含抽象方法，那么该类一定要声明为抽象类，否则将出现编译错误。
  3. 抽象类可以包含抽象方法和非抽象方法。
- **抽象方法：**
  1. 抽象方法是一种没有任何实现的方法，该方法的的具体实现由子类提供。抽象方法不能被声明成final和static。
  2. 任何继承抽象类的子类必须实现父类的所有抽象方法，除非该子类也是抽象类。
  3. 如果一个类包含若干个抽象方法，那么该类必须声明为抽象类。抽象类可以不包含抽象方法。
  4. 抽象方法的声明以分号结尾，例如：public abstract sample();

### synchronized修饰符

> synchronized关键字声明的方法同一时间只能被一个线程访问。Synchronized修饰符可以应用于四个访问修饰符。

### volatile修饰符

> volatile修饰的成员变量在每次被线程访问时，都强迫从共享内存中重读该成员变量的值。而且，当成员变量发生变化时，强迫线程将变化值回写到共享内存。这样在任何时刻，两个不同的线程总是看到某个成员变量的同一个值。一个volatile对象引用可能是null。

### transient修饰符

> 序列化的对象包含被transient修饰的实例变量时，java虚拟机(JVM)跳过该特定的变量。

该修饰符包含在定义变量的语句中，用来预处理类和变量的数据类型:

```java
public transient int limit = 55;   // will not persist
public int b; // will persist
```



# 六、Java 运算符

> 计算机的最基本用途之一就是执行数学运算，作为一门计算机语言，Java也提供了一套丰富的运算符来操纵变量。

## 算术运算符

> 变量A的值为10，变量B的值为20：

| 操作符 | 描述                              | 例子               |
| ------ | --------------------------------- | ------------------ |
| +      | 加法 - 相加运算符两侧的值         | A + B等于30        |
| -      | 减法 - 左操作数减去右操作数       | A – B等于-10       |
| *      | 乘法 - 相乘操作符两侧的值         | A * B等于200       |
| /      | 除法 - 左操作数除以右操作数       | B / A等于2         |
| ％     | 取模 - 左操作数除以右操作数的余数 | B%A等于0           |
| ++     | 自增 - 操作数的值增加1            | B++ 或 ++B 等于 21 |
| --     | 自减 - 操作数的值减少1            | B-- 或 --B 等于 19 |

## 关系运算符

> 变量A的值为10，变量B的值为20：

| 运算符 | 描述                                                         | 例子                   |
| ------ | ------------------------------------------------------------ | ---------------------- |
| ==     | 检查如果两个操作数的值是否相等，如果相等则条件为真。         | （A == B）为假(非真)。 |
| !=     | 检查如果两个操作数的值是否相等，如果值不相等则条件为真。     | (A != B) 为真。        |
| >      | 检查左操作数的值是否大于右操作数的值，如果是那么条件为真。   | （A> B）非真。         |
| <      | 检查左操作数的值是否小于右操作数的值，如果是那么条件为真。   | （A <B）为真。         |
| > =    | 检查左操作数的值是否大于或等于右操作数的值，如果是那么条件为真。 | （A> = B）为假。       |
| <=     | 检查左操作数的值是否小于或等于右操作数的值，如果是那么条件为真。 | （A <= B）为真。       |

## 位运算符

> 变量A的值为60和变量B的值为13：

| 操作符 | 描述                                                         | 例子                           |
| ------ | ------------------------------------------------------------ | ------------------------------ |
| ＆     | 按位与操作符，当且仅当两个操作数的某一位都非0时候结果的该位才为1。 | （A＆B），得到12，即0000 1100  |
| \|     | 按位或操作符，只要两个操作数的某一位有一个非0时候结果的该位就为1。 | （A \| B）得到61，即 0011 1101 |
| ^      | 按位异或操作符，两个操作数的某一位不相同时候结果的该位就为1。 | （A ^ B）得到49，即 0011 0001  |
| 〜     | 按位补运算符翻转操作数的每一位。                             | （〜A）得到-60，即1100 0011    |
| <<     | 按位左移运算符。左操作数按位左移右操作数指定的位数。         | A << 2得到240，即 1111 0000    |
| >>     | 按位右移运算符。左操作数按位右移右操作数指定的位数。         | A >> 2得到15即 1111            |
| >>>    | 按位右移补零操作符。左操作数的值按右操作数指定的位数右移，移动得到的空位以零填充。 | A>>>2得到15即0000 1111         |

## 逻辑运算符

> 布尔变量A为真，变量B为假

| 操作符 | 描述                                                         | 例子                |
| ------ | ------------------------------------------------------------ | ------------------- |
| &&     | 称为逻辑与运算符。当且仅当两个操作数都为真，条件才为真。     | （A && B）为假。    |
| \| \|  | 称为逻辑或操作符。如果任何两个操作数任何一个为真，条件为真。 | （A \| \| B）为真。 |
| ！     | 称为逻辑非运算符。用来反转操作数的逻辑状态。如果条件为true，则逻辑非运算符将得到false。 | ！（A && B）为真。  |

## 赋值运算符

| 操作符  | 描述                                                         | 例子                            |
| ------- | ------------------------------------------------------------ | ------------------------------- |
| =       | 简单的赋值运算符，将右操作数的值赋给左侧操作数               | C = A + B将把A + B得到的值赋给C |
| + =     | 加和赋值操作符，它把左操作数和右操作数相加赋值给左操作数     | C + = A等价于C = C + A          |
| - =     | 减和赋值操作符，它把左操作数和右操作数相减赋值给左操作数     | C - = A等价于C = C -  A         |
| * =     | 乘和赋值操作符，它把左操作数和右操作数相乘赋值给左操作数     | C * = A等价于C = C * A          |
| / =     | 除和赋值操作符，它把左操作数和右操作数相除赋值给左操作数     | C / = A等价于C = C / A          |
| （％）= | 取模和赋值操作符，它把左操作数和右操作数取模后赋值给左操作数 | C％= A等价于C = C％A            |
| << =    | 左移位赋值运算符                                             | C << = 2等价于C = C << 2        |
| >> =    | 右移位赋值运算符                                             | C >> = 2等价于C = C >> 2        |
| ＆=     | 按位与赋值运算符                                             | C＆= 2等价于C = C＆2            |
| ^ =     | 按位异或赋值操作符                                           | C ^ = 2等价于C = C ^ 2          |
| \| =    | 按位或赋值操作符                                             | C \| = 2等价于C = C \| 2        |

## 条件运算符（?:）

> 条件运算符也被称为三元运算符。该运算符有3个操作数，并且需要判断布尔表达式的值。该运算符的主要是决定哪个值应该赋值给变量。

```java
variable x = (expression) ? value if true : value if false
```

## instanceOf 运算符

> 该运算符用于操作对象实例，检查该对象是否是一个特定类型（类类型或接口类型）。

```java
//( Object reference variable ) instanceOf  (class/interface type)

String name = 'James';
boolean result = name instanceOf String; // 由于name是Strine类型，所以返回真
```

如果被比较的对象兼容于右侧类型,该运算符仍然返回true。

```java
class Vehicle {}

public class Car extends Vehicle {
   public static void main(String args[]){
      Vehicle a = new Car();
      boolean result =  a instanceof Car;
      System.out.println( result);
   }
}
```

## 运算符优先级

> 下表中的运算符优先级由上至下依次降低：

| 类别     | 操作符                                     | 关联性   |
| -------- | ------------------------------------------ | -------- |
| 后缀     | () [] . (点操作符)                         | 左到右   |
| 一元     | + + - ！〜                                 | 从右到左 |
| 乘性     | * /％                                      | 左到右   |
| 加性     | + -                                        | 左到右   |
| 移位     | >> >>>  <<                                 | 左到右   |
| 关系     | >> = << =                                  | 左到右   |
| 相等     | ==  !=                                     | 左到右   |
| 按位与   | ＆                                         | 左到右   |
| 按位异或 | ^                                          | 左到右   |
| 按位或   | \|                                         | 左到右   |
| 逻辑与   | &&                                         | 左到右   |
| 逻辑或   | \| \|                                      | 左到右   |
| 条件     | ？：                                       | 从右到左 |
| 赋值     | = + = - = * = / =％= >> = << =＆= ^ = \| = | 从右到左 |
| 逗号     | ，                                         | 左到右   |

# 七、Java String 类

> 在 Java语言中有8种基本类型和一种比较特殊的类型`String`。由于`String`在Java世界中使用过于频繁，Java为了避免在一个系统中产生大量的String对象，引入了字符串常量池（当然基础类型也有）。

## 常量池

常量池就类似一个Java系统级别提供的缓存，指的是在编译期被确定，并被保存在已编译的.class文件中的一些数据。它包括了关于类、方法、接口等中的常量，也包括字符串常量。Java会确保一个字符串常量只有一个拷贝。

```java
String s1 = "Programming";
String s2 = new String("Programming");
String s3 = "Program" + "ming";
String s4 = new String(s2);
String s5 = "Programming";

System.out.println(s1 == s2);//false
System.out.println(s4 == s2);//false
System.out.println(s1 == s3);//true
System.out.println(s1 == s5);//true
System.out.println(s1 == s1.intern());//true

s2.intern();
System.out.println(s1 == s2);//false 没有将返回值赋值给s2

s2=s2.intern();
System.out.println(s1 == s2);//true
```

- s1和s3中的”Programming”都是字符串常量，它们在编译期就被确定了，所以s1==s3为true；而”Program”和”ming”也都是字符串常量，当一个字符串由多个字符串常量连接而成时，JVM对此做了一个优化，s3也同样在编译期就被解析为一个字符串常量，所以s3也是常量池中 ”Programming”的一个引用。 所以我们得出s5==s1==s3
-  用new String() 创建的字符串不是常量，不能在编译期就确定，所以new String() 创建的字符串不放入常量池中，它们有自己的地址空间。所以有s2！=s4
- String对象的intern()方法会得到字符串对象在常量池中对应的版本的引用（如果常量池中有一个字符串与String对象的equals结果是true），如果常量池中没有对应的字符串，则该字符串将被添加到常量池中，然后返回常量池中字符串的引用。

**补充：**存在于.class文件中的常量池，在运行期被JVM装载，并且可以扩充。String的intern()方法就是扩充常量池的一个 方法；当一个String实例str调用intern()方法时，Java查找常量池中是否有相同Unicode的字符串常量，如果有，则返回其的引用， 如果没有，则在常量池中增加一个Unicode等于str的字符串并返回它的引用。

## String是不可变的

> String 是一个典型的 Immutable 类，被声明成为 final class，所有属性也都是 final 的。也由于它的不可变，类似拼接、裁剪字符串等动作，都会产生新的 String 对象。

- 可以缓存Hash值：因为 String 的 hash 值经常被使用，例如 String 用做 HashMap 的 key。不可变的特性可以使得 hash 值也不可变，因此只需要进行一次计算。

- 常量池的需要：如果一个String对象已经被创建过了，那么就会从 String Pool 中取得引用。只有 String 是不可变的，才可能使用 String Pool。

- 线程安全：String 不可变性天生具备线程安全，可以在多个线程中安全地使用。

## equals() & ==

- String类已经重写过了equals方法，这对于String简单来说就是比较两字符串的Unicode序列是否相当，如果相等返回true。而==是比较两字符串的地址是否相同，也就是是否是同一个字符串的引用。

- 在符合数据类型中，则equals和==都是比较两对象的地址是否相同，除非重写equals，详见hashcode与equals的区别。

## StringBuffer & StringBuilder

- StringBuffer和StringBuilder都实现了AbstractStringBuilder抽象类，拥有几乎一致对外提供的调用接口。
- 其底层在内存中的存储方式与String相同，都是以一个有序的字符序列（char类型的数组，JDK 9 以后是 byte）进行存储，不同点是StringBuffer/StringBuilder对象的值是可以改变的，并且值改变以后，对象引用不会发生改变。
- 两者对象在构造过程中，首先按照默认大小申请一个字符数组（这个大小是 16），由于会不断加入新数据，当超过默认大小后，会创建一个更大的数组，并将原先的数组内容通过arraycopy复制过来，再丢弃旧的数组。因此，对于较大对象的扩容会涉及大量的内存复制操作，如果能够预先评估大小，可提升性能。

- **在线程安全上，StringBuilder是线程不安全的，而StringBuffer是线程安全的。**区别仅在于最终的方法是否加了 synchronized，即三者的执行效率上 StringBuilder > StringBuffer > String 。

**小结：**

1. String适用于少量的字符串操作的情况。

2. StringBuilder适用于单线程下在字符缓冲区进行大量操作的情况。

3. StringBuffer适用多线程下在字符缓冲区进行大量操作的情况。


# 八、Object 方法

## 概况

```java
public native int hashCode()

public boolean equals(Object obj)

protected native Object clone() throws CloneNotSupportedException

public String toString()

public final native Class<?> getClass()

protected void finalize() throws Throwable {}

public final native void notify()

public final native void notifyAll()

public final native void wait(long timeout) throws InterruptedException

public final void wait(long timeout, int nanos) throws InterruptedException

public final void wait() throws InterruptedException
```

## equals()

1. **等价关系**

   ```java
   //自反性
   x.equals(x); // true
   
   //对称性 
   x.equals(y) == y.equals(x); // true
   
   //传递性 
   if (x.equals(y) && y.equals(z))
       x.equals(z); // true;
   
   //一致性，多次调用 equals() 方法结果不变
   x.equals(y) == x.equals(y); // true
   
   //与 null 的比较
   //对任何不是 null 的对象 x 调用 x.equals(null) 结果都为 false
   x.equals(null); // false;
   ```

   

2. **等价与相等**

   - 对于基本类型，== 判断两个值是否相等，基本类型没有 equals() 方法。
   - 对于引用类型，== 判断两个变量是否引用同一个对象，而 equals() 判断引用的对象是否等价。

3. **实现**

   ```java
   public class EqualExample {
   
       private int x;
       private int y;
       private int z;
   
       public EqualExample(int x, int y, int z) {
           this.x = x;
           this.y = y;
           this.z = z;
       }
   
       @Override
       public boolean equals(Object o) {
           if (this == o) return true;  //检查是否为同一个对象的引用，如果是直接返回 true
           if (o == null || getClass() != o.getClass()) return false;  //检查是否是同一个类型，如果不是，直接返回 false
   
           EqualExample that = (EqualExample) o;  //将 Object 对象进行转型
   
           if (x != that.x) return false;  //判断每个关键域是否相等
           if (y != that.y) return false;
           return z == that.z;
       }
   }
   ```

   

## hashCode()

- hashCode() 返回散列值，而 equals() 是用来判断两个对象是否等价。等价的两个对象散列值一定相同，但是散列值相同的两个对象不一定等价。
- 在覆盖 equals() 方法时应当总是覆盖 hashCode() 方法，保证等价的两个对象散列值也相等。

## toString()

> 默认返回 Example@4554617c 这种形式，其中 @ 后面的数值为散列码的无符号十六进制表示。
>
> ## clone()
>
> 1. **cloneable**
>
>    clone() 是 Object 的 protected 方法，它不是 public，一个类不显式去重写 clone()，其它类就不能直接去调用该类实例的 clone() 方法。
>
> 2. **浅拷贝**
>
>    拷贝对象和原始对象的引用类型引用同一个对象。
>
> 3. **深拷贝**
>
>    拷贝对象和原始对象的引用类型引用不同对象。
>
> 4. **clone() 的替代方案**
>
>    使用 clone() 方法来拷贝一个对象即复杂又有风险，它会抛出异常，并且还需要类型转换。Effective Java 书上讲到，最好不要去使用 clone()，可以使用拷贝构造函数或者拷贝工厂来拷贝一个对象。