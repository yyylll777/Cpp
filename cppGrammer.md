# CPP

**Do or Not Do ,There Is No Try!**

**Edited by yyyllll**

## 术语

arguments---实参   left brace\right brace---左右大括号   identifiers---标识符   parameters---形参   access specifiers---访问说明符   encapsulated---封装   member-initializer list---构造函数成员初始值列表   scope---域   statement---语句   pseudocode---伪代码   solid circle---实心圆   dotted line---虚线   indented---缩进   Incrementing---递增   Truncation---截断   round---四舍五入   arithmetic overflow---数值溢出   operand---操作数   quotient---商   explicit conversion---显式转换implicit conversion---隐式转换   promotion---提升   unary operator---一元运算符   whole number---非负整数   Polymorphism---多态   evaluate---计算   Divide-and-Conquer---分治法   vector---向量

## 1. C++编程的介绍

### 1.1  第一个C++程序

```c++
// Fig. 2.1
// Text-printing program.
#include <iostream> // enables program to output data to the screen
// function main begins program execution
int main() {
    std::cout << "Welcome to C++!\n"; // display message
    return 0; // indicate that program ended successfully
} 
```

**每个程序都应该以注释开头用以解释程序的目的**

第三行是预处理指令，是在程序被编译之前给预处理器的信息。这一行通知预处理器在程序中包括输入/输出流头文件\<iostream>。此标头是一个包含信息的文件，编译器在编译任何将数据输出到屏幕或从键盘输入数据时使用使用C++的输入/输出流。关于\<iostream>的更多细节会在后面的章节讨论。

```c++
int main() {
```

​      main后面的括号表示main是一个称为函数的程序构建块。每个程序都必须有一个main函数。函数名前面的关键词指明函数的返回类型，函数名后面的括号，是书写形参之处，形参列表可以为空，大括号里的部分称为函数体。

```c++
std::cout << "Welcome to C++!\n";
```

在编程语言中，命名空间是一种特殊的作用域，它包含了处于该作用域中的所有标示符，而且其本身也是由标示符表示的。命名空间的使用目的是为了将逻辑相关的标示符限定在一起，组成相应的命名空间，可使整个系统更加模块化，最重要的是它可以防止命名冲突。就好比在两个函数或类中定义相同名字的对象一样，利用作用域标示符限定该对象是哪个类里定义的。

使用using std::cout 事先声明：`cout<<"Hello!"<<std::endl;`//分别引入，需要用哪个引用哪个，保证程序中名称的唯一性

使用using namespace std声明：`cout<<"Hello!"<<endl;`//**引入名字空间的所有内容，不推荐这样写**

在输出语句的上下文中，<<运算符被称为流插入操作符，操作人员执行此程序时，运算符右侧的值，即右侧操作数，将插入输出流中。请注意，<<运算符指向数据所在的位置。字符串文字面量通常按照它们出现在双引号之间的方式打印。但是，这些字符（\n）没有打印在屏幕上。反斜杠（\）被称为转义符。它表示要输出一个“特殊”字符。常见的转义字符如下图：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230903202207026.png"  />
</div>
const对象一旦创建后其值就不能改变，所以const对象必须初始化。

### 1.2 初始化问题

可以使用大括号初始化，也可以使用等号和小括号初始化。

- 初始化的概念：创建变量时赋予它一个值（不同于赋值的概念）
- 类的构造函数控制其对象的初始化过程，无论何时只要类的对象被创建就会执行构造函数
- 如果对象未被用户指定初始值，那么这些变量会被执行默认初始化，默认值取决于变量类型和定义变量的位置
- 无论何时只要类的对象被创建就会执行构造函数，通过显式调用构造函数进行初始化被称为显式初始化，否则叫做隐式初始化
- 使用等号（=）初始化一个类变量执行的是拷贝初始化，编译器会把等号右侧的初始值拷贝到新创建的对象中去，不使用等号则执行的是直接初始化
- 传统C++中列表初始化仅能用于普通数组和POD类型，C++11新标准将列表初始化应用于所有对象的初始化（但是内置类型习惯于用等号初始化，类类型习惯用构造函数圆括号显式初始化，vector、map和set等容器类习惯用列表初始化）

**初始化不等于赋值**

初始化的含义是创建变量时赋予其一个初始值，而赋值的含义是把对象的当前值擦去，并用一个新值替代它。C++定义了初始化的好几种不同形式，例如我们定义一个int变量并初始化为0，有如下4种方式：

```c++
int i = 0；
int i = {0};//C++11
int i{0};//C++11
int i(0);
```

变量名不能和关键字重复。有效的标识符包括一系列字符（字母、数字和下划线）组成，并且不以数字开头。在C++中，区分字母的大小写，因此，A1和a1不是一回事。

变量的声明必须在变量使用的位置之前。

### 1.3  C++编程范式(C++ programming paradigm)

![image](assets/image-20231120130924-l6dwb3i.png)

![image](assets/image-20231120130950-j9xwx7a.png)​

![image](assets/image-20231120131018-hducmu3.png)

![image](assets/image-20231120131538-qw4vjo6.png)​​​​​![image](assets/image-20231120131039-ygbrdzr.png)

在计算机科学中，一个函数的副作用就是该函数除了返回计算结果之外，还对其他部分(如外部变量、数据结构、系统状态等)进行了修改或产生了其他影响。如果一个函数没有副作用，那么给定相同的输入，它总会产生相同的输出，而且不会改变系统的状态。例如下列的加法函数

```python
def add(x,y):
	return x+y
//没有副作用。无论调用多少次，只要输入相同，总是会返回相同的结果，而且不会改变系统的状态。
```

```python
counter=0;
def increment_counter(x):
	global counter
	counter+=x
	return counter
//有副作用，改变了全局变量counter的值
```

​    函数式编程鼓励使用无副作用的函数，因为这样的函数更容易理解和调试，也更容易进行并行和分布式计算。使得代码更加模块化。

### 1.4 命名空间/名字空间(name space)

[详解c++的命名空间namespace - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/126481010)

[命名空间 (C++) | Microsoft Learn](https://learn.microsoft.com/zh-cn/cpp/cpp/namespaces-cpp?view=msvc-170)

在c++中，名称（name）可以是符号常量、变量、函数、结构、枚举、类和对象等等。工程越大，名称互相冲突性的可能性越大。另外使用多个厂商的类库时，也可能导致名称冲突。为了避免，在大规模程序的设计中，以及在程序员使用各种各样的C++库时，这些标识符的命名发生冲突，标准C++引入关键字namespace（命名空间/名字空间/名称空间），可以更好地控制标识符的作用域。

命名空间是一个声明性区域，为其内部的标识符（类型、函数和变量等的名称）提供一个范围。 命名空间用于将代码组织到逻辑组中，还可用于避免名称冲突，尤其是在基本代码包括多个库时。 命名空间范围内的所有标识符彼此可见，而没有任何限制。 命名空间之外的标识符可通过使用每个标识符的完全限定名（例如 `std::vector<std::string> vec;`）来访问成员，也可通过单个标识符的 [using 声明](https://learn.microsoft.com/zh-cn/cpp/cpp/using-declaration?view=msvc-170) (`using std::string`) 或命名空间中所有标识符的using namespace std;来访问成员。 头文件中的代码应始终使用完全限定的命名空间名称。

不要使用如下的命名空间写法：

```cpp
using namespace std;
```

可以使用如下形式的写法：

```cpp
using std::cout;
using std::endl;
```

### 1.5 声明与定义

声明是引入标识符并描述其类型，无论是什么类型，对象还是函数。编译器需要该声明，以便识别在别处使用该标识符。

```cpp
extern int bar;
extern int g(int,int);
double f(int,double);
class foo;
```

定义是实例化这个标识符。链接器需要定义，以便将对标识符的引用链接到标识符所表示的实体。

```cpp
int bar;
int g(int lhs,int rhs){
    return lhs*rhs
};
class foo{
  //do something  
};
```

两者的区别：

1.定义有时可以取代声明，反之不可以

2.标识符可以被声明多次，但只能定义一次

3.定义通常伴随着编译器为标识符分配内存



## 2. 类、对象、成员函数的介绍

### 2.1 类的基本概念

在上一节中，讨论了类，对象，数据成员(属性)，成员函数(行为)。有日期对象、时间对象、音频对象、视频对象、汽车对象、人对象等。几乎任何名词都可以在属性（如名称、颜色和大小）和行为（如计算、移动和通信）方面合理地表示为软件对象。

可以将汽车比喻为类，汽车可以完成的任务就是成员函数。在C++中，我们经常创建一个称为类的程序单元来容纳一组函数执行类的任务——这些任务被称为类的成员函数。例如代表银行帐户的类可能包含用于存款的成员函数给一个账户，另一个从账户提款，第三个查询账户的当前余额是。一个类类似于一辆汽车的工程图纸，哪个房子设计了加速踏板、制动踏板、方向盘等。

就像有人必须根据工程图纸制造汽车一样驾驶汽车时，必须先从类中构建一个对象，然后程序才能执行任务类的成员函数定义的。这样做的过程称为实例化。然后，一个对象被称为其类的实例。

就像汽车的工程图纸可以多次重复使用来制造许多汽车一样，你可以多次重用一个类来构建许多对象。在构建新类和程序时重用现有类可以节省时间和精力。重用还可以帮助您构建更可靠、更有效的系统，因为现有的类和组件通常都经过了广泛的测试、调试和性能调优。正如可互换部件的概念对工业革命至关重要一样，可重用类对对象技术推动的软件革命也至关重要。

当你驾驶汽车时，踩下油门会向汽车发送执行任务的信息--也就是说，走得更快。类似地，您向对象发送消息。每个消息都实现为成员函数调用，告诉对象的成员函数执行其任务。例如，程序可能会调用特定银行帐户对象的存款成员函数来增加帐户余额。

汽车除了具有完成任务的能力外，还具有一些属性，如颜色、车门数量、油箱中的汽油量、当前速度和行驶总里程记录（即里程表读数）。与它的功能一样，汽车的属性也作为其设计的一部分在其工程图中表示（例如，包括里程表和燃油表）。当你驾驶一辆真正的汽车时，这些属性会随汽车一起携带。每辆车都有自己的特点。例如，每辆车都知道自己油箱里有多少油，但不知道其他车油箱里有多油。

类似地，一个对象在程序中使用时也会附带一些属性。这些属性被指定为对象类的一部分。例如，银行帐户对象具有余额属性，表示帐户中的金额。每个银行帐户对象都知道它所代表的帐户中的余额，但不知道银行中其他帐户的余额。属性由类的数据成员指定。

类将属性和成员函数封装（即包装）到从创建的对象中这些类——对象的属性和成员函数是密切相关的。对象可以相互通信，但通常不允许它们知道其他对象是如何实现的——实现细节隐藏在对象本身中。正如我们将看到的，这种信息隐藏对于良好的软件工程至关重要。

一个新的对象类可以通过继承快速方便地创建——类吸收了现有类的特性，可能会对其进行自定义并添加独特的特点。在我们的汽车类比中，一个“敞篷”类的物体当然是更普通的“汽车”的一个对象，但更具体地说，车顶可以升高或降低。



类包含：

1.由变量定义的数据域

2.由函数定义的行为

**代表类型的名字必须首字母大写。**

### 2.2 对象的构成

对象是类的实例，具有唯一的标识、状态和行为：

1.对象状态由数据域(也称为属性)及其当前值构成

2.对象的行为由一组函数定义

在你创造一个类的对象之前，不可以调用类中的成员函数。

### 2.3 类：数据成员、set和get函数

#### 2.3.1 类的定义

```c++
// Fig. 3.2: Account.h
// Account class that contains a name data member
// and member functions to set and get its value.
#include <string> // enable program to use C++ string data type

class Account {
public:
// member function that sets the account name in the object
    void setName(std::string accountName) {
       name = accountName; // store the account name
    }
    
// member function that retrieves the account name from the object
    std::string getName() const {
        return name; // return name's value to this function's caller
    }
private:
    std::string name; // data member containing account holder's name
}; // end class Account
```

上述代码即为Account类的定义。

#### 2.3.2 关键词class和class body

1.在类的定义中，结束的大括号后面要写上分号。忘记类定义末尾的分号是语法错误。为了较好的可复用性，可以将类的定义单独写为一个.h文件。

2.在C++中，需要对类、对象和函数等命名，若名称中间没有空格和标点，除第一个单词外后面的单词首字母均大写。称为驼峰式命名。

如果第一个单词首字母大写，称之为`upper camel case`（`CamelCase`，大驼峰式），例如`"GetUserName"`。
如果第一个单词首字母小写，称之为`lower camel case`（`camelCase`，小驼峰式），例如`"getUserName"`。

#### 2.3.3 类数据成员

数据成员存在于：

1.在程序调用对象的成员函数之前

2.在成员函数执行之时

3.在成员函数完成执行之后

数据成员的声明在类的定义内，但在类的成员函数体之外声明。如上诉Account类的定义。按照惯例，一般将数据成员的定义放在class body的最后。

#### 2.3.4 函数形参

在函数的形参中，每个形参必须指明类型。当一个函数有多个形参时，每个形参之间用逗号隔开。实参的个数和顺序必须和形参的个数顺序相同。函数的形参是局部变量。

**实参和形参的类型必须一致，但不必相同**

### 2.4 使用构造函数初始化对象

#### 2.4.1 构造函数

构造函数是特殊的成员函数，必须和类的名字一样。C++在每个对象建立时，都要调用构造函数。像成员函数一样，构造函数也可以有形参，对应的实参值帮助初始化对象的数据成员。每个类都可以定义一个构造函数，该构造函数为该类的对象指定自定义初始化。

**构造函数的特点：**

1.在创建对象时，自动的进行初始化工作。

2.构造函数在声明时，前面不能加返回类型，void也不可以。

3.构造函数与类同名。

4.没有返回值。

5.可以重载构造函数。

6.构造函数可以不带参数。

**默认构造函数：调用时可以不需要实参的构造函数。即参数表为空的构造函数或全部参数都有默认值的构造函数。**

```cpp
Clock(){
	//class body
}//默认构造函数，无参数，函数体可能为空
Clock(int n=0,int x=1,double y=0){
    //class body
};//默认构造函数，默认参数，函数体可能为空
```

上述两种形式的构造函数如果同时在类中出现，将会产生编译错误。

**默认构造函数的角色：**

1.若内嵌对象成员没有被显式的初始化，该内嵌对象的无参构造函数会被自动调用。若内嵌对象没有无参构造函数，则编译器会报错。

```cpp
class X{
private:
    Circle c1;//c1即为内嵌对象
public:
    X() {}  
};
```

2.也可以在初始化列表中手工构造对象。参见2.7节。

**若类的数据域是一个对象类型(且它没有无参构造函数)，则该对象初始化可以放到类的构造函数初始化列表中。**

**创建对象：**

```cpp
Circle circle1;//正确，但是不推荐这么写
Circle circle();//错误，编译器会认为这是一个函数声明
Circle circle3{};//正确，推荐写法。这里明确显式用空初始化列表初始化Circle3对象(调用Circle的默认构造函数)
```

**类可以不声明构造函数，此情况下，编译器会提供一个带有空函数体的无参构造函数**

1.一个类可以有多个构造函数

```cpp
class Student
{
    Student() {};//默认构造函数 default constructor
    Student(int age) {};//非默认构造函数
    Student(int age, bool sex) {};//非默认构造函数
};

int main()
{
    Student stu1;//调用默认构造函数
    Student stu2(10);//调用带一个整形参数的构造函数
    Student stu3(10, true);//调用两个参数的那个构造函数

    return 0;
}
```

2.编译器合成的默认构造函数

如果我们一个构造函数都没有定义，编译器也会为我们合成一个默认构造函数（default constructor）。

```cpp
class Student
{
};

int main()
{
    Student stu1;//调用编译器合成的默认构造函数（虽然我们没有看见那个函数在哪，编译器真是太热心了）

    return 0;
}
```

3.禁止编译器合成默认构造函数

只要我们自己定义了构造函数，编译器就不会再多管闲事替我们热心的合成一个默认的构造函数了。

下面的类已经没有默认构造函数了，因为我们定义了非默认构造函数，编译器不再替我们合成，而我们自己也没有定义默认构造函数。

```cpp
class Student
{
    Student(int age) {};//非默认构造函数
    Student(int age, bool sex) {};//非默认构造函数
};

int main()
{
    Student stu2(10);//调用带一个整形参数的构造函数
    Student stu3(10, true);//调用两个参数的那个构造函数

    return 0;
}
```

这样的类也有一个不便之处，那就是像下面这样定义对象会报错：

<img src="assets/image-20231129211723-btg13bh.png" alt="image" style="zoom:50%;" />如果要解决这个问题，就只能像一开始那样，自己显式的定义一个默认构造函数。

如果类中已经定义构造函数，默认情况下编译器就不再隐含生成默认构造函数。如果此时依然希望编译器隐含生成默认构造函数，可以使用"=default"

```CPP
class Clock{
public:
	Clock()=default;//指示编译器提供默认构造函数
	CLock(int n,intx,int y);//构造函数
private:
	int hour,minute,second;
}
```

```
Clock(){}
```

使用上述形式的构造函数也可以满足需求，但是上述形式的构造函数在每次生成对象时都会调用，使用default只要在需要的时候才会调用。

#### 2.4.2 对象访问运算符

使用点运算符访问对象中的数据和函数。

```cpp
Circle circle1;
circle.radius=10;
int area =circle1.getArea();
```

#### 2.4.3 explicit关键词

指定单个参数的构造函数应声明为explicit

#### 2.4.4 在对象创立时初始化对象

```c++
#include <iostream>
#include "Account.h"

using namespace std;

int main(){
    Account account1{"Jane Green"};
    Account account2{"John Blue"};
    
    cout<<"account1 name is: "<<account1.getName()<<endl;
    cout<<"account2 name is: "<<account2.getName()<<endl;
}
```

在任何没有明确定义构造函数的类中，编译器都会提供一个没有参数的默认构造函数。默认构造函数不会初始化类的基本类型数据成员，但会为另一个类的对象的每个数据成员调用默认构造函数。例如在如下的代码中：

```c++
class Account{
public:
    void setName(std::string accountName){
        name=accountName;
    }
    std::string getName() const{
        return name;
    }
private:
    std::string name;
}
```

​     上述例中的类的默认构造函数调用了string类的默认构造函数初始化名为name的数据成员为空的字符串。

​    **一个未被初始化的基本类型变量包含一个未定义的值**

如果你定义了一个传统的（custom）的构造函数在类中，编译器不会为类生成一个默认构造函数。在这种情况下，就**不可以**使用如下的语句创造一个Account对象，除非你定义的构造函数有一个空的形参列表。后续我们会知道，在C++11的标准中，允许你强迫编译器创造一个默认的构造函数即使你已经定义了非默认函数。**除非类的数据成员的默认初始化是可接受的，否则通常应该提供一个自定义构造函数，以确保在创建类的每个新对象时，数据成员都以有意义的值进行了正确的初始化。**

```c++
Account myAaccount;
```

### 2.5 类的示例

balance(余额)

#### 2.5.1 UML类图

```c++
#include <string>
class Account {
public:
    // constructor initializes data member name with parameter accountname
    Account(std::string accountName, int initialBalance)
            :name{accountName}{
            if (initialBalance>0){
                 balance=initialBalance;
           }
    }
    void deposit(int depositAmount){
        if(depositAmount>0){
            balance=balance+depositAmount;
        }
    }

    int getBalance() const{
        return balance;
    }
    void setName(std::string accountName){
        name=accountName;
    }

    std::string getName() const{
        return name;
    }
private:
    std::string name;
    int balance{0};
};
```

在上述代码中，即使变量balance没有在任何一个成员函数中声明，所有的成员函数仍然可以使用balance，我们可以在这些成员函数中使用 balance因为它是同一个类定义中的数据成员。

上诉类的UML类图为：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230912212113861.png" alt="image-20230912212113861" style="zoom:50%;" />
</div>


### 2.6 匿名对象

**有时候需要创建一个只用一次的对象，此时，无需给对象命名，这种对象叫做匿名对象。**匿名对象用在成员拷贝，如下例：

```cpp
Classname();//无参构造函数
Classname(arguments);//有参构造函数
```

```cpp
#include <iostream>
using namespace std;

class Circle{
public:
    double radius;
    Circle(){
        radius=1;
    }

    Circle(double newRadius){
        radius=newRadius;
    }

    double getAera(){
        return radius*radius*radius;
    }
};

int main(){
    Circle circle1,circle2;
    circle1=Circle();
    circle2=Circle(5);

    cout<<"area is"<<circle1.getAera()<<endl;
    cout<<"area is"<<circle2.getAera()<<endl;
    cout<<"area is"<<Circle().getAera()<<endl;
    cout<<"area is"<<Circle(5).getAera()<<endl;
}
```

![image](assets/image-20231129215137-2qpm77u.png)​

### 2.7 构造函数初始化列表

在构造函数中用初始化列表初始化数据域。

```cpp
className (parameterList)
	:dataField1{value1},dataField2{value2}//这一行就是初始化列表
{
    //do something
}
```

对于基础类型，下列两种写法效果相同。

```cpp
Circle::Circle():radius{1}{
    
}
```

```cpp
Circle::Circle(){
    radius=1;
}
```

**使用构造函数初始化列表的原因：**

因为在类的数据域中可能存在一个对象类型，此对象被称为对象中的对象，或者内嵌对象。

**内嵌对象必须在被嵌对象的构造函数体执行完成前就构造完成。**因此使用构造函数初始化列表

考虑下列代码：

```cpp
class Time{
//code omitted
};

class Action{
public:
    Action(int hour,int minute,int second){
        time=Time(hour,minute,second)
    }

private:
    Time time;
};
```

在Action类中，构造函数的函数体中，对time对象执行赋值操作(使用Time创建的匿名对象)。也就是说在构造函数的函数体执行之前，time对象就要存在了，不存在的话就无法进行赋值操作。那么time对象在何处创建并初始化的呢？应该在函数体执行之前构造并初始化完成。即使用构造函数的成员初始化列表进行time的初始化。

若类的数据域是一个对象类型(且它没有无参构造函数)，则该对象初始化必须放在初始化列表内。

### 2.8 不可变对象

不可变对象，即对象创建后，其内容不可改变，除非通过成员拷贝

不可变类：不可变对象所属的类

让类变为不可变类的方法：

1.所有数据域均设置为private属性

2.没有更改器函数

3.也没有能够返回可变数据域对象的引用或指针的访问器

多线程编程和函数式编程会用到不可变类。

### 2.9  类的前向引用声明

类应该先声明，后引用

如果需要在某个类的声明之前，引用该类，则应进行前向引用声明

前向引用声明只为程序引入一个标识符，但具体声明在其他地方

### 2.10 常量(Constant)/const关键字

1.常量是程序中的一块数据，这个数据一旦声明后就不能修改了。

如果这块数据有一个名字，这个名字就叫做命名常量。比如const int A=42,A就是命名常量

如果这个常量从字面上看就可以知道它的值，那它就叫做“字面值常量”，例如上例中的42即为字面值常量。

2.符号常量(包括枚举值)必须全部大写并用下划线分隔单词

例如：MAX_ITERATIONS,COLOR_RED,PI

通过下列方式定义一个常量：

```cpp
const datatype CONSTANTNAME = VALUE;//const和数据类型可以互相交换
```

```cpp
const double PI=3.14159;
const int SIZE=3;
int const X=5;
const int C=3;
const char C='k';
const char* STR="hello";
```

上述代码中，int const和const int 等价。

PI、SIZE等就叫做**命名常量**或者**符号常量**

#### 2.10.1 常量表达式(constant expressions)

1.常量表达式是编译期i可以计算值的一个表达式。

例如，C++数组的大小要求是编译期的一个常量(原生数组以及array)

```cpp
int n=1;
n++;
array<int,n> a1;//error!n不是一个常量表达式
const int x=2;
array<int,x> a2;//正确！n是一个常量表达式
```

2.const修饰的对象未必是编译期常量

```cpp
const int rcn=n;//rcn是一个运行期常量，编译器在编译期不知道它的值
rcn=++n;//
array<int,rcn> a3;//
```

#### 2.10.2 constexpr:编译期常量表达式说明符

constexpr说明符声明**可在编译时计算函数或变量的值**

```cpp
constexpr int max(int a , int b) { // c++11 引入 constexpr
    if (a > b) 
        return a;   // c++14才允许constexpr函数中有分支循环等
	else       
        return b;
}

int main() {
	int m = 1;
	const int rcm = m++;   // rcm是运行期常量
	const int cm = 4;      // 编译期常量，等价于: constexpr int cm = 4;
	int a1[ max(m , rcm)]; // 错误：m & rcm 不是编译期常量
	std::array<char , max(cm , 5)> a2; // OK: cm 和 5 是编译期常量
}
```

constexpr函数可以接受非常量实参，但此时的结果不再是一个常量表达式。



#### 2.10.3 const vs constexpr

1.**主要区别**


const:告知程序员，const 修饰的内容是不会被修改的。主要目的是帮程序员避免bug 。

```cpp
char* s1 = "Hello"; // C语言允许，但C++编译出错

*s1 = 'h’;          // C语言中，语法正确，但运行时会出错 

const char* s2 = "World"; // C++ 要求加const

*s2 = 'w';                // C++编译器报错
```

constexpr ：用在所有被要求使用“constant expression”的地方（就是constexpr修饰的东西可以在编译期计算得到值），主要目的是让编译器能够优化代码提升性能 。

2.constexpr：初学者只需了解其含义即可


constexpr用法有非常多的细节（cppreference.com 列出了30 多个条目）

C++14 、C++17 、C++20 对它都有细节修改

#### 2.10.4 字面值(字面量)

C++中字面值常量是一类特殊的常量，它们没有名字，只能用它们的值来称呼，因此得名“字面值常量”。常见的字面值常量包括以下几类：

- 整型字面值常量：1,2,3,4,5等等
- 浮点型字面值常量：1.1,2.2,3.3等等
- 布尔类型字面值常量：true，false
- 字符字面值常量：'a','b','c','d'等等
- 字符串字面值常量："abc","def"等等

其中只有**字符串字面值常量**存储在全局区，可以取地址，其他的字面值常量都放在寄存器上，不能取内存地址。

比起字面值常量，使用const等定义的常量有一个可以称呼的名字，如`const int a=2;`名字就是`a`

#### 2.10.5 C++14 字符串字面量

1. C++11 Raw String literals (C++11“原始/生”字符串字面量)


从名字上就可以看出，这种“Raw String literals”应该长得很原始。那么这个原始该怎么体现出来呢？我们通过语法和简单示例就能看出来。

语法:  

```cpp
R"delimiter( raw_characters )delimiter"
```

```cpp
#include <iostream>
const char* s1 = R"(Hello
World)";

// s1效果与下面的s2和s3相同
const char* s2 = "Hello\nWorld";
const char* s3 = R"NoUse(Hello
World)NoUse";

int main(){
    std::cout << s1 << std::endl;
    std::cout << s2 << std::endl;
    std::cout << s3 << std::endl;
}
```



从例子中看出，“Raw String literals”在程序中写成什么样子，输出之后就是什么样子。我们不需要为“Raw String literals”中的换行、双引号等特殊字符进行转义。

2. C++14: String Literals (C++14的字符串字面量)


C++14将运算符  ""s 进行了重载，赋予了它新的含义，使得用这种运算符括起来的字符串字面量，自动变成了一个 std::string 类型的对象。

```cpp
auto hello = "Hello!"s;              // hello is of std::string type

auto hello = std::string{"Hello!"};  // equals to the above

auto hello = "Hello!";               // hello is of const char* type
```

 例子： 

```cpp
#include <string>
#include <iostream>

int main() {
    using namespace std::string_literals;
    std::string s1 = "abc\0\0def"; 
    std::string s2 = "abc\0\0def"s;
    std::cout << "s1: " << s1.size() << " \"" << s1 << "\"\n";
    std::cout << "s2: " << s2.size() << " \"" << s2 << "\"\n";
}
```

上面例子的一个可能输出结果如下：

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240413185609863.png" alt="image-20240413185609863" style="zoom:50%;" />



### 2.11 用指针访问对象成员(对象指针)

对象指针可以指向新的对象名。箭头运算符->,使用指针访问对象成员。

```cpp
Circle circle;
Circle* pCircle=&circle1;

cout<<(*pCircle).radius<<endl;
cout<<(*pCircle).getArea<<endl;

(*pCircle).radius=5.5;

cout<<pCircle->radius<<endl;
cout<<pCircle->getArea()<<endl;
```

### 2.12 C++成员的就地初始化

非静态成员可以就地初始化。

在类中进行数组的就地初始化，编译器不能进行数组大小的自动推断。

```cpp
class X{
	int a[] {1,4,5};//错误！
    int a1[3] {1,4,5};//正确！
}；
```

### 2.13 类的成员的初始化次序

**执行次序**：就地初始化->构造函数初始化列表->在构造函数体中为成员赋值

**初始化优先级**：在构造函数体中为成员赋值->构造函数初始化列表->就地初始化

若一个成员同时就地初始化和构造函数列表初始化，则就地初始化语句被忽略不执行。

### 2.14 断言(Assertion)与静态断言

断言是一条检测假设成立与否的语句。**如果假设成立，断言不会产生作用，如果假设不成立，断言会终止程序的运行。**

1.1. assert :C语言的宏(Macro)，运行时检测。

用法：

```cpp
//包含头文件 <cassert>  以调试模式编译程序

assert( bool_expr ); // bool_expr 为假则中断程序
```

```cpp
std::array a{ 1, 2, 3 };  //C++17 类型参数推导

for (size_t i = 0; i <= a.size(); i++) {
	assert(i < 3);  //断言：i必须小于3，否则失败
	std::cout << a[ i ];
	std::cout << (i == a.size() ? "" : " ");
}
```

1.2. assert()依赖于NDEBUG 宏


NDEBUG这个宏是C/C++标准规定的，所有编译器都有对它的支持。

   (1)  调试(Debug)模式编译时，编译器不会定义NDEBUG，所以assert()宏起作用。

   (2)  发行(Release)模式编译时，编译器自动定义宏NDEBUG，使assert不起作用

如果要强制使得assert()生效或者使得assert()不生效，只要手动 #define NDEBUG 或者 #undef NDEBUG即可。

1.3. assert 帮助调试解决逻辑bug （部分替代“断点/单步调试”）

```cpp
#undef NDEBUG   // 强制以debug模式使用<cassert>

int main() {
	int i;
	std::cout << "Enter an int: ";
	std::cin >> i;
	assert((i > 0) && "i must be positive"); //&&是一个非空指针，一定是真的。
	return 0;
}
```

上面示例的第6行代码中，若assert中断了程序则表明程序出bug了！程序员要重编代码解决这个bug，而不是把assert()放在那里当成正常程序的一部分

2.C++11：static_assert (C++11的静态断言 )

2.1. static_assert ( bool_constexpr, message)//C++17起，message可选


其中两个参数解释如下：

(1)      bool_constexpr:   编译期常量表达式，可转换为bool 类型

(2)      message: 字符串字面量 ，是断言失败时显示的警告信息。自C++17起，message是可选的 

2.2. 作用：编译时断言检查
// 下面的语句能够确保该程序在32位的平台上编译进行。

// 如果该程序在64位平台上编译，就会报错

```cpp
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");
```

2.3. static_assert的用途
常用在模版编程中 ，对写库的作者用处大

在static_assert的第一个参数 bool_constexpr  中不能有变量表达式

3.何时使用断言


若某些状况是你预期中的，那么用错误处理；若某些状况永不该发生，用断言

```cpp
int n{ 1 } , m{ 0 };
std::cin >> n;
assert((n != 0) && "Divisor cannot be zero!"); // 不合适
int q = m / n;


int n{ 1 } , m{ 0 };
do {                // 这是修补bug的代码
	std::cin >> n;    // 断言失败后，要解决这个bug
} while (n == 0);   // 在这里编写修复bug的代码
assert((n != 0) && "Divisor cannot be zero!");
int q = m / n;
```

### 2.15 不可变对象和类

不可变对象：对象创建后，其内容不可改变，除非通过成员拷贝，对于编写多线程程序很有帮助。

不可变类：不可变对象所属的类。

**如何让一个类成为不可变类：**

1.所有数据域均设置为private属性

2.没有更改器函数

3.没有能够返回可变数据域对象的引用或指针的访问器







## 3.控制语句、运算符及bool类型

### 3.1 算法

任何计算问题都可以通过按特定顺序执行一系列操作来解决。用以下方法解决问题的程序：

1.要执行的操作

2.这些操作的执行顺序

就叫做算法。指定程序中语句(操作)执行的顺序称为程序控制。

### 3.3 伪代码(Pseudocode)

使用伪代码，不必担心C++中的细枝末节。伪代码并不在计算机上执行，一个精心准备的伪代码程序可以很容易地转换成相应的C++程序。在我们的伪代码，我们通常不包括变量声明，但是一些程序员选择列出变量并说明它们的用途。

### 3.4 控制结构

它们使您能够指定要执行的下一个语句不一定是按顺序执行的下一个语句。这就是所谓的控制权转移(transfer of control)。所有的程序都可以用三种结构表示：顺序结构、选择结构和循环结构。C++提供了四种循环语句，while，do...while,for和range-based for。C++的关键词如下：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230914102112293.png" alt="image-20230914102112293" style="zoom:50%;" />
</div>

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230914102230933.png" alt="image-20230914102230933" style="zoom:50%;" />
</div>

关键词必须小写，并且不能用作标识符。

### 3.5 带有初始化器的if和switch语句(C++17)

#### 3.5.1 带有初始化器的if语句

不带初始化器的if语句：

```cpp
int foo(int arg){
	return arg;
}
int main(){
	auto x=foo(42);
	if(x>40){
        //do something with x
    }
    else{
        //do something with x
    }
    //auto x=3;
}
```

带初始化器的if语句：

```cpp
int foo(int arg){
	return arg;
}
int main(){
	//auto x=foo(42);
	if(auto x=foo(42);x>40){
        //do something with x
    }
    else{
        //do something with x
    }
    auto x=3;//名字x可以重用
}
```

为何使用带有初始化器的if语句：

1.本应限制于if块的变量，侵入了周边的作用域

2.若编译器确知变量作用域限于if块，则可以更好地优化代码

#### 3.5.2 带有初始化器的switch语句

语法：

```cpp
switch (initializer;variable);
```

示例：

```cpp
switch(int i=rand()%100;i){
	case 1：
        //do something
    default:
        std::cout<<i<<endl;
        break;
}
```



### 3.6 if...else

悬挂else问题(Dangling-else Problem)。

在整个文本中，我们总是将控制语句正文括在大括号中,从而避免了一个被称为悬挂else问题的逻辑错误。**else的匹配**：**不管你if—else是如何嵌套使用，对不对齐，你看的顺不顺眼，我else只会和离得最近的if去匹配**，所以要养成良好的习惯，即在if和else后都加上大括号。

#### 3.6.1 三元运算符

?:是C++唯一的三元运算符。可以在代码中代替if...else让代码更加简洁。例如：

```c++
cout<<(studentGrade>=60? "passed":"failed");
```

若？前的语句为真，则执行：前的内容，反之执行：后的内容。由于此运算符的优先级较低，所以一般将整个运算符放在括号内，在if...else不能执行功能时用来代替。冒号两侧不光可以输出字符串，还可以执行操作，如下：

```c++
grade>=60?cout<<"passed":"failed";
```



### 3.7 嵌套控制语句(narrowing conversion)

**使用列表初始化防止narrowing conversion**

A narrowing conversion changes a value to a data type that might not be able to hold some of the possible values. For example, a fractional value is rounded when it is converted to an integral type, and a numeric type being converted to Boolean is reduced to either True or False.

在之前，初始化值可以写为

```c++
int x=12.7
```

此种情况下，C++会浮点部分截断，即narrowing conversion，实际上赋给x的值是12。许多编译器会给出警告，但仍然会允许编译。但是使用列表初始化，例如:

```c++
int x{12.7};
//or
int x={12.7};
```

就会产生编译错误，帮助你预防潜在的逻辑错误。

### 3.8 复合赋值运算符

![image-20230917214949437](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230917214949437.png)

### 3.9 递增和递减运算符

即++ 和 --

![image-20230917215156198](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230917215156198.png)

#### 3.10 运算符优先级以及关联

![image-20230917220012294](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230917220012294.png)

### 3.11 布尔数据类型

 C++语言在其标准化过程中引入了`bool`、`true`和`false`关键字，增加了原生数据类型来支持布尔数据。布尔数据类型主要与条件语句相关。

例如:

```cpp
bool isMybook;
bool isRunning={false};
bool isBoy();
```

**‍布尔数据类型与整型的转换：**

整数0和布尔false互相转化

整数1和布尔true互相转化

任意非0整数和布尔true相互转化

![image-20240405155247642](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240405155247642.png)

**编码规范：**

布尔变量/函数的命名应该使用前缀"is"

```cpp
isMale,isOpen,isVisible
```

‍

## 4.控制语句：逻辑运算符

### 4.1for循环

for循环的基本结构为：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230920094634851.png" alt="image-20230920094634851" style="zoom:50%;" />
</div>

两个分号是必不可少的，用while表示for可以写为：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230920201646295.png" alt="image-20230920201646295" style="zoom:50%;" />
</div>

如果在for循环中，第一部分被省略，C++会假定判断条件始终为真，循环一直进行。

程序经常在循环体中显示控制变量值或在计算中使用它，但这种使用不是必需的。控制变量通常用于控制迭代，尽管控制变量的值可以在for循环的主体中更改，但应避免这样做是因为这种做法可能会导致细微的错误。如果程序必须修改循环体中控制变量的值，请使用while而不是for。

setw(int n)是c++中在输出操作中使用的字段宽度设置，设置输出的域宽，n表示字段宽度。**只对紧接着的输出有效**，紧接着的输出结束后又变回默认的域宽。当后面紧跟着的输出字段长度小于n的时候，在该字段前面用空格补齐；当输出字段长度大于n时，全部整体输出。头文件为#include <iomanip>

```c++
#include <iostream>
#include <iomanip>

using namespace std;

int main()
{
    // 开头设置宽度为 4，后面的 runoob 字符长度大于 4，所以不起作用
    cout << setw(4) << "runoob" << endl;
    // 中间位置设置宽度为 4，后面的 runoob 字符长度大于 4，所以不起作用
    cout << "runoob" << setw(4) << "runoob" << endl;
    // 开头设置间距为 14，后面 runoob 字符数为6，前面补充 8 个空格 
    cout << setw(14) << "runoob" << endl;
    // 中间位置设置间距为 14 ，后面 runoob 字符数为6，前面补充 8 个空格 
    cout << "runoob" << setw(14) << "runoob" << endl;
    return 0;
}
```

representational error---表征错误

不要使用double（或float）类型的变量来执行精确的货币计算。浮点数的不精确性可能导致错误。

clunky---笨重

类型long long和其他C++的整数类型的范围在不同的平台会有所不同。

类成员函数是类的一个成员，它可以操作类的任意对象，可以访问对象中的所有成员。



C ++中的abs()函数返回参数的绝对值。abs() 方法在C++语言中，最早的C98版本中，只对double、float、long double类型生效，不支持int类型，作用是求数据的绝对值。从C++11开始，增加了对int整型数据类型的支持。

size函数用来获取字符串长度。

**请注意，类的任何成员函数可以直接调用任何其他成员函数来对类的同一对象执行操作

**Banker's Rounding：**

传统的 “四舍五入” 会让数量非常大的数据计算之后偏大，因为两端距离相等的时候始终选择绝对值大的，而 “四舍六入五成双” 的 Banker's Rounding 规则会让数据两端取舍的概率均等，因为对于不同的数值，偶数可能在左边，也可能在右边，计算之后的数据不会明显偏大或偏小。Banker's rounding 就是对于0.5的情况，向最近的偶数舍入，例如0.5舍入为0，3.5和4.5都舍入为4。

### 4.2 switch

If no match occurs and the switch does not contain a default case, program control simply continues with the first statement after the switch.

如果没有匹配，并且不包含默认情况，程序控制只需继续执行switch后的第一条语句。

尽管case和defult可以以任意顺序出现在switch中，但还是习惯于将default放在最后，当default在最后时，break就不是必须的。

在case后，除了可以使用整数，还可以使用字符常量(以单引号包裹)，还可以使用枚举常量(enum)。

注意1：switch语句中表达式类型只能是整型或者字符型。
注意2：case里如果没有break，那么程序会一直向下执行。
总结：与if语句比，对于多条件判断时，switch的结构清晰，执行效率高，缺点是switch不可以判断区间。

**在case中，可以用x ... y 表示范围在[x,y]的值，两边都是闭区间。**

```cpp
#include <iostream>
using namespace std;

int main() {

	int month;
	cin >> month;
    if(month < 1 || month > 12) //优先判断是否合法月份
        cout << "不合法" << endl;
    else{
        switch(month){ //根据月份判断
            case 3 ... 5: //连续的值
                cout << "春季" << endl;  break;
            case 6 ... 8:
                cout << "夏季" << endl;  break;
            case 9 ... 11:
                cout << "秋季" << endl;  break;
            default:
                cout << "冬季" << endl;
        }
    }
	return 0;
}
```

### 4.3 break

break语句在while、for、do…while或switch中执行时，会导致立即退出该语句——执行从循环语句之后的第一个语句开始。

### 4.4 continue

continue语句在while、for或do…while中执行时，跳过循环体中的其余语句，继续循环的下一次迭代。

### 4.5 逻辑操作符(与或非)

C++’s logical operators enable you to form more complex conditions by combining simple conditions. 逻辑操作符包括;&&(与)、||(或)、！(非)。

`boolalpha`的作用是使bool型变量按照`false、true`的格式输出。如不使用该标识符，那么结果会按照`1、0`的格式输出。当使用boolalpha后，以后的bool类型结果都将以true或false形式输出，除非使用noboolalpha取消 boolalpha流的格式标志。

Lvalues can also be used as rvalues on the right side of an assignment,but not vice versa.



## 5. 函数和递归

inline functions ---内联函数   function template---函数模板

### 5.1 C++中的程序构件

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230924160336816.png" alt="image-20230924160336816" style="zoom:50%;" />
</div>

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230924160354364.png" alt="image-20230924160354364" style="zoom:50%;" />
</div>

function prototype---函数原型

#### 5.1.1 函数原型

A function prototype is a declaration of a function that tells the compiler the function’s name, its return type and the types of its parameters.

参数强制转换是编译器可以将参数从一种类型隐式转换为另一种类型的一种技术。 它遵循论据提升规则。 如果一个参数是较低的数据类型，则可以将其转换为较高的数据类型，但反之则不成立。 原因是如果将一个较高的数据类型转换为较低的数据类型，则可能会丢失一些数据。

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230924164652933.png" alt="image-20230924164652933" style="zoom:50%;" />
</div>
### 5.2 C++库标头

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230924204238783.png" alt="image-20230924204238783" style="zoom:50%;" />
</div>

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230924204258834.png" alt="image-20230924204258834" style="zoom:50%;" />
</div>

macro---宏

### 5.3 随机数的产生

随机数的产生可以使用i=rand();

rand函数产生一个0到RAND_MAX之间的无符号整数，如果rand真的产生了一个任意整数，那么在范围内的整数的出现概率是相同的。头文件为 <**cstdlib**​  **&gt;**

为了产生范围在0-5之内的随机整数，我们使用：

```c++
rand()%6;
```

由于要模拟骰子的点数，所以在后面+1.

C++14引入了一个新的语法特性，即数字分隔符（Digit Separators，也被称为"单下划线"）。这个特性的引入，主要是为了提高代码的可读性。在处理大量数字，特别是长数字串时，数字分隔符可以帮助我们更清晰地看到数字的大小和单位。例如，我们可以将一个长整数`1000000000`写成`1'000'000'000`

rand实际上产生的是伪随机数(pseudorandom numbers)，Repeatedly calling rand produces a sequence of numbers that appears to be random. However, the sequence repeats itself each time the program executes.

srand函数的头文件为：<cstdlib>

需要一个无符号整数实参以及seeds rand函数来创造一组随机数，且每次执行产生的一组随机数都是不同的。

rand()函数和srand()函数必须配套使用

```c++
#include <iostream>
#include <iomanip>
#include <cstdlib>
using namespace std;

int main() {
   unsigned int seed{0};
   cout<<"enter seed: ";
   cin>>seed;
   srand(seed);

   for(unsigned int counter{1};counter<=10;++counter){
       cout<<setw(10)<<(1+rand()%6);
       if(counter%5==0){
           cout<<endl;
       }
   }
}
```

还可以使用时间作为种子(seed)，为了不必每次都要输入seed，我们可以使用如下代码：

```c++
srand(static_cast<unsigned int>(time(0)));
```

time函数返回自从1970年1月1号到当前时间的秒数，返回的值类型为time_t,头文件为<ctime>,由于srand需要无符号整数作为实参，所以采用static_cast<unsigned int>将之转化为合适的类型。

#### 5.3.1 放缩及平移随机数

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230926150912826.png" alt="image-20230926150912826" style="zoom:50%;" />
</div>

where the shiftingValue is equal to the first number in the desired range of consecutive integers and the scalingFactor is equal to the width of the desired range of consecutive integers

### 5.4 枚举类型(enum)

关键字enum class，后面为类型名和一组表示整数常量的标识符。例如下述代码：

```c++
enum class Status{CONTINUE,WON,LOST};
```

CONTINUE代表0， WON代表1， LOST代表2

一个枚举类中的标识符必须是唯一的，但是不同的枚举常数可以有相同的整数值。用户自定义类型Status的变量只能赋值在枚举中声明的三个值中的一个。

按照惯例，你应该把一个enum class 名字的第一个字母大写。

另一个流行的scoped enumeration是：

```c++
enum class Months {JAN = 1, FEB, MAR, APR, MAY, JUN, JUL, AUG, SEP, OCT, NOV, DEC};
```

第一个值被设置为1，剩下的值就会从1开始递增，任何一个枚举常数都可以在枚举定义中被赋予一个整数值，并且后续的枚举常数每个都比列表中的前一个常数高一个值1，直到下一个显式设置。

标识符表示的默认为整数(int),但是也可以指定不同的类型。

```c++
enum class Status : unsigned int {CONTINUE, WON, LOST};
```

### 5.5 C++11中的随机数

使用rand函数，不具备很好的统计特性，仍然可以被预测到，在C++11中，引入了头文件\<random>

在本节中，我们将使用默认的随机数生成引擎- -default_random_engine和均匀分布的uniform_int_distribution，将伪随机整数均匀分布在指定的取值范围内。默认范围是从0到你的平台上的一个int的最大值。

class template---类模板

```cpp
#include <iostream>
#include <iomanip>
#include <random>
#include <ctime>
using namespace std;

int main() {
    default_random_engine engine{static_cast<unsigned int>(time(nullptr))};
    uniform_int_distribution<unsigned int> randomInt{1, 6};

    for(unsigned int counter{1};counter<=10;++counter){
        cout<<setw(10)<<randomInt(engine);

        if(counter%5==0){
            cout<<endl;
        }
    }
}
```

### 5.6 作用域规则

当块是嵌套的，并且外块中的标识符与内块中的标识符具有相同的名字时，外块中的标识符被"隐藏"，直到内块终止- -内块"看到"自己的局部变量的值而不是封闭块的相同命名变量的值。

局部变量也可以被声明为静态的。这样的变量也有块范围，但与其他局部变量不同的是，一个静态的局部变量在函数返回到它的调用者时保留了它的值。下次调用该函数时，**静态局部变量包含该函数上次执行完毕时的值**。

所有数值类型的静态局部变量默认初始化为零。下面的语句声明静态局部变量计数，并将其初始化为0：

```c++
static unsigned int count;
```

An identifier declared outside any function or class has **global namespace scope**.

全局变量是通过在任何类或函数定义之外放置变量声明来创建的。这些变量在程序执行的整个过程中保持其值。

**将变量声明为全局而非局部，当一个不需要访问变量的函数意外或恶意修改变量时，就会出现意想不到的副作用。这是最小特权原则的另一个例子- -除了真正的全局资源，如cin和cout，全局变量应该避免。一般来说，变量应该在其需要访问的最窄范围内进行声明**。仅在特定函数中使用的变量应声明为该函数中的局部变量而不是全局变量。

函数原型中的参数，其作用域始于左括号，终于右括号

```cpp
double area(double radius);//radius的作用域仅在于括号内，不能用于程序正文以及其他地方
```

类的成员具有类作用域，其范围包括类体和非内联成员函数的函数体。

如果在类作用域以外访问类的成员，要通过类名(访问静态成员)，或者该类的对象名、对象引用、对象指针(访问非静态成员)。

### 5.7 函数调用栈和激活记录

#### 5.7.1 栈

pushing---进栈   popping---出栈

栈是后人先出结构(last-in, first-out (LIFO) data structures)，即最后一个进栈的会最先出栈。

函数调用栈(function-call stack)，有时也称为程序执行栈，和数据结构意义上的“栈”不同。

栈帧(Stack Frames)

每次函数调用其他函数，一条记录就会放入栈中，这条记录，就叫做栈帧或者活动记录(activation record)，包含被调用函数为了返回调用函数所需要的返回地址。如果被调用的函数返回而不是在返回之前调用另一个函数，则弹出函数调用的堆栈帧，控制转移到弹出堆栈帧中的返回地址。If the called function returns instead of calling another function before returning, the stack frame for the function call is popped, and control transfers to the return address in the popped stack frame.

调用栈的美妙之处在于，每个被调用的函数总是在调用栈的顶端找到它需要返回给它的调用者的信息。并且，如果一个函数对另一个函数进行了调用，新函数调用的栈帧就被简单地推到了调用栈上。这样，新被调用函数返回其调用者所需的返回地址就位于栈的顶端。

函数在执行过程中需要存在非静态的局部变量。如果函数调用其他函数，它们需要保持活动状态。但是当一个被调用函数返回到它的调用者时，被调用函数的非静态局部变量需要"离开"。被调用函数的堆栈框架是为被调用函数的非静态局部变量预留内存的绝佳场所。只要被调用的函数是活动的，该栈帧就存在。当该函数返回而不再需要它的非静态局部变量时，它的堆栈框架从堆栈中弹出，并且这些非静态局部变量不再存在。

stack overflow(栈溢出)

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230927150733200.png" alt="image-20230927150733200" style="zoom:50%;" />
</div>

```c++
#include <iostream>
using namespace std;

int square(int);

int main(){
    int a{10};
    cout << a << " squared: " <<square(a) << endl;
}

int square(int x){
    return x*x;
}
```

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230927151536894.png" alt="image-20230927151536894" style="zoom:50%;" />
</div>

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230927152131273.png" alt="image-20230927152131273" style="zoom:50%;" />
</div>

### 5.8 内联函数(inline functions)

从软件工程的观点来看，将程序作为一组函数来实现是很好的，但是函数调用涉及执行时间开销。C++提供内联函数来帮助减少函数调用开销。

**将限定符置于函数定义中函数的返回类型之前，建议编译器在函数调用的每个地方(适当的时候)生成函数体代码的副本，以避免函数调用。**这往往会使程序变大。编译器可以忽略内联限定符，一般对除最小函数外的所有函数都这样做。可重复使用的内联函数通常放置在头文件中，因此它们的定义可以包含在每个使用它们的源文件中。

如果一个函数是内联的，那么在编译时，编译器会把该函数的代码副本放置在每个调用该函数的地方。对内联函数进行任何修改，都需要重新编译函数的所有客户端，因为编译器需要重新更换一次所有的代码，否则将会继续使用旧的函数。如果想把一个函数定义为内联函数，则需要在函数名前面放置关键字 **inline**，在调用函数之前需要对函数进行定义。

**内联函数的声明和定义一般不分开(也可以分开，具体参见如下链接)**[c++ - Is possible to separate declaration and definition of inline functions? - Stack Overflow](https://stackoverflow.com/questions/11428147/is-possible-to-separate-declaration-and-definition-of-inline-functions)

**对内联函数不能进行异常接口说明**

**内联函数的定义必须出现在内联函数第一次被调用之前。**

**如果已定义的函数多于一行，编译器会忽略 inline 限定符**。

inline只适合函数体内代码简单的函数使用，不能包含复杂的结构控制语句例如while、switch，并且内联函数本身不能是直接递归函数(自己内部还调用自己的函数)。

以下情况不宜使用内联：

（1）如果函数体内的代码比较长，使用内联将导致内存消耗代价较高。

（2）如果函数体内出现循环，那么执行函数体内代码的时间要比函数调用的开销大。

（3）内联函数不能递归。

```c++
#include <iostream>
using namespace std;

inline double cube(const double side){
   return side*side*side;
}

int main(){
    double sideValue;
    cout<<"Enter the side length of your cube: ";
    cin >> sideValue;
    
    cout<<"Volume of cube with side "
    <<sideValue<<" is "<<cube(sideValue)<<endl;
}
```

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231022211505274.png" alt="image-20231022211505274" style="zoom:50%;" />
</div>
当函数在类的声明中实现，它自动成为内联函数。

```cpp
class A{
public:
    A()=default;
    double f1(){
        //do something
    }
    double f2();
};

double A::f2(){
    //do something
}
//f1就变成了内联函数
//f2不是内联函数
```



### 5.9 函数默认参数

某些函数有这样一种形参， 在函数的很多次调用中它们都被赋予一个相同的值， 我们把这个反复出现的值称为函数的默认实参。

**当程序在函数调用时，省略形参的默认实参，编译器会重写函数调用并向那个实参插入默认值**。

```c++
#include <iostream>
using namespace std;

unsigned int boxVolume(unsigned int length=1,unsigned int width=1,unsigned int height=1);

int main() {
    cout<<"The default box volume is: "<<boxVolume();

    cout<<"\n\nThe volume of a box with length 10,\n"
    <<"width 1 and height 1 is: "<<boxVolume(10);

    cout<<"\n\nThe volume of a box with length 10,\n"
    <<"width 5 and height 2 is: "<<boxVolume(10,5,2)<<endl;
}

unsigned int boxVolume(unsigned int length,unsigned int width,unsigned int height){
    return length*width*height;
}
```

在上述代码中，函数的原型指明三个形参都有默认值1。第一次调用boxVolum函数，没有指定实参，所以使用的是三个默认值1。第二次调用只传递了一个length实参，所以width和height仍然使用的默认实参1。最后一次调用，传入了三个实参，就不要默认实参了。

**任何显式传递给函数的实参均从左至右赋值给函数的形参**。

默认实参必须是函数形参列表最右边的实参。当调用的函数有两个或者多个默认实参，如果一个遗漏的实参不是最右边的实参，那么所有的实参都必须被省略。默认实参必须在函数名称首次出现时指明---典型的，在函数原型中。如果函数原型遗漏了，那么默认实参应该在函数头中指明。默认值可以是任意表达式，包括常量，全局变量或者函数调用。默认实参也可以在内联函数中使用。

```cpp
定义时应当注意：参数列表中默认值参数应后置
void t1(int x,int y=0,int z);//错误
void t2(int x-0,inty=0,int z);//错误

void t3(int x,int y=0,int z=0);//正确
void t4(int x=0,int y=0;int z=0);//正确

调用时应当注意：参数列表中实参应前置
t3(1, ,7);//错误
t4( , ,6);//错误

t3(1);//正确，y,z使用默认值
t4(1,2);//正确，z使用默认值
```

**函数重载时，不允许重定义默认参数。**

```
#include <iostream>
using namespace std;

void printArea(double radius=1.0){
    cout<<radius*2<<endl;
}

void printArea(int radius=2){
    cout<<radius*radius<<endl;
}

int main() {

    printArea();
    printArea(4);

    return 0;
}

```

![image-20240407161009177](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240407161009177.png)

### 5.10 一元作用域解析运算符(::)

**当一个同名的局部变量在作用域时，C++提供一元作用域解析运算符(::)来访问全局变量。**   一元作用域解析运算符不能用于访问外部块中同名的局部变量。如果一个全局变量的名字与一个局部变量的名字在范围上不相同，则可以直接访问一个全局变量，而不需要一元作用域解析运算符。

```c++
#include <iostream> 
using namespace std;
int number{7};
int main() {
    double number{10.5};
    cout << "Local double value of number = "
         <<number
         << "\nGlobal int value of number = "
         <<::number<<endl;
}
```

![image-20240407153543910](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240407153543910.png)

第二个作用是在类外定义函数，例如：

```cpp
#include<iostream>  
using namespace std; 
 
class A  
{ 
public:  
 
   // Only declaration 
   void fun(); 
}; 
 
// Definition outside class using :: 
void A::fun() 
{ 
   cout << "fun() called"; 
} 
 
int main() 
{ 
   A a; 
   a.fun(); 
   return 0; 
} 
```

第三个作用是访问类的静态变量，参照本文档的8.14节

第四个作用是：**如果有多个继承：**如果两个祖先类中存在相同的变量名，则可以使用作用域运算符进行区分。例如：

```cpp
// Use of scope resolution operator in multiple inheritance. 
#include<iostream> 
using namespace std; 
 
class A 
{ 
protected: 
    int x; 
public: 
    A() { x = 10; } 
}; 
 
class B 
{ 
protected: 
    int x; 
public: 
    B() { x = 20; } 
}; 
 
class C: public A, public B 
{ 
public: 
   void fun() 
   { 
      cout << "A's x is " << A::x; 
      cout << "\nB's x is " << B::x; 
   } 
}; 
 
int main() 
{ 
    C c; 
    c.fun(); 
    return 0; 
}
```

第五个作用是：**对于命名空间**：如果两个命名空间中都存在一个具有相同名称的类，则可以将名称空间名称与作用域解析运算符一起使用，以引用该类而不会发生任何冲突

```cpp
#include<iostream> 
int main(){ 
    std::cout << "Hello" << std::endl;
} 
```

在这里，cout和endl属于std命名空间。具体参照本文的8.14.5

第六个作用是：**在另一个类中引用一个类：**如果另一个类中存在一个类，我们可以使用嵌套类使用作用域运算符来引用嵌套的类。

```cpp
#include<iostream> 
using namespace std; 
 
class outside 
{ 
public: 
      int x; 
      class inside 
      { 
      public: 
            int x; 
            static int y;  
            int foo(); 
 
      }; 
}; 
int outside::inside::y = 5;  
 
int main(){ 
    outside A; 
    outside::inside B; 
 
} 
```



### 5.11 重载函数(Overloading Functions)

**C++允许多个相同名称的函数被定义，只要它们具有不同的特征。这就叫做函数重载。**

**C++通过验证引用的实参的数量、数据类型和顺序来选择合适的函数调用。**函数重载被用来生成多个执行相似任务、具有相同名字的函数，但数据类型不同。

```c++
#include <iostream>
using namespace std;

int square(int x){
    cout<<"square of integer "<<x<<"is";
    return x*x;
}

double square(double y){
    cout<<"square of double "<<y<<"is";
    return y*y;
}

int main(){
    cout<<square(7);
    cout<<endl;
    cout<<square(7.5);
    cout<<endl;
}
```

重载函数通过他们的特征来区分，特征(signatures)是函数的名字和形参类型(按顺序)的结合。编译器需要为C++中的所有函数，在符号表中生成唯一的标识符，来区分不同的函数。而对于同名不同参的函数，编译器在进行`name mangling`操作时，会通过函数名和其参数类型生成唯一标识符，来支持函数重载，以实现类型安全的联结属性(type-safe linkage)。类型安全的联结属性保证了合适的重载函数被调用，并且实参的类型和形参的类型一致。

注意：`name mangling` 后得到的函数标识符与返回值类型是无关的，因此函数重载与返回值类型无关。

- 函数的参数个数、参数类型、参数顺序不同三者中满足其中一个，就是函数重载了
- 如果只有函数返回值不同，不是函数重载；返回值不同，参数也不同的时候，可以作为函数重载

函数的重载的规则：

* 函数名称必须相同。
* 参数列表必须不同（个数不同、类型不同、参数排列顺序不同等）。
* 函数的返回类型可以相同也可以不相同。
* **仅仅返回类型不同不足以成为函数的重载。**
* 如果重载函数有默认参数，调用函数时，可能导致匹配失败
* const不能作为函数重载的特征

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230928161659440.png" alt="image-20230928161659440" style="zoom:50%;" />
</div>

上述代码就显示了编译器以汇编语言生成的函数名(mangled function names)。对于GNU C++ 每个mangled name(main函数除外)都以两个下划线开始，后面跟字母Z、一个数字和函数的名字，Z后面的数字指明函数名包括多少个字符。例如square函数的形参为int类型，就在square后加i。**在nothing1中，形参类型分别为int、float、char和int**​ **&amp;**​  **,所以nothing后加ifcRi。**

重载函数可以有不同的返回类型，但是如果返回类型不同，他们必须有不同的形参列表。

### 5.12 函数模板(function templates)

重载函数通常用于在不同数据类型上执行涉及**不同程序逻辑的类似操作**。**如果每种数据类型的程序逻辑和操作完全相同，使用函数模板可以更紧凑、方便地执行重载操作。**   编写了以一个函数的模板定义，C + +根据对该函数调用提供的参数类型，自动生成单独的函数模板特殊化(function template specializations)，以妥善处理每种类型的调用。因此，定义一个函数模板本质上是定义了一整族重载函数。

**C++提供了模板(template)编程的概念。所谓模板，实际上是建立一个通用函数或类，其类内部的类型和函数的形参类型不具体指定，用一个虚拟的类型来代表。这种通用的方式称为模板。**

在 C++ 中，模板分为函数模板和类模板两种。函数模板是用于生成函数的，类模板则是用于生成类的。

函数模板的写法如下：

```cpp
template <typename 类型参数1, typename 类型参数2, ...>
返回值类型  模板名(形参表)
{
    函数体
}
```

函数模板看上去就像一个函数。

例如对于交换多种类型的值的函数，可以编写函数模板如下：

```cpp
template <typename T>
void Swap(T & x, T & y)
{
    T tmp = x;
    x = y;
    y = tmp;
}
```

上述代码形参列表中的形参不能改成不带引用的形式：

```cpp
void Swap(T x,T y)
```

上述形式的代码不能实现两个数值的交换，因为在将实参传递给形参后，是形参进行的数值交换，main函数体内的实参并没有进行数值交换。所以要使用引用。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231208111923867.png" alt="image-20231208111923867" style="zoom:80%;" />

同一个类型参数只能替换为同一种类型。编译器在编译到调用函数模板的语句时，会根据实参的类型判断该如何替换模板中的类型参数。

所有的模板定义都以关键词template开始(第一行)，后面跟模板形参列表。每个模板形参列表内的形参都在前面加上关键词typename或者class(在此种情形下，两者等价)。template parameters有三种类型：
1）Type parameters（类型参数）：
2）Nontype parameters（非类型参数）：
3）template template parameters（双重模板参数）

类型参数是基本类型或用户自定义类型的占位符。占位符就是先占住一个固定的位置，等着你再往里面添加内容的符号，广泛用于计算机中各类文档的编辑。格式占位符(%)是在C/C++语言中格式输入函数，如 scanf、printf 等函数中使用。其意义就是起到格式占位的意思，表示在该位置有输入或者输出。

这些占位符，例如T，被用来指定函数形参的类型(例如第二行)和指定函数的返回类型(第二行),还有在函数体内声明变量(第三行)。一个函数模板的定义就像函数的定义一样，只是使用类型参数作为实际数据类型的占位符。

```cpp
template<typename T>
T maximum(T value1,T value2,T value3){
    T maximumValue{value1};

    if(value2>maximumValue){
        maximumValue=value2;
    }

    if(value3>maximumValue){
        maximumValue=value3;
    }

    return maximumValue;
}
```

函数模板在第一行声明了单个类型参数T作为函数maximum待测数据类型的占位符。对于特定的模板定义，类型参数的名称必须在模板形参列表中唯一。**当编译器在程序源代码中检测到maximum调用时，在整个模板定义中将maximum调用中的实参类型替换成T，C++创建了一个完整的函数，用于确定指定类型的3个值中的最大值- -这3个值必须具有相同的类型，因为在本例中我们只使用了一个类型参数。**    然后对新创建的函数进行编译- -**模板是代码生成的一种手段**。

```c++
#include <iostream>
#include "maximum.h"
using namespace std;

int main(){
    cout<<"input three integer values: ";
    int int1,int2,int3;
    cin>>int1>>int2>int3;
    cout<<"the maximum integer value is: "
    <<maximum(int1,int2,int3);

    cout << "\n\nInput three double values: ";
    double double1, double2, double3;
    cin >> double1 >> double2 >> double3;
    cout << "The maximum double value is: "
    <<maximum(double1, double2, double3);

    cout<<"\n\nInput three characters: ";
    char char1, char2, char3;
    cin >> char1 >> char2 >> char3;
    cout << "The maximum character value is: "
    << maximum(char1, char2, char3)<< endl;
}
```

为type int创建的函数模板特殊化将T的每个出现替换为int如下：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20230929214445061.png" alt="image-20230929214445061" style="zoom:50%;" />
</div>

函数模板不是函数，写了函数模板，但不在任何地方使用它(也不显式实例化)，则编译器不会为该函数模板生成任何代码。函数模板实例化分为隐式实例化和显式实例化。

#### 5.12.1 隐式实例化

仍以 swap 为例，我们在main 中调用 swap(a,b)时，就发生了隐式实例化。当函数模板被调用，且在之前没有显式实例化时，即发生函数模板的隐式实例化。如果模板实参能从调用的语境中推导，则不需要提供。效率较低。

```cpp
//template2.cpp #include
template void print(const T &r) {
std::cout << r << std::endl;
}
int main() {
// 隐式实例化print(int) print(1);
// 实例化 print(char) print<>('c');
// 仍然是隐式实例化，我们希望编译器生成print(double) print(1);
return 0;
}
```



### 5.13递归(recursion)

**对于一些问题，函数调用自身是有用的。递归函数是一个可以直接或间接调用自身的函数(通过另一个函数)。C++标准文件指出，在程序中不应该调用main函数，也不应该递归调用main函数。它的唯一目的是作为程序执行的起点**。该函数只知道如何求解最简单的情况(simplest case)，或所谓的基本情况(base case)。如果以base case调用该函数，该函数返回一个结果。如果函数被更复杂的问题调用，它通常将问题分为两个概念部分- -函数知道如何做的部分和它不知道如何做的部分。为了使递归可行，后一部分问题必须与原问题相似，不过是略微简单或更小的版本。这个新问题看起来像原来的问题，所以函数调用自身的一个副本来工作在更小的问题上- -这被称为递归调用，也被称为递归步骤。递归步骤通常包括关键字return，因为它的结果会与函数知道如何解决的部分问题相结合，形成结果传回原调用者，可能是main。

递归步骤在执行时，对函数的原始调用仍然是"开放的"，即还没有执行完毕。递归步骤可以导致更多的递归调用，因为函数不断地将每个新的子问题划分为两个概念部分。**为了使递归最终终止，每次函数调用自身与原问题稍微简单的版本，这个越来越小的问题序列最终必须收敛于base case。此时，函数识别出base case并返回一个结果到函数的前一个副本，然后一系列的返回沿着这个行进行，直到原始的调用最终返回最终的结果给main。**

#### 5.13.1阶乘

```c++
#include <iostream>
#include <iomanip>

using namespace std;
unsigned long factorial(unsigned long);

int main() {
    for(unsigned int counter{0};counter<=10;++counter){
        cout<<setw(2)<<counter<<"!="<<factorial(counter)<<endl;
    }
}

unsigned long factorial(unsigned long number){
    if(number<=1){
        return 1;
    }
    else{
        return number* factorial(number-1);
    }
}
```

factorial函数的形参类型为unsigned long，返回结果的类型为unsigne long，这是unsigned long int的简写。C++标准规定unsigned long int 的长度至少要和int一样。一般的，unsigned long int在计算机内存储为四个字节。

### 5.14 使用递归的例子：斐波那契数列

C++只规定了4种操作符的求值顺序--&&，||，逗号(,)和（？:）。

### 5.15 递归VS.迭代

1.迭代和递归都是基于一个控制语句：迭代使用一个迭代语句；递归使用了一个选择语句。

2.迭代和递归都涉及迭代：迭代显式地使用一个迭代语句；递归通过重复的函数调用实现迭代。

3.迭代和递归各自涉及一个终止测试：当循环继续条件失败时，迭代终止；递归在识别base case时终止。

4.counter控制的迭代和递归每次逐渐接近终止：迭代修改counter，直到counter假设一个值使得循环连续条件失败；递归产生原始问题的更简单的版本，直到达到base case。

5.迭代和递归都可以无限地发生：如果循环延续性测试从未变得错误，则随着迭代的进行会出现一个无限的循环；如果递归步骤在每次递归调用过程中没有以收敛于base case的方式减少问题，则会发生无限递归。

```c++
#include <iostream>
#include <iomanip>
using namespace std;

unsigned long factorial(unsigned int);

int main() {
    for(unsigned int counter{0};counter<=10;++counter){
        cout<<setw(2)<<counter<<"!="<<factorial(counter)
        <<endl;
    }
}

unsigned long factorial(unsigned int number){
    unsigned long result{1};

    for(unsigned int i{number};i>=1;--i){
        result*=i;
    }
    return result;
}
```

上述代码使用迭代的方法实现了斐波那契数列。

#### 5.15.1递归的负面效果

递归具有负面效应。它反复调用函数的机制，进而调用函数的开销。这在处理器时间和内存空间上都可能是昂贵的。每一次递归调用都会导致函数变量的另一个副本被创建；这会消耗相当大的内存。迭代通常发生在函数内部，因此省略了重复函数调用和额外内存分配的开销。

仍然选择递归的原因是**任何可以递归求解的问题也可以迭代求解(非递归)。当递归方法更自然地反映问题并产生更易于理解和调试的程序时，通常选择递归方法。选择递归解的另一个原因是，当递归为解时，迭代解可能不明显。**

### 5.16 round函数

使用round函数解决四舍五入问题比较简单。

在C++中，round()函数是[标准库](https://so.csdn.net/so/search?q=%E6%A0%87%E5%87%86%E5%BA%93&spm=1001.2101.3001.7020) 中的一个函数，用于对浮点数进行四舍五入。
函数原型为：

```cpp
double round(double x);
```

参数x是一个双精度浮点数。
round()函数将返回最接近参数x的整数。如果x正好在两个整数中间，则向远离零的整数方向取整。例如：

```cpp
#include <iostream>
#include <cmath>

int main() {
    double num1 = 2.5;
    double num2 = 2.3;
    std::cout << "round(2.3) is: " << round(num1) << std::endl;  // 输出 "round(2.3) is: 2"
    std::cout << "round(2.3) is: " << round(num2) << std::endl;  // 输出 "round(-2.3) is: -2"
    return 0;
}
```

![image](assets/image-20231120155332-aihtbjt.png)​

### 5.17 函数的参数

1.在函数被调用时才分配形参的存储单元

2.实参可以是常量、变量或表达式、

3.实参类型必须与形参相符或可以隐式转换为形参类型

4.值传递是传递参数值，即单向传递

5.引用传递可以实现双向传递

6.常引用(const)作参数可以保障实参数据的安全

**当函数执行完毕，在函数体内定义的变量，全部都被释放了。引用在定义时必须初始化，但是在函数的形参中使用引用并不会进行初始化。这是因为引用在定义时必须初始化，是在为引用分配内存时，必须进行初始化，但函数的形参，系统并不会为他分配内存，所以就不需要初始化。**

#### 5.17.1 可变数量形参

使用模板类initializer_list<T>可以向函数传递同类型不定个数参数，例如：

```cpp
void log_info(initializer_list<string> lst) {
	for(auto &info: lst){
		cout<<info<<' ';
	}
	cout<<endl;
}
log_info({"hello","world","!"});
```

### 5.18 对象作为函数参数和返回值

#### 5.18.1 作为参数

对象作为函数参数，可以按值传递，也可以按引用传递。

```cpp
//按值传递
void print(Circle c){
    //do something
}

int main(){
    Circle myCircle{5.0};
    print(myCircle);
}
```

```cpp
//按值传递
void print(Circle& c){
    //do something
}

int main(){
    Circle myCircle{5.0};
    print(myCircle);
}
```

```cpp
//按值传递
void print(Circle* c){
    //do something
}

int main(){
    Circle myCircle{5.0};
    print(&myCircle);
}
```

#### 5.18.2 作为函数返回值

形式如下：

```cpp
Object f(函数形参){
    //do something
    return Object(args);
}

// main(){
	Object o=f;
}

```



## 6. 类-数组(array)和string

### 6.1 数组

数组是一组连续的内存位置，它们都具有相同的类型。为了指代数组中的特定位置或元素，我们指定数组的名称和特定元素在数组中的位置编号。数组名称遵循与其他变量名相同的约定。

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231001165145398.png" alt="image-20231001165145398" style="zoom:50%;" />
</div>

下标必须是整数或整数表达式，带下标的数组名是一个左值，它可以在赋值的左边使用，就像非数组变量名一样。通过调用函数可以知道数组的长度，例如c.size()。包含下标的括号实际上是一个操作符，它与用于调用函数的括号具有相同的优先级。

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231001171333171.png" alt="image-20231001171333171" style="zoom:50%;" />
</div>
### 6.2 声明array

数组在内存中占据空间，使用声明的形式来指定数组所需的元素类型和元素个数。数组和向量都是类模板。使用数组必须使用头文件\<array>

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231001171554957.png" alt="image-20231001171554957" style="zoom:50%;" />
</div>

例如：<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231001171714336.png" alt="image-20231001171714336" style="zoom:50%;" />

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231210132356537.png" alt="image-20231210132356537" style="zoom:80%;" />

```cpp
array<type,arraySize> arrayName{值1,值2,...};
```

#### 6.2.1 C++17关于array的新特性

C++17引入了一种新特性，对类模板的参数进行推导，例如：

```cpp
std::array a1{1,4,6};
std::array a2{'w','b','o'};
```

### 6.3 使用数组的例子

#### 6.3.1 声明数组并使用循环初始化数组的元素

size_t是一种数据相关的无符号整数类型，它被设计得足够大以便能够内存中任意对象的大小。size_t由来: 在C++中，设计 size_t 就是为了适应多个平台的 。size_t的引入增强了程序在不同平台上的可移植性。在需要通过数组下标来访问数组时，通常建议将下标定义size_t类型，因为一般来说在进行下标访问时，下标都是正的。这种类型对于任何表示数组大小或数组下标的变量都是推荐的。头文件为\<cstddef>。此头文件包含在各种其他的头文件中，如果程序出现错误，说size_t未定义，只需要在程序中加上#include\<cstddef>

```c++
#include <iostream>
#include <iomanip>
#include <array>
using namespace std;

int main(){
    array<int,5> n;
    for(size_t i{0};i<n.size();++i){
        n[i]=0;
    }
    cout<<"element"<<setw(10)<<"value"<<endl;

    for(size_t j{0};j<n.size();++j){
        cout<<setw(7)<<j<<setw(10)<<n[j]<<endl;
    }
}
```

上诉代码将数组初始化并将数组内元素打印出来。

#### 6.3.2 在声明里通过初始化列表初始化数组

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231001180540167.png" alt="image-20231001180540167" style="zoom:50%;" />
</div>

如果初始化列表内的元素个数小于数组长度，剩余的元素会被初始化为0。如果大于数组长度，则是错误。

#### 6.3.3 用常量设定数组的大小并通过计算设置数组元素

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231001194743972.png" alt="image-20231001194743972" style="zoom:50%;" />
</div>

第10行使用const限定符声明一个常量变量数组Size，其值为5。常量变量(Constant variables)也被称为命名常量(named constants)或只读变量(read-only variables)。**一个常量变量在声明时必须初始化**，此后不能修改。尝试将arraySize初始化后进行修改，会出现错误。

#### 6.3.4 数组元素的和

```c++
#include <iostream>
#include <array>
using namespace std;

int main() {
    const size_t arraySize{4};
    array<int,arraySize> a{10,20,30,40};
    int total{0};

    for(size_t i{0};i<a.size();i++){
        total+=a[i];
    }

    cout<<"total of array elements is: "<<total<<endl;
}
```

上诉代码计算数组元素的和。

#### 6.3.8 Static Local arrays and Automatic Local arrays

程序在首次遇到静态局部数组的声明时，对其进行初始化。如果你没有显式地初始化一个静态数组，那么在创建该数组时，编译器会将该数组的每个元素初始化为零。C + +对其他局部变量不执行这样的默认初始化。

局部变量有时被称为自动变量，因为当函数执行完毕时，局部变量会被自动销毁。

```c++
#include <iostream>
#include <array>
using namespace std;

void staticArrayInit();
void automaticArrayInit();
const size_t arraySize{3};

int main() {
    cout<<"first call to each function:\n";
    staticArrayInit();
    automaticArrayInit();

    cout<<"\n\nSecond call to each function:\n";
    staticArrayInit();
    automaticArrayInit();
    cout<<endl;
}

void staticArrayInit(){
    static array<int,arraySize> array1;
    cout<<"\nValues on entering staticArrayInit:\n";

    for(size_t i{0};i<array1.size();++i){
        cout<<"array1["<<i<<"]="<<array1[i]<<" ";
    }

    cout<<"\nValues on exiting staticArrayInit:\n";

    for(size_t j{0};j<array1.size();++j){
        cout<<"array1["<<j<<"]="<<(array1[j]+=5)<<" ";
    }
}

void automaticArrayInit(){
    array<int, arraySize> array2{1, 2, 3};
    cout << "\n\nValues on entering automaticArrayInit:\n";

    for (size_t i{0}; i < array2.size(); ++i) {
        cout << "array2[" << i << "] = " << array2[i] << " ";
    }
    cout << "\nValues on exiting automaticArrayInit:\n";

    for (size_t j{0}; j < array2.size(); ++j) {
        cout << "array2[" << j << "] = " << (array2[j] += 5) << " ";
    }
}
```

如前所述，static数组的值，在函数执行一次后，值不会销毁。

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231004112420215.png" alt="image-20231004112420215" style="zoom:50%;" />
</div>

### 6.4 基于范围的for循环(range based for statement)

如前所述，对数组中的所有元素进行处理是很常见的。基于范围的for循环允许您在不使用counter的情况下执行此操作，从而避免了"跳出"数组的可能性，也无需您执行自己的边界检查。

```c++
#include <iostream>
#include <array>
using namespace std;

int main() {
   array<int,5> items{1,2,3,4,5};
   cout<<"items before modification: ";

   for(int item:items){
       cout<<item<<" ";
   }

   for(int& itemRef: items){
       itemRef*=2;
   }

   cout<<"\nitems after modification: ";
   for(int item:items){
       cout<<item<<" ";
   }

   cout<<endl;
}
```

```c++
 for(int item:items){
       cout<<item<<" ";
   }
```

可以与如下的代码执行的功能一样：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231004113420642.png" alt="image-20231004113420642" style="zoom:50%;" />
</div>

基于范围的for语句简化了通过数组进行迭代的代码。上诉第二个代码块的for循环，可以讲是：对于每一次迭代，将items的下一个元素的值赋给int类型的变量item，然后执行循环。因此，对于每次迭代，item都代表items的一个值(不是下标)。在基于范围的for的函数头中，在冒号(：)的左边声明一个所谓的范围变量，并在右边指定一个数组的名称。**You can use the range-based for statement with most of the C++ Standard Library’s prebuilt data structures (commonly called containers).**

当通过数组的代码在循环时不需要访问元素的下标时，可以使用基于范围的for语句代替counter控制的for语句。l例如，计算数组中所有元素的和，就不需要数组下标。**但是，如果一个程序由于某种原因必须使用下标，而不是简单地通过数组(例如,在每个数组元素值的旁边打印一个下标数字,如本章前面的例子)循环，则应该使用counter进行for语句控制。**

### 6.6 数组的排序和查找

```c++
#include <iostream>
#include <iomanip>
#include <array>
#include <string>
#include <algorithm>
using namespace std;

int main() {
    const size_t arraySize{5};
    array<string,arraySize> colors{"red","orange","yellow","blue","green"};
    cout<<"unsorted array\n";
    for(string color:colors){
        cout<<color<<" ";
    }
    sort(colors.begin(),colors.end());
    cout<<"sorted array:\n";
    for(string item:colors){
        cout<<item<<" ";
    }
    bool found{binary_search(colors.begin(),colors.end(),"indigo")};
    cout<<"\n\n\"indigo\" "<<(found? "was":"was not")
    <<"found in colors"<<endl;

    found= binary_search(colors.begin(),colors.end(),"cyan");
    cout<<"\"cyan\" "<<(found?"was":"was not")
    <<"found in colors"<<endl;
}
```

使用binary_search函数，首先必须对一组元素进行升值排序。函数的前两个实参表明寻找的范围，最后一个实参表示要寻找的元素。返回一个bool值指出是否寻找到此元素。

### 6.7 多维数组

二维数组的声明：

```cpp
array<array<int,3>,3> a;
```



```c++
#include <iostream>
#include <array>
using namespace std;

const size_t rows{2};
const size_t columns{3};
void printArray(const array<array<int,columns>,rows>&);

int main(){
    array<array<int,columns>,rows> array1{1,2,3,4,5,6};
    array<array<int,columns>,rows> array2{1,2,3,4,};

    cout<<"values in array1 by row are: "<<endl;
    printArray(array1);

    cout<<"\nvalues in array2 by row are: "<<endl;
    printArray(array2);
}

void printArray(const array<array<int,columns>,rows>& a){
    for(auto const& row:a){
        for(auto const& element:row){
            cout<<element<<' ';
        }
        cout<<endl;
    }
}
```

为了处理二维数组的元素，我们使用了一个嵌套循环，其中外循环通过行进行迭代，内循环通过给定行的列进行迭代。如上诉代码21-22行所示。

上诉的嵌套循环代码可以替换为如下的形式：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231008160913427.png" alt="image-20231008160913427" style="zoom:50%;" />
</div>

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231008160941572.png" alt="image-20231008160941572" style="zoom:50%;" />
</div>

上诉代码可以求得二维数组所有元素的总和。

二维数组的声明如下所示：

```c++
array<array<int,columns>,rows> array1{1,2,3,4,5,6};
```

columns表示二位数组的列数，rows代表二位数组的行数。

对二维数组使用size函数，返回的是数组的行数。例如：a.size()返回数值2。

### 6.8 C++字符串类(string)

C++中使用string类处理字符串。操作string对象中的字符串时，有时会用到"index".

创建string对象：

1.用无参构造函数创建一个空字串

```cpp
string newString;
```

2.由一个字符串常量或字符串数组创建string对象

```cpp
string message{"aloha world"};//

char charArr[]={'h','e','l','l','o'};
string message1{charArr};//
```

string的成员函数可以参见[std::basic_string - cppreference.com](https://en.cppreference.com/w/cpp/string/basic_string)

![image-20240412145727164](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240412145727164.png)



### 6.9 C++17 结构化绑定(structured binding)

结构化绑定声明是一个声明语句，意味着声明了一些标识符并对标识符做了初始化，在C++17标准中引入。

将指定的一些名字绑定到初始化器的子对象或者元素上。

```cpp
cv-auto &/&& [标识符列表]= 表达式；
cv-auto &/&& [标识符列表] {表达式}；
cv-auto &/&& [标识符列表] (表达式);
```

cv-auto:可能由const/volatile修饰的auto关键字

&/&& ：左值引用或者右值引用

标识符列表：逗号分隔的标识符

#### 6.9.1 用于原生数组的结构化绑定声明

若初始化表达式为数组类型，则标识符列表中的名字绑定到数组元素。

1.标识符数量必须等于数组元素数量

2.标识符类型与数组元素类型一致

```cpp
int main(){
    int priArr[] {42,21,7};
    
    auto [a1,a2,a3]=priArr;//a1是priArr[0]的拷贝，a2,a3类推
    const auto [b1,b2,b3] (priArr);//b1是priArr[0]的只读拷贝，b2,b3类推
    auto &[c1,c2,c3] {priArr};//c1是priArr[0]的引用，c2,c3类推
    c3=14;//priArr[2]的值变为14
    return 0;
}
```

#### 6.9.2 用于std::array的结构化绑定声明

若初始化表达式为数组类型，则标识符列表中的名字绑定到数组元素。

1.标识符数量必须等于array中的元素数量

2.标识符类型与array中的元素类型一致

```cpp
int main(){
	std::array stdArr={'a','b','c'};//C++17
    auto [d1,d2,d3]{stdArr};
    return 0;
}
```

#### 6.9.3 用于对象数据成员的结构化绑定

若初始化表达式为类/结构体类型，则标识符列表中的名字绑定到类/结构体的**非静态数据成员**上

1)       数据成员必须为公有成员

2)       标识符数量必须等于数据成员的数量

3)       标识符类型与数据成员类型一致

```cpp
class C {  // 可以改用 struct C，然后去掉下面的public属性说明
public:
    int i { 420 }; // 就地初始化
    char ca[ 3 ] { 'O', 'K', '!' };
};

int main() {
    C c;
    auto [a1, a2] {c}; // a1是int类型，a2是char[]类型
    std::cout << "c.i:" << a1 << " c.ca:" << b2 << std::endl;
}
```

 


auto后跟&，则标识符是数据成员的引用

auto前可放置const，表明标识符是只读的

```cpp
int main() {
  C c; // c.i: 420;  c.ca: 'O','K','!'
  auto [a1, a2] {c}; // a1是c.i的拷贝，a2是char[]类型
  auto& [b1, b2] {c}; // b1是int&类型，是c.i的引用，
// b2是char(&)[3]类型(数组的引用)，是c.ca的引用
  a1 = 100;
  std::cout << "c.i:" << c.i << std::endl; // 输出420，改a1不影响c.i
  b1 = 200;
  std::cout << "c.i:" << c.i << std::endl; // 输出200，通过b1修改了c.i
}
```









## 7.指针

指针也允许pass-by-reference，并且可以用来创造和操作动态数据结构，例如列表、队列、栈和树(lists, queues, stacks and trees)。

### 7.1 指针变量的声明和初始化

指针变量包含内存地址作为其值，**指针包含变量的内存地址，而变量的内存地址又包含一个特定的值。在这个意义上，变量名直接引用一个值，指针间接引用一个值。通过指针引用一个值称为间接引用。**   例如下图指针变量的间接引用以及count的直接引用。

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231011123244375.png" alt="image-20231011123244375" style="zoom:50%;" />
</div>

### 7.2 声明指针

指针就像其他变量一样，在使用之前必须先声明，例如上图中的指针，可以声明为：

```c++
int* countPtr, count;
```

指针可以被声明指向任何数据类型的对象。

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231011124314175.png" alt="image-20231011124314175" style="zoom:50%;" />
</div>

上诉代码，指针的类型为int*,指针变量的名字为countPtr,可以存放一个int类型数据的地址。

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231013095546619.png" alt="image-20231013095546619" style="zoom:50%;" />
</div>
void类型的指针只能用来存放地址，不能用此指针访问内存空间。

#### 7.2.1 初始化指针

**无论是在声明时还是在赋值时，都需要将指针初始化为nullptr或内存地址。**    具有nullptr的指针"point to nothing",被称为空指针(null pointer).**初始化所有指针，防止指向未知或未初始化的内存区域。**    将指针初始化为NULL或者0是相同的操作，0是唯一的可以直接赋值给指针的整数，而不用事先将整数类型转化为指针类型(一般使用reinterpret_cast)

### 7.3 指针操作符

#### 7.3.1 取地址操作符(&)

&是一元操作符，用来取得操作数的地址，例如下列代码：

```c++
int y{5}; // declare variable y 
int* yPtr{nullptr}; // declare pointer variable yPtr
yPtr = &y; // assign address of y to yPt
```

上述代码将变量y的内存地址通过&取得，并赋值给yPtr,现在，指针yPtr间接的引用了变量y的值5。地址运算符不能应用于文字，也不能应用于导致临时值(像计算结果一样)的表达式。

#### 7.3.2 解引用操作符(*)

返回一个左值，表示其指针操作数指向的对象。例如对于上述代码，下列的两段代码的结果是相同的：

```c++
cout<<*yPtr<<endl;
```

```c++
cout<<y<<endl;
```

Using * in this manner is called dereferencing a pointer.还可以作为左值被赋值：

```c++
*yPtr=9;
```

还可以进行如下操作。

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231011134623067.png" alt="image-20231011134623067" style="zoom:50%;" />
</div>

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231011134828530.png" alt="image-20231011134828530" style="zoom:50%;" />
</div>

#### 7.3.3 使用&和*

```c++
#include <iostream>
using namespace std;
int main() {
    int a{7};
    int* aPtr=&a;

    cout<<"the address of a is:"<<&a<<"\n the value of aPtr is: "<<aPtr;
    cout<<"\n\nthe value of a is: "<<a<<"\nthe value of *aPtr is:"<<*aPtr<<endl;
}
```

#### 7.3.4 二级指针

指针(指针变量的简称)用于存放普通变量的地址，二级指针用于存放指针变量的地址。二级指针的声明格式如下：

```cpp
数据类型** 指针名
```

使用指针的目的：1.传递地址 2.存放动态分配内存的地址

在函数中，如果传递普通变量的地址，形参用指针；传递指针变量的地址，形参用二级指针。

#### 7.3.5 空指针

用0或者NULL都可以表示空指针。声明指针后，在赋值前让指针指向空，表示没有指向任何地址。C++11建议用nullptr表示空指针，也就是(void*)0。

1.如果对空指针解引用，程序会崩溃。

2.在函数中，应该有判断形象是否为空指针的代码，目的是保证程序的健壮性。

出现野指针的情况有三种：

1.指针在定义时，如果没有进行初始化，它的值是不确定的。

2.如果用指针指向了动态分配的内存，内存被释放以后，指针不会置空，但是，指向的地址已经失效。

3.指针指向的变量已经超过变量的作用域(变量的内存空间已经被收回)

避免方法：

1. 指针在定义时，如果没有可以指向的地址，就初始化为nullptr。
2. 动态分配的内存释放以后，将其置为nullptr。
3. 函数不要返回局部变量的地址。

#### 7.3.6 野指针

野指针即指针指向的不是一个有效(合法)的地址。在程序中访问野指针可能会造成程序的崩溃。

### 7.4 函数的参数传递

在C++中有三种方式将实参传递给函数：

**1.pass-by-value.(传值)**

**2.pass-by-reference with a reference argument.(传引用)**

**3.pass-by-reference with a pointer argument.(传地址)**

指针和引用一样，也可以用来修改调用者中的变量或者通过引用传递大数据对象，避免复制对象的开销。

![image-20240403163829188](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240403163829188.png)



#### 7.4.1 Pass-By-Reference with a Pointer Actually Passes the Pointer By Value

用指针通过引用传递一个变量实际上没有通过引用传递任何东西(一个指向该变量的指针被值传递并复制到函数对应的指针参数中)。被调用的函数只需解引用指针就可以访问调用者的该变量，从而完成pass-by-reference。

#### 7.4.2 三种传递方式的使用原则

1)不需要在函数中修改实参

1.如果实参很小，如C++内置的数据类型或小型结构体，则按值传递

2.如果实参是数组，则使用const指针，这是唯一的选择(无法为数组建立引用)

3.如果实参是较大的结构体 ，则使用const指针或const引用

4.数据实参是类，则使用const引用，传递类的标准方式是按引用传递

2）需要在函数中修改实参

1.如果实参是内置数据类型，则使用指针

2.如果实参是数组，则只能使用指针

3.如果实参是结构体，则使用指针或引用

4.如果实参是类，使用引用

### 7.5  built-in arrays(内置数组)

在前面的内容，介绍了array，一种固定大小的元素的列表。现在介绍另一种固定大小的数据结构built-in arrays.

#### 7.5.1声明和访问built-in arrays

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231011155531092.png" alt="image-20231011155531092" style="zoom:50%;" />
</div>

声明的格式如上，arraysize必须是大于零的整数常量。   **[ ]不会提供边界检查的功能。**

#### 7.5.2 初始化bulit-in arrays

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231011160047967.png" alt="image-20231011160047967" style="zoom:50%;" />
</div>

如果提供比元素个数更少的初始化值，剩下的元素都是值初始化的-基本数值类型设置为0，bools设置为false，指针设置为nullptr，类对象由它们的默认构造函数初始化。如果提供过多的初始化值，就会出现编译错误。

如果从带有初始化值列表的声明中省略了built-in数组的大小，则编译器将built-in数组大小调整为初始化器列表中的元素个数。

数组在内存中占用的空间是连续的。

#### 7.5.3 将数组作为参数传递给函数

数组的名字就是数组第一个元素的地址。所以arrayName就等同于&arrayName[0].因此就不需要使用&获取数组的地址从而传递给函数，可以直接传递数组的名字。

正如在之前中所看到的那样，接收到调用者中变量的指针的函数可以修改调用者中的变量。对于内置数组，这意味着被调用的函数可以修改调用者内置数组的所有元素- -除非该函数在对应的内置数组参数前加上const表示不应该修改元素。

#### 7.5.4 声明内置数组形参

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231011162004454.png" alt="image-20231011162004454" style="zoom:50%;" />
</div>

可以使用上述代码在函数头中声明内置数组。与array对象不一样，内置数组不知道自身的大小，所以函数的形参列表应该同时包括内置数组以及数组的大小。

一维内置数组用于函数的参数时，只能传递数组的地址，并且要把数组的长度也传递进去，除非数组中有最后一个元素的标志。

上述代码还可以写为如下形式：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231011164456242.png" alt="image-20231011164456242" style="zoom:50%;" />
</div>

**当声明一个内置数组形参时，为了清晰起见，使用[ ]符号而不是指针符号。**

#### 7.5.5 C++11: Standard Library Functions begin and end

sort函数也可以用在内置数组里，例如：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231011165727023.png" alt="image-20231011165727023" style="zoom:50%;" />
</div>

begin和end函数的头文件为\<iterator>。都将内置数组作为实参，并返回一个指针，该指针可用于表示C++标准库函数中需要处理的元素范围，如sort函数。

#### 7.5.6 内置数组的限制

内置数组有几个限制：

1.They cannot be compared using the relational and equality operators—you must use a loop to compare two built-in arrays element by element.

2.They cannot be assigned to one another—an array name is effectively a pointer that is const.

3.They don’t know their own size—a function that processes a built-in array typically receives both the built-in array’s name and its size as arguments.

4.They don’t provide automatic bounds checking—you must ensure that array-access expressions use subscripts that are within the built-in array’s bounds.

#### 7.5.7 Built-In Arrays Sometimes Are Required

**一些情况下，必须使用内置数组，例如处理程序的command-line arguments。**

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231011171901102.png" alt="image-20231011171901102" style="zoom:50%;" />
</div>

#### 7.5.6 清空内置数组

用memset()函数可以将内置数组的全部元素清零。(只适用于C++基本数据类型)

C 库函数 **void *memset(void *​**str, int c, size_t n)**   复制字符 **c**（一个无符号字符）到参数 **str** 所指向的字符串的前 **n** 个字符。

此函数的原型：

```cpp
void *memset(void *str, int c, size_t n)

//str -- 指向要填充的内存块。
//c -- 要被设置的值。该值以 int 形式传递，但是函数在填充内存块时是使用该值的无符号字符形式。
//n -- 要被设置为该值的字符数。
```

```cpp
#include <stdio.h>
#include <string.h>
 
int main ()
{
   char str[50];
 
   strcpy(str,"This is string.h library function");
   puts(str);
 
   memset(str,'$',7);
   puts(str);
   
   return(0);
}
```

![image](assets/image-20231127164134-voxfwbr.png)​

#### 7.5.7 复制内置数组

C 库函数 **void *memcpy(void *str1, const void *​**str2, size_t n)**   从存储区 **str2** 复制 **n** 个字节到存储区 **str1**。

下面是 memcpy() 函数的声明：

```cpp
void *memcpy(void *str1, const void *str2, size_t n)
```

* **str1** -- 指向用于存储复制内容的目标数组，类型强制转换为 void* 指针。
* **str2** -- 指向要复制的数据源，类型强制转换为 void* 指针。
* **n** -- 要被复制的字节数。

```cpp
// 将字符串复制到数组 dest 中
#include <stdio.h>
#include <string.h>

int main ()
{
   const char src[50] = "http://www.runoob.com";
   char dest[50];

   memcpy(dest, src, strlen(src)+1);
   printf("dest = %s\n", dest);

   return(0);
}
```

![image](assets/image-20231127164633-3m7efgd.png)​

### 7.6 指针和const

**Many possibilities exist for using (or not using) const with function parameters, so how do you choose the most appropriate?**    应该使用最小特权原则，总是赋予一个函数足够的访问其参数中的数据的权限来完成其指定的任务，但not more。

这一节就是讨论如何使用const和指针实现上述的最小特权原则。

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231011173200810.png" alt="image-20231011173200810" style="zoom:50%;" />
</div>

有四种方式将指针传递给函数：

1.a nonconstant pointer to nonconstant data,

2.a nonconstant pointer to constant data

3.a constant pointer to nonconstant data

4.a constant pointer to constant data

#### 7.6.1 nonconstant pointer to nonconstant data

最高的访问权限是由非const指针授予非const数据：

1.数据可以通过解引用指针进行修改 

2.指针可以修改指向其他数据

#### 7.6.2 nonconstant pointer to constant data(常量指针)

常量指针就是指向常量值的一个指针变量：

1.一个指针可以被修改为可以指向任意合适类型的数据。

2.指针所指向的数据不能通过该指针进行修改(即，不能通过解引用的方法修改)。

**这种类型的指针可以声明为：const int**​ * countPtr 即countPtr是一个nonconstant pointer指向constant data

```c++
#include <iostream>
void f(const int*)

int main(){
    int y{0};
    f(&y);
}
void f(const int* xPtr){
    *xPtr=100;
}
```

```cpp
const int x=1;
const int* p1;
p1=&x;

*p1=10;//错误！

char* s1="hello";//错误！
const char* s2="hello";//正确！
```



上述代码试图通过指针修改const类型的数据，就会出现错误。

一般用于修饰函数的形参，表示不希望在函数里修改内存地址中的值。

当一个函数被调用，且用内置数组作为实参，它(内置数组)的内容被有效的pass-by-reference。因为内置数组的名字被隐式的转换为数组第一个元素的地址。但是在默认情况下，array和vector对象是pass-by-value(整个对象的副本被传递)。对对象中的每个数据项做副本并存储在函数调用栈上需要消耗执行时间。当对象的指针被传递，只有对象地址的副本必须传递，而对象本身不需要。

如果数据不需要被被调用函数修改，使用constant data的指针或者引用传递大型的对象，可以减少使用pass-by-value使用副本带来的开销。还可以提供数据数值传递的安全性。

#### 7.6.3 Constant Pointer to Nonconstant Data(指针常量)

A constant pointer to nonconstant data is a pointer that:

1.永远指向相同的内存地址

2.该内存地址的数据可以通过指针修改

指针在声明为const时，必须初始化，但是如果指针是函数的形参，则使用传递给函数的指针对其进行初始化。

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231012091620236.png" alt="image-20231012091620236" style="zoom:50%;" />
</div>
‍

```cpp
int x=1,y=1;
int* const p2=&x;

p2=10;//correct!x=10
p2=&y;//error!指针p2是constant的
```

数组名就是数组的首地址的别名。可以说数组名就是一个指针常量。

#### 7.6.4 Constant Pointer to Constant Data

最小访问权限由const指针授予const数据：

1.指针永远指向相同的内存地址

2.该内存地址的数据不能通过指针修改

这就是一个内置数组应该如何传递给一个只从数组中读取的函数，使用数组下标符号，而不对其进行修改。

```c++
#include <iostream>
using namespace std;

int main() {
    int x{5},y;
    const int* const ptr{&x};

    cout<<*ptr<<endl;
    *ptr=7;
    ptr=&y
}
```

上述代码试图修改const指针和const数据，就会出现错误。

### 7.7 sizeof操作符

当对内置数组使用sizeof操作符以后，sizeof会返回一个size_t类型的内置数组的总字节数。**当在函数中使用指针作为形参，接收内置数组作为实参，sizeof操作符返回的是指针的字节数，而不是内置数组的总字节数。**

```c++
#include <iostream>
using namespace std;
size_t getSize(double*);

int main() {
    double numbers[20];
    cout<<"the number of bytes in the array is "<<sizeof(numbers);

    cout<<"\nthe number of bytes returned by getSize is "<<getSize(numbers)<<endl;
}

size_t getSize(double* ptr){
    return sizeof(ptr);
}
```

计算内置数组含有多少个元素可以使用如下命令：

```c++
sizeof numbers / sizeof(numbers[0])
```

下列程序使用sizeof操作符判断基本数据类型、内置数组和指针的字节数

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231012110557638.png" alt="image-20231012110557638" style="zoom:50%;" />
</div>

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231012110619359.png" alt="image-20231012110619359" style="zoom:50%;" />
</div>

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231012110701266.png" alt="image-20231012110701266" style="zoom: 50%;" />
</div>

当sizeof的操作数是一个表达式时，与sizeof一起使用的括号是不需要的。记住sizeof是一个编译时(compile-time)操作符，所以它的操作数在运行时不被评估。

### 7.8 指针表达式及指针算数运算

**指针的算数运算只适用于指向内置数组的指针。**

一个指针可以被递增( + + )或递减( -- )，一个整数可以被加到一个指针( +或+ =)或从一个指针( -或- =)中减去，或者一个指针可以从另一个相同类型的指针中减去- -这种特殊的操作只适用于指向同一个内置数组的两个指针。

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231012111516910.png" alt="image-20231012111516910" style="zoom:50%;" />
</div>
#### 7.8.1 对指针进行加减整数操作

对指针加上整数，并不是直接将此整数加到指针的值上，例如，对于上述的指针vPtr，原始值为3000，命令3000+2，vPtr的值并不是3002，加上的整数还要乘以指针指向的对象的字节数，即vPtr=3000+(2*4)=3008(认定指针指向的内存对象的大小为4个字节)。

#### 7.8.2 指针相减

指向同一内置数组的指针变量可以相互减去。

例如，指针变量v1和v2分别包含地址3008和3000，

```c++
x=v2-v1;
```

会将v2和v1之间的元素个数的值赋给变量x，x=2。**Pointer arithmetic is meaningful only on a pointer that points to a built-in array.**   我们不能假设同一类型的两个变量在内存中连续存储，除非它们是内置数组的相邻元素。

#### 7.8.3 指针赋值

**如果两个指针的类型相同，就可以将一个指针赋给另一个指针。否则，就必须使用cast operator(一般是reinterpret_cast)，将赋值语句的右边的指针的类型转换为左侧指针的类型。该规则的例外是指向void (即, void )的指针，它是一个通用指针，能够表示任何指针类型。**

**说可以用任意类型的指针对 void 指针对 void 指针赋值,不需要类型转换。如果要将 void 指针赋给其他类型的指针，则需要强制类型转换。**

#### 7.8.4  Cannot Dereference a void*

一个void\*的指针不能进行解引用操作。因为void\*的指针指向的是未知类型的内存地址。

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231012125517012.png" alt="image-20231012125517012" style="zoom:50%;" />
</div>
#### 7.8.5 指针相比较

指针可以使用等式和关系运算符进行比较。使用关系运算符比较指针是无意义的，除非两个指针指向的是同一个内置数组。指针之间的比较，比较的是指针存储的地址。A common use of pointer comparison is determining whether a pointer has the value nullptr, 0 or NULL (i.e., the pointer does not point to anything).

### 7.9 指针和内置数组的关系

指针可以用来做任何涉及数组下标的操作。

考虑如下的声明：

```c++
int b[ 5 ]; // create 5-element int array b; b is a const pointer 
int* bPtr; // create int pointer bPtr, which isn't a const pointer
```

可以将数组的第一个元素的地址赋给指针变量

```c++
bPtr=b;
```

上诉语句和下述代码效果相同

```c++
bPtr=&b[0];
```

而

```c++
b+=3;
```

**会造成编译错误，因为它试图通过指针算数运算修改内置数组的名字。**

#### 7.9.1 Pointer/Offset Notation

还是考虑上述的代码，内置数组的第三个元素，即b[3],可以用指针表示为：

```c++
*(bPtr + 3)
```

3代表指针的偏移量。当指针指向一个内置数组的起始元素时，偏移量表示应该引用哪个内置数组元素，且偏移量的值与下标相同。这种表示法被称为Pointer/Offset Notation。括号是必要的，因为括号的优先级高于+。在没有括号的情况下，前面的表达式会在* bPtr的值(即在b 中加入3 ,假设bPtr指向内置数组的开始)的副本中加上3。

正如内置数组的元素可以用指针表达式引用一样，地址：

```c++
&b[3]
```

可以写为：

```c++
bPtr + 3
```

#### 7.9.2Pointer/Offset Notation with the Built-In Array’s Name as the Pointer

内置数组名可以作为指针处理，用于指针算术运算。例如

```c++
*(b + 3)
```

也表示数组的第三个元素。

一般情况下，所有带下标的内置数组表达式都可以用一个指针和一个偏移量写出。在这种情况下，使用指针/偏移量表示法，内置数组的名称作为指针。前面的表达式不修改内置数组的名称；b仍然指向内置数组的第1个元素。

#### 7.9.3 Pointer/Subscript Notation

指针可以带下标正如内置数组一样。例如，表达式

```c++
bPtr[1]
```

refers to b[1]; this expression uses pointer/subscript notation.

#### 7.9.4 Demonstrating the Relationship Between Pointers and Built-In Arrays

四种表示方法：

1.array subscript notation

2.pointer/offset notation with the built-in array’s name as a pointer

3.pointer subscript notation

4.pointer/offset notation with a pointer

```c++
#include <iostream>
using namespace std;

int main() {
    int b[]{10,20,30,40};
    int* bPtr{b};
// output built-in array b using array subscript notation
    cout<<"array b displayed with:\n\narray subscript notation\n";

    for(size_t i{0};i<4;++i){
        cout<<"b["<<i<<"]="<<b[i]<<'\n';
    }
// output built-in array b using array name and pointer/offset notation
    cout<<"\npointer/offset notation where"<<"the pointer is the array name\n";

    for(size_t offset1{0};offset1<4;++offset1){
        cout<<"*(b+"<<offset1<<")="<<*(b+offset1)<<'\n';
    }
// output built-in array b using bPtr and array subscript notation
    cout<<"\npointer subscript notation\n";

    for(size_t j{0};j<4;++j){
        cout<<"bPtr["<<j<<"]="<<bPtr[j]<<'\n';
    }
// output built-in array b using bPtr and pointer/offset notation
    cout<<"\npointer/offset notation\n";

    for(size_t offset2{0};offset2<4;++offset2){
        cout<<"*(bPtr+"<<offset2<<")="<<*(bPtr+offset2)<<'\n';
    }
}
```

运行结果为：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231012210327531.png" alt="image-20231012210327531" style="zoom:50%;" />
</div>

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231012210342250.png" alt="image-20231012210342250" style="zoom:50%;" />
</div>

### 7.10 基于指针的字符串(Pointer-Based Strings)

**字符和字符常量:**

字符是C + +源程序的基本构件。一个程序可能包含字符常量。**字符常量是在单引号中表示为字符的整数值。**

**字符串**：

**字符串是作为单个单位处理的一系列字符。**    一个字符串可能包括字母、数字和各种特殊字符，如+、-、*、/和$。C++中的字符串字面量(String literals)，或字符串常量，用双引号写成如下：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231012211740742.png" alt="image-20231012211740742" style="zoom:50%;" />
</div>

**基于指针的字符串**：

基于指针的字符串是一个存储字符的内置数组，并以空字符(null character('\\0'))结尾,其标记了字符串在内存中终止的位置。字符串通过指针访问其第一个字符。字符串文本sizeof的结果是包含终止空字符的长度。

**字符串字面量作为初始化值**：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231012212221184.png" alt="image-20231012212221184" style="zoom:50%;" />
</div>

当声明内置字符串数组包含字符串时，内置数组必须足够大，以存储字符串及其终止空字符。

没有在一个内置的字符数组中分配足够的空间来存储终止字符串的空字符是一个逻辑错误。

创建或使用不包含终止空字符的C字符串会导致逻辑错误。

**在内置字符数组中存储字符串时，确保内置数组足够大，以容纳将要存储的最大字符串。C + +允许任意长度的字符串。如果一个字符串比待存储字符串的内置数组长，那么内置数组末尾以外的字符将跟随内置数组覆盖内存中的数据，从而导致逻辑错误和潜在的安全漏洞。**

**访问C字符串中的字符**

由于C字符串是一个内置的字符数组，我们可以直接用数组下标记法访问字符串中的单个字符。例如，在前面的声明中，color[0]是字符' b '，color[2]是字符' u '，color[4]是空字符。

**用cin读取字符串到char内置数组中**

一个字符串可以使用cin读入到一个内置的char类型数组中，例如，下面的语句读取一个字符串到内置的20个元素char数组中：

```c++
cin>>word;
```

用户输入的字符串存储在word数组中。上述语句读取字符，直到遇到空白字符或EOF字符才会停止。字符串不应超过19个字符，为终止空字符留有余地。**使用setw流操作符可以保证读入word的字符串不超过内置数组的大小。**    例如：

```c++
cin>>setw(20)>>word;
```

规定cin最多读取19个字符到word，并保留第20个位置，用于存储字符串的终止空字符。The setw stream manipulator is not a sticky setting—it applies only to the next value being input.如果输入了19个以上的字符，剩下的字符虽然没有保存在word中，但是会在输入流中，可以被下一次的输入操作读取。

EOF(end of file)就是文件的结束，通常来判断文件的操作是否结束的标志。

EOF不是特殊字符，而是定义在头文件<stdio.h>的常量，一般等于-1；

在微软的DOS和Windows中，读取数据时终端不会产生EOF。此时，应用程序知道数据源是一个终端（或者其它“字符设备”），并将一个已知的保留的字符或序列解释为文件结束的指明；最普遍地说，它是ASCII码中的替换字符（Control-Z，代码26）。

在C语言中，或更精确地说成C标准函数库中表示文件结束符（end of file）。在while循环中以EOF作为文件结束标志，这种以EOF作为文件结束标志的文件，必须是文本文件。在文本文件中，数据都是以字符的ASCII代码值的形式存放。我们知道，ASCII代码值的范围是0~127，不可能出现-1，因此可以用EOF作为文件结束标志。

档案存取或其它 I/O 功能可能传回等于象征符号值 (巨集) EOF 指示档案结束的情形发生。实际上 EOF 的值通常为 -1，但它依系统有所不同。巨集 EOF会在编译原始码前展开实际值给预处理器。

C语言中，EOF常被作为文件结束的标志。还有很多文件处理函数处错误后的返回值也是EOF，因此常被用来判断调用一个函数是否成功。

**Reading Lines of Text into Built-In Arrays of char with cin.getline**

在某些情况下，希望将整行文本输入到一个内置的字符数组中。为此，cin对象提供成员函数getline，它包含三个参数- -一个内置的用于存储文本行的char数组、一个长度和一个分隔符。

A delimiter is one or more characters that separate text strings. Common delimiters are **commas** (,), semicolon (;), quotes (", '), braces ({}), pipes (|), or slashes (/ ). When a program stores sequential or tabular data, it delimits each item of data with a predefined character.

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231013093643204.png" alt="image-20231013093643204" style="zoom:50%;" />
</div>

函数在遇到分隔符'\n'时停止读取字符，在输入EOF符时或者输入的字符数量比函数的第二个参数少1时停止读取字符。内置数组中的最后一个字符被保留为终止空字符。如果最后一个字符遇到'\n',会读取后将其丢弃。函数的第三个参数是默认的，所以上述代码可以写为：

```c++
cin.getline(sentence,80);
```

使用cout可以将char数组的内容输出：

```c++
cout<<sentence;
```

像cin一样，cout并不关心内置char数组有多大。字符被输出，直到遇到一个终止的空字符；**空字符不显示。**   [注: cin和cout假设char的内置数组应该被处理成以空字符结尾的字符串。cin和cout没有为其他内置数组类型提供类似的输入输出处理能力]

### 7.11 Smart Pointers(智能指针)

带指针的动态内存管理，它允许你在执行时根据需要创建和销毁对象。对这一过程的不当管理是导致细微错误的根源。我们将讨论"智能指针"，它通过提供内置指针之外的附加功能，帮助您避免动态内存管理错误。

提供了三种智能指针:

1.unique_ptr:不允许多个指针共享资源，可以用标准库中的move函数转移指针

2.shared_ptr:多个指针共享资源

3.weak_ptr:可以复制shared_ptr，但其构造或者释放对资源不产生影响

### 7.12 左值、纯右值和将亡值

区分左值右值的真正说法是：能否用“取地址&”运算符获得对象的内存地址。

对于临时对象，它可以存储于寄存器中，所以是没办法用“取地址&”运算符；

对于常量，它可能被编码到机器指令的“立即数”中，所以是没办法用“取地址&”运算符；

这也是C/C++标准的规定。

字符串字面值常量是C++标准中明确指明的特例，为常量左值，所以可以取地址&运算，其地址属于进程的只读内存空间。其它的字面值常量都是“纯右值”

左值：例如变量、数组元素、结构体成员、引用和解引用的指针

**1.左值**

指定了一个函数或者对象，它是一个可以取地址的表达式

```cpp
int lv1{ 42 }; // Object
int main() {
   int& lv2{ lv1 }; // Lvalue reference to Object
   int* lv3{ &lv1 }; // Pointer to Object
}

int& lv4() { return lv1; } // Function returning Lvalue Reference
```

1.1左值例子

(1)   解引用表达式*p

(2)   字符串字面量"abc"

(3)   前置自增/自减表达式 ++i / --i

(4)   赋值或复合运算符表达式(x=y或m*=n等）

**2.C++11: 纯右值**

是不和对象相关联的值(字面量)或者其求值结果是字面量或者一个匿名的临时对象

2.1纯右值例子

(1)   除字符串字面量以外的字面量，比如 32, 'a'

(2)   返回非引用类型的函数调用 int f() { return 1;}

(3)   后置自增/自减表达式i++/i--

(4)   算术/逻辑/关系表达式（a+b、a&b、a<<b）（a&&b、a||b、~a）（a==b、a>=b、a<b）

(5)   取地址（&x）

左值可以当成右值使用

**3.C++11: 将亡值** 

xvalue(eXpiring Value，将亡值)：将亡值也指定了一个对象，是一个将纯右值转换为右值引用的表达式

```cpp
int prv(int x) { return 6 * x; } // pure rvalue 

int main() {
   const int& lvr5{ 21 }; // 常量左值引用可引用纯右值
   int& lvr6{ 22 }; // 错！非常量左值引用不可引用纯右值
   int&& rvr1{ 22 }; // 右值引用可以引用纯右值
   int& lvr7{ prv(2) }; // 错！非常量左值引用不可引用纯右值
   int&& rvr2{ prv(2) }; // 右值引用普通函数返回值
   rvr1 = ++rvr2; // 右值引用做左值使用
}
```

#### 7.12.1 **右值引用**

&&是右值引用，函数返回的临时变量是右值

### 7.13  指针类型的函数

即函数的返回类型为指针类型，需要注意的是：不要将非静态局部地址用作函数的返回值，因为非静态的局部变量的地址在函数执行完毕以后，就销毁了。

正确的例子：1.主函数中定义的数组，在子函数中对该数组的元素进行某种操作以后，返回其中一个元素的地址，这就是合法有效的地址。2.在子函数中通过动态内存分配操作取得的内存地址返回给主函数是合法有效的，但是内存分配和释放不在同一级别，要注意不能忘记释放(在主函数中进行释放)，避免内存泄漏。

### 7.14 函数指针

如果把函数的地址作为参数传递给函数，就可以在函数中灵活的调用函数。

使用函数指针的步骤：

1.声明函数指针

2.使函数指针指向函数的地址

3.通过函数指针调用函数

如果在程序中定义了一个函数，那么在编译时系统就会为这个函数代码分配一段存储空间，这段存储空间的首地址称为这个函数的地址。而且函数名表示的就是这个地址。既然是地址我们就可以定义一个指针变量来存放，这个指针变量就叫作函数指针变量，简称函数指针。声明函数指针时，必须提供函数的类型，函数的类型就是**返回值**和**参数列表。例如：**

```cpp
int func(int a,string b);
```

上述函数的函数指针可以声明为;

```cpp
int (*FuncPtr)(int,string)
```

*FuncPtr两端的括号必不可少。如果不写括号，则FuncPtr是一个返回值是int指针的函数。

**当我们把函数名作为一个值使用时，该函数自动地转换为指针。**

```cpp
FuncPtr = length;//FuncPtr指向名为length的指针
FuncPtr = &length;//和上述语句等价。取地址符是可选的
```

使用时可以直接使用指向函数的指针调用该函数，不需要解引用操作：

```cpp
int b1=FuncPtr(7,"hello");
int b1=(*FuncPtr)(7,"hello");//和上述语句的调用等价
int b1=length(7,"hello");//直接调用函数
```

指向不同函数类型的指针之间不存在转换规则。

**需要注意的是，指向函数的指针变量没有 ++ 和 -- 运算。**

```cpp
#include <iostream>
using namespace std;

int Max(int, int);  //函数声明

int main() {
    int(*p)(int, int);  //定义一个函数指针
    int a, b, c;
    p = Max;  //把函数Max赋给指针变量p, 使p指向Max函数
    cout<<"please enter your number: "<<endl;
    cin>>a>>b;
    c = p(a, b);  //通过函数指针调用Max函数
    cout<<a<<b<<c<<endl;
}

int Max(int x, int y)  //定义Max函数
{
    int z;
    if (x > y)
    {
        z = x;
    }
    else
    {
        z = y;
    }
    return z;
}
```

### 7.15  指针数组

指针数组即数组的元素是指针类型，例如：

```cpp
Point *pa[2];//由pa[0]和pa[1]两个指针组成
```

### 7.16 内置数组的排序

C++的内置函数qsort()可以用来对内置数组的元素进行排序。

函数的原型为：

```cpp
void qsort(void *base, size_t nitems, size_t size, int (*compar)(const void *, const void*))
```

* base -- 指向要排序的数组的第一个元素的指针。
* nitems -- 由 base 指向的数组中元素的个数。
* size -- 数组中每个元素的大小，以字节为单位。
* compar -- 用来比较两个元素的函数。

函数不返回任何值。

```cpp
#include <stdio.h>
#include <stdlib.h>

int values[] = { 88, 56, 100, 2, 25 };

int cmpfunc (const void * a, const void * b)
{
   return ( *(int*)a - *(int*)b );
}

int main()
{
   int n;

   printf("排序之前的列表：\n");
   for( n = 0 ; n < 5; n++ ) {
      printf("%d ", values[n]);
   }

   qsort(values, 5, sizeof(int), cmpfunc);

   printf("\n排序之后的列表：\n");
   for( n = 0 ; n < 5; n++ ) {
      printf("%d ", values[n]);
   }
  
  return(0);
}
```

### 7.17 对象指针

对象指针的定义形式：

```cpp
类名 *对象指针名;
Point a{5,10};
Point *ptr;
ptr=&a;
```

### 7.18 简化的C++内存模型

将内存划分为4个部分

1.stack(栈)

编译器自动分配释放，栈向低地址方向生长。

2.heap(堆)

一般由程序员分配释放，若程序员不释放，程序结束可能由操作系统回收。在C++中，即使用new和delete运算符实现。堆向高地址方向生长。

3.global/static(全局区/静态区)

全局变量和静态变量的存储是放在一块的。

可以简单的认为：

程序启动全局/静态变量就在此处

程序结束后释放

4.constant(常量区)

可以简单理解为所有常量都放在一块

该区域内容不可修改

### 7.19 using,typedef和#define的用法

#define和typedef：

**#define是一个预处理指示符**

1.用来定义宏。编译器不做类型检查

2.

```
#define TRUE 1 //结尾无分号，宏名为TRUE
//会将程序中所有出现TRUE的地方替换为1
```

**typedef创建能在任何位置替代类型名的别名**

```cpp
typedef someType newTypeName
示例：
typedef _Bool bool;//将bool作为类型_Bool的别名
```

**用using替代typedef:**

语法：using identifier=type-id

```cpp
//类型别名，等同于typedef unsigned int UINt;
using UInt=unsigned int;//名称'UInt'现在指代类型：unsigned int
UInt x=42u;

//类型别名，等同于typedef void (*FuncType)(int,int);
using FuncType=void(*) (int,int);
//'FuncType'现在指代指向函数的指针
void example(int,int){}
FuncType f=example;
```

定义模板的别名，只能使用using



## 8. 类：更深层次的理解

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231013111409847.png" alt="image-20231013111409847" style="zoom:50%;" />
</div>
### 8.1 接口与实现分离

我们的每个先前的类定义示例都将一个类放在一个头文件中进行重用，然后将类的定义包含到一个包含main的源代码文件中，这样我们就可以创建和操作类的对象。

传统的思想认为，使用类的一个对象，客户(例如main函数)只需要知道：

1.调用什么成员函数

2.需要向每个成员函数提供什么实参

3.期望从每个成员函数得到什么返回类型

客户端代码不需要知道这些功能是如何实现的。

隐藏类的实现细节使得更容易更改类的实现，同时最小化，并有希望消除对客户端代码的更改。

**两个重要的C++软件工程概念：**

1.接口与实现分离(Separating interface from implementation.)

2.在头文件中使用include guard以防止头文件中的代码被包含在同一个源代码文件中不止一次。由于一个类只能被定义一次，因此使用这样的预处理指令可以防止多定义错误。

宏保护除了文件名外，最好再加上包名或者自动生成的时间信息，避免异包同名文件的情况

#### 8.1.1 类的接口

接口定义和规范了人和系统等事物之间的交互方式。例如，收音机的控件作为收音机用户与其内部组件之间的接口。控件允许用户执行一组有限的操作(如更改台站、调整音量、在AM台和FM台之间选择等)。不同的收音机可以实现操作的方式不同- -有的提供按钮，有的提供拨号，有的支持语音指令。该接口规定了无线电允许用户执行哪些操作，但没有说明这些操作是如何在无线电内部实现的。

类似地，类的接口描述了类的客户可以使用哪些服务以及如何请求这些服务，而不是类如何执行这些服务。类的Public接口由类的public成员函数(也被称为类的public services)组成。就像你很快看到的那样，你可以通过编写一个类定义来指定一个类的接口，这个类定义只列出类的成员函数原型和类的数据成员。

#### 8.1.2 Separating the Interface from the Implementation(分离类的接口与实现)

**为了将类的接口从实现中分离出来，我们将类Time分解成两个文件- -定义类Time的头文件Time . h和定义类Time成员函数的源代码文件Time . cpp** ,因此：

1.类是可重用的

2.类的客户知道类提供哪些成员函数，如何调用它们以及期望的返回类型

3.客户端不知道类的成员函数是如何实现的

根据约定，成员函数的定义放在和类同名的源文件中，且文件扩展名为.cpp。即成员函数在一个单独的.cpp文件中定义，类在.h文件中定义，客户即包含main函数的程序在另一个.cpp文件中定义。

#### 8.1.3 ifndef/define/endif

**ifndef/define/endif主要目的是防止头文件的重复包含和编译**​[C/C++中#ifndef的用法 - 简书 (jianshu.com)](https://www.jianshu.com/p/b328f133f89a)　

```c++
#include <string>
#ifndef TEST_10_13_TIME_H
#define TEST_10_13_TIME_H
class Time{
public:
    void setTime(int,int,int);
    std::string toUniversalString() const;
    std::string toStandardString() const;
private:
    unsigned int hour{0};
    unsigned int minute{0};
    unsigned int second{0};
};
#endif //TEST_10_13_TIME_H
```

当我们构建更大的程序时，其他的定义和声明也会放在头文件中。由于各种原因，头文件可能会出现问题。在项目编译期间，通常会编译每个.cpp文件。简单来说，这意味着编译器将获取您的.cpp文件，打开包含在其中的所有文件，将它们全部连接成一个大文本文件，然后执行语法分析，最后将其转换为一些中间代码，进行优化/执行其他任务，最后生成目标体系结构的程序集输出。因此，如果一个文件被多次包含在一个.cpp文件下，则编译器会将其文件内容添加两次，因此，**如果该文件中包含定义，则会出现编译器错误，提示您重新定义了一个变量**。当文件在编译过程中由预处理器步骤处理时，第一次到达其内容时，前两行将检查是否已为预处理器定义了CLASS_H。如果没有，它将定义CLASS_H并继续处理它与#endif指令之间的代码。下一次预处理器看到文件的内容时，对FILE_H的检查将为false，因此它将立即向下扫描到#endif并在此之后继续。这样可以防止重新定义错误。

当Time . h被首次#include时，标识符TIME _ H还没有被定义。在这种情况下，#define指令定义了TIME _ H，预处理器包含了. cpp文件中Time . h头文件的内容。如果再#include头文件，则由于已经定义了TIME _ H，预处理器将忽略# ifndef和# endif之间的代码。

**使用# ifndef，# defined和# endif预处理指令来形成一个include guard，以防止头文件在源代码文件中被多次包含。**

#### 8.1.4 作用域解析运算符(Scope Resolution Operator)

在代码中，在类的名字后面加作用域解析运算符，再加成员函数的名称。此运算符将成员函数与类的定义联系在一起。Time::告诉编译器每个成员函数都在该类的范围内，并且它的名字为其他类成员所知道。

“::”指明了成员函数所属的类。如：M::f(s)就表示f(s)是类M的成员函数。 作用域，如果想在类的外部引用静态成员函数，或在类的外部定义成员函数都要用到。使用命名空间里的类型或函数也要用到（如：std::cout, std::cin, std::string 等等）

没有Time::，编译器就无法知道成员函数属于Time类。相反，编译器会认为它们是"自由(free)的"或"松散(loose)的"函数，比如main - -这些函数也被称为全局函数。这种函数无法访问类的private数据或者调用类的成员函数。

#### 8.1.5 Time Class Member Function toUniversalString and String Stream Processing

cout是标准输出流，ostringstream类的对象(来自头文件\<sstream>)提供了相同的功能，但是会将输出写入内存中的string对象。使用ostringstream类的str成员函数得到格式化的string。

```c++
string Time::toUniversalString() const {
    ostringstream output;
    output<<setfill('0')<<setw(2)<<hour<<":"<<setw(2)<<minute<<":"<<setw(2)<<second;
    return output.str();
}
```

在上述代码中，ostringstream类创造了output对象。像使用cout一样使用output即可。参数化流操作符setfill用来指定填充字符，当一个整数在一个比该值的位数更宽的字段中输出时。**填充字符出现在数字的左边，因为数字默认右对齐。例如分钟值为2，将会显示为02，因为填充字符设定为'0'。如果数值为两位数，如28，就不会进行填充,一旦操作符setfill使用，后面的所有值都会进行填充(sticky setting)。Ostringstream的str成员函数得到格式化字符串，返回给客户端。**

**Each sticky setting (such as a fill character or precision) should be restored to its previous setting when it’s no longer needed. Failure to do so may result in incorrectly formatted output later in a program.**

#### 8.1.6 Implicitly Inlining Member Functions

如果在类的体中定义了成员函数，则成员函数被隐式地声明为内联的。请记住，编译器保留不内联任何函数的权利。

在类定义内部定义一个成员函数，将成员函数(如果编译器选择这样做)内联。这样可以提高性能。

在类头文件中只定义最简单、最稳定的成员函数(也就是说,其实现方式不可能改变)，因为对头的每一次更改都需要重新编译依赖于该头(在大型系统中,一项耗时的工作)的每个源代码文件。

#### 8.1.7 成员函数对比全局函数

使用面向对象编程方法在调用函数时往往需要较少的参数。这种好处源于将数据成员和成员函数封装在一个类中，赋予了成员函数访问数据成员的权利。

成员函数通常比非面向对象程序中的函数更短，因为数据成员中存储的数据在理想情况下已经被构造函数或存储新数据的成员函数验证。由于数据已经在对象中，成员函数调用往往没有参数或者参数少于非面向对象语言中的函数调用。因此，函数调用、函数定义和函数原型都更短。这改善了程序开发的许多方面。

成员函数调用通常比常规函数调用(非面向对象的语言)不带或少带参数，这降低了传递错误参数、错误参数类型或错误参数数量的可能性。

#### 8.1.8 对象的尺寸(Object Size)

刚接触面向对象编程的人常常假设对象必须相当大，因为它们包含数据成员和成员函数。从逻辑上讲，这是真的- -你可以把对象看作是包含数据和函数的(而我们的讨论也肯定鼓励了这一观点)；然而，从物理上看，事实并非如此。

对象只包含数据，因此对象比同时包含成员函数时要小得多。编译器从类的所有对象中分别创建成员函数的一个副本(仅)。类中的所有对象共享这一个副本。当然，每个对象都需要自己的类的数据副本，因为数据可以在对象之间变化。函数代码对于类中的所有对象都是一样的，因此，它们之间可以共享。

### 8.2 编译和链接过程

下图展示了编译和链接过程，生成可供使用的可执行Time应用程序。通常一个类的接口和实现将由一个程序员创建和编译，并由单独的程序员使用，程序员实现使用该类的客户代码。因此，该图显示了类实现程序员和客户代码程序员的需求。图中的虚线分别显示了类实现程序员、客户代码程序员和Time application user所需的片段。

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231014191124433.png" alt="image-20231014191124433" style="zoom:50%;" />
</div>

一个类实现程序员负责创建一个可重用的Time类，创建头部Time . h和包含头部的源代码文件Time . cpp，然后编译源代码文件来创建Time的目标代码。为了隐藏类的成员函数实现细节，类实现程序员会向客户代码程序员提供报头Time . h (它规定了类的接口和数据成员)和Time对象代码(即代表Time成员函数的机器码指令)。客户代码程序员没有被赋予Time . cpp，因此客户仍然不知道Time的成员函数是如何实现的。

客户端代码程序员只需要知道Time的接口就可以使用类，并且必须能够链接它的目标代码。由于类的接口是Time . h头中类定义的一部分，因此客户代码程序员必须有权访问该文件，并且必须#将其包含在客户的源代码文件中。在客户端代码编译时，编译器使用Time . h中的类定义，保证主函数正确创建和操作类Time的对象。

要创建可执行的Time应用程序，最后一步就是链接:

1. the object code for the main function (i.e., the client code),
2. the object code for class Time’s member-function implementations, and
3. the C++ Standard Library object code for the C++ classes (e.g., string) used by the class-implementation programmer and the client-code programmer.

### 8.3 Class Scope and Accessing Class Members(类的范围和访问类的成员)

类的数据成员和成员函数属于类的范围。默认情况下，非成员函数被定义在全局命名范围(global namespace scope)。在类的范围内，类的成员可以被所有的类的成员函数访问并且可以通过名字被引用。在类的范围之外，public类成员可以通过下列三种方式被访问：

1.对象的名字

2.对一个对象的引用

3.一个对象的指针

**我们称之为对象上的句柄。句柄的类型使编译器能够确定客户端通过该句柄可访问的接口(例如,成员函数)。**

在类的作用域之外，类成员通过对象上的一个句柄（对象名、对对象的引用或对对象的指针）进行引用。

可以通过对象的名字或对象的引用，在后面加.访问对象的成员。通过指向对象的指针引用对象的成员，指针的名字和(->)后跟成员的名字，即：pointerName->memberName。

### 8.4 Access Functions and Utility Functions(访问函数和辅助函数)

#### 8.4.1 访问函数(access functions)

访问函数可以读取或显示数据，而不修改数据。访问函数的另一个常用的应用是检验条件的真伪---这种函数通常被叫做谓词函数(predicate funcations)，例如，任何容器类的empty函数- -一个能够容纳许多对象的类，如数组或向量。程序可能在试图从容器对象中读取另一个项目之前测试empty函数。

#### 8.4.2 辅助函数

辅助函数(helper function)是一个private成员函数，它支持类的其他成员函数的操作。辅助函数被声明为private的，因为他们不是被类的客户使用的。一个常用的辅助函数的用途是在一个函数中放置一些通常的代码，这些代码本来可以在其他几个成员函数中复制。

### 8.5 构造函数及析构函数

**如果某个类的成员函数已经提供了该类的构造函数或其他成员函数所需的全部或部分功能，则从该构造函数或其他成员函数中调用该成员函数。这简化了代码的维护，并降低了如果修改代码实现时出错的可能性。一般来说：避免重复代码。**

构造函数可以调用类的其他成员函数，如set或get函数，但由于构造函数是对对象的初始化，数据成员可能还没有被初始化。在数据成员被正确初始化之前使用数据成员会导致逻辑错误。

将数据成员私有化，通过public成员函数控制对这些数据成员的访问，特别是写访问，有助于保证数据的完整性。

数据完整性的好处并不是自动生成的，因为数据成员是private的- -您必须提供适当的有效性检查。

#### 8.5.1 重载构造函数以及委托构造函数

类的构造函数和成员函数也可以重载。重载构造函数允许对象初始化不同类型and/or数量的实参。要重载一个构造函数，应该在类定义中为每个版本的构造函数提供一个原型，并为每个重载版本提供一个单独的构造函数定义。这也适用于类的成员函数。例如，对于下列代码：

```cpp
Clock(int newH,int newM,int newS):hour(newH),minute(newM),second(newS){ }//构造函数
Clock():hour(0),minute(0),second(0){ }//构造函数
```

可以使用委托构造函数的形式，将上述代码改写为：

```
Clock(int newH,int newM,int newS):hour(newH),minute(newM),second(newS){ }
Clock:Clock(0,0,0){ }
```

就像构造函数可以调用类的成员函数，C++11允许构造函数调用同一类中的其他构造函数。**调用的这个构造函数叫做委托构造函数** ，将自己的工作委托给其他构造函数。

#### 8.5.2 委托构造函数/代理构造函数

即一个构造函数可以调用另外的构造函数

```cpp
class A{
public:
    A():A(0){}//调用了带一个参数的构造函数
    A(int i):A(i,0){}
    A(int i,int j){
        num1=i;
        num2=j;
        average=(num1+num2)/2;
    }
private:
    int num1;
    int num2;
    int average;
};
```

**被委托的构造函数要放在主调构造函数的初始化构造列表位置。**

**避免递归调用构造函数**

### 8.6 析构函数(Destructors)

析构函数是一种成员函数的类型。析构函数的参数列表是空的。析构函数的命名格式为~加类的名字：

```cpp
~类名()
```

析构函数也许不会指定形参以及返回类型。当对象销毁时，析构函数被隐式的调用。例如，当程序执行离开对象被实例化的范围时，对象就会被破坏。析构函数本身并没有释放对象的内存---它执行终止事务管理(termination housekeeping)的功能在对象的内存再生之前，所以内存可能被用于存储新的对象。

每个类都有析构函数，如果没有显式的定义析构函数，编译器会定义一个"empty"析构函数。

**析构函数不可以重载**，可以手动调用。构造函数不能手动调用。

### 8.7 当构造函数和析构函数都被调用

这些函数调用发生的顺序取决于执行进入和离开对象实例化的范围的顺序。一般的，析构函数的调用和它对应的构造函数的调用顺序相反。

#### 8.7.1 全局范围内对象的构造函数和析构函数

在其他程序中的任何函数(包括main函数)开始执行之前(尽管全局对象的构造函数的执行顺序并不保证)，构造函数被定义在全局范围的对象调用。当main终止时，相应的析构函数被调用。exit函数强迫程序立即终止并且不执行本地对象的析构函数。exit函数通常出现在程序发生不可修复的错误时。abort函数和exit函数类似，会迫使程序立即终止，并且不允许调用程序员定义的任何类型的清理代码。

#### 8.7.2 non-static局部对象的构造函数和析构函数

非静态局部对象的构造函数在执行到达该对象被定义的位置时被调用，相应的析构函数在执行离开对象的范围(也就是说,该对象所定义的块已经执行完毕)时被调用。

如果程序以exit函数或abort函数的方式终止，则不调用本地对象的析构函数。

#### 8.7.3 static局部对象的构造函数和析构函数

静态局部对象的构造函数只调用一次，当执行首先到达对象被定义的地方时- -当main程序终止或程序调用exit函数退出时，相应的析构函数被调用。

全局和static对象销毁的顺序和他们创建的顺序相反。static对象不会调用析构函数如果程序调用abort函数终止。

#### 8.7.4 构造函数和析构函数何时被调用

```c++
//
// Created by 22364 on 2023/10/15.
//
#include <string>

#ifndef TEAT_10_15_2_CREATEANDDESTROY_H
#define TEAT_10_15_2_CREATEANDDESTROY_H

class CreateAndDestroy{
public:
    CreateAndDestroy(int,std::string);
    ~CreateAndDestroy();

private:
    int objectID;
    std::string message;
};
#endif //TEAT_10_15_2_CREATEANDDESTROY_H
```

```c++
#include <iostream>
#include "CreateAndDestroy.h"
using namespace std;

CreateAndDestroy::CreateAndDestroy(int ID,string messageString)
    :objectID{ID},message{messageString} {
    cout<<"object "<<objectID<<" constructor runs "
    <<message<<endl;
}

CreateAndDestroy::~CreateAndDestroy(){
    cout<<(objectID==1||objectID==6?"\n":"");
    cout<<"object "<<objectID<<" destroy runs "
    <<message<<endl;
}
```

```c++
#include <iostream>
#include "CreateAndDestroy.h"
using namespace std;

void create();
CreateAndDestroy first{1,"(gobal before main)"};//全局对象

int main() {
    cout<<"\\nMAIN FUNCTION: EXECUTION BEGINS"<<endl;
    CreateAndDestroy second{2,"(local in main)"};
    static CreateAndDestroy third{3,"(local static in main)"};

    create();

    cout<<"\\nMAIN FUNCTION: EXECUTION RESUMES"<<endl;
    CreateAndDestroy fourth{4,"(local in main)"};
    cout<<"\\nMAIN FUNCTION: EXECUTION ENDS"<<endl;
}

void create() {
    cout << "\nCREATE FUNCTION: EXECUTION BEGINS" << endl;
    CreateAndDestroy fifth{5, "(local in create)"};
    static CreateAndDestroy sixth{6, "(local static in create)"};
    CreateAndDestroy seventh{7, "(local in create)"};
    cout << "\nCREATE FUNCTION: EXECUTION ENDS" << endl;
}
```

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231016211957849.png" alt="image-20231016211957849" style="zoom:50%;" />
</div>

上述代码在main函数中声明了三个对象，当程序执行到对象声明处时，每个对象的构造函数被调用。fourth和second对象的析构函数调用的顺序和他们构造函数的调用顺序相反，当程序的执行到达main函数的结尾时。因为third对象声明为static的，所以在程序终止以后仍然存在。third对象的析构函数的调用在first对象的析构函数调用之前，但是在所有其他对象销毁之后。

seventh的析构函数先调用再调用fifth对象的析构函数(和他们构造函数的调用顺序相反)，在create函数终止时。sixth对象被声明为static,在程序终止以后仍然存在。sixth对象的析构函数调用在third和first对象的析构函数的调用之前，但是在所有其他对象销毁之后。

### 8.8 Default Memberwise Assignment(默认逐成员初始化)

```c++
//
// Created by 22364 on 2023/10/17.
#include <string>

#ifndef TEST_10_17_DATE_H
#define TEST_10_17_DATE_H

class Date{
public:
    explicit Date(unsigned int=1,unsigned int =1,unsigned int=2000);
    std::string toString() const;
private:
    unsigned int month;
    unsigned int day;
    unsigned int year;
};

#endif //TEST_10_17_DATE_H
```

```c++
#include <sstream>
#include <string>
#include "Date.h"
using namespace std;

Date::Date(unsigned int m, unsigned int d, unsigned int y)
    :month{m},day{d},year{y} {}
string Date::toString() const {
    ostringstream output;
    output<<month<<'/'<<day<<'/'<<year;
    return output.str();
}
```

```c++
#include <iostream>
#include "Date.h"
using namespace std;

int main() {
    Date date1{7,4,2004};
    Date date2;

    cout<<"date1= "<<date1.toString()
        <<"\ndate2="<<date2.toString()<<"\n\n";

    date2=date1;

    cout<<"after default memberwise assignment,date2="
    <<date2.toString()<<endl;

}
```

**赋值操作符=可以用来将同一个类的一个对象赋值给另一个对象。默认情况下，默认情况下，这种指派是通过memberwise assignment(也称为copy assignment)进行的- -赋值运算符右侧对象的每个数据成员被单独赋值到赋值运算符左侧对象中的同一个数据成员。**

**注意：**   当使用的类的数据成员包含指向动态地址的指针时， Memberwise assignment会引起严重的问题；我们在后续内容讨论了这些问题，并给出了如何处理这些问题的方法。

对象可以作为函数参数传递，也可以从函数返回。这种传递和返回默认情况下使用数值传递执行- -传递或返回对象的一个副本。在这种情况下，C + +创建一个新的对象，并使用一个拷贝构造函数将原对象的值拷贝到新对象中。对于每个类，编译器提供一个默认的副本构造器，将原对象的每个成员复制到新对象的相应成员中。同成员分配一样，拷贝构造函数在与数据成员包含指针的类一起使用动态分配内存时会引起严重的问题。

### 8.9 实例化(instantiation)

就像有人在实际驾驶汽车之前必须从工程图纸中创建一个汽车一样，在一个程序能够执行类的成员函数定义的任务之前，必须从类中创建一个对象。这样做的过程被称为实例化。然后，一个对象被称为它类的一个实例。

### 8.10 const对象和const成员函数

一些对象不需要被改变，就可以声明为const。You may use const to specify that an object is not modifiable and that any attempt to modify the object should result in a compilation error.

```c++
const Time noon{12,0,0};
```

C++不允许const对象调用成员函数，除非成员函数也被声明为const的。即使对于不修改对象的get成员函数也是如此。这也是我们将所有不修改被调用对象的成员函数都声明为const的一个关键原因。

**const对象只能调用const成员函数**​

**const成员函数只能调用const成员函数**​

**const成员函数中不能改变成员变量的值**

**定义一个const成员函数调用non-const成员函数是编译错误。**

**const对象调用non-const对象是编译错误**

试图将构造函数和析构函数声明为const是编译错误。

即使成员函数没有没有改变对象，但是const对象仍然不能调用它，成员函数必须显式的声明为const，才可以被const对象调用。

### 8.11 Composition: Objects as Members of Classes(组成：对象作为类的成员)

```c++
//Date.h
// Created by 22364 on 2023/10/17.
#include <string>

#ifndef TEST_10_17_DATE_H
#define TEST_10_17_DATE_H

class Date{
public:
    static const unsigned int monthsPerYear{12};
    explicit Date(unsigned int=1,unsigned int =1,unsigned int=1900);
    std::string toString() const;
    ~Date();// provided to confirm destruction order
private:
    unsigned int month;
    unsigned int day;
    unsigned int year;

    unsigned int checkDay(int) const;
};

#endif //TEST_10_17_DATE_H
```

```c++
//Date.cpp
#include <sstream>
#include "Date.h"
#include <array>
#include <iostream>
#include <stdexcept>
using namespace std;

Date::Date(unsigned int mn, unsigned int dy, unsigned int yr)
    :month{mn},day{dy},year{yr} {
    if(mn<1||mn>monthsPerYear){
        throw invalid_argument("month must be 0-12");
    }
    cout<<"date object constructor for date"<<toString()<<endl;
}
string Date::toString() const {
    ostringstream output;
    output<<month<<'/'<<day<<'/'<<year;
    return output.str();
}

Date::~Date(){
    cout<<"date object destructor for date"<<toString()<<endl;
}

unsigned int Date::checkDay(int testDay) const {
    static const array<int, monthsPerYear + 1> daysPerMonth{
        0,31,28,31,30,31,30,31,31,30,31,30,31};
    if(testDay>0&&testDay<=daysPerMonth[month]){
        return testDay;
    }
    if (month==2&&testDay==29&&(year%400==0||(year%4==0&&year%100!=0))){
        return testDay;
    }
    throw invalid_argument("Invalid day for current month and year");
}
```

```c++
//Employ.h
#include <string>

#ifndef TEST_10_17_EMPLOYEE_H
#define TEST_10_17_EMPLOYEE_H

#include <string>
#include "Date.h"

class Employee{
public:
    Employee(const std::string&,const std::string&,const Date&,const Date&);
    std::string toString() const;
    ~Employee();

private:
    std::string firstName;
    std::string lastName;
    const Date birthDate;
    const Date hireDate;
};
#endif //TEST_10_17_EMPLOYEE_H
```

```c++
//Employ.cpp
#include <iostream>
#include <sstream>
#include "Employee.h"
#include "Date.h"
using namespace std;

Employee::Employee(const std::string& first, const std::string& last, const Date &dateOfBirth, const Date &dateOfHire)
    :firstName(first),lastName(last), birthDate(dateOfBirth), hireDate(dateOfHire){
    cout<<"Employee object constructor: "<<firstName<<' '<<lastName<<endl;
}

string Employee::toString() const {
    ostringstream output;
    output<<lastName<<", "<<firstName<<" Hired: "<<hireDate.toString()<<" birthday: "<<birthDate.toString();
    return output.str();
}

Employee::~Employee(){
    cout<<"Employee object destructor: "<<lastName << ", " << firstName << endl;
}
```

```c++
//main.cpp
#include <iostream>
#include "Date.h"
#include "Employee.h"
using namespace std;


int main() {
    Date birth{7,24,1949};
    Date hire{3,12,1988};
    Employee manager{"Bob","Blue",birth,hire};

    cout<<"\n"<<manager.toString()<<endl;
}
```

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231019094400439.png" alt="image-20231019094400439" style="zoom:50%;" />
</div>

在一个类中包含其他类的对象，就叫做composition(组合)(or aggregation(聚合)）。现在，我们展示了一个类的构造函数如何通过成员初始化子(member initializers)将参数传递给成员对象构造函数。

**数据成员按照在类定义(不是按照它们在构造函数member-initializer list的顺序)中声明的顺序进行构造，并在构造其包含的类对象之前进行构造。**

#### 8.11.1 类的默认副本构造函数

在类class的定义内，构造函数没有接收Date类型的形参，那么，Employee构造函数的成员初始化列表为什么可以通过向Date类的构造函数传递Date类的对象来初始化birthDate和hireDate。正如我们在之前提到的，编译器为每个类提供了一个默认的复制构造函数，它将构造函数的参数对象的每个数据成员复制到被初始化对象的相应成员中。

即，birth和hire均是Date的对象，Employee的对象manager将对象birth和hire作为实参传递给Employee的构造函数，在Employee的构造函数的成员初始化列表里，将Date对象dateOfBirth和dateOfHire传递给在Employee类中定义的private数据成员，此数据成员即为const的Date对象birthDate和hireDate。问题在于，Date类的构造函数并没有接收对象的形参，原因就在于类的默认副本构造函数。

上诉运行的结果，可以看出析构函数执行的顺序。这些输出证实了Employee对象是从外部被销毁的，即Employee析构函数先运行(输出显示从输出窗口底部开始的五条线)，然后成员对象被破坏的顺序与它们被构造的顺序相反。

string类的析构函数不包含输出语句。

#### 8.11.2 如果不使用成员初始化列表？

如果一个成员对象不通过成员初始化列表初始化，成员对象的默认构造函数会被隐式调用。默认构造函数建立的值(如果有的话)可以用set函数重写。然而，对于复杂的初始化，这种方法可能需要大量的额外工作和时间。

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231019095345124.png" alt="image-20231019095345124" style="zoom:50%;" />
</div>

如果一个数据成员是另一个类的对象，public该成员对象并不违反对该成员对象private成员的封装和隐藏。但是，它却违背了封装类实现的封装性和隐藏性，所以类的成员对象仍然应该是private的。

### 8.12 友元函数和友元类(friend Functions and friend Classes)

**类的友元函数是一个非成员函数，有权访问类的public和non-public成员。** 单独的函数，整个类或者其他类的成员函数都可以被声明为其他类的friends。**友元的目的**就是让一个函数或者类访问另一个类中的private成员

在当前类以外定义的、不属于当前类的函数也可以在类中声明，但要在前面加 friend 关键字，这样就构成了友元函数。友元函数可以是不属于任何类的非成员函数，也可以是其他类的成员函数。

友元函数可以访问当前类中的所有成员，包括 public、protected、private 属性的。

还可以将整个类声明为另一个类的“friend”，这就是友元类。友元类中的所有成员函数都是另外一个类的友元函数。类的友元关系是单向的。例如：如果声明B类是A类的友元，B类的成员函数就可以访问A类的私有和保护数据，但A类的成员函数却不能访问B类的私有保护数据。

#### 8.12.1 友元的声明

将classTwo声明为classOne的友类，只要在classOne的定义中声明如下语句：

```c++
friend class ClassTwo;
```

friend的声明可以出现在类的任意位置，不受访问限定符public和private和protected的影响。友谊是被给予的，而不是被接受的——为了让B类成为a类的朋友，a类必须明确声明B类是它的朋友。友谊不是对称的，如果A类是B类的朋友，你就不能推断B类是A类的朋友。友谊是不可传递的——如果A类是B类的朋友，B类是C类的朋友——你就不能推断出A类是C类的朋友。

#### 8.12.2 通过友元函数修改类的private成员

```c++
#include <iostream>
using namespace std;

class Count{
   friend void setX(Count&,int);
public:
    int getX() const{return x;}
private:
    int x{0};
};

void setX(Count& c,int val){
    c.x=val;
}

int main(){
    Count counter;
    cout<<"counter.x after instantiation: " << counter.getX() << endl;
    setX(counter,8);//25 set x using a friend function 友元函数直接在main函数中调用
    cout<<"counter.x after call to setX friend function: "
    <<counter.getX()<<endl;
}
```

setX函数是一个独立(全局)函数，不是Count类的成员函数。由于此原因，当setX函数被counter对象调用，19行的语句将counter作为实参传给setX，而不是使用对象的名字调用函数---例如(counter.setX(8))。函数setX被允许访问类Count的私有数据成员x，只是因为setX被声明为该类的friend。

可以将重载函数指定为类的友元。每个想要成为友元的函数都必须在类定义中明确声明为类的友元。

即使友元函数的原型出现在类定义中，友元也不是成员函数。

**将所有friend声明首先放在类定义的主体内，并且不要在它们之前使用任何访问说明符。**

**友元类和友元函数打破了类的封装性**

### 8.13 使用this指针

每个类的功能只有一个副本，但一个类可以有很多对象，那么成员函数如何知道要操作哪个对象的数据成员呢？每个对象都可以通过一个名为this（C++关键字）的指针访问自己的地址。this指针不是对象本身的一部分，也就是说，this指针占用的内存不会反映在对象的sizeof操作的结果中。相反，this指针（由编译器）作为隐式参数传递给对象的每个**非静态成员函数**。后续介绍了静态类成员，并解释了为什么this指针没有隐式传递给静态成员函数。

**this 是 C++ 中的一个关键字，也是一个 const 指针，它指向当前对象，通过它可以访问当前对象的所有成员。**

**所谓当前对象，是指正在使用的对象。例如对于​**​**`stu.show();`**​ ，stu 就是当前对象，this 就指向 stu。this 只能用在类的内部，通过 this 可以访问类的所有成员，包括 private、protected、public 属性的。**

**this 虽然用在类的内部，但是只有在对象被创建以后才会给 this 赋值，并且这个赋值的过程是编译器自动完成的，不需要用户干预，用户也不能显式地给 this 赋值。**

#### 8.13.1 使用this指针避免命名冲突

```c++
void Time::setHour(int hour){
    if(hour>=0&&hour<24){
        this->hour=hour;
    }
    else{
        throw invalid_argument("hour must be 0-23");
    }
}
```

**一种通常的显式的使用this指针的方法是防止类的数据成员和成员函数形参(或者是其他局部变量)的命名冲突**

例如，一个成员函数的局部变量和类的数据成员名字相同，如上述代码所示，局部变量被认为隐藏hide或遮盖shadow了数据成员---仅使用函数体内的局部变量的名字代表局部变量而不是数据成员。但是可以使用->操作符访问数据成员。

```
this->hour=hour;
```

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231020105930121.png" alt="image-20231020105930121" style="zoom:50%;" />
</div>
#### 8.13.2 this指针的类型

this指针的类型取决于对象的类型，以及在其中使用this指针的成员函数是否声明为const:

1.在Employee类的non-const成员函数中，this指针的类型为Employee* const——一个指向nonconstant Employee的constant指针。

2.在const成员函数，this指针的类型为const Employee* const——指向constant Employee的constant指针。

#### 8.13.3 隐式和显式的使用this指针访问对象的数据成员

```c++
#include <iostream>
using namespace std;

class Test{
public:
    explicit Test(int);
    void print() const;
private:
    int x{0};
};

Test::Test(int value)
    :x{value} {
}

void Test::print() const {
    cout << " x = " << x;
    cout << "\n this->x = " << this->x;
    cout << "\n(*this).x = " << (*this).x << endl;
}

int main() {
    Test testObject{12};
    testObject.print();
}
```

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231020111211205.png" alt="image-20231020111211205" style="zoom:50%;" />
</div>

this指针的一个有趣的用途是防止对象被分配给它自己

#### 8.13.4 使用this指针完成级联函数(Cascaded Function)调用

this指针的另一个用途是启用级联成员函数调用——也就是说，在同一语句中顺序调用多个函数。

```cpp
//
// Created by 22364 on 2023/10/20.
//
#include <string>

#ifndef TEST_10_20_TIME_H
#define TEST_10_20_TIME_H

class Time{
public:
    explicit Time(int=0,int=0,int=0);

    Time& setTime(int,int,int);
    Time& setHour(int);
    Time& setMinute(int);
    Time& setSecond(int);

    unsigned int getHour() const;
    unsigned int getMinute() const;
    unsigned int getSecond() const;
    std::string toUniversalString() const;
    std::string toStandardString() const;
private:
    unsigned int hour{0};
    unsigned int minute{0};
    unsigned int second{0};

};
#endif //TEST_10_20_TIME_H
```

```c++
#include <iomanip>
#include <sstream>
#include <stdexcept>
#include "Time.h"
using namespace std;

Time::Time(int hr, int min, int sec) {
    setTime(hr, min, sec);
}

Time& Time::setTime(int h, int m, int s){
    setHour(h);
    setMinute(m);
    setSecond(s);
    return *this;
}

Time& Time::setHour(int h){
    if (h >= 0 && h < 24){
        hour = h;
    }
    else{
        throw invalid_argument("hour must be 0-23");
    }
    return *this;
}

Time& Time::setMinute(int m){
    if (m >= 0 && m < 60){
        minute = m;
    }
    else{
        throw invalid_argument("minute must be 0-59");
    }
    return *this;
}
Time& Time::setSecond(int s){
    if (s >= 0 && s < 60){
        second = s;
    }
    else{
        throw invalid_argument("second must be 0-59");
    }
    return *this;
}

unsigned int Time::getHour() const {return hour;}

unsigned int Time::getMinute() const {return minute;}

unsigned int Time::getSecond() const {return second;}

string Time::toUniversalString() const{
    ostringstream output;
    output << setfill('0') << setw(2) << getHour() << ":"
    <<setw(2) << getMinute() << ":" << setw(2) << getSecond();
    return output.str();
}

string Time::toStandardString() const{
    ostringstream output;
    output << ((getHour() == 0 || getHour() == 12) ? 12 : getHour() % 12)
    <<":" << setfill('0') << setw(2) << getMinute() << ":" << setw(2)
    <<getSecond() << (hour < 12 ? " AM" : " PM");
    return output.str();
}
```

```c++
#include <iostream>
#include "Time.h"
using namespace std;

int main(){
    Time t;
    t.setHour(18).setMinute(30).setSecond(22);// cascaded function calls

    cout<<"Universal time: " << t.toUniversalString()
    <<"\nStandard time: " << t.toStandardString();

    cout<<"\n\nNew standard time: "
    <<t.setTime(20, 20, 20).toStandardString()<<endl;//cascading
}
```

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231020140215461.png" alt="image-20231020140215461" style="zoom:50%;" />
</div>
### 8.14 static类成员(静态成员)

这个规则有一个重要的例外，即类的每个对象都有自己的类的所有数据成员的副本。在某些情况下，类的所有对象只应共享变量的一个副本。使用静态数据成员是出于这些和其他原因。这样的变量表示“类范围”的信息，即由所有实例共享的数据，并且不特定于类的任何一个对象。即，静态数据成员为该类的所有对象共享，静态数据成员具有静态生存期。

#### 8.14.1 Motivating Classwide Data

当一个类的所有对象都有一个数据副本就足够了时，使用静态数据成员来节省存储空间，比如一个可以由该类所有对象共享的常量。

#### 8.14.2 static数据成员的范围和初始化

**基本类型静态数据成员默认初始化为0。** 如果静态数据成员是提供默认构造函数的类的对象，则无需初始化该静态数据成员，因为将调用其默认构造函数。静态成员变量只能放在所有成员函数的外部进行初始化。

1.声明为“constexpr”类型的静态数据成员必须在类中声明并初始化。

2.声明为“inline”(C++17起)或者“const int”类型的静态数据成员**可以**在类中声明并初始化。

3.其他情况下，静态数据成员必须在类的外部进行定义并初始化，且不带static关键字。

#### 8.14.3 访问静态数据成员

通常使用类的public的成员函数或者fridends访问类的private(以及protected)静态成员。类的静态成员存在，即使不存在该类的对象。要在不存在类的对象时访问public静态类成员，只需在数据成员的名称前面加上类名和作用域解析运算符（::）。例如，如果我们前面的变量martianCount是公共的，则可以使用表达式Martian:：martianCount来访问它，即使在没有火星对象的情况下也是如此。   **（当然，不鼓励使用公共数据。）**

要在不存在私有或受保护的静态类成员的对象时访问该类成员，请提供一个公共静态成员函数，并通过在其名称前加类名和作用域解析运算符来调用该函数。静态成员函数是类的服务，而不是类的特定对象的服务。

**类的静态数据成员和静态成员函数存在，即使没有实例化该类的对象，也可以使用。**

![image](assets/image-20231130210625-et66nze.png)​

例如以下代码：

```cpp
class A{
public:
    A(int a=0){
        x=a;
    }
    static void f1();
    static void f2(A a);
private:
    int x;
    static int y;
};
void A::f2(A a){
    cout<<A::y;
	cout<<x;//error 静态成员函数访问非静态成员变量，只能通过对象的名字访问
	cout<<a.x;//right
}
void A::f1(){
	cout<<A::y<<endl;
}
int main(){
	A::f1();
	A mA(3);
	A::f2(mA);
	mA.A::f1();
}
```

当变量和函数不依赖于类的实例时，在类中使用静态成员。

#### 8.14.4 Demonstrating static Data Members

```c++
#ifndef TEST_10_20_2_EMPLOYEE_H
#define TEST_10_20_2_EMPLOYEE_H
#include <string>

class Employee{
public:
    Employee(const std::string&,const std::string&);
    ~Employee();
    std::string getFirstName() const;
    std::string getLastName() const;

    static unsigned int getCount();
private:
    std::string firstName;
    std::string lastName;

    static unsigned int count;
};
#endif //TEST_10_20_2_EMPLOYEE_H
```

```c++
#include <iostream>
#include "Employee.h"
using namespace std;

unsigned int Employee::count{0};

unsigned int Employee::getCount() {return count;}

Employee::Employee(const std::string& first, const std::string& last)
    :firstName(first),lastName(last){
    ++count;
    cout << "Employee constructor for " << firstName
    <<' ' << lastName << " called." << endl;
}

Employee::~Employee(){
    cout<<"~Employee() called for " << firstName
    <<' ' << lastName << endl;
    --count;
}

string Employee::getFirstName() const {return firstName;}

string Employee::getLastName() const {return lastName;}
```

```c++
#include <iostream>
#include "Employee.h"
using namespace std;

int main() {
    cout<<"Number of employees before instantiation of any objects is "
    <<Employee::getCount()<<endl;
    {
        Employee e1{"Susan","Baker"};
        Employee e2{"Robert","Jones"};

        cout<<"Number of employees after objects are instantiated is "
        <<Employee::getCount();

        cout<<"\n\nEmployee 1: "
        <<e1.getFirstName() << " " << e1.getLastName()
        <<"\nEmployee 2: "
        <<e2.getFirstName() << " " << e2.getLastName() << "\n\n";
    }

    cout << "\nNumber of employees after objects are deleted is "
    <<Employee::getCount()<<endl;
}
```

通过上图可以看到，在Employee的对象创造之前，就使用了getCount函数，在Employee对象销毁后，仍然可以使用getCount函数。**如果成员函数不访问类的非静态数据成员或非静态成员函数，则应将其声明为静态。与非静态成员函数不同，静态成员函数没有this指针，因为静态数据成员和静态成员函数独立于类的任何对象而存在。this指针必须引用类的特定对象，并且当调用静态成员函数时，内存中可能没有该类的任何对象。**

**Declaring a static member function const is a compilation error.**    The const qualifier indicates that a function cannot modify the contents of the object on which it operates, but static member functions exist and operate independently of any objects of the class.

##### 8.15.4.1 nested scope

If two different entities named by the same identifier are in scope at the same time, and they belong to the same name space, the scopes are nested (no other form of scope overlap is allowed), and the declaration that appears in the inner scope hides the declaration that appears in the outer scope:

```c++
// The name space here is ordinary identifiers.
 
int a;   // file scope of name a begins here
 
void f(void)
{
    int a = 1; // the block scope of the name a begins here; hides file-scope a
    {
      int a = 2;         // the scope of the inner a begins here, outer a is hidden
      printf("%d\n", a); // inner a is in scope, prints 2
    }                    // the block scope of the inner a ends here
    printf("%d\n", a);   // the outer a is in scope, prints 1
}                        // the scope of the outer a ends here
 
void g(int a);   // name a has function prototype scope; hides file-scope a
```

#### 8.14.5 命名空间

##### 8.14.5.1 概述

**在c++中，名称（name）可以是符号常量、变量、函数、结构、枚举、类和对象等等。工程越大，名称互相冲突性的可能性越大。另外使用多个厂商的类库时，也可能导致名称冲突。为了避免在大规模程序的设计中，以及在程序员使用各种各样的C++库时，这些标识符的命名发生冲突，标准C++引入关键字namespace（命名空间/名字空间/名称空间），可以更好地控制标识符的作用域。**

##### 8.14.5.2 定义

```c++
//定义一个名字为A的命名空间（变量、函数）
namespace A {
    int a = 100;
}
namespace B {
    int a = 200;
}
void test02()
{
    //A::a  a是属于A中
    cout<<"A中a = "<<A::a<<endl;//100
    cout<<"B中a = "<<B::a<<endl;//200
}
```

##### 8.14.5.3 命名空间只能全局范围内定义（以下为错误写法）

<div>
<img src="https://pic4.zhimg.com/v2-abe9b1f908fc537a25d6205eb4e4b193_r.jpg" alt="img" style="zoom:50%;" />
</div>
##### 8.14.5.4 命名空间可以嵌套

```c++
namespace A {
    int a = 1000;
    namespace B {
        int a = 2000;
    }
}
void test03()
{
    cout<<"A中的a = "<<A::a<<endl; //1000
    cout<<"B中的a = "<<A::B::a<<endl; //2000
}
```

##### 8.14.5.5 命名空间是开放的，即可以随时把新的成员加入已有的命名空间中(常用)

```c++
namespace A {
    int a = 100;
    int b = 200;
}
//将c添加到已有的命名空间A中
namespace A {
    int c = 300;
}
void test04()
{
    cout<<"A中a = "<<A::a<<endl;//100
    cout<<"A中c = "<<A::c<<endl;//200
}
```

##### 8.14.5.6 命名空间 可以存放 变量 和 函数

```c++
namespace A {
    int a=100;//变量
 
    void func()//函数
    {
        cout<<"func遍历a = "<<a<<endl;
    }
}
void test05()
{
    //变量的使用
    cout<<"A中的a = "<<A::a<<endl;
 
    //函数的使用
    A::func();
}
```

##### 8.14.5.7 命名空间中的函数 可以在“命名空间”外 定义

```c++
namespace A {
    int a=100;//变量
 
    void func();
}
 
void A::func()//成员函数 在外部定义的时候 记得加作用域
{
    //访问命名空间的数据不用加作用域
    cout<<"func遍历a = "<<a<<endl;
}
 
void funb()//普通函数
{
    cout<<"funb遍历a = "<<A::a<<endl;
}
void test06()
{
   A::func();
    funb();
}
```

无名命名空间，意味着命名空间中的标识符只能在本文件内访问，相当于给这个标识符加上了static，使得其可以作为内部连接（了解）

```c++
namespace{
    int a = 10;
    void func(){
        cout<<"hello namespace"<<endl;
    }
}
void test(){
 
    //只能在当前源文件直接访问a 或 func
    cout<<"a = "<<a<<endl;
    func();
}
```

### 8.15 对象数组

声明方式1：

```cpp
Circle ca1[10];
```

声明方式2：用匿名对象构成的列表初始化数组

```cpp
auto ca2[3]={Circle{3},Circle{},Circle{5}};
```

声明方式3：使用C++11列表初始化，列表成员为隐式构造的匿名对象

```cpp
Circle ca3[3]{3.1,{},5};
Circle ca4[3]={3.1,{},5};
```

声明方式4：用new在堆区生成对象数组

```cpp
auto* p1=new Circle[3];
auto p2=new Circle[3]{3.1,{},5};
delete []p1;
delete []p2;
p1=p2=nullptr;
```



## 9. 运算符重载

本章展示了如何使C++的运算符能够处理类对象--一个称为运算符重载的过程。当运算符作用于类类型的运算对象时，可以通过运算符重载重新定义该运算符的含义。明智的使用运算符重载能令我们的程序更易于编写和阅读。

### 9.1 使用标准类库string中的重载操作符

```c++
#include <iostream>
#include <string>
using namespace std;

int main(){
    string s1{"happy"};
    string s2{"birthday"};
    string s3;// creates an empty string

    cout<<"s1 is \"" <<s1<< "\"; s2 is \""<<s2
    <<"\"; s3 is \""<<s3<<'\"'
    <<"\n\nThe results of comparing s2 and s1:"<<boolalpha
    <<"\ns2 == s1 yields "<<(s2==s1)
    <<"\ns2 != s1 yields "<<(s2!=s1)
    <<"\ns2 > s1 yields "<<(s2>s1)
    <<"\ns2 < s1 yields "<<(s2<s1)
    <<"\ns2 >= s1 yields "<<(s2>=s1)
    <<"\ns2 <= s1 yields "<<(s2<=s1);

    cout<<"\n\ntesting s3.empty():\n";

    if(s3.empty()){
        cout<<"s3 is empty;assigning s1 to s3;\n";
        s3=s1;
        cout<<"s3 is \""<<s3<<"\"";
    }

    cout << "\n\ns1 += s2 yields s1 = ";
    s1 += s2; // test overloaded concatenation
    cout << s1;

    cout << "\n\ns1 += \" to you\" yields\n";
    s1 += " to you";//39行
    cout << "s1 = " << s1;

    // test string concatenation with a C++14 string-object literal
    cout << "\n\ns1 += \", have a great day!\" yields\n";
    s1 += ", have a great day!"s;
    cout << "s1 = " << s1 << "\n\n";

    cout << "The substring of s1 starting at location 0 for\n"
    <<"14 characters, s1.substr(0, 14), is:\n"
    <<s1.substr(0, 14)<<"\n\n";

    cout << "The substring of s1 starting at\n"
    <<"location 15, s1.substr(15), is:\n"<<s1.substr(15)<<"\n";

    // test copy constructor
    string s4{s1};
    cout << "\ns4 = " << s4 << "\n\n";

    // test overloaded copy assignment (=) operator with self-assignment
    cout << "assigning s4 to s4\n";
    s4=s4;
    cout << "s4 = " << s4;

    s1[0] = 'H';
    s1[6] = 'B';
    cout << "\n\ns1 after s1[0] = 'H' and s1[6] = 'B' is:\n"
    <<s1<<"\n\n";

    try{
        cout<<"attempting to assign 'd' to s1.at(100) yields:\n";
        s1.at(100)='d';
    }
    catch(out_of_range& x){
        cout<<"An exception occurred: " << x.what() << endl;
    }
}
```

运行结果如下：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231023153044650.png" alt="image-20231023153044650" style="zoom:50%;" />
</div>

s3使用默认的string构造函数创造空字符串。

used the stream manipulator boolalpha to set the output stream to display condition values as the strings "false" and "true".

string的成员函数，如果字符串为空，则返回true,反之，返回false。

string的成员函数substr,返回string对象的一部分。

函数 at() 在使用时会检查下标是否有效。如果给定的下标超出字符的长度范围，系统会抛出 out_of_range 异常。

1.如果at函数被non-const对象调用，此函数会返回一个可修改的左值，可以用在赋值操作符的左侧，可以赋给那个位置新的值。

2.如果at函数被const string对象调用，函数会返回一个不可修改的左值。只能获得那个值，而不能修改。

#### 9.1.1 string类中的函数

[c++ string 的常用库函数的用法_c++ string arg-CSDN博客](https://blog.csdn.net/usstmiracle/article/details/107688331)

#### 9.1.2 运算符与函数

**1.Special Operators Usage with Objects (与对象一起用的运算符)**

 1.1. string类：使用“+”连接两个字符串

```cpp
string s1("Hello"), s2("World!");

cout << s1 + s2 << endl;
```

1.2. array 与 vector类：使用[] 访问元素

```cpp
array<char, 3> a{};

vector<char> v(3, 'a'); //'a', 'a', 'a'

a[0] v[1] = 'b';
```

1.3. path类：使用“/”连接路径元素

```cpp
std::filesystem::path p**{};** 

p = p / "C:" / "Users" / "cyd";
```

**2.The operator vs function (运算符与函数的异同)**

2.1. 运算符可以看做是函数

2.2. 不同之处

2.2.1. 语法上有区别

```cpp
3 * 2        //中缀式

* 3 2       //前缀式

multiply(3,2); //前缀式

3  2  *        //后缀式(RPN)
```

2.2.2. 不能自定义新的运算符 (只能重载)

```cpp
3 ** 2    // C/C++中错误

pow(3, 2) // 3的平方
```

2.2.3. 函数可overload, override产生任何想要的结果，但运算符作用于内置类型的行为不能修改

```cpp
multiply (3, 2)  // 可以返回1

3 * 2            // 结果必须是6
```

2.3. 函数式编程语言的观念

一切皆是函数

Haskell中可以定义新的运算符

 

### 9.2 运算符重载基础

#### 9.2.1 运算重载不是自动的

必须编写运算符重载函数才可以执行所需的操作。运算符通过向往常一样编写non-static成员函数或者非成员函数来重载。只是函数名称以operator开头，后跟重载运算符的符号。例如，函数名为 operator+将用于重载运算符+，以便用于特定用户定义类型的对象。当运算符作为成员函数重载时，它们必须是non-static，因为它们必须在类的某个对象上被调用，并在该对象上进行操作。

#### 9.2.2 不需要进行重载的操作符

为了在一个类的对象上使用一个运算符，必须为该类定义重载的运算符函数-除了三个例外：

1.赋值操作符(=)，在大多数的类中用来数据成员的赋值。对于带指针成员的类，成员指派是危险的，因此我们将显式地重载此类类的指派运算符。

2.取地址操作符(&)

3.逗号操作符(,)

#### 9.2.3 不能进行重载的运算符

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231023174011287.png" alt="image-20231023174011287" style="zoom:50%;" />
</div>
sizeof运算符也不能重载。

#运算符不可以重载

#### 9.2.4 运算符重载的规则和限制

当你准备为自己的类重载运算符时，有几个规则和限制是你应该牢记的：

1.重载不会改变操作符的优先级

2.操作符的结合性不会因为重载而改变

3.An operator’s “arity” (that is, the number of operands an operator takes) cannot be changed

4.只有现存的操作符可以重载

5.不可以重载操作符以改变操作符对基本类型变量的作用，例如，不能让+表示两个整数相减。操作符重载仅仅工作在用户自定义的类的对象或者（用户自定义类型的对象和基本类型对象的混合）。**运算符作用于C++内部提供的数据类型时，原来含义保持不变**

6.像+和+=，必须单独重载

7.当重载( ),[ ],->或者任何赋值操作符时，操作符重载函数必须声明为类的成员。其他的情况，操作符重载函数可以是成员函数或者非成员函数。

<div>
<img src="https://ask.qcloudimg.com/http-save/7611843/si26ree8rw.png" alt="image" style="zoom:50%;" />
</div>
8.不能创造新的运算符

#### 9.2.5 运算符重载函数的格式

重载的运算符是具有特殊名字的函数：他们的名字由关键字operator和其后要定义的运算符号共同组成。和其他函数一样，重载的运算符也包括返回类型、参数列表以及函数体。

1.运算符重载函数作为类的成员函数

```cpp
函数类型 operator 重载运算符(形参列表){
    函数体;
}//形参个数=原操作数个数-1(后置++、--除外)
```

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231207132623880.png" alt="image-20231207132623880" style="zoom:80%;" />



<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231207132710812.png" alt="image-20231207132710812" style="zoom:80%;" />



<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231207132725372.png" alt="image-20231207132725372" style="zoom:80%;" />



2.运算符重载函数作为类的友元函数

```c++
friend 函数类型 operator 重载运算符(形参列表){
    函数体;
}
```

3.运算符重载为非成员函数

函数的形参代表自左向右排列的各操作数。

重载为非成员函数时，参数个数=原操作数个数(后置++、--除外)，至少应该有一个自定义类型的参数。

‍后置单目运算符++和--的重载函数，形参列表中要增加一个int，但不必写形参名。

如果在运算符的重载函数中需要操作某类对象的私有成员，可以将此函数声明为该类的友元

‍<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231207131648776.png" alt="image-20231207131648776" style="zoom: 80%;" />

“函数类型”指出重载运算符的返回值类型，operator是定义运算符重载函数的关键词，“重载运算符”指出要重载的运算符名字，是C++中可重载的运算符，比如要重载加法运算符，这里直接写“+”即可，“形参表”指出重载运算符所需要的参数及其类型。

### 9.3 重载一元运算符

#### 9.3.1 重载++和--运算符

“++”和“–”重载运算符也有前缀和后缀两种运算符重载形式，以“++”重载运算符为例，其语法格式如下：

```c++
函数类型 operator ++（）
```

```c++
函数类型 operator ++(int）
```

例如下述代码：

```c++
#include<iostream>
using namespace std;

class MyClass2
{
public:
    MyClass2(int i){ n = i; }
    int operator ++(){ n++; return n; }
    int operator ++(int){ n += 2; return n; }
    void display()
    {
        cout << "n=" << n << endl;
    }
private:
    int n;
};

int main()
{
    MyClass2 A(5), B(5);
    A++;
    ++B;
    A.display();
    B.display();
    system("pause");
}

```

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231024154848627.png" alt="image-20231024154848627" style="zoom:50%;" />
</div>

#### 9.3.2 重载->运算符

“->”运算符是成员访问运算符，这种单目运算符只能被重载为成员函数，一般成员访问运算符的格式如下：

```c++
对象->成员
```

成员访问运算符“->”函数重载的一般形式为：

```c++
数据类型 类名::operator->();
```

例如下述代码：

```c++
#include <iostream>
using namespace std;

class PClass
{
    int n; double m;
public:
    PClass *operator->()
    {
        return this;
    }
    void setvalue(int n1, double m1)
    {
        n = n1; m = m1;
    }
    void disp()
    {
        cout<< "n=" << n << ",m=" << m<<endl;
    }
};

int main()
{
    PClass s;
    s->setvalue(10, 20.5);
    s->disp();
    s.setvalue(20, 89.8);
    s.disp();
}
```

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231024161051162.png" alt="image-20231024161051162" style="zoom:50%;" />
</div>

上述程序中，重载“->”运算符的成员函数，该函数返回当前对象的指针。从而导致“s->disp()；”和“s.disp();”两个语句都是正确的，实际上，前者通过调用重载“->”运算符成员函数转换成后者的格式。

### 9.4 重载二元操作符

二元操作符可以重载为含有一个形参的non-static成员函数或者重载为含两个形参(其中一个形参必须是类的对象或者类的对象的引用)的非成员函数。一个非成员操作符函数经常因为性能原因被声明为类的friend。

##### 9.4.1 二元操作符重载函数(non static成员函数)

考虑使用<比较自行定义的属于string类的两个对象。当将二元运算符<重载为non-static成员函数，如果y和z是string类的对象，那么y<z会被编译器看作y.operator < (z)，y通过this指针传递，z通过参数传递。例如下列代码，重载<运算符：

```c++
class String{
public：
    bool operator<(const String&) const
    ...
};
```

**只有当二元操作符的左操作数是类的对象，二元操作符的重载函数才可以是类的成员函数。**

若要将二元运算符函数声明为非静态成员函数，您必须用以下形式声明它：

> ret-type **`operator`** op(arg)

其中，ret-type 是返回类型，op 是上表中列出的运算符之一，而 arg 必须是类的对象。

##### 9.4.2 二元操作符重载函数(非成员函数)

若要将二元运算符函数声明为全局函数，您必须用以下形式声明它：

> ret-type **`operator`** op(arg1,arg2)

其中，ret-type 和 op 是成员运算符函数，而 arg1 和 arg2 是自变量。 至少有一个参数必须是类的对象(或者是对象的引用)。

对二元运算符的返回类型没有限制；但是，大多数用户定义的二元运算符将返回类类型或对类类型的引用。

如果y和z都是类的对象或者对象的引用，编译器会看作operator<(y,z)

```c++
bool operator<(const String&, const String&);
```

### 9.5 重载二元流插入和提取操作符

```c++
#ifndef TEST_10_24_PHONENUMBER_H
#define TEST_10_24_PHONENUMBER_H

#include <iostream>
#include <string>

class PhoneNumber{
    friend std::ostream& operator<<(std::ostream&,const PhoneNumber&);
    friend std::istream& operator>>(std::istream&,PhoneNumber&);
private:
    std::string areaCode;
    std::string exchange;
    std::string line;
};
#endif //TEST_10_24_PHONENUMBER_H
```

```c++
//
// Created by 22364 on 2023/10/24.
//
#include <iomanip>
#include "PhoneNumber.h"
using namespace std;

ostream& operator<<(ostream& output,const PhoneNumber& number){
    output << "Area code: " << number.areaCode << "\nExchange: "
    <<number.exchange << "\nLine: " << number.line << "\n"
    <<"(" << number.areaCode << ") " << number.exchange << "-"
    <<number.line << "\n";
    return output;// enables cout << a << b << c;
}
// overloaded stream extraction operator; cannot be a member function
// if we would like to invoke it with cin >> somePhoneNumber;
istream& operator>>(istream& input, PhoneNumber& number){
    input.ignore();
    input >> setw(3) >> number.areaCode;
    input.ignore(2);
    input >> setw(3) >> number.exchange;
    input.ignore();
    input >> setw(4) >> number.line;
    return input;
}
```

```c++
#include <iostream>
#include "PhoneNumber.h"
using namespace std;

int main(){
    PhoneNumber phone;

    cout<<"Enter phone number in the form (555) 555-5555:"<<endl;

    // cin >> phone invokes operator>> by implicitly issuing
    // the non-member function call operator>>(cin, phone)
    cin>>phone;

    // cout << phone invokes operator<< by implicitly issuing
    // the non-member function call operator<<(cout, phone)
    cout<<phone<<endl;
}
```

在第二张图中，对于<<的重载函数的定义，当在mian函数中调用此函数后，引用形参input就变成了cin的alias，引用参数number就变成了phone的alias.由于两个函数都被声明为类的friend,所以可以访问类的private成员。流操作符setw限制了读入string的字符。When used with cin and strings, setw restricts the number of characters read to the number of characters specified by its argumen t (i.e., setw(3) allows three characters to be read).调用istream的成员函数ignore可以略过括号、空格和破折号。

dash characters---破折号

```c++
cin>>phone
```

相当于：

```
operator>>(cin,phone)
```

```c++
cout<<phone
```

相当于：

```c++
operator<<(cout,phone)
```

operator<<和operator>>函数都被声明为非成员friend函数，他们是非成员函数是因为PhoneNumber类的对象必须是操作符的右操作数。**二元操作符的重载函数只有在左操作符是类的对象时才可以成为类的成员函数。Overloaded operator functions for binary operators can be member functions only when the left operand is an object of the class in which the function is a member.**

**成员函数重载：可以通过this指针访问本类的成员，可以少写一个参数，但是表达式左边的的第一个参数必须是类对象，通过该类对象来调用成员函数。即表达式左侧的左侧操作数就是对象本身。例如对于cout​<<classobject,classobject是用户自定义的类的对象，通过该类调用成员函数，即使用cout对象调用operator<<函数，这样的话，operator<<​需要是cout对象从属的ostream类的成员函数，但是ostream类属于C++的标准库类，不允许修改。因此，如果右操作数是用户自定义的类的对象，必须将<​<重载为非成员函数。**

### 9.6 重载一元操作符

一元操作符可以重载为没有参数的non-static成员函数或者一个参数的非成员函数。此参数必须是对象或者对象的引用。成员函数必须是non-static 的才可以访问类的每个队形的non-static成员。

##### 9.6.1 重载一元操作符函数作为成员函数

考虑重载一元操作符!，以此检验输入的string类的对象是否为空。这个函数会返回一个bool值。例如将操作符!重载函数重载为成员函数(没有参数)，对于对象s,!s,编译器会将之认为s.operator!( )，操作数s是string类的对象，operator!为string类的成员函数。

```c++
class String{
public:
    bool operator!() const;
    ...
};
```

##### 9.6.2一元操作符重载函数为非成员函数

还是考虑string类的对象s,s必须是类的对象或者对象的引用。!s会被编译器认为是：operator!(s)

```c++
bool operator!(const String&);
```

### 9.7 重载++和--

为了重载++和--操作符，编译器需要区分操作符是操作数的前缀还是后缀，因此重载函数必须有明显的特征以供编译器区分。

##### 9.7.1 前缀递增操作符重载

考虑将整数1加到Date类的对象d1上。如果重载函数被定义为成员函数，编译器会生成成员函数调用：

```c++
d1.operator++();
```

此成员函数的原型为：

```cpp
Date& operator++();//类名后的&必不可少
```

如果重载函数被声明为非成员函数，编译器会生成函数调用：

```c++
operator++(d1);
```

此函数的函数原型为：

```c++
Date& operator++(Date&);
```

##### 9.7.2 后缀递增操作符重载

为了与前缀进行区分，对于d1++，编译器会生成成员函数调用：

```c++
d1.operator ++ (0);//0只用来区分前缀和后缀操作
```

函数原型为：

```c++
Date operator ++ (int);//在实现此函数时，不应该使用括号内的整型形参
```

**参数0是一个虚职，为了让编译器区分前缀和后缀。**如果后缀操作符重载函数为非成员函数，当编译器遇到d1++，会生成函数调用：

```c++
operator++(d1,0)
```

函数原型为：

```c++
Date operator++(Date&,int);
```

x++最终返回的是临时变量的值，而临时变量的值不能作为左值。x++是右值，编译器会先生成一份x值的临时复制，然后再对x递增，最后返回临时复制内容。++x不同，是对x递增后马上返回其自身，所以++x是左值。

**The extra object that’s created by the postfix increment (or decrement) operator can result in a performance problem—especially when the operator is used in a loop. For this reason, you should prefer the overloaded prefix increment and decrement operators.**



leap year---闰年

Wrap-around Error：当值的增量超过其类型的最大值时，就会发生环绕错误，进而导致“环绕”到非常小、负值或未定义的值。

helpIncrement函数用来防止出现上述错误。

### 9.8 动态内存管理(Dynamic Memory Management)和nullptr

可以控制内置或者用户自定义类型的对象或者数组的内存的分配和释放。这就叫做动态内存管理，使用操作符new和delete实现。可以使用new操作符在程序执行期间动态的分配精确数量的内存来存储对象或者数组。对象或内置数组在自由存储区(free store)创造，自由存储区是内存中分配给程序用来存储对象的区域。**new和delete都是运算符，不是库函数**，不需要单独添加头文件。

#### 9.8.1 free store VS heap

[C++ 自由存储区是否等价于堆？ - melonstreet - 博客园 (cnblogs.com)](https://www.cnblogs.com/QG-whz/p/5060894.html)

当我问你C++的内存布局时，你大概会回答：

> “在C++中，内存区分为5个区，分别是堆、栈、自由存储区、全局/静态存储区、常量存储区”。

如果我接着问你自由存储区与堆有什么区别，你或许这样回答：

> “malloc在堆上分配的内存块，使用free释放内存，而new所申请的内存则是在自由存储区上，使用delete来释放。”

这样听起来似乎也没错，但如果我接着问：

> 自由存储区与堆是两块不同的内存区域吗？它们有可能相同吗？

你可能就懵了。

事实上，我在网上看的很多博客，划分自由存储区与堆的分界线就是new/delete与malloc/free。然而，尽管C++标准没有要求，但很多编译器的new/delete都是以malloc/free为基础来实现的。那么请问：借以malloc实现的new，所申请的内存是在堆上还是在自由存储区上？

从技术上来说，堆（heap）是C语言和操作系统的术语。堆是操作系统所维护的一块特殊内存，它提供了动态分配的功能，当运行程序调用malloc()时就会从中分配，稍后调用free可把内存交还。而自由存储是C++中通过new和delete动态分配和释放对象的抽象概念，通过new来申请的内存区域可称为自由存储区。基本上，所有的C++编译器默认使用堆来实现自由存储，也即是缺省的全局运算符new和delete也许会按照malloc和free的方式来被实现，这时藉由new运算符分配的对象，说它在堆上也对，说它在自由存储区上也正确。但程序员也可以通过重载操作符，改用其他内存来实现自由存储，例如全局变量做的对象池，这时自由存储区就区别于堆了。我们所需要记住的就是：

> 堆是操作系统维护的一块内存，而自由存储是C++中通过new与delete动态分配和释放对象的抽象概念。堆与自由存储区并不等价。

一旦内存分配完毕，就可以通过new返回的指针访问它。当不再需要此内存，就可以通过delete将它返回到自由存储区以释放内存。

#### 9.8.2 使用new获取动态内存

new 运算符的用法如下：

```c++
Time* timePtr{new Time};
new <类型名>(初值);//申请一个变量的空间
new <类型名>[常量表达式];//申请数组
```

Time是任意类型名，timePtr是类型为Time*的指针。这样的语句会动态分配出一片大小为 sizeof(Time) 字节的内存空间，并且将该内存空间的起始地址赋值给 timePtr。如果要求分配的空间太大，操作系统找不到足够的内存来满足，那么动态内存分配就会失败，此时程序会拋出异常，或者返回空指针nullptr。

例如：

```c++
int* p;
p = new int;
*p = 5;

int *aPtr=new int[8];
int* arr1 = new int[5];
int* nums1 = new int[5] { 1, 3, 2, 5, 4 };
```

第二行动态分配了一片 4 个字节大小的内存空间，而 p 指向这片空间。通过 p 可以读写该内存空间。

new运算符的初始化

```
int* buffer = new int{}; // 初始化为0
int* buffer = new int{0}; // 初始化为0
char* s=new char('a');
int* buffer = new int[512]{}; // 512个int都初始化为0
int* buffer = new int{5}; // 初始化为5
```

动态内存使用完毕以后，要使用delete运算符释放。销毁一个动态分配的对象并释放对象的内存，使用delete操作符：

```c++
delete <指针名>;//删除一个变量/对象
delete []<指针名>;//删除一个数组空间
```

不能删除未被new操作符分配的内存。这样做会导致未定义的行为。

**删除一个动态分配的内存块后，一定不要再删除同一个块。防止这种情况的一种方法是立即将指针设置为nullptr。删除nullptr没有影响。**

nullptr作为空指针

```cpp
int* q=nullptr;
```

C++保证用删除数组的形式删除非数组的内存分配是安全的，如下例：

```cpp
char* p=new char(32);
//可以使用下列两种方式删除
delete p;
delete [] p;
```

**Operators new and delete can be overloaded, but this is beyond the scope of the book. If you do overload new, then you should overload delete in the same scope to avoid subtle dynamic memory management errors.**

new和delete操作符也可以重载。如果重载了new，就要同时重载delete。

**动态分配出来的内存没有变量名，只能通过指向它的指针来操作内存中的数据。**

**动态分配的内存生命周期和程序相同，程序退出时，如果没有释放，系统会自动回收。**

**当动态分配的内存不再需要时，不释放动态分配的内存会导致系统过早耗尽内存。这有时被称为** “内存泄漏”

**当类的对象包含指向动态分配的内存的指针时，不提供拷贝构造函数以及重载赋值操作符是一个潜在的错误。**

#### 9.8.3 在堆中创建对象

在堆中创建对象，由程序员控制对象的生存期。

```cpp
ClassName *pObject=new ClassName{};//用无参构造函数创建对象
ClassName *pObject=new ClassName{arguments};//用有参构造函数创建对象
```



### 9.9 拷贝构造函数

The null terminated strings are basically a sequence of characters, and the last element is one null character (denoted by ‘\0’).

**对于动态分配内存的内置数组，range-based for不能正常工作**

**当类的对象包含指向动态分配的内存的指针时，不提供拷贝构造函数以及重载赋值操作符是一个潜在的错误。**

#### 9.9.1 拷贝构造函数

**它是一种特殊的构造函数，它在创建对象时，是使用同一类中之前创建的对象来初始化新创建的对象。****拷贝构造函数**就是函数名是当前类的名字，参数为当前类的另一个对象的函数，拷贝构造函数通常用于：

- 通过使用另一个同类的对象来初始化新创建的对象。
- 复制对象把它作为参数传递给函数。
- 复制对象，并从函数返回这个对象。

声明拷贝构造函数：

```cpp
Circle (Circle&);
Circle (const Circle&);
```

如果在类中没有定义拷贝构造函数，编译器会自行定义一个。编译器自定义生成的拷贝构造函数可以实现对应数据成员的复制。自定义的拷贝构造函数可以实现特殊的复制功能。 **当类中拥有指针类型的成员变量时，拷贝构造函数中需要以深拷贝（而非浅拷贝）的方式复制该指针成员。**

**The argument to a copy constructor should be a const reference to allow a const object to be copied.**

如果不希望对象被复制构造，可以使用"=delete"指示编译器不生成默认拷贝构造函数。例如：

```cpp
class Point{
public:
	Point(int xx=0,int yy=0){x=xx;y=yy;}//构造函数
	Point(const Point& p)=delete;
private:
	int x,y//私有数据
}
```

#### 9.9.2 浅拷贝和深拷贝

1.**浅拷贝**：拷贝指针，而非指针指向的内容。简单的复制拷贝操作。

以下两种情况会出现浅拷贝：

1.创建新对象时，调用类的隐式/默认构造函数。

2.为已有对象赋值时，使用赋值运算符。

2.**深拷贝**：拷贝指针指向的内容。在堆区重新申请内存空间，进行拷贝操作。当被复制的对象数据成员是指针类型时，不是复制该指针成员本身，而是将指针所指对象进行复制。

‍而使用移动语义和移动构造函数，可以避免深拷贝的情况，节省资源。

如何深拷贝：

1.自行编写拷贝构造函数，不使用编译器隐式生成的拷贝构造函数

2.重载赋值运算符，不使用编译器隐式生成的赋值运算符函数

#### 9.9.3 何时执行拷贝构造函数

1.用已有对象构造新对象的时候(通过使用另一个同类型的对象来初始化新创建的对象)

```c++
Student stu;//先定义一个对象
Student stu2(stu);//(1)会调用拷贝构造函数
Student stu3=stu ;//(2)会调用拷贝构造函数，这里和（1）是一样的，仅仅是写法不同而已
```

如果对象已经被创建，会调用赋值操作符而不是复制构造函数：

```cpp
Student stu;

Student stu2;//在这里被创建

stu2 = stu;//这里调用赋值操作符重载（见后文）
```

代码示例：

```cpp
#include <iostream>//cin cout
using namespace std;

class Student
{
public:
    //规则1：如果类的用户自己定义了构造函数
    // ，编译器就不会自动合成类的默认构造函数Student(void)
    //这样类就不存在默认构造函数了

    //类的用户自己定义了拷贝构造函数（拷贝构造函数也算是一个构造函数）
    //按照规则1，此时类不再拥有Student(void)这个函数
    Student(const Student& from)
    {
        cout << "copy constructor called." << endl;
    }

    //由于上面已经定义了一个构造函数，按照规则1，
    //Student stu;这条语句就会因为类不存在默认构造函数而编译报错
    //为了能够让我们可以写Student stu;这条语句来创建对象
    // ，我们在这里显示定义类的默认构造函数
    Student(void)
    {
        cout << "default constructor called." << endl;
    }
};

int main(int argv, char* argc[])
{
    cout << "flag1" << endl;//打印标记信息，用来查看函数执行的顺序
    Student stu;//先定义一个对象
    cout << "flag2" << endl;//打印标记信息，用来查看函数执行的顺序
    Student stu2(stu);//(1)会调用拷贝构造函数
    cout << "flag3" << endl;//打印标记信息，用来查看函数执行的顺序
    Student stu3 = stu;//(2)会调用拷贝构造函数，这里和（1）是一样的，仅仅是写法不同而已
    cout << "flag4" << endl;//打印标记信息，用来查看函数执行的顺序

    return 0;
}
```

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231029163045414.png" alt="image-20231029163045414" style="zoom:50%;" />
</div>
2.给函数传递值类型参数的时候(复制对象把它作为参数传递给函数)：调用函数时，将使用实参对象初始化形参对象，发生拷贝构造。
</div>

```cpp
void test_function(Student s)
{//s在该函数被调用的时候创建，该函数执行完之后释放
    s.m_name = "李四";//修改s的名字
}
int main()
{
    Student stu("张三");
    test_function(stu);//(1)创建stu的副本，函数内使用副本
    cout<<stu.m_name;//还是输出“张三”，因为修改的是，函数内的副本
}
```

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231029165803226.png" alt="image-20231029165803226" style="zoom: 50%;" />
</div>

完整代码：

```cpp
#include <iostream>//cin cout
#include <string>
using namespace std;

class Student
{
public:
    Student(const Student& from)//拷贝构造函数
    {
        cout << "copy constructor called." << endl;
    }
    //如果只提供上面的拷贝构造函数，编译器就不再生成默认构造函数
    //，会而导致类对象就不可以直接创建，所以还需要提供一个默认构造函数
    Student(void)
    {
        cout << "default constructor called." << endl;
    }
    Student(const string& name) :m_name(name)
    {
        cout << "string constructor called." << endl;
    }
    string m_name;//存放学生姓名
};
void test_function(Student s)
{//s在该函数被调用的时候创建，该函数执行完之后释放
    cout << "flag2" << endl;
    s.m_name = "李四";//修改s的名字
    cout << "flag3" << endl;
}//s释放的时刻
int main()
{
    cout << "flag0" << endl;
    Student stu("张三");
    cout << "flag1" << endl;
    test_function(stu);//(1)创建stu的副本，函数内使用副本
    cout << "flag4" << endl;
    cout << stu.m_name;//还是输出“张三”，因为修改的是，函数内的副本
}
```

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231029163210998.png" alt="image-20231029163210998" style="zoom:50%;" />
</div>

```cpp
#include <iostream>

using namespace std;

class Student {
public:
	Student();	// default构造函数
	Student(const Student& obj);	// 拷贝构造函数

	int getNumber();

private:
	int number;
};

// 定义默认构造函数
Student::Student(){
	this->number = 0;
    cout << "default constructor" << endl;
}

// 定义拷贝构造函数
Student::Student(const Student& obj) {
	this->number = obj.number;
    cout << "copy constructor" << endl;
}

int Student::getNumber() {
	return this->number;
}

// 输出某个对象的number
void showNumber(Student a) {
	cout << a.getNumber();
}

int main(){
	Student s;  // 调用默认构造函数
	showNumber(s);

	return 0;
}
```

你认为输出结果会是什么？首先肯定会输出一个"default constructor"，因为s的默认构造函数输出了该字符串。那么，showNumber()会输出什么呢？正确的输出是：

```cpp
default constructor
copy constructor
0
```

这就回到了我们开头的那句话，**拷贝构造函数定义了一个对象如何以值传递给函数**。

在函数showNumber()中，参数a是以值传递的方式传入的。所以主函数中调用showNumber()时，对象s被复制到了形参a当中。**这个复制操作是通过调用了拷贝构造函数完成的**，所以调用了自身的拷贝构造函数，自然会输出一遍"copy constructor"。

相当于执行了这样一个操作

```c++
Student a(s);
```

等待showNumber()结束之后，再析构a这个对象。

这也就是为什么传递用户自定类型通常用引用传递，同时也解释了，为什么拷贝构造函数传参为什么是引用传参？

设想，如果拷贝构造函数这么写，会发生什么？

```c++
Student (const Student obj);
```

假设有个Student对象s。我值传递s进入了拷贝构造函数，那么按照之前所说，编译器会去申请一个空间给形参obj，同时调用自身的拷贝构造函数把s的数据成员的值传给obj。但是这个调用拷贝构造函数的过程，又是一个值传递，又需要开辟一个空间....

所以，只要以值传递的方式调用拷贝构造函数，就会申请空间，申请空间的过程中又会申请空间，又申请空间的过程又又申请空间。如此往复，会陷入无限套娃的死循环。

**所以拷贝构造函数一定不能是值传递。**

3.函数返回值类型对象的时候：函数执行完成返回主调函数时，将使用return语句中的对象初始化一个临时无名对象，传递给主调函数，此时发生拷贝构造。

```cpp
Student get_copy(void)
{
    Student s;
    return s;//这里以s为参数构造构造一个副本，并返回副本，这里发生了拷贝
}
```

完整代码：

```cpp
#include <iostream>//cin cout
#include <string>
using namespace std;

class Student
{
public:
    Student(const Student& from)//拷贝构造函数
    {
        cout << "copy constructor called." << endl;
    }
    //如果只提供上面的拷贝构造函数，编译器就不再生成默认构造函数
    //，会而导致类对象就不可以直接创建，所以还需要提供一个默认构造函数
    Student(void)
    {
        cout << "default constructor called." << endl;
    }
};
Student test_function(void)
{//s在该函数被调用的时候创建，该函数执行完之后释放
    cout << "flag2" << endl;
    Student stu;
    cout << "flag3" << endl;
    return stu;
}//s释放的时刻
int main()
{
    cout << "flag1" << endl;
    test_function();//(1)创建stu的副本，函数内使用副本
    cout << "flag4" << endl;
}
```

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231029163321976.png" alt="image-20231029163321976" style="zoom:50%;" />
</div>


#### 9.9.4 句柄(handle)

句柄不能是常量,在程序设计中，句柄是一种特殊的[智能指针](https://baike.baidu.com/item/智能指针/10784135?fromModule=lemma_inlink)，当一个[应用程序](https://baike.baidu.com/item/应用程序/5985445?fromModule=lemma_inlink)要引用其他系统（如数据库、操作系统）所管理的内存块或对象时，就要使用句柄。

### 9.10 Operators as Member vs. Non-Member Functions

当操作符函数为成员函数时，左操作数必须是一个对象(或者是对象的引用)。如果左操作数必须是不同类的对象或者基础类型，则操作符函数必须声明为非成员函数。如果需要非成员函数访问类的private和protected成员，可以将非成员函数声明为类的friend。

### 9.11 类型转换

对象的类型定义了对象能够包含的数据和能够参与的运算，其中一种运算被大多数类型支持，就是将对象从一种给定的类型转换为另一种相关类型。

当程序的某处我们使用了一种类型而其实对象应该取另一种类型时，程序会自动进行类型转换，当给某种类型的对象强行赋了另一种类型的值时，会发生什么呢？

```cpp
bool b=42;//b为真
int i=b;//i的值为1
i=3.14;//i的值为3
double pi=i;//pi的值为3.0
unsigned char c=-1;//假设char为8bite,c的值为255
signed char c2=256;//假设char占8bite,c2的值是未定义的
```

类型所能表示的值的范围决定了转换的过程：

1.当我们把一个整数值赋给浮点类型时，小数部分记为0。如果该整数所占的空间超过了浮点类型的容量，精度可能有损失。

2.当我们赋给无符号类型一个超出它表示范围的值时，结果是初始值对无符号类型表示数值总数取模后的余数。例如，8比特大小的unsigned char可以表示0-255区间内的值，如果我们赋了一个区间以外的值，则实际的结果是该值对256取模后所得的余数。因此，把-1赋给8比特大小的unsigned char所得的结果是255。

3.当我们赋给带符号类型一个超出它表示范围的值时，结果是未定义的(undefined)。此时，程序可能继续工作、可能崩溃，也可能生成垃圾数据。

当在程序的某处使用了一种算术类型的值而其实所需的是另一种类型的值时，编译器同样会执行上诉的类型转换。例如，我们使用了一个非布尔值作为条件，那么它会被自动的转换成布尔值，这一做法和把非布尔值赋给布尔变量时的操作完全一样：

```cpp
int i=42;
if(i)//if条件的值将为true
    i=0;
```

如果i的值为0，则条件的值为false；i的所有非零取值都将使条件为true。**如果我们把一个布尔值用在算术表达式里，则它的取值非0即1，所以一般不宜在算术表达式里使用布尔值。**

尽管我们不会故意给无符号对象赋一个负值，却可能写出这么做的代码。例如，当一个算术表达式中既有无符号数又有int值时，那个int值就会转换为无符号数。把int转换为无符号数的过程和把int直接赋给无符号变量一样：

```cpp
unsigned u=10;
int i=-42;
std::cout<<i+i<<std::endl;//输出-84
std::cout<<u+i<<std::endl;//如果int占32位，输出4294967264
```

在第二个表达式，相加前首先把整数-42转换为无符号数。把负数转换为无符号数类似于直接给无符号数赋一个负值，结果等于这个负数加上无符号数的模。当从无符号数中减去一个值时，不管这个值是不是无符号数，我们都必须确保结果不能是一个负值。

### 9.12 再探类型转换

类型转换分为隐式类型转换和显式类型转换(强制类型转换)。

#### 9.12.1 隐式类型转换

如果两种类型有关联，那么当程序需要其中一种类型的运算对象时，可以用另一种关联类型的对象或值来替代。即，如果两种类型可以互相转换(conversion)，那么它们就是关联的。

例如,下列表达式的目的是将val初始化为6.

```cpp
int val=3.783+3;//编译器可能会警告该运算损失了精度
```

加法的两个运算对象类型不同：3.783为double类型，3为int类型。C++不会直接将两个不同类型的值相加，而是先根据类型转换规则设法将运算对象的类型统一后再求值。上述的类型转换是自动进行的，被称为隐式转换(implicit cinversion)。算术类型之间的隐式转换被设计的尽可能避免损失精度。

**何时发生隐式类型转换**：

1.在大多数表达式中，比int类型小的整数值首先提升为较大的整数类型

2.在条件中，非布尔值转换为布尔类型

3.初始化过程中，初始值转换为变量的类型；复制语句中，右侧运算对象转换成左侧运算对象的类型

4.如果算术运算或关系运算的运算对象有多种类型，需要转换成同一种类型

5.函数调用时也会发生类型转换

#### 9.12.2 算术转换

算术转换的含义是把一种算术类型转换成另外一种算术类型。

**整型提升**：负责把小整数类型转换成较大的整数类型。对于bool、char、signed char、unsigned char、short和unsigned short等类型来说，只要他们所有可能的值都能存在int里，他们就会提升为int类型；否则，提升成unsigned int类型。

较大的char类型(wchar_t、char16_t、char32_t)提升成int、unsigned int、long、unsigned long、long long和unsigned long long中最小的一种类型，前提是转换后的类型要能够容纳原类型所有可能的值。

#### 9.12.3 其他隐式类型转换

除了算术转换之外还有几种隐式类型转换：

**数组转换成指针**：在大多数用到数组的表达式中，数组自动转换成指向数组首元素的指针：

```cpp
int ia[10];
int* p=ia;//ia转换成指向数组首元素的指针
```

当数组被用作decltype关键字的参数，或者作为取地址符(&)、sizeof及typeid等运算符的运算对象时，上述转换不会发生。如果用一个引用来初始化数组，上诉转换也不会发生。

**指针的转换**：1.常量整数值0或者字面值nullptr能转换成任意指针类型

2.指向任意非常量的指针能转换成void*

3.指向任意对象的指针能转换成const void*

**转换成布尔类型**：存在一种从算术类型或指针类型向布尔类型自动转换的机制。如果指针或算术类型的值为0，转换结果是false;否则转换结果是true。

```cpp
char *cp=get_string();
if(cp)//如果指针cp不是0，条件为真
while(*cp)//如果*cp不是空字符，条件为真
```

**转换成常量**：允许将指向非常量类型的指针转换成指向相应的常量类型的指针，对于引用也是这样。也就是说，如果T是一种类型，我们就能将指向T的指针或引用分别转换成指向const T的指针或引用。

```cpp
int i;
const int &j=i;//非常量转换成const int的引用
const int *p=&i;//非常量的地址转换成const的地址
int &r=j,*q=p;//错误：不允许const转换成非常量
```

相反的转换不存在，因为它试图删掉底层const。

**类类型定义的转换**：类类型能定义由编译器自动执行的转换，不过编译器每次只能执行一种类类型的转换。如果同时提出多个转换请求，这些请求将被拒绝。

类类型转换的例子：在需要标准库string类型的地方使用c风格字符串；在条件部分读入istream

```cpp
string s,t="a value";//字符串字面值转换成string类型
while(cin>>s);//while的条件部分把cin转换成布尔值
```

#### 9.12.4 显式转换(强制类型转换)

在 C 语言中，我们大多数是用 (type_name) expression 这种方式来做强制类型转换，但是在 C++ 中，更推荐使用四个转换操作符来实现显式类型转换：

有时我们希望显式的将对象强制转换成另一种类型，例如，在下列代码中执行浮点数除法：

```cpp
int i,j;
double slope=i/j;
```

就要使用某种方法将i和/或j显式的转换成double,这种方法称作强制类型转换(cast)

一个命名的强制类型转换的格式如下：

```cpp
cast-name<type>(expression);
```

type是转换的目标类型，expression是要转换的值。如果type是引用类型，则结果是左值。cast-name是static_cast、dynamic_cast、const_cast和reinterpret_cast中的一种。

**Ⅰ.static_cast**:

任何具有明确定义的类型转换，只要不包含底层const，都可以使用static_cast。

```cpp
double slope=static_cast<double>(j)/i;
```

当需要把一个较大的算术类型赋值给较小的类型时，static_cast非常有用。对于编译器无法自动执行的类型转换也非常有用。

如果要在原生数据类型(基础数据类型)之间进行数据转换，应该使用static_cast关键字。

如果涉及到类的话，static_cast只能在**有相互联系的类型中进行相互转换**

1.将一个基本类型转换为另一个基本类型，例如将整数转换为浮点数或将字符转换为整数。

```cpp
int a = 42;
double b = static_cast<double>(a); // 将整数a转换为双精度浮点数b
```

2.指针类型之间的转换

将一个指针类型转换为另一个指针类型，尤其是**在类层次结构中从基类指针转换为派生类指针。**

   进行上行转换（把派生类的指针或引用转换成基类表示）是安全的
   进行下行转换（把基类的指针或引用转换为派生类表示），由于没有动态类型检查，所以是不安全的

```cpp
class Base {};
class Derived : public Base {};

Base* base_ptr = new Derived();
Derived* derived_ptr = static_cast<Derived*>(base_ptr); // 将基类指针base_ptr转换为派生类指针derived_ptr

```

3.引用类型之间的转换

类似于指针类型之间的转换，可以将一个引用类型转换为另一个引用类型。在这种情况下，也应注意安全性。

```cpp
Derived derived_obj;
Base& base_ref = derived_obj;
Derived& derived_ref = static_cast<Derived&>(base_ref); // 将基类引用base_ref转换为派生类引用derived_ref
```

static_cast在编译时执行类型转换，在进行指针或引用类型转换时，需要自己保证合法性。

如果想要运行时类型检查，可以使用dynamic_cast进行安全的向下类型转换。

4.把空指针转换成目标类型的空指针
5.把任何类型的表达式转换为void类型
 **注意：static_cast不能转换掉expression的const、volitale或者__unaligned属性。**

**Ⅱ.const_cast**:

用法:

```cpp
 const_cast <new_type> (expression)
```

 expression必须是一个指针、引用或者指向对象类型成员的指针。

1.修改const对象

当需要修改const对象时，可以使用`const_cast`来删除const属性。

```cpp
const int a = 42;
int* mutable_ptr = const_cast<int*>(&a); // 删除const属性，使得可以修改a的值
*mutable_ptr = 43; // 修改a的值
```

2.const对象调用非const成员函数

当需要使用const对象调用非const成员函数时，可以使用const_cast删除对象的const属性。

```cpp
class MyClass {
public:
    void non_const_function() { /* ... */ }
};

const MyClass my_const_obj;
MyClass* mutable_obj_ptr = const_cast<MyClass*>(&my_const_obj); // 删除const属性，使得可以调用非const成员函数
mutable_obj_ptr->non_const_function(); // 调用非const成员函数
```

不过上述行为都不是很安全，可能导致未定义的行为，因此应谨慎使用。**const_cast用于强制去掉这种不能被修改的常数特性，但需要特别注意的是const_cast不是用于去除变量的常量性，而是去除指向常数对象的指针或引用的常量性，其去除常量性的对象必须为指针或引用。**

**Ⅲ.reinterpret_cast**

reinterpret_cast用于在不同类型之间进行低级别的转换。

expression必须是一个指针、引用、算术类型、函数指针或者成员指针。

首先从英文字面的意思理解，interpret是“解释，诠释”的意思，加上前缀“re”，就是“重新诠释”的意思；cast 在这里可以翻译成“转型”,它仅仅是重新解释底层比特（也就是对指针所指针的那片比特位换个类型做解释），**而不进行任何类型检查。**

reinterpret_cast主要有三种强制转换用途：***改变指针或引用的类型、将指针或引用转换为一个足够长度的整形、将整型转换为指针或引用类型***。

因此，reinterpret_cast可能导致未定义的行为，应谨慎使用。

1.指针类型之间的转换

在某些情况下，需要在不同指针类型之间进行转换，如将一个int指针转换为char指针。

```cpp
int a = 42;
int* int_ptr = &a;
char* char_ptr = reinterpret_cast<char*>(int_ptr); // 将int指针转换为char指针
```

**Ⅳ.dynamic_cast**

  **(1）其他三种都是编译时完成的，dynamic_cast是运行时处理的，运行时要进行类型检查。**

**（2）不能用于内置的基本数据类型的强制转换。**

**（3）dynamic_cast转换如果成功的话返回的是指向类的指针或引用，转换失败的话则会返回NULL。**

**（4）使用dynamic_cast进行转换的，基类中一定要有虚函数，否则编译不通过。**需要检测有虚函数的原因：类中存在虚函数，就说明它有想要让基类指针或引用指向派生类对象的情况，此时转换才有意义。这是由于运行时类型检查需要运行时类型信息，而这个信息存储在类的虚函数表。 只有定义了虚函数的类才有虚函数表

**（5）在类的转换时，在类层次间进行上行转换时，dynamic_cast和static_cast的效果是一样的。在进行下行转换时，dynamic_cast具有类型检查的功能，比static_cast更安全。**

向上转换，即为子类指针指向父类指针（一般不会出问题）；向下转换，即将父类指针转化子类指针。

向下转换的成功与否还与将要转换的类型有关，即要转换的指针指向的对象的实际类型与转换以后的对象类型一定要相同，否则转换失败。

​     **在C++中，编译期的类型转换有可能会在运行时出现错误，特别是涉及到类对象的指针或引用操作时，更容易产生错误。dynamic_cast操作符则可以在运行期对可能产生问题的类型转换进行测试。** 

**‍编码规范：**

类型转换必须显式声明，永远不要依赖隐式类型转换。

### 9.13 隐式的类类型转换(转换构造函数)

上述类型转换介绍了C++在内置类型之间定义了几种自动转换规则。我们也可以为类定义隐式转换规则。如果构造函数只接受一个实参，则它实际上定义了转换为此类类型的隐式转换机制，有时我们把这种构造函数称作转换构造函数(converting constructor)，此构造函数将实参类型的对象转换成类类型。

**能通过一个实参调用的构造函数定义了一条从构造函数的参数类型向类类型隐式转换的规则。**

例如：在Sales_data类中，接受string的构造函数和接受istream的构造函数分别定义了从这两种类型向Sales_data隐式转换的规则。也就是说，在需要使用Sales_data的地方，我们可以使用string或者istream代替：

```cpp
string null_book="9-999-99999-9";
//构造一个临时的Sales_data对象
//
item.combine(null_book);
```

**只允许一步类类型转换**：编译器只会自动的执行一步类型转换。

关键字explicit只对一个实参的构造函数有效。需要多个实参的构造函数不能用于执行隐式转换，所以无需将这些构造函数指定为explicit的。只能在类内声明构造函数时使用explicit关键字，在类外部定义时不应重复。

```cpp
//错误：只能在类内声明构造函数时使用explicit关键字，在类外部定义时不应重复。
explicit Sales_data::Sales_data(istream& is){
    read(is,*this);
}
```

**explicit构造函数只能用于直接初始化:发生隐式转换的另一种情况是当我们执行拷贝形式的初始化时(使用=）。此时我们只能使用直接初始化而不能使用explicit构造函数：**

```cpp
Sales_data item1(null_book);//正确：直接初始化
Sales_data item2=null_book;//错误：不能将explicit构造函数用于拷贝形式的初始化过程
```

当我们用explicit关键字声明构造函数时，它将只能以直接初始化的形式使用。**而且编译器将不会在自动类型转换过程中使用该构造函数。**

### 9.14 类型转换运算符

类型转换运算符可以完成类类型的类型转换。类型转换运算符(conversion operator)是类的一种特殊成员函数，负责将一个类类型的值转换成其他类型。类型转换函数的一般形式如下所示：

```cpp
operator type() const;
```

type表示某种类型。类型转换运算符可以面向任意类型(除了void以外)进行定义，只要该类型能作为函数的返回类型。因此，不允许转换成数组或者函数类型，但是允许转换成指针(包括数组指针及函数指针）或者引用类型。

类型转换运算符既没有显式的返回类型，也没有形参，而且必须定义成类的成员函数。类型转换运算符通常不应该改变待转换对象的内容，因此类型转换运算符一般声明为const。

```cpp
class SmallInt{
public:
    SmallInt(int i=0):val(i)
     {
          if(i<0||i>255)
               throw std::out_of_range("bad smallint value");
      }
      operator int() const{return val;}
private:
    std::size_t val;
};
```

上述代码将算术类型的值转换成SmallInt对象，而类型转换运算符将SmallInt对象转换成int.

![image](assets/image-20231102203919-k2hsvop.png)​​

### 9.15 Overloading the Function Call Operator ()

赋值（=）、下标（[]）、调用（()）和成员访问箭头（->）运算符必须是成员函数。

对于赋值运算符来说，我们知道一个c++类，程序员如果没有为其定义了赋值操作符重载函数，编译器也会隐式的定义，这样倘若再定义全局赋值运算符重载函数，将会发生二义性。即使编译器允许这样的定义手法，在调用的时候也编译不过：

**函数调用运算符必须是成员函数**

### 9.16 移动语义

C++11标准中提供了一种新的构造方法---移动构造。在某些情况下，我们没有必要复制对象---只需要移动它们。

C++11引入移动语义：源对象资源的控制权全部交给目标对象

当临时对象在被复制后，就不再被利用了。我们完全可以把临时对象的资源直接移动，这样就避免了多余的复制操作。

![image-20231205212147802](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231205212147802.png)

&&是右值引用，函数返回的临时变量是右值



## 10. 继承(Inheritance)

派生类必须使用类派生列表明确指出它是从哪个基类继承而来的。因为每个派生类对象都是属于基类的，并且一个基类可以由多个派生类，基类代表的对象比任意派生类代表的对象多。For example, the base class Vehicle represents all vehicles, including cars, trucks, boats, airplanes, bicycles and so on.By contrast, derived-class Car represents a smaller, more specific subset of all vehicles.

继承关系形成类的层级结构(class hierarchies)，一个基类与派生类之间存在层级关系。虽然类可以独立存在，但一旦它们被使用在继承关系中，它们就成为其他类的附属。一个类要么成为基类- -向其他类提供成员，要么成为派生类- -从其他类继承成员，或者两者兼而有之。

### 10.1 基类和派生类

基类往往更加具有一般性，派生类往往更加具体。单继承(single inheritance)，一个类是从一个基类派生出来的。多重继承(multiple inheritance)，一个派生类同时从两个或者多个基类继承而来。

![image](assets/image-20231104193623-ckhmkda.png)例如，在上图中，CommunityMember是Employee\Student\Alumnus的直接基类。是图中其他类的间接基类。

#### 10.1.1 继承的基本概念

![image](assets/image-20231104194728-mss53nz.png)

现在重新考虑上图中的继承层次，继承开始于基类Shape，为了指明TwoDimensionalShape是由Shape派生而来，TwoDimensionalShape类的定义可以写为：

```cpp
class TwoDimensionalShape : public Shape
```

这是public继承的示例，也是最常用的一种形式。还有private和protected继承。对于所有形式的继承，基类的private成员不能由基类的派生类直接访问，但是这些基类的private成员仍然是继承的(即，他们仍然是派生类的一部分)。对于public继承，当基类变成派生类的一部分，除private外的成员仍然保持原始的成员访问权限。(例如，基类的public成员仍然是派生类的Public成员，protected成员仍然是派生类的protected成员)。通过继承基类的成员函数，派生类可以操控基类的private成员(如果这些继承的成员函数提供了基类的这种功能)。

继承关系并不适宜于所有的类的关系。一些情况下，复合(composition)关系更加适宜。类似地处理基类对象和派生类对象是可能的；它们的共性表现在基类成员身上。

#### 10.1.2 基类和派生类的类型转换

公有(public继承)派生类对象可以被当作基类的对象使用，反之不可以。因为：

1.派生类的对象可以隐含转换为基类对象

2.派生类的对象可以初始化基类的引用

3.派生类的指针可以隐含转换为基类的指针

通过基类对象名、指针只能使用从基类继承的成员。

### 10.2 引用和指针

复合类型是指基于其他类型定义的类型，引用和指针属于其中的两种两种类型。与声明变量相比，定义复合类型的变量要复杂一些。**一条声明语句由一个基本数据类型(base type)和紧随其后的一个声明符列表组成。每个声明符命名了一个变量并指定该变量为与基本数据类型有关的某种类型。**   ​

目前为止，我们接触到的声明语句中，声明符就是变量名，此时变量的类型也就是声明的基本数据类型。还可以有更复杂的声明符，它基于基本数据类型得到更复杂的类型，并把它指定给变量。

#### 10.2.1 引用

引用是引用变量的简称，是C++新增的复合类型。引用是以定义的变量的别名。引用的主要用途是用作函数的形参和返回值。被引用的变量的生命周期一定要比引用长，这是使用引用的基本原则。

引用就是为类的对象起了另外一个名字，引用类型引用另外一种类型。通过将声明符写成&d的形式来定义引用类型，d为声明的变量名：

```cpp
int ival=1024;
int& refVal=ival;
int& refVal;//错误，引用必须初始化
```

一般在初始化变量时，初始值会被拷贝到新建的对象中。然而在定义引用时，程序把引用和它的初始值绑定在一起，而不是将初始值拷贝给引用。一旦初始化完成，引用将和它的初始值对象一直绑定在一起。因为无法令引用重新绑定到另外一个对象，因此引用必须初始化，初始化后不可改变。

通过pass-by-reference，调用者赋予被调用函数直接访问调用者数据，并修改该数据的能力。

Pass-by-reference会削弱安全性，被调用函数可能会损坏调用者的数据。Pass-by-reference可以消除拷贝大量数据的传值开销。

带&的是引用型参数，它是地址传递，其**实参**会随着形参的改变而改变；不带&的参数是一般参数，是值传递，其实参不会随着形参的改变而改变。所以，结构改变，并且需要传回这种改变的要用引用型参数，否则用一般参数。

**1.可以在一行中同时定义被引用变量和引用变量。**

**2.引用在定义时要进行初始化。**

```c++
int x,&number=x; 
or
int x;
int &number=x;
```

**3.对引用的操作就是对被引用的变量的操作。**

**4.引用类型变量的初始值不能是常数。**

```cpp
int &ref=90;//错误！
```

**5.可以使用动态分配的内存空间初始化一个引用变量。**

**6.C++指针与引用符号应该靠近类型而非名字**

```cpp
float* p;//不应该是float *p
int& x//不应该是int &x
```

在函数调用中，只需提及变量的名字(例如,number)就可以通过引用来传递它。在被调用函数的函数体内，引用参数实际上指的是调用函数的原始变量，原始变量可以通过被调用函数直接修改。函数原型和头文件必须一致。

**在引用类型前面加上const，const 引用的目的是,禁止通过修改引用值来改变被引用的对象。**

#### 10.2.2 引用的本质

引用的本质是指针常量，传递的是变量的地址。传引用的代码更加简洁，传引用不必使用二级指针。

#### 10.2.3 指针

指针是指向另外一种类型的复合类型。与引用相似，指针也实现了对其他对象的间接访问。指针本身就是一个对象，允许对指针赋值和拷贝，在指针的生命周期内它可以先后指向几个不同的对象。指针无需在定义时赋初值。在块作用域内定义的指针如果没有被初始化，也将拥有一个不确定的值。

![image](assets/image-20231106211534-7bverx2.png)​

因为引用不是对象，没有实际地址，所以不能定义指向引用的指针。

空指针：空指针不指向任何对象，在试图使用一个指针之前代码应该首先检查它是否为空。

```cpp
int *p1=nullptr;//等价于 int *p1=0;
int *p2=0;//直接将p2初始化为字面量0
//需要首先#include cstdlib
int *p3=NULL;
```

得到空指针最直接的办法就是使用字面值nullptr来初始化指针。nullptr是一种特殊的字面值，它可以被转换为任意其他的指针类型。

#### 10.2.4 引用和 const

如果引用的数据对象类型不匹配，当引用为const时，C++将创建临时变量，让引用指向临时变量。

如果函数的实参不是左值或与const引用形参的类型不匹配，那么C++将创建正确类型的匿名变量，将实参的值传递给匿名变量，并让形参来引用该变量。

1.使用const可以避免无意中修改数据的编程错误

2.使用const可以使函数能够处理const和非const实参，否则只能接收非const实参

3.使用const，函数可以正确生成并使用临时变量

#### 10.2.5 引用用于函数的返回值

‍传统的函数返回机制与值传递类似。函数的返回值被拷贝到一个临时位置(寄存器或栈)，然后调用者程序再使用这个值。返回引用的语法：

```cpp
返回的数据类型& 函数名(形参列表){

}
```

1.如果返回局部变量的引用，此引用本质是野指针。

2.可以返回函数的引用形参、类的成员、全局变量、静态变量。

### 10.3 基类和派生类的关系

**使用继承，而不是复制粘贴**

#### 10.3.1 基类和派生类的构造函数和析构函数

**派生类的构造函数必须调用基类的构造函数**

**析构函数和友元函数，不能从基类继承而来。**

**当派生类的构造函数调用基类的构造函数时，传向基类构造函数的实参必须与基类的构造函数指定的参数的个数和类型一致，否则会出现编译错误。**

**在派生类的头文件中，使用\#include包含基类。**

之前的章节介绍了public和protected访问修饰符。一个基类的公共成员可以在它的体内和任何地方访问，即程序对此类的对象有一个句柄(名字，引用或指针)或者此类的派生类。基类的private成员只能在体内或者friend类访问。

使用protected访问修饰符提供了一种介于public和private之间的访问等级。将基类的原本的private成员改为protected的，则派生类就可以直接访问基类的private成员。基类的protected成员可以在基类的体内访问，也可以被基类的成员和类的friend访问，还有派生类的成员和派生类的friend也可以访问。

**使用继承可以使得代码更容易维护。**

### 10.4 派生类中的构造函数和析构函数

构造函数：先调用基类的构造函数，再调用派生类的构造函数；基类先，派生类后
析构函数：先调用派生类的析构函数，再调用基类的析构函数。派生类先，基类后

**当程序创建派生类对象时，派生类构造函数会立即调用基类构造函数，基类构造函数的主体将执行，派生类的成员初始值设定项将执行，最后派生类构造函数的主体将执行。如果层次结构包含两个以上的级别，则此过程将向上级联。**

当派生类对象被销毁时，程序将调用该对象的析构函数。这开始了析构函数调用的链（或级联），其中派生类析构函数以及直接和间接基类的析构函数以及类成员的执行顺序与构造函数的执行顺序相反。当调用派生类对象的析构函数时，析构函数将执行其任务，然后调用层次结构中下一个基类的析构函数。此过程将重复进行，直到调用层次结构顶部的最后一个基类的析构函数。然后，从内存中删除该对象。

**假设我们创建一个派生类的对象，其中基类和派生类都包含（通过组合）其他类的对象。创建该派生类的对象时，首先执行基类成员对象的构造函数，然后执行基类构造函数主体，然后执行派生类成员对象的构造函数，然后执行派生类的构造函数主体。派生类对象的析构函数的调用顺序与其相应构造函数的调用顺序相反。**

默认情况下，基类构造函数、析构函数和重载赋值运算符不由派生类继承。但是，派生类构造函数、析构函数和重载赋值运算符可以调用基类版本。

#### 10.4.1 继承基类的构造函数

子类为完成基类初始化，在 C++11 之前，需要在初始化列表调用基类的构造函数，从而完成构造函数的传递。

如果派生类没有构造函数，在这种情况下，C++会为派生类生成默认构造函数，并隐式的调用基类的默认构造函数。

有时，派生类的构造函数只是指定与基类的构造函数相同的参数，并简单地将构造函数参数传递给基类的构造函数。C++11 允许您指定派生类应继承基类的构造函数。为此，需要显式包含 using 声明

* C++11规定

  * 可用using语句继承基类构造函数。
  * 但是只能初始化从基类继承的成员。

    * 派生类新增成员可以通过类内初始值进行初始化。
  * 语法形式：

```cpp
using BaseClass::BaseClass;//继承基类的所有构造函数
```

* **如果派生类有自己新增的成员，且需要通过构造函数初始化，则派生类要自定义构造函数。可以在派生类构造函数中调用基类构造函数。**

除了少数例外（下面列出），对于基类中的每个构造函数，编译器都会生成一个派生类构造函数，该构造函数调用相应的基类构造函数。每个生成的构造函数都与派生类同名。

When you inherit constructors:

1.每个生成的构造函数都具有与其对应的基类构造函数相同的访问说明符（public、protected 或 private）。

2.copy 和 move 构造函数不会被继承。

3.如果通过在其原型中放置 = delete 来删除基类中的构造函数，则派生类中的相应构造函数也会被删除。

4.如果派生类未显式定义构造函数，编译器仍会在派生类中生成默认构造函数。

5.如果在派生类中显式定义的构造函数具有相同的参数列表，则不会继承给定的基类构造函数。

6.基类构造函数的默认参数不会被继承。相反，编译器在派生类中生成重载构造函数。例如，如果基类声明构造函数

```cpp
BaseClass(int = 0, double = 0.0);
```

编译器生成以下两个不带默认参数的派生类构造函数

```cpp
DerivedClass();
DerivedClass(int); 
DerivedClass(int, double);
```

它们都调用指定默认参数的 BaseClass 构造函数。

如果不继承基类的构造函数:

1.派生类的新增成员：派生类定义构造函数初始化

2.继承来的成员：调用基类构造函数进行初始化

3.派生类的构造函数需要向基类的构造函数传递参数

单继承时构造函数的定义语法：

```cpp
派生类名::派生类名(基类所需的形参，本类成员所需的形参)：基类名(参数表),本类成员初始化列表
{
	//其他初始化操作;
};	
```

多继承且有对象成员时派生类的构造函数的定义：

```cpp
派生类名::派生类名(形参表):
基类名1(参数)，基类名2(参数),...,基类名n(参数),本类成员(含对象成员)初始化列表
{
	//其他初始化操作;
};
```

构造函数的执行顺序：

1.调用基类的构造函数，基类构造函数的调用顺序按照它们被继承时声明的顺序(自左向右)

2.对初始化列表中的成员进行初始化。顺序按照它们在类中定义的顺序；对象成员初始化时自动调用其所属类的构造函数

3.执行派生类的构造函数体中的内容

#### 10.4.2 继承中的默认构造函数

**若基类的构造函数未被显式的调用，基类的默认构造函数就会被调用。**

例如：

```cpp
Circle(){
	radius=1.0;
}//等价于下列的函数形式

Cirlce():Shape{} {
    radius=1.0;
}//Shape为Circle的基类
```

**所以，要考虑给基类提供默认构造函数。**

#### 10.4.3 派生类的复制构造函数

从基类继承而来的成员的复制构造由基类的复制构造函数完成，派生类新增的成员的复制构造由派生类的复制构造函数完成。

若派生类没有声明复制构造函数：编译器会在需要时生成一个隐含的复制构造函数，先调用基类的复制构造函数，再为派生类新增的成员执行复制。

若派生类定义复制构造函数：1.一般要为基类的复制构造函数传递参数 2.复制构造函数只能接收一个参数，既用来初始化派生类定义的成员，也将被传递给基类的复制构造函数 3.基类的复制构造函数形参类型是基类对象的引用，实参可以是派生类对象的引用。

#### 10.4.4 派生类的析构函数

析构函数不被继承，派生类如果需要，要自行声明析构函数

声明方法与无继承关系时类的析构函数相同

不需要显式的调用基类的析构函数，系统会自动的隐式调用

先执行派生类析构函数的函数体，再调用基类的析构函数

#### 10.4.5 访问从基类继承的成员(继承中的名字隐藏)

当派生类与基类中有相同成员时：

1.若未特别限定，则通过派生类对象使用的是派生类中的同名成员 

2.如要通过派生类对象访问基类中被隐藏的同名成员，应使用基类名和作用域操作符(::)来限定。

内部作用域的名字隐藏外部作用域的(同名)名字

而派生类视为内部作用域，基类视为外部作用域。

**可以避免某些潜在的危险行为**

### 10.5 重定义函数

1. Redefining Functions (重定义函数)


Shape::toString() 被Circle继承，因此可以通过Circle对象调用该函数。

```cpp
std::cout << circle.toString();
```

但基类的toString()无法输出派生类对象信息

可以重定义派生类的toString()以描述派生类对象

```cpp
#include <string>

std::string Shape::toString() {
	using namespace std::string_literals;
	return "Shape color "s + color
		+ ((filled) ? " filled"s : " not filled"s);
}

string Circle::toString() {
	return "Circle color " + color +
		 " filled " + ((filled) ? "true" : "false");
}
string Rectangle::toString() {
	return "This is a rectangle object";
}
```

2. Redefine (重定义)

![image-20240414153420073](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240414153420073.png)


3. Redefine v.s. Overload (重定义与重载)

3.1. **Overload Functions (重载函数)**


3.1.1. more than one function with the same name (多个函数名字相同)


3.1.2. But different in at least one of the signatures: (但至少一个特征不同)


(1)     parameter type        (参数类型)

(2)     parameter number      (参数数量)

(3)     parameter sequence    (参数顺序)

3.2. **Redefine Functions (重定义函数)**


3.2.1. The functions have the same signature (函数特征相同)


(1)     Name (同名)

(2)     Parameters (including type, number and sequence) (同参数：类型，数量和顺序)

(3)     Return type (返回值类型)

3.2.2. Defined in base class and derived class, respectively (在基类和派生类中分别定义)

### 10.6 public, protected and private Inheritance(访问控制属性)

我们一般使用public继承，使用protected继承比较少见。

![image](assets/image-20231107142207-1rcshm9.png)当使用public继续生成派生类，基类中的public成员变成了派生类的public成员，基类的protected成员变成了派生类的protected成员。基类的Private成员不可以由派生类直接访问，但是可以通过基类的public和protected成员函数访问。

当使用基类派生派生类，使用public\protected\private都有可能。

**public继承：**

基类的public和protected成员，访问属性在派生类中保持不变；基类的private成员，派生类的成员函数不可以直接访问。派生类中的成员函数可以直接访问基类的public和protected成员，但是不能直接访问基类的private成员。通过派生类的对象，只能访问public成员。

**private继承**：是最严格的一种继承

基类的public和protected成员都以private的身份出现在派生类中；基类的private成员，派生类的成员函数不可以直接访问。派生类中的成员函数可以直接访问基类中的public和protected成员，但是不能直接访问基类的private成员。通过派生类的对象，不能访问从基类继承的任何成员。

**protected继承**：

基类的public和protected成员都以protected的身份出现在派生类中；基类的private成员，不可以直接访问。派生类中的成员函数，可以直接访问基类中的public和protected成员，但是不能直接访问基类的private成员。通过派生类的对象，不能访问从基类继承的任何成员。

### 10.7 虚基类

当派生类从多个基类继承，而这些基类又有共同基类，则在访问此共同基类的成员时，将产生冗余，并有可能因冗余带来不一致性。

虚基类的声明：以virtual说明基类继承方式。例如：

```cpp
class B1:virtual public B
```

虚基类主要用来解决多继承时可能发生的对同一基类继承多次而产生的二义性问题；为最远的派生类提供唯一的基类成员，而不重复产生多次复制。

**在第一级继承时就要将共同基类设计为虚基类**

![image-20231206155430145](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231206155430145.png)



## 11. 多态(Polymorphism)

### 11.1 引言

使用多态性，您可以设计和实现易于扩展的系统，只要新类是程序通常处理的继承层次结构的一部分，就可以添加新类，而无需对程序的常规部分进行修改。程序中唯一必须更改以适应新类的部分是那些需要直接了解添加到层次结构中的新类的部分。例如，如果我们创建继承自 Animal 类的 Tortoise 类（它可能通过爬行一英寸来响应移动消息），我们只需要编写 Tortoise 类和实例化 Tortoise 对象的模拟部分。处理每只动物的模拟部分通常可以保持不变。

### 11.2 多态初窥

假定我们需要设计一个游戏，此游戏需要操作多个不同类型的对象，包括类Martian,Venutian,Plutonian,SpaceShip和LaserBeam。设想上述的几个类都是从基类SpaceObject继承而来，此基类包括成员函数draw。每个派生类都以适合该类的方式实现此函数。一个屏幕管理程序包含一个容器(例如，vector),该容器包含指向各种类对象的 SpaceObject 指针。为了刷新屏幕，屏幕管理程序会周期性的向每个对象发送相同的信息---即draw函数。每个类类型的对象都会以独特的方式回应此函数。例如，Martin类的对象会用适当数量的触角将自己画成红色，SpaceShip对象可能会将自己画成一个银色的飞碟，LaserBeam对象可能会在屏幕上将自己绘制为明亮的红色光束。一条发送到不同类的对象的消息(此处即为draw函数)会导致不同的结果。

多态屏幕管理器有助于向系统添加新类，只需对其代码进行最少的修改。

**多态性使您能够处理一般性问题，并让执行时环境关注细节。您可以指示各种对象以适合这些对象的方式运行，甚至不知道它们的类型，只要这些对象属于同一继承层次结构，并且正在通过公共基类指针或公共基类引用进行访问。**

多态性促进了可扩展性：为调用多态行为而编写的软件是独立于消息发送到的对象的特定类型编写的。因此，可以在不修改基本系统的情况下将可以响应现有消息的新型对象合并到这样的系统中。只有实例化新对象的客户端代码才能适应新类型。

广义的多态概念：不同类型的实体/对象对于同一消息有不同的响应，这就是多态性。

#### 11.2.1 联编

即确定具有多态性的语句调用哪个函数的过程

1.静态联编

在程序编译时确定调用哪个函数，例如函数重载

2.动态联编

在程序运行时，才能够确定调用哪个函数，例如用动态联编实现的多态，也称为运行时多态



### 11.3 继承关系中对象的关系

通过public继承，派生类的对象可以视为是基类的对象。

#### 11.3.1 Invoking Base-Class Functions from Derived-Class Objects

```cpp
//
// Created by 22364 on 2023/11/6.
//
#include <iostream>
#include <iomanip>
#include "CommissionEmployee.h"
#include "BasePlusCommissionEmployee.h"
using namespace std;

int main(){
    // create base-class object
    CommissionEmployee commissionEmployee{
            "Sue", "Jones", "222-22-2222", 10000, .06};
    // create derived-class object
    BasePlusCommissionEmployee basePlusCommissionEmployee{
            "Bob", "Lewis", "333-33-3333", 5000, .04, 300};

    cout << fixed << setprecision(2); // set floating-point formatting

    // output objects commissionEmployee and basePlusCommissionEmployee
    cout << "DISPLAY BASE-CLASS AND DERIVED-CLASS OBJECTS:\n"
       <<commissionEmployee.toString() // base-class toString
       <<"\n\n"
       <<basePlusCommissionEmployee.toString(); // derived-class toString

    // natural: aim base-class pointer at base-class object
    CommissionEmployee* commissionEmployeePtr{&commissionEmployee};
    cout << "\n\nCALLING TOSTRING WITH BASE-CLASS POINTER TO "
       << "\nBASE-CLASS OBJECT INVOKES BASE-CLASS TOSTRING FUNCTION:\n"
       <<commissionEmployeePtr->toString();// base version

    // natural: aim derived-class pointer at derived-class object
    BasePlusCommissionEmployee* basePlusCommissionEmployeePtr{
            &basePlusCommissionEmployee};// natural
    cout << "\n\nCALLING TOSTRING WITH DERIVED-CLASS POINTER TO "
       << "\nDERIVED-CLASS OBJECT INVOKES DERIVED-CLASS "
       << "TOSTRING FUNCTION:\n"
       <<basePlusCommissionEmployeePtr->toString();// derived version

    // aim base-class pointer at derived-class object
    commissionEmployeePtr = &basePlusCommissionEmployee;
    cout << "\n\nCALLING TOSTRING WITH BASE-CLASS POINTER TO "
       << "DERIVED-CLASS OBJECT\nINVOKES BASE-CLASS TOSTRING "
       << "FUNCTION ON THAT DERIVED-CLASS OBJECT:\n"
       <<commissionEmployeePtr->toString() //base version
       <<endl;
}
```

![image](assets/image-20231107164803-snjexhd.png)​

在上述代码最后的一段，将派生类对象basePlusCommissionEmployee的地址赋给基类的指针commissionEmployeePtr。虽然基类的指针此时指向派生类对象，但是在使用基类指针调用成员函数toString时，调用的是基类的成员函数toString。**该程序中每个toString成员函数调用的输出显示，被调用的函数取决于指针所指的实际对象的类型，而不是指针的类型。**

#### 11.3.2 Aiming Derived-Class Pointers at Base-Class Objects

可以将派生类对象的地址赋给基类类型的指针，但是反过来不可以。

#### 11.3.3 Derived-Class Member-Function Calls via Base-Class Pointers

使用基类指针，编译器允许我们只调用基类里的成员函数。因此，如果基类的指针指向一个派生类对象，试图访问派生类特有的成员函数，就会出现编译错误。例如下列代码所示：

```cpp
//
// Created by 22364 on 2023/11/6.
//
#include <string>
#include "CommissionEmployee.h"
#include "BasePlusCommissionEmployee.h"
using namespace std;

int main(){
    // create derived-class object
    BasePlusCommissionEmployee basePlusCommissionEmployee{
            "Bob", "Lewis", "333-33-3333", 5000, .04, 300};

    // aim base-class pointer at derived-class object (allowed)
    CommissionEmployee* commissionEmployeePtr{&basePlusCommissionEmployee};

    // invoke base-class member functions on derived-class
    // object through base-class pointer (allowed)
    string firstName{commissionEmployeePtr->getFirstName()};
    string lastName{commissionEmployeePtr->getLastName()};
    string ssn{commissionEmployeePtr->getSocialSecurityNumber()};
    double grossSales{commissionEmployeePtr->getGrossSales()};
    double commissionRate{commissionEmployeePtr->getCommissionRate()};

    // attempt to invoke derived-class-only member functions
    // on derived-class object through base-class pointer (disallowed)
    double baseSalary{commissionEmployeePtr->getBaseSalary()};
    commissionEmployeePtr->setBaseSalary(500);
}
```

![image](assets/image-20231107190724-6pvmznu.png)​

编译器会允许指向派生类对象的基类类型指针访问派生类特有的函数--前提是显式的将基类类型的指针cast到派生类类型的指针。这种操作叫做向下转型(downcasting)。向下转型允许只能由派生类对象完成的派生类特定操作由基类类型的指针完成。但是向下转型会存在潜在的危险。后续章节会介绍如何消除这种潜在的危险。

### 11.4 (虚函数及虚析构函数)Virtual Functions and Virtual Destructors

#### 11.4.1 为何虚函数有用？

假定Circle\Triangle\Rectangle\square都是基类Shape的派生类。这些类中的每个类都可能被赋予通过成员函数绘制自身的能力，但每个形状的功能却截然不同。在一个绘制形状集合的程序中，将所有的形状笼统地视为基类Shape的对象是有用的。然后，对于任意形状的绘制，我们可以简单地使用基类Shape指针来调用绘图函数，让程序根据基类Shape指针在任意时刻所指向的对象的类型，动态地确定使用哪个派生类绘图函数的(也就是说,在运行时)。这是多态行为。

**通过使用虚函数，对象的类型(而不是用来调用对象的成员函数的句柄的类型），决定了调用哪个版本的虚函数。**

#### 11.4.2 声明虚函数

为了实现上述的功能，我们在基类中将draw函数声明为虚函数，并且在每个派生类中重写draw函数以绘制相应的形状。从实现的角度看，重写一个函数无异于重新定义一个(也是一直沿用的做法)。派生类中的重写函数与基类中的重写函数具有相同的函数原型。如果我们没有将基类函数声明为虚函数，我们可以重新定义那个函数。如果我们将基类函数声明为虚函数，我们可以重写它以实现多态行为。虚函数的声明格式如下：

```cpp
virtual 函数类型 函数名();
```

不需要形参列表。

虚函数的实现要在类外实现，不能在类内实现。

一旦一个函数被声明为虚拟，从那个点开始，它在继承层次结构中一直保持虚拟，即使当派生类重写该函数时，该函数没有被明确声明为虚拟。

尽管某些函数由于在类层次结构中的一个较高的声明而隐含地是虚拟的，但为了清晰起见，在类层次结构的每个层次上都显式地声明这些函数是虚拟的。

当派生类选择不重写其基类的虚拟函数时，派生类只需继承其基类的虚拟函数实现。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231207135611311.png" alt="image-20231207135611311" style="zoom:80%;" />

#### 11.4.3 Invoking a virtual Function Through a Base-Class Pointer or Reference

如果一个程序通过基类类型的指向派生类对象的指针调用虚函数(即，shapePtr->draw())或者一个指向派生类对象的基类引用(即，shapeRef.draw()),程序会通过对象的类型动态的选择正确的派生类函数执行，而不是根据指针或者引用的类型。**在执行时刻(而不是在编译时)选择合适的函数调用称为动态绑定。**   

![image-20231207150439139](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231207150439139.png)

#### 11.4.4 通过对象的名字调用虚函数

当通过名称引用特定对象并使用点成员选择算子( 例如，squareObject.draw () )调用一个虚函数时，函数调用在编译时(这被称为静态绑定)得到解决，所调用的虚函数是为该特定对象的类(或被继承)定义的虚函数- -这不是多态行为。与虚函数的动态绑定只发生在指针和引用。

#### 11.4.5 虚函数的注意事项

为了防止错误，将C++11的override关键字应用到每个派生类函数重写基类虚函数的原型中。这使得编译器能够检查基类是否具有具有相同签名的虚拟成员函数。如果不是，则编译器产生错误。这不仅可以确保你用合适的签名覆盖基类函数，还可以防止你意外地隐藏一个具有相同名字和不同签名的基类函数。

#### 11.4.6 虚析构函数

使用多态性处理类层次结构的动态分配对象时，可能会出现问题。到目前为止，您已经看到了未使用关键字 virtual 声明的析构函数。如果通过将 delete 运算符应用于指向该对象的基类指针来销毁具有非虚拟析构函数的派生类对象，则 C++ 标准指定该行为未定义。**构造函数不能是虚函数。**

**当我们delete一个动态分配的对象的指针时将执行析构函数。如果该指针指向继承体系中的某个类型，则有可能出现指针的静态类型与被删除对象的动态类型不符的情况。例如，如果delete一个Quote**​***类型的指针，而指针指向了一个Bulk_quote类型的对象。如果这样的话编译器必须清楚它应该执行的是Bulk_quote的析构函数。***

此问题的简单解决方案是在基类中创建一个公共虚拟析构函数。如果基类析构函数声明为虚拟析构函数，则任何派生类的析构函数也是虚拟的。例如，在类 CommissionEmployee 的定义中，我们可以按如下方式定义虚拟析构函数：

```cpp
virtual ~CommissionEmployee() {};
```

现在，如果通过将 delete 运算符应用于基类指针来显式销毁层次结构中的对象，则会根据基类指针指向的对象调用相应类的析构函数。请记住，当派生类对象被销毁时，派生类对象的基类部分也会被销毁，因此派生类和基类的析构函数都必须执行。基类析构函数在派生类析构函数之后自动执行。从现在开始，我们将在每个包含虚拟函数并需要析构函数的类中包含一个虚拟析构函数。

**如果类具有虚拟函数，则始终提供虚拟析构函数，即使该类不需要虚拟析构函数。这可确保在通过基类指针删除派生类对象时，将调用自定义派生类析构函数（如果有）。**

构造函数不能是虚拟的。将构造函数声明为 virtual 是编译错误。

前面的析构函数定义也可以写成如下：

```cpp
virtual ~CommissionEmployee() = default;
```

在 C++11 中，可以告诉编译器显式生成默认构造函数、复制构造函数、移动构造函数、复制赋值运算符、移动赋值运算符或析构函数的默认版本，方法是遵循特殊成员函数的原型 = default。例如，当您显式定义类的构造函数，并且仍希望编译器也生成默认构造函数时，这很有用，在这种情况下，请将以下声明添加到类定义中：

```cpp
ClassName() = default;
```

#### 11.4.7 override\final关键字

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231207153847516.png" alt="image-20231207153847516" style="zoom:80%;" />

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231207154054598.png" alt="image-20231207154054598" style="zoom:80%;" />



override的价值在于：避免程序员在覆写时错命名或无虚函数导致隐藏bug。

在 C++11 之前，派生类可以重写其任何基类的虚函数。在 C++11 中，在其原型中声明为 final 的基类**虚函数**，如：

```cpp
virtual 函数名(参数列表) final;
```

**不能在任何派生类中重写，这保证了基类的final成员函数定义将由所有基类对象以及基类的直接和间接派生类的所有对象使用。**同样，在 C++11 之前，任何现有类都可以用作层次结构中的基类。从 C++11 开始，您可以将一个类声明为 final，以防止它被用作基类，如

```cpp
class MyClass final { // this class cannot be a base class 
   // class body 
};
```

尝试重写final成员函数或从final基类继承会导致编译错误。

### 11.5 Type Fields and switch Statements

决定对象类型的一种方式是使用switch语句检查对象中字段的值。这使我们能够区分对象类型，然后为特定对象调用适当的操作，类似于多态性。例如，在形状层次结构中，如果每个形状类(例如，Circle\Triangle\Rectangle\square)的对象都具有shapeType属性，switch语句就可以检查对象的shapeType决定调用哪个toString函数。

使用switch逻辑会使得程序面临各种潜在的问题。例如，您可能忘记在必要时包含类型测试，或者可能忘记在 switch 语句中测试所有可能的情况。通过添加新类型来修改基于 switch 的系统时，可能会忘记在所有相关的 switch 语句中插入新大小写。类的每次添加或删除都需要修改系统中每个关联的 switch 语句;跟踪这些更改可能非常耗时且容易出错。

**多态编程可以消除对switch逻辑的需求。通过使用多态机制来执行等效逻辑，可以避免通常与switch逻辑相关的各种错误。**

**使用多态性的一个有趣的结果是程序呈现出简化的外观。它们包含较少的分支逻辑和更简单的顺序代码。**

### 11.6 抽象类和纯虚函数

**当我们将类看作一种类型时，我们假定程序会创造属于此种类型的对象。然而在某些情况下，定义从未打算从中实例化任何对象的类很有用。即，只定义类，并不为类实例化对象。这种类叫做抽象类(abstract classes)。因为这种类在继承层次结构中经常用作基类，也叫做抽象基类。可以被用来实例化对象的类叫做具体类(concrete classes)。**

#### 11.6.1 Pure virtual Functions(纯虚函数)

通过声明类的一个或多个虚拟函数是“纯”的，类是抽象的。纯虚函数是通过在其声明中放置“=0”来指定的，如：

```cpp
virtual 函数类型 函数名(参数列表) = 0; // pure virtual function
```

“=0”是一个纯说明符。**纯虚函数不提供实现。每个具体的派生类都必须用这些函数的具体实现重写所有基类纯虚函数;否则，派生类也是抽象的。**

![image-20231207151406150](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231207151406150.png)

虚函数和纯虚函数的区别是：虚函数有实现，为派生类提供重写函数的选项；纯虚函数没有实现，要求派生类重写该派生类的函数，以便该派生类具体化;否则，派生类将保持抽象。**回到我们前面的空间对象示例，基类 SpaceObject 具有函数 draw 的实现是没有意义的（因为如果没有关于正在绘制的空间对象类型的特定信息，就无法绘制通用空间对象）。**   定义为虚拟函数（而不是纯虚拟函数）的函数示例是返回对象名称的函数。我们可以命名一个通用的Space Object (例如,"space object")，因此可以为该函数提供一个默认的实现，并且该函数不需要是纯虚的。但是，该函数仍然被声明为虚拟的，因为预期派生类将重写该函数，为派生类对象提供更具体的名称。

**一个抽象类在一个类层次结构中为由它派生出来的各种类定义了一个公共接口。一个抽象类包含一个或多个具体派生类必须重写的纯虚函数。**

**在派生类中不能重写一个纯虚函数使得该类是抽象的。试图实例化抽象类的对象会导致编译错误。**

**一个抽象类至少有一个纯虚函数，一个抽象类也可以有数据成员和具体函数(concrete functions,包含构造函数和析构函数)，它们受派生类继承的一般规则的约束。**

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231207151600476.png" alt="image-20231207151600476" style="zoom:80%;" />

虽然我们不能实例化抽象基类的对象，但是我们可以使用抽象基类来声明指针和引用，这些指针和引用可以指向从抽象类派生的任何具体类的对象。程序通常使用此类指针和引用对派生类对象进行多态操作。

#### 11.6.2 Device Drivers: Polymorphism in Operating Systems

多态性对于实现分层的软件系统特别有效。例如，在操作系统中，每一种类型的物理设备都可能与其他类型的物理设备有很大的不同。即便如此，从设备和到设备分别读取数据或写入数据的命令可能具有一定的统一性。发送给设备驱动对象的写消息需要在该设备驱动的上下文中进行特定的解释，以及该设备驱动如何操作特定类型的设备。然而，写入调用本身与写入系统中的任何其他设备并无二致- -将一定数量的字节从内存放到该设备上。面向对象的操作系统可以使用一个抽象的基类来提供一个适合所有设备驱动程序的接口。然后，通过对该抽象基类的继承，形成所有操作类似的派生类。设备驱动程序提供的(即,公共职能)功能在抽象基类中作为纯虚函数提供。这些纯虚函数的实现都是在对应于特定类型设备驱动的派生类中提供的。这种架构还允许新的设备很容易地添加到系统中。用户只需在设备中插入并安装其新的设备驱动程序即可。操作系统通过其设备驱动程序与这个新设备"对话"，它具有与所有其他设备驱动程序相同的公共成员功能- -设备驱动程序抽象基类中定义的那些。

### 11.7 RTTI(运行时类型识别)

运行时类型识别(runtime type information)(RTTI),

C++ 的 RTTI（Run-Time Type Information）是一种运行时类型信息机制，用于在程序运行时获取对象的类型信息。RTTI 主要包括两个关键字：typeid 和 dynamic_cast。

* typeid 运算符，用于返回表达式的类型。
* dynamic_cast 运算符，用于将基类的指针或引用安全地转换成派生类的指针或引用。

一般来说动态类型值得是某个基类指针或引用，指向一个派生类对象，且基类中有虚函数，此时会绑定对象的动态类型。

一般来说，只要有可能我们应该尽量使用虚函数。当操作被定义成虚函数时，编译器将根据对象的动态类型自动的选择正确的函数版本。然而，并非任何时候都能定义一个虚函数。假设我们无法使用虚函数，则可以使用一个RTTI运算符。

运算符dynamic_cast检查指针指向的对象的类型，然后确定该类型是否与指针正在转换的类型有is - a关系。如果是，则动态类型转换返回对象的地址。如果不是，则动态类型转换返回nullptr。

操作符typeid返回对type _ info对象的引用，该对象包含关于操作数类型的信息，包括类型名称。为了使用typeid，程序必须包含头文件\<typeinfo>。

当被调用时，type _ info成员函数name返回一个基于指针的字符串，该字符串包含type _ info对象所表示类型的名称。

运算符dynamic_cast和typeid是C + +的运行时类型信息( RTTI )特征的一部分，它允许程序在运行时确定对象的类型。

#### 11.7.1 动态类型转换

1.为何需要dynamic_cast？

```cpp
void printObject(Shape& shape)// shape是派生类对象的引用
{
  cout << "The area is "
       << shape.getArea() << endl;
// 如果shape是Circle对象，就输出半径
// 如果shape是Rectangle对象，就输出宽高
}
```

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240414201320828.png" alt="image-20240414201320828" style="zoom:50%;" />

如果需要修改函数，让它显示圆的半径应该怎么办？

2. Dynamic Casting Example


2.1. dynamic_cast 运算符


(1)     沿继承层级向上、向下及侧向转换到类的指针和引用

(2)     转指针：失败返回nullptr

(3)     转引用：失败抛异常

2.2. 例子


先将Shape对象用dynamic_cast转换为派生类Circle对象

然后调用派生类中独有的函数

```cpp
// A function for displaying a Shape object
void printObject(Shape &shape)
{
    cout << "The area is "
       << shape.getArea() << endl;
    Shape *p = &shape;
    Circle *c = dynamic_cast<Circle*>(p);
  // Circle& c = dynamic_cast<Circle&>(shape); 
  // 引用转换失败则抛出一个异常 std::bad_cast
    if (c != nullptr) // 转换失败则指针为空
      {
          cout << "The radius is "    
              << p1->getRadius() << endl;    
          cout << "The diameter is "    
             << p1->getDiameter() << endl;
      }
}

```

#### 11.7.2 向上转换和向下转换





## 12. 流输入输出：A Deeper Look

### 12.1 Introduction

在C++ 程序中，首选C++样式的 I/O 而不是C样式的 I/O。

![image-20240415193415977](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240415193415977.png)

![image-20231227204148642](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231227204148642.png)

### 12.2 流(Streams)

C++ I/O occurs in streams, which are sequences of bytes. C++ provides both “low-level” and “high-level” I/O capabilities. Low-level I/O capabilities (i.e., unformatted I/O) specify that some number of bytes should be transferred device-to-memory or memory-to-device. In such transfers, the individual byte is the item of interest. Such low-level capabilities provide high-speed, high-volume transfers but are not particularly convenient. Programmers generally prefer a higher-level view of I/O (i.e., formatted I/O), in which bytes are grouped into meaningful units, such as integers, floating-point numbers, characters, strings and user-defined types. These type-oriented capabilities are satisfactory for most I/O other than high-volume file processing.

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240415193212864.png" alt="image-20240415193212864" style="zoom:67%;" />

#### 12.2.1 Classic Streams vs. Standard Streams

以前，C++经典流库(classic stream libraries)只支持char类型基础的I/O操作。因为char类型只占用一个字节，它只能表示有限的一组字符(例如ASCII码)。然而许多语言使用的字母表中包含的字符数量多于单个字节char所能表示的数量。The ASCII character set does not provide these characters, but the Unicode® character set does.Unicode is an extensive international character set that represents the majority of the world’s languages, mathematical symbols and much more. C++ provides Unicode support via the types wchar_t (the original C++ type for processing Unicode) and C++11 types char16_t and char32_t.

此外，标准流库(standard stream libraries)被实现为类模板式的类数组和向量。

#### 12.2.2 iostream Library Headers

The\<iostream> header defines the cin, cout, cerr and clog objects, which correspond to the standard input stream, the standard output stream, the unbuffered standard error stream and the buffered standard error stream, respectively.The \<iomanip> header declares the parameterized stream manipulators such as setprecision and setw —for formatted I/O.

#### 12.2.3 Stream Input/Output Classes and Objects

The iostream library defines each alias with the typedef specifier, which you'll sometimes use to create more readable type names. For example, the following statement defines the alias CardPtr as a synonym for type Card*:

```cpp
typedef Card* CardPtr;
```

### 12.3 流输出(Stream Output)

cout与cin本质上是对象。

格式化和非格式化的输出能力由ostream提供。Capabilities include output of standard data types with the stream insertion operator (<<); output of characters via the put member function; unformatted output via the write member function; output of integers in decimal, octal and hexadecimal formats; output of floatingpoint values with various precision, with forced decimal points, in scientific notation (e.g., 1.234567e-03) and in fixed notation (e.g., 0.00123457); output of data justified in fields of designated widths; output of data in fields padded with specified characters; and output of uppercase letters in scientific notation and hexadecimal notation.

C++中最重要的三个输出流：ostream\ofstream\ostringstream 还有三个预定义好的输出流对象：cout\cerr\clog

![image-20231227204501096](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231227204501096.png)

![image-20231227205903925](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231227205903925.png)

![image-20231227210412352](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231227210412352.png)

#### 12.3.1. Output of char* Variables

```cpp
#include <iostream>
using namespace std;

int main() {
    const char* const word{"again"};

    cout<<"Value of word is: "<<word
       <<"\nValue of static_cast<const void*>(word) is:"
       <<static_cast<const void*>(word)<<endl;
}
```

*在上述代码中，char类型的指针指向字符串again的首字符地址。*

在 C++ 程序中，字符串可以存储在字符数组中，我们可以用指针访问数组，自然也就可以用指针访问字符串。

字符串指针本质是一个 char 类型的指针，然后将它指向一个字符串的开头，即字符串中的第一个字符。

#### 12.3.2 C风格字符串

![image](assets/image-20231127204407-cgpeujb.png)

![image-20231205215453224](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231205215453224.png)

![image-20231205215512010](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231205215512010.png)

##### 字符串指针

用指针指向字符串，和指向数组没有什么区别，要么在定义指针后给指针赋值，要么在定义时就初始化。

例如：

```cpp
char str[] = "http://c.biancheng.net";
char* p = str;//初始化字符指针，令其指向 str 数组中的字符串

char* q; // 定义一个字符指针
q = str; // 令其指向字符串的开头
```

实际场景中，我们还会经常见到如下定义的字符串指针：

```cpp
char *p = "http://c.biancheng.net";
```

字符串“Hello World!”存放在内存中的常量区，指针 p 指向常量区中的这个字符串。

注意，常量区的内容是不允许修改的，因此对于上面定义的字符串 "http://c.biancheng.net"，不可以通过指针 p 修改它。

字符指针指向字符串的方法：

由于字符串在内存中连续存储的特点，可以使用指针进行操作，并且指针必须是字符型的。通常将指针指向字符串的首地址，利用指针的后移可以指向后续字符。字符指针指向字符串一般有三种的方法：

1.为字符指针初始化字符串首地址

例如：char *p = "I am happy";
这时字符串常量 "I am happy" 在内存中占用11个字节，以上初始化过程是将这段存储空间的首地址赋给字符型指针p，我们称指针p指向字符串"I am happy"，存储示意图如下所示：

![image](assets/image-20231109202726-9w5annd.png)

字符串指针变量的定义说明与指向字符变量的指针变量说明只能按对指针变量的赋值不同来区别。
例如：
char c,*p=&c;
表示p是一个指向字符变量c的指针变量。
而：
char *s="C Language";
则表示s是一个指向字符串的指针变量。把字符串的首地址赋予s。
2.为字符指针赋值字符串首地址

例如：

```cpp
char *p;
p = "I am happy";
```

以上赋值语句“p = "I am happy";”是将字符串存储空间的首地址赋给指针p，然后p便指向字符串。注意不是将字符串赋给指针p。

3.让指针指向存放字符串的数组

```cpp
char a[20] = "I am happy", *p = a;
```

以上定义了字符数组a并为之初始化字符串"I am happy"，然后定义了字符指针p，将p初始化为指向数组a的首地址，即指向了字符串的第一个字符 'I'。

一般来说，如果给cout提供一个指针，它将打印地址。但如果指针的类型为char*，cout将显示指向的字符串。如果要显示字符串的地址，则必须将这种指针强制转换成另一种指针类型。例如：

```cpp
char ch = 'A';
cout << &ch;  // A
```

对于上述代码，从类型的角度而言，`&ch`​的类型为`char*`​，而字符串的类型为`const char*`​，字符数组退化后的类型为`char*`​，因此类型的角度而言无法区分它指的是字符串的地址还是字符的地址，统一按字符串处理。

字符串的类型实际上是由常量字符构成的数组(array)。而字符数组的类型为const char*   *,所以字符串的类型为const char**

尽管C++支持C风格字符串，但在C++程序中最好不要使用C风格的字符串。因为使用起来不方便，且容易引发程序漏洞。C风格字符串不是一种类型，而是为了表达和使用字符串而形成的一种约定俗成的写法。按照此习惯书写的字符串存放在字符数组中并以空字符结束。

![image](assets/image-20231109210413-pbc1bck.png)

#### 12.3.2 Character Output Using Member Function put

basic_ostream的成员函数put，一次输出一个字符。例如：

```cpp
cout.put('A');
```

会显示字符'A'。The put function also may be called with a numeric expression that represents an ASCII value, as in the following statement, which also outputs A:

```cpp
cout.put(65);
```

### 12.4 流输入(Stream Input)

The stream extraction operator (>>) normally skips white-space characters (such as blanks, tabs and newlines) in the input stream.

![image-20231227222335209](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231227222335209.png)



![image-20231227222413853](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231227222413853.png)

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231229191511529.png" alt="image-20231229191511529" style="zoom:80%;" />

![image-20231229191527414](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231229191527414.png)

#### 12.4.1 get and getline 成员函数

\>>运算符用空格分隔数据，即，在使用此运算符读取数据时，遇到空格就停止读取。

不带参数的 get 成员函数从指定的流中输入一个字符（包括空格字符和其他非图形字符，例如表示文件末尾的键序列），并将其作为函数调用的值返回。当在流上遇到文件末尾时，此版本的 get 将返回 EOF。EOF 通常具有值 –1，并在标头中定义，该标头通过流库标头间接包含在代码中\<iostream>。

```cpp
#include <iostream>
using namespace std;

int main() {
    int character; // **use int, because char cannot represent EOF**

// prompt user to enter line of text
    cout << "Before input, cin.eof() is "<<cin.eof()
       <<"\nEnter a sentence followed by Enter and end-of-file:\n";

    // use get to read each character; use put to display it
    while((character=cin.get())!=EOF){
        cout.put(character);
    }

    // display end-of-file character
    cout << "\nEOF in this system is: " << character
       <<"\nAfter input of EOF, cin.eof() is " <<cin.eof() << endl;
}
```

![image](assets/image-20231109214426-08v6msu.png)

使用int类型的值，因为在许多平台上，char只能表示非负值，但是EOF为-1。

此外，我们还可以用输入输出流对象的一些成员函数来实现输入和输出。

* `cout.put()`​输出单个字符，可以连续输出
* `cin.get()`​读入一个字符（包括空白字符），返回读入成功的字符，如遇到文件结束符，返回 EOF
* `cin.get(ch)`​读入一个字符并赋值给变量 ch，成功读入则返回真
* `cin.get`​(字符数组或指针，字符个数 n，终止字符) 读入 n-1 个字符，如遇到终止字符则提前结束
* `cin.getline`​(字符数组或指针，字符个数 n，终止字符) 与上面的 cin.get 类似，但是遇到终止字符时，**字符指针会移到该终止字符后面，而 cin.get 则会停留在原位置**
* `cin.eof()`​如果到达文件末尾（遇文件终止符）返回真，否则返回假
* `cin.peek()`​返回当前指针指向的字符，但只是观测，指针仍然停留在当前位置
* `cin.putback(ch)`​将字符 ch 返回到输入流，插入到当前指针位置
* `cin.ignore`​(n, 终止字符) 跳过输入流中 n 个字符，若遇到终止符提前结束，此时指向终止字符后面一个位置

**get()函数是cin输入流对象的成员函数，cin.get()从流中读取并取走一个字符，有三种形式：**

1. 无参数的；
2. 有一个参数的；
3. 有3个参数的。

1.无参数的

其调用形式为

```cpp
cin.get()
```

用来从指定的输入流中提取一个字符（包括空白字符），函数的返回值就是读入的字符。 若遇到输入流中的文件结束符，则函数值返回文件结束标志EOF(End Of File)，一般以-1代表EOF，用-1而不用0或正值，是考虑到不与字符的ASCII代码混淆，但不同的C++系统所用的EOF值有可能不同。

```cpp
#include <iostream>
using namespace std;

int main()
{
	char c;
	cout << "enter a sentence:" << endl;
	while ((c = cin.get()) != EOF){
		cout.put(c);
	}

	cout << "end" << endl;

	return 0;
}
```

2.有一个参数的

```cpp
cin.get(ch)
```

其作用是从输入流中读取一个字符，赋给字符变量ch。如果读取成功则函数返回true，如失败(遇文件结束符) 则函数返回false（文件结束符 为 ctrl + z）。上面的例子可以改写如下：

```cpp
#include <iostream>
using namespace std;

int main()
{
	char c;
	cout << "enter a sentence:" << endl;

	while (cin.get(c))//读取一个字符赋给字符变量c,如果读取成功,cin.get(c)为真
	                  //读取字符为文件结束符（Ctrl + z）时，cin.get(c)为假
	{
		cout.put(c);
	}
	cout << "end" << endl;

	return 0;
}
```

3.有三个参数的

```cpp
    cin.get(字符数组, 字符个数n, 终止字符)
或
    cin.get(字符指针, 字符个数n, 终止字符)
```

其作用是从输入流中读取n-1个字符，赋给指定的字符数组(或字符指针指向的数组)，如果在读取n-1个字符之前遇到指定的终止字符，则提前结束读取。如果读取成功则函数返回true(真)，如失败(遇文件结束符) 则函数返回false(假)。如果在函数原型中省略终止字符，默认为'\n'。

具有三个参数（字符数组、大小限制和分隔符（具有默认值换行符））的成员函数 get 从输入流中读取字符，最多读（大小限制数目-1）个字符，或直到读取分隔符。输入字符串以 null 字符结尾。分隔符不放置在字符数组中，而是保留在输入流中。

将上例改写如下：

```cpp
#include <iostream>
using namespace std;
int main()
{
	char ch[20];
	cout << "enter a sentence:" << endl;
	cin.get(ch, 10, '\n');//指定换行符为终止字符
	cout << ch << endl;
	system("pause");
	return 0;
}
```

```cpp
#include <iostream>
using namespace std;

int main()
{
    // create two char arrays, each with 80 elements
    const int SIZE{80};
    char buffer1[SIZE];
    char buffer2[SIZE];

    // use cin to input characters into buffer1
    cout << "Enter a sentence:\n";
    cin >> buffer1;

    // display buffer1 contents
    cout << "\nThe string read with cin was:\n" << buffer1 << "\n\n";

    // use cin.get to input characters into buffer2
    cin.get(buffer2, SIZE);

    // display buffer2 contents
    cout << "The string read with cin.get was:\n" << buffer2 << endl;
}
```

`cin`​ 这个函数输入取数据的过程：

```cpp
// cin如何读取
	int a, b;
	cin >> a >> b;
```

大家肯定知道，假定我们在这里输入3 5 8 9 11，a最终会读取的数字是 3。但是实际上cin是将3 5 8 9 11都放入了缓冲区，等待a去读取，a从头开始读，读到int类型的数据，并将3拿出来赋给a,这时候缓冲区内还剩下：5 8 9 11。注意：这里3后面的' '是存在的，缓冲区内的字符会一直留着直到后面被读取。然后接着b再读取，读到的是数字5，然后5便赋给b,剩下的字符留在缓冲区等待程序后续操作。

成员函数 getline的操作类似于三参数 get 成员函数。getline 函数从输入流中删除分隔符，但不将其存储在字符串中。

```cpp
#include <iostream>
using namespace std;

int main(){
    const int SIZE{80};
    char buffer[SIZE]; // create array of 80 characters

    // input characters in buffer via cin function getline
    cout << "Enter a sentence:\n";
    cin.getline(buffer, SIZE);
  
    cout << "\nThe sentence entered is:\n" << buffer << endl;
}
```

#### 12.4.2 istream Member Functions peek, putback and ignore

istream的成员函数ignore读取并舍弃字符。接收两个实参：

1.指定字符数-默认值为1

2.停止忽略字符的分隔符 - 默认分隔符为 EOF。

该函数将丢弃指定数量的字符，如果在输入流中遇到分隔符，则丢弃更少的字符。

它的原型是：

```cpp
istream & ignore(int n =1, int delim = EOF);
```

此函数的作用是跳过输入流中的 n 个字符，或跳过 delim 及其之前的所有字符，哪个条件先满足就按哪个执行。两个参数都有默认值，因此 cin.ignore() 就等效于 cin.ignore(1, EOF)， 即跳过一个字符。

例如：

```cpp
ignore(6,'\n');
```

这里的意思是说从缓冲区的第一个字符开始读，读到第6个字符，这些字符我们就全部从缓冲区里舍去，假如这段字符长这样hello c++，那么现在缓冲区里还剩下c++,这里的字符是一个一个来的，假如是数字，例如：13 1 89 72，调用了cin.ignore(6,'\n')之后呢，缓冲区里还剩下9 72,没错，89变成了9，就是因为舍去的是前六位字符而不是数字，所以这里也是很多人容易错的地方，觉得是舍弃6个整数。
接着，看'\n'，这个的意思就简单了，只要你输入了'\n',也就是我们键入回车的时候，ignore()便不再从缓冲区里舍弃字符了，也就是你回车之前的所有字符全部从缓冲区里拿出来。这个'\n'也可以定义为其他字符，只要遇到这个字符ignore()便停止他的行为。

```cpp
//ignore()用法
#include <iostream>

using namespace std;

int main()
{
	int a, b;
	cin >> a; 
	//从缓冲区舍弃字符，到第五个停止，如果遇到换行符，舍弃换行符之前的所有字符
	cin.ignore(5, '\n'); 
	cin >> b;
	cout << "a is : " << a << endl;
	cout << "b is : " << b << endl;
	return 0;
}
```

输入`25 86 91 12`​，首先`25`​被`a`​从缓冲区中拿出来，此时缓冲区剩下`  86 91 12`​，然后开始舍弃，数到第五位，也就是`91`​中`9`​的位置，`9`​和它之前的数据被全部舍弃，b再进去读取，便读取到`1`​，输出正确。

![image](assets/image-20231110143441-4txstqm.png)​

这里我们在数字8后键入了回车，按照前面所说，`a`​拿走了`25`​，回车将`8`​以及它之前的数据全部丢掉，再给b进去读取，因此直接读取`96`​

![image](assets/image-20231110143507-zxo765j.png)​

cin.ignore(),大可以把cin.ignore()理解为`cin.ignore(1,'\n')`​,就是舍弃掉第一个字符或者回车之前的数据，我们可以用它舍弃掉缓冲区里的空格字符或者存在的换行符。

```cpp
// 代码差不多
#include <iostream>

using namespace std;

int main()
{
	int a, b;
	cin >> a;
	cin.ignore(); //唯一的区别在这！
	cin >> b;
	cout << "a is : " << a << endl;
	cout << "b is : " << b << endl;
	return 0;
}
```

putback成员函数将get函数从输入流中获取的上一个字符放回该流中。

peek成员函数返回输入流的下一个字符，但并不会将此字符从流中移除。

### 12.5 Unformatted I/O Using read, write and gcount

未格式化的输入/输出使用istream的read函数和ostream的write成员函数。read将字节放入char类型的数组中。write将char数组中的字节输出。例如：

```cpp
char buffer[]{"HAPPY BIRTHDAY"}; 
cout.write(buffer, 10);
```

输出buffer中的前十个字节(包括空字符)，

```cpp
cout.write("ABCDEFGHIJKLMNOPQRSTUVWXYZ", 10);
```

上述代码将会输出字母表的前十个字母。

成员函数gcount报告上次输入操作读取的字符数量。

```cpp
#include <iostream>
using namespace std;

int main(){
    const int SIZE{80};
    char buffer[SIZE];

    // use function read to input characters into buffer
    cout << "Enter a sentence:\n";
    cin.read(buffer, 20);

    // use functions write and gcount to display buffer characters
    cout << "\nThe sentence entered was:\n";
    cout.write(buffer, cin.gcount());
    cout << endl;
}
```

运行结果为：

![image](assets/image-20231110153012-c6tzpam.png)​



### 12.6 Stream Manipulators(操纵符): 格式化输出

‍![image-20231227211614536](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231227211614536.png)

![image-20231227212928057](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231227212928057.png)



#### 12.6.1 Integral Stream Base: dec, oct, hex and setbase

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main(){
    int number;

    cout<<"Enter a decimal number: ";
    cin >> number; // input number

    // use hex stream manipulator to show hexadecimal number
    cout << number << " in hexadecimal is: " << hex<< number << "\n";

    // use oct stream manipulator to show octal number
    cout << dec << number << " in octal is: " << oct << number << "\n";

    // use setbase stream manipulator to show decimal number
    cout << setbase(10)<< number << " in decimal is: " << number << endl;
}
```

<img src="assets/image-20231110154736-p6jzmnl.png" alt="image" style="zoom:67%;" />​

#### 12.6.2 设置浮点数精度(precision, setprecision)

使用setprecision流操作符或者ostream的成员函数precision控制浮点数的精度。使用setprecision流操作符会改变随后操作的浮点数的精度，直到下一次使用setprecision。使用成员函数precision会返回当前使用的浮点数的精度。头文件为\<iomanip>

setprecision(0)的实际效果取决于编译器，不同的编译器实现是不同的。

![image-20231227213031433](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231227213031433.png)

```cpp
#include <iostream>
#include <iomanip>
#include <cmath>
using namespace std;

int main(){
    double root2{sqrt(2.0)}; // calculate square root of 2

    cout << "Square root of 2 with precisions 0-9.\n"
       << "Precision set by ostream member function precision:\n";
    cout << fixed; // use fixed-point notation

    // display square root using ostream function precision
    for (int places{0}; places <= 9; ++places){
        cout.precision(places);
        cout << root2 << "\n";
    }

    cout << "\nPrecision set by stream manipulator setprecision:\n";

    // set precision for each digit, then display square root
    for (int places{0}; places <= 9; ++places){
        cout <<setprecision(places) << root2 << "\n";
    }
}
```

运行结果如下;

![image](assets/image-20231110164455-wr3ff4u.png)​

#### 12.6.3 Field Width (width, setw)

istream和ostream类的成员函数width()设置field width(即，应输出值的字符位置数或应输入的最大字符数)。

If values output are narrower than the field width, fill characters are inserted as padding.A value wider than the designated width will not be truncated—the full number will be printed.The width function with no argument returns the current setting.

**宽度设置仅适用于下一次插入或提取（即宽度设置not sticky）;之后，将宽度隐式设置为 0（即，输入和输出将使用默认设置执行）。假设宽度设置适用于所有后续输出是一个逻辑错误。**

如果输出的数值占用的宽度超过setw(int n)设置的宽度，则按照实际宽度输出。

```cpp
float f=0.364823;
std::cout<<std::setw(3)<<f<<std::endl;
```

上述代码的输出结果为：

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240415212608288.png" alt="image-20240415212608288" style="zoom:67%;" />

cout.width()默认为右对齐，且只对后面第一个输出有作用。

cin.width()遇到空格自动停止接收。例如对于下列代码，输入This is a test of the width member function。cin.width(5)，遇到空格停止读入，所以只读入了This，使用cout.width(widthValue++)输出，widthValue先使用再递增，所以此时为cout.width(4)。

```cpp
#include <iostream>
using namespace std;

int main(){
    int widthValue{4};
    char sentence[10];

    cout << "Enter a sentence:\n";
    cin.width(5); // input only 5 characters from sentence

    // set field width, then display characters based on that width
    while(cin>>sentence){
        cout.width(widthValue++);
        cout<<sentence<<"\n";
        cin.width(5);
    }
}
```

![image](assets/image-20231110165226-stiu11h.png)​

#### 12.6.4 User-Defined Output Stream Manipulators

```cpp
#include <iostream>
using namespace std;

// bell manipulator (using escape sequence \a)
ostream& bell(ostream& output){
    return output << '\a'; // issue system beep
}

// carriageReturn manipulator (using escape sequence \r)
ostream& carriageReturn(ostream& output){
    return output << '\r'; // issue carriage return
}

// tab manipulator (using escape sequence \t)
ostream& tab(ostream& output) {
    return output << '\t'; // issue tab
}

// endLine manipulator (using escape sequence \n and flush stream
// manipulator to simulate endl)
ostream& endLine(ostream& output){
    return output << '\n' << flush; // issue endl-like end of line
}

int main(){
    // use tab and endLine manipulators
    cout << "Testing the tab manipulator:" <<endLine
       <<'a'<<tab<<'b'<<tab<<'c'<<endLine;

    cout << "Testing the carriageReturn and bell manipulators:"
       <<endLine<<"..........";

    cout<<bell;//use bell manipulator

    // use carriageReturn and endLine manipulators
    cout << carriageReturn<< "-----" << endLine;
}
```

![image](assets/image-20231111130636-fk32sg8.png)​

上述代码创建了自己定义的流操作符。

对于输出流操作符，返回类型和形参必须是ostream&类型。

### 12.7 格式化输出(Stream Format States and Stream Manipulators)

![image](assets/image-20231111132848-w9nuh1a.png)![image](assets/image-20231111132900-5k47dog.png)​

#### 12.7.1 Trailing Zeros and Decimal Points (showpoint)

流操作符showpoint是一个sticky setting，强迫浮点数数字以其小数点和尾随零输出。例如，浮点数79.0输出为79，在不使用showpoint的情况下。或者使用showpoint输出79.00000。重置showpoint设置，使用流操作符noshowpoint。默认的浮点数精度为6，不使用fixed和scientific操作符，精度表示的是有效数字，而不是小数点以后的。例如9.9000，输出9.9。9.990输出9.99。例如下列程序：

```cpp
#include <iostream>
using namespace std;

int main(){
    // display double values with default stream format
    cout << "Before using showpoint"
       <<"\n9.9900 prints as: " << 9.9900
       << "\n9.9000 prints as: " << 9.9000
       <<"\n9.0000 prints as: " << 9.0000;

    // display double value after showpoint
    cout<<showpoint
       <<"\n\nAfter using showpoint"
       <<"\n9.9900 prints as: " << 9.9900
       <<"\n9.9000 prints as: " << 9.9000
       <<"\n9.0000 prints as: " << 9.0000 << endl;
}
```

![image](assets/image-20231111141845-2khmmn8.png)​

#### 12.7.2 Justification (left, right and internal)

使用流操作符left或者right可以让要输出的内容在指定的宽度内左对齐或者右对齐。

```cpp
#include <iostream>
#include <iomanip>
using namespace std;
int main() {
    int x{12345};

    // display x right justified (default)
    cout << "Default is right justified:\n\"" <<setw(10) << x << "\"";

    // use left manipulator to display x left justified
    cout << "\n\nUse left to left justify x:\n\""
         << left << setw(10) << x << "\"";

    // use right manipulator to display x right justified
    cout << "\n\nUse right to right justify x:\n\""
       << right << setw(10) << x << "\"" << endl;
}
```

![image](assets/image-20231111142450-6rbkbuw.png)​

流操作符internal指出数字的正负号(或者使用流操作符showbase显示数字使用的进制)应该在指定的输出宽度的最左边输出，数字的数量应该靠右显示。中间的空白区域使用填充字符填充，默认情况下为空格。showpos操作符使得正数的符号+强制显示。例如下述代码：

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main(){
// display value with internal spacing and plus sign
    cout<<internal<<showpos<<setw(10)<<123<<endl;
}
```

![image](assets/image-20231111142909-h1nlnbc.png)将123换成-123后，输出结果为：

![image](assets/image-20231111142940-l9npswl.png)​

对于指定的宽度10，数字-123，-号在最左面显示，123在最右边显示，中间以空格字符填充。

#### 12.7.3 设置填充字符(fill, setfill)

对于指定的字段宽度，使用fill成员函数指定填充字符。默认情况下的填充字符为空格。函数返回先前的填充字符。setfill操作符也可以指定填充字符。

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    int x{10000};

    // display x
    cout << x << " printed as int right and left justified\n"
         << "and as hex with internal justification.\n"
         << "Using the default pad character (space):\n";

    // display x
    cout << setw(10) << x << "\n";

    // display x with left justification
    cout << left << setw(10) << x << "\n";

    // display x with base as hex with internal justification
    cout << showbase << internal<< setw(10) << hex << x << "\n\n";

    cout << "Using various padding characters:" << endl;

    // display x using padded characters (right justification)
    cout<<right;
    cout.fill('*');
    cout << setw(10) << dec << x << "\n";

    // display x using padded characters (left justification)
    cout << left << setw(10) <<setfill('%') << x << "\n";

    // display x using padded characters (internal justification)
    cout <<internal << setw(10) <<setfill('^') << hex << x << endl;
}
```

![image](assets/image-20231111144119-6oyvnm6.png)​

#### 12.7.4 Integral Stream Base (dec, oct, hex, showbase)

C++提供流操作符dec,hex和oct让整数以十进制、十六进制和八进制的形式显示。如果没有指定以哪种进制显示，默认以十进制显示。以0开头的数字为八进制，以0x或者0X开头的数字为十六进制。

```cpp
#include <iostream>
using namespace std;

int main(){
    int x{100};

    // use showbase to show number base
    cout << "Printing octal and hexadecimal values with showbase:\n"
       <<showbase;

    cout << x << endl; // print decimal value
    cout << oct << x << endl; // print octal value
    cout << hex << x << endl; // print hexadecimal value
}
```

![image](assets/image-20231111151007-5r4qk7j.png)​​​

#### 12.7.5 Floating-Point Numbers; Scientific and Fixed Notation (scientific, fixed)

浮点值可以四舍五入到若干位有效数或精度，这是出现在小数点前后的总位数。可以通过使用 setprecision 操作符来控制显示浮点数值的有效数的数量。

```cpp
// This program demonstrates how the setprecision manipulator
// affects the way a floating-point value is displayed.
#include <iostream>
#include <iomanip> // Header file needed to use setprecision
using namespace std;

int main()
{
    double number1 = 132.364, number2 = 26.91;
    double quotient = number1 / number2;
    cout << quotient << endl;
    cout << setprecision(5) << quotient << endl;
    cout << setprecision(4) << quotient << endl;
    cout << setprecision(3) << quotient << endl;
    cout << setprecision(2) << quotient << endl;
    cout << setprecision(1) << quotient << endl;
    return 0;
}
```

![image](assets/image-20231111151211-c73riga.png)

程序中的第一个值显示在第 11 行，没有设置 setprecision 操作符（默认情况下，系统使用 6 个有效数显示浮点值）。后续的 cout 语句打印相同的值，但四舍五入为 5、4、3、2 和 1 个有效数。

请注意，与 setw 不同的是，setprecision 不计算小数点。例如，当使用 setprecision(5) 时，输出包含 5 位有效数，但是需要 6 个位置来显示 4.9188。如果一个数字的值可以由少于 setprecision 指定的精度位数来表示，则操作符将不起作用。

使用流操作符scientific和fixed可以控制浮点数的输出格式。scientific强制浮点数以科学计数法的形式显示。

setprecision函数指明了浮点数应该显示的小数点后的位数，使用此函数，需要头文件<iomanip>。setprecision是一个parameterized stream manipulator。而endl是一个nonparameterized stream manipulator。
fixed指明浮点数的值应该显示为定点数，而不是科学计数法。fixed与setprecision(n)连用可以控制小数点后的位数。
当使用fixed和setprecision时，打印的值为四舍五入到由 setPrecision 的参数指示的小数位数，但内存中的值保持不变,例如87.946和67.543的输出分别为87.95和67.54，也可以使用showpoint和fixed实现上述功能，如果没有fixed，后面的零不会打印。例如7.3000会打印为7.3。

```cpp
#include <iostream>
using namespace std;

int main(){
    double x{0.001234567};
    double y{1.946e9};

    // display x and y in default format
    cout << "Displayed in default format:\n" << x << '\t' << y;

    // display x and y in scientific format
    cout << "\n\nDisplayed in scientific format:\n"
            <<scientific << x << '\t' << y;

    // display x and y in fixed format
    cout << "\n\nDisplayed in fixed format:\n"
            << fixed<< x << '\t' << y << endl;  
}
```

![image](assets/image-20231111152147-rb7jk42.png)​

#### 12.7.6 Uppercase/Lowercase Control (uppercase)

uppercase流操作符可以让十六进制或者科学计数法显示数字时，使得原本是小写的字母变为大写。下例为未使用uppercase操作符之前：

```cpp
#include <iostream>
using namespace std;

int main(){
    cout << "Printing uppercase letters in scientific\n"
       << "notation exponents and hexadecimal values:\n";

// use std::uppercase to display uppercase letters; use std::hex and
    // std::showbase to display hexadecimal value and its base
    cout << 4.345e10 << "\n"
       << hex << showbase << 123456789 << endl;
}
```

![image](assets/image-20231111154358-b720jqi.png)​

在使用uppercase操作符后：

```cpp
#include <iostream>
using namespace std;

int main(){
    cout << "Printing uppercase letters in scientific\n"
       << "notation exponents and hexadecimal values:\n";

// use std::uppercase to display uppercase letters; use std::hex and
    // std::showbase to display hexadecimal value and its base
    cout <<uppercase<< 4.345e10 << "\n"
       << hex << showbase << 123456789 << endl;
}
```

![image](assets/image-20231111154456-us9vzai.png)​

#### 12.7.7 Specifying Boolean Format (boolalpha)

C++提供了数据类型bool，其值可以是false的，也可以是true的，作为旧式的0表示假，任何非零值表示真的首选替代。布尔变量默认输出为0或1。可以使用流操作符boolalpha让输出流将bool值输出为字符串false或者true。使用noboolalpha使得bool值输出为整数(即，默认设置)。

```cpp
#include <iostream>
using namespace std;

int main(){
    bool booleanValue{true};

    // display default true booleanValue
    cout << "booleanValue is " << booleanValue;

    // display booleanValue after using boolalpha
    cout << "\nbooleanValue (after using boolalpha) is "
       <<boolalpha<<booleanValue;

    cout << "\n\nswitch booleanValue and use noboolalpha\n";
    booleanValue = false; // change booleanValue
    cout << noboolalpha; // use noboolalpha

    // display default false booleanValue after using noboolalpha
    cout << "\nbooleanValue is " << booleanValue;

    // display booleanValue after using boolalpha again
    cout << "\nbooleanValue (after using boolalpha) is "
       <<boolalpha<<booleanValue<<endl;

}
```

![image](assets/image-20231111155233-r63pxfn.png)​

#### 12.7.8 Setting and Resetting the Format State via Member Function flags

在对要输出流进行了几次操作符的改动后，怎么才能恢复到默认格式呢？无实参的flag成员函数将当前的设置格式作为fmtflags格式返回，此格式代表格式状态。有实参的flags函数，以fmtflags格式为实参，将格式状态设置为fmtflags指明的格式，并返回先前的状态设置。

```cpp
#include <iostream>
using namespace std;

int main(){
    int integerValue{1000};
    double doubleValue{0.0947628};

    // display flags value, int and double values (original format)
    cout << "The value of the flags variable is: " << cout.flags()
       <<"\nPrint int and double in original format:\n"
       <<integerValue << '\t' << doubleValue;

    // use cout flags function to save original format
    ios_base::fmtflags originalFormat{cout.flags()};
    cout << showbase << oct << scientific; // change format

    // display flags value, int and double values (new format)
    cout << "\n\nThe value of the flags variable is: "<<cout.flags()
       <<"\nPrint int and double in a new format:\n"
       <<integerValue << '\t' << doubleValue;

    cout.flags(originalFormat); // restore format

    // display flags value, int and double values (original format)
    cout << "\n\nThe restored value of the flags variable is: "
       <<cout.flags()<<"\nPrint values in original format again:\n"
       <<integerValue << '\t' << doubleValue << endl;
}
```

![image](assets/image-20231111161052-revcey1.png)​

### 12.8 Stream Error States(流的错误状态)

每个流对象都包含一组状态比特以表示流的状态---sticky format settings,error indicators等。以下述代码为例：

```cpp
#include <iostream>
using namespace std;

int main(){
    int integerValue;

    // display results of cin functions
    cout << "Before a bad input operation:"
       <<"\ncin.rdstate(): " <<cin.rdstate()
       <<"\n cin.eof(): "<<cin.eof()
       <<"\n cin.fail(): "<<cin.fail()
       <<"\n cin.bad(): "<<cin.bad()
       <<"\n cin.good(): "<<cin.good()
       <<"\n\nExpects an integer, but enter a character: ";

    cin >> integerValue; // enter character value

    // display results of cin functions after bad input
    cout << "\nAfter a bad input operation:"
       <<"\ncin.rdstate(): "<<cin.rdstate()
       <<"\n cin.eof(): "<<cin.eof()
       <<"\n cin.fail(): "<<cin.fail()
       <<"\n cin.bad(): "<<cin.bad()
       <<"\n cin.good(): "<<cin.good();

    cin.clear(); // clear stream

    // display results of cin functions after clearing cin
    cout << "\n\nAfter cin.clear()" << "\ncin.fail(): "<<cin.fail()
       <<"\ncin.good(): "<<cin.good()<<endl;
}
```

![image](assets/image-20231111165325-y0bp7sm.png)​

**rdstate成员函数：**   成员函数rdstate返回流中的错误状态。例如，通过调用cout.rdstate返回流的状态，然后通过switch语句检查eofbit、badbit、failbit 和 goodbit来检查这些状态。检测流状态的首选方法是使用成员函数eof， fial, bad 和 good， 使用这些函数不要求了解具体的状态位。

**eof成员函数**判定是否在流中遇到了end-of-file。在此例中，一开始没有输入任何内容，函数返回0(false)。此函数检查流的eofbit数据成员的值，该值在输入流遇到文件结束符后被设置为真。Returns **true** if the associated stream has reached end-of-file.Specifically, returns **true** if `eofbit`​ is set in **rdstate()**   .此函数仅报告最近 I/O 操作设置的流状态;它不检查关联的数据源。例如，最近的I/O操作是get(),get()函数返回文件的最后一个字节，eof()返回false。下一个get()函数从输入流中不会提取到任何字符，并且会设置eofbit.只有这样，eof()才会返回true。

```cpp
#include <cstdlib>
#include <fstream>
#include <iostream>
 
int main()
{
    std::ifstream file("test.txt");
    if (!file) // operator! is used here
    {  
        std::cout << "File opening failed\n";
        return EXIT_FAILURE;
    }
 
    // typical C++ I/O loop uses the return value of the I/O function
    // as the loop controlling condition, operator bool() is used here
    for (int n; file >> n;)
       std::cout << n << ' ';
    std::cout << '\n';
 
    if (file.bad())
        std::cout << "I/O error while reading\n";
    else if (file.eof())
        std::cout << "End of file reached successfully\n";
    else if (file.fail())
        std::cout << "Non-integer data encountered\n";
}
```

**fail成员函数**判定一个流操作是否失败。此函数检查流的failbit数据成员，Returns **true** if an error has occurred on the associated stream.当在流中发生格式错误时，failbit位将被设置。例如程序要求输入整数，但是在输入流中有非整数的字符的情况。在遇到这种错误时，这些字符不会丢失。成员函数fail将报告流操作失败了，通常这种错误是可以恢复的。

```cpp
#include <cstdlib>
#include <fstream>
#include <iostream>
 
int main()
{
    std::ifstream file("test.txt");
    if (!file) // operator! is used here
    {  
        std::cout << "File opening failed\n";
        return EXIT_FAILURE;
    }
 
    // typical C++ I/O loop uses the return value of the I/O function
    // as the loop controlling condition, operator bool() is used here
    for (int n; file >> n;)
       std::cout << n << ' ';
    std::cout << '\n';
 
    if (file.bad())
        std::cout << "I/O error while reading\n";
    else if (file.eof())
        std::cout << "End of file reached successfully\n";
    else if (file.fail())
        std::cout << "Non-integer data encountered\n";
}
```

![image](assets/image-20231111171049-682rojd.png)

**bad成员函数：**判定流操作是否失败。当发生数据丢失时，将会设置badbit位。成员函数bad将报告流操作是否失败了。一般情况下，这种严重的错误是不能修复的。

**good成员函数:**   如果流中的eofbit、failbit 和 badbit位都没有被设置，那么goodbit位将被设置，即如果函数eof, fail 和 bad都返回false值，则成员函数good返回true值。I/O操作只在“好的”流中才能进行。

**clear成员函数:**   clear成员函数将流的状态重置为“好的”，使得流可以继续执行I/O操作。clear函数的默认参数是goodbit ,所以语句cin.clear()清空了cin， 并且为该流设置goodbit位。语句cin.clear(ios::failbit)则为流设置failbit位。

**如果failbit位 和 badbit位其中至少一个被设置, 则basic_ios的成员函数operator!返回true；operator void*返回false值(0)**

##### 重载！和bool

重载运算符可用于测试流在条件下的状态。operator!成员函数返回true如果badbit和failbit其一为true,或者两者均为true。如果badbit为真，failurebit为真或两者都为真，则operator bool成员函数返回false。当在选择语句或迭代语句的控制下测试真/假条件时，这些函数在 I/O 处理中非常有用。例如下列语句：

```cpp
if(!cin){
    //process invalid input stream
}
```

如果cin的流由于输入失败而无效，则执行代码。或者：

```cpp
while(cin>>variableName){
    //process valid input
}
```

只要每个输入操作都成功，就可以执行循环，并在输入失败或遇到end-of-file时终止循环。

‍

## 13. 文件处理

### 13.1 引言

内存中数据的存储是暂时的。文件用于数据的持久化- -数据的永久保留。计算机将文件存储在二次存储设备上，如硬盘、CD、DVD、闪存和磁带。

### 13.2 文件和流(Files and Streams)

C++将文件简单的看作一系列字节。

![image](assets/image-20231111194232-tr5po7n.png)​

每个文件以end-of-file标记或在操作系统维护的管理数据结构中记录的特定字节数结束。当一个文件打开，就创建了一个对象，流就和此对象联系起来。流和对象之间的联系为程序和文件提供了交流通道。

为了文件处理，C++的头文件\<iostream>\<fstream>必须包含。

![image](assets/image-20231111200544-sbjti2x.png)​

头文件fstream定义了三个类型来支持文件IO：ifstream从一个给定文件读取数据，ofstream向一个给定的文件写入数据，fstream可以读写给定文件。要在 C++ 中进行文件处理，必须在 C++ 源代码文件中包含头文件 <iostream> 和 <fstream>。

每当我们想要读写一个文件时，可以定义一个文件流对象，并将对象与文件关联起来。

![image](assets/image-20231112161427-dnbujii.png)

‍![image-20231229192724837](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231229192724837.png)

‍![image-20231229192735057](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231229192735057.png)

![image-20231229192925658](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231229192925658.png)

### 13.3 向文件写入数据

ofstream类可以向文本文件写入数据。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240415201011454.png" alt="image-20240415201011454" style="zoom:67%;" />



当文件已经存在的情况下，已有的内容会被清除。

### 13.4 ofstream类使用的示例

C++不对文件施加任何结构。因此，在C++中不存在类似于记录(可以用几个相关的字段组成一条记录)的概念。必须构造满足应用需求的文件。下面的例子展示了如何在一个文件上施加一个简单的记录结构。

```cpp
#include <iostream>
#include <string>
#include <fstream>
#include <cstdlib>
using namespace std;

int main() {
    // ofstream constructor opens file
    ofstream outClientFile{"clients.txt", ios::out};

    // exit program if unable to create file
    if (!outClientFile) {//overloaded ! operator
        cerr << "File could not be opened" << endl;
        exit(EXIT_FAILURE);
    }

    cout << "Enter the account, name, and balance.\n"
       << "Enter end-of-file to end input.\n? ";

    int account; // the account number
    string name; // the account owner's name
    double balance; // the account balance

    // read account, name and balance from cin, then place in file
    while(cin>>account>>name>>balance){
        outClientFile << account << ' ' << name << ' ' << balance << endl;
        cout<<"? ";
    }
}
```

**上述代码，创建一个顺序文件，该文件可能用于应收账款系统，以帮助管理其信贷客户欠公司的钱。**

#### 13.4.1 文件打开模式

上述代码将数据写入文件，因此我们通过创建ofstream对象打开文件进行输出。向对象的构造函数传入了两个实参，文件名字和文件打开方式(file-open mode)。对于一个ofstream对象，文件打开模式可以是ios::out(the default)，用以向文件输出数据。或者ios::app,用以在文件末尾增加数据(不会修改文件中原先存在的任何数据)。在上述代码中，创造了ofstream的对象-outClientFile，和文件clients.txt联系起来。由于没有指定文件的存储路径，最终文件会和程序存放在同一路径。ofstream的构造函数打开文件---这与文件建立了一条通信线路。因为ios::out是默认的，所以：

```cpp
ofstream outClientFile{"clients.txt", ios::out};
```

也可以写为：

```cpp
ofstream outClientFile{"clients.txt"};
```

**现存的文件由模式ios::out打开会被截断---即文件中的所有数据均被丢弃。如果文件不存在，则ofstream对象会创造一个文件(文件名即为指定的名字)。**

![image](assets/image-20231112163445-hnaqhmu.png)​

上述几种打开模式可以组合在一起，使用位或运算符。

```cpp
stream.open("name.txt",ios::out|ios::app);
```





#### 13.4.2 通过open函数打开文件

也可以创造一个ofstream对象而不需要打开特定的文件---这种情况下，文件可以在后续的操作中附加到对象上。例如，下列的语句：

```cpp
ofstream outClientFile;
```

创造了对象，但并没有和文件联系起来。ofsream的成员函数open打开一个文件，并将其附加在一个现存的ofstream对象上，如下所示：

```cpp
outClientFile.open("clients.txt", ios::out);
```

上述语句中的ios::out也是默认的，即也可以省略。

#### 13.4.3 测试文件是否成功打开

在创建了ofstream对象后并试图打开它，if语句使用了重载的ios的成员函数operator!来判定打开操作是否成功。operator!函数返回true如果failbit或者badbit被流设置---这种情况下，由于打开操作失败，两者其一或者两者均被设置。可能的原因是：

1.试图打开一个不存在的文件以读取

2.试图打开一个在无权访问的文件夹中的文件以读写。

3.为了写入打开文件，但没有可用的硬盘空间。

The argument Passing to exit is returned to the environment from which the program was invoked.EXIT_SUCCESS (defined in \<cstdlib>) to exit indicates that the program terminated normally; passing any other value (in this case EXIT_FAILURE) indicates that the program terminated due to an error.

#### 13.4.4 Overloaded bool Operator

上述代码在while语句中，隐式的对cin调用成员函数operator bool。只要failbit和badbit均未被设置，while的条件就会保持true的状态。

#### 13.4.5 Processing Data

如果上述程序成功打开文件，程序就开始处理数据。When end-of-file is encountered or bad data is entered, operator bool returns false and the while statement terminates.

#### 13.4.6 Closing a File

对于上述程序，一旦用户输入end-of-file指示符，main函数终止。此操作隐式的调用了outClientFile的析构函数，此析构函数用来关闭文件。也可以显示的关闭，使用成员函数close：

```cpp
outClientFile.close();
```

**Always close a file as soon as it’s no longer needed in a program.**

### 13.5 从文件中读取数据

#### 13.5.1 基本概念

ifstream类可以从文本文件中读取数据。需要检测文件是否成功打开。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240415203423492.png" alt="image-20240415203423492" style="zoom:50%;" />

若要正确读取数据，必须确切了解数据的存储格式。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240415204058835.png" alt="image-20240415204058835" style="zoom:67%;" />

#### 13.5.2 检测文件是否成功打开：

1.可能出现的错误：

读文件时，文件不存在；写文件时介质只读

2.检测文件是否成功打开的方法

open()之后马上调用fail()函数，fail()函数返回true，文件未打开

```cpp
ofstream output("hello.txt");
if(output.fail()){
	cout<<R"(can't open file "hello.txt")";
}
```

#### 13.5.3 检测文件是否到达末尾

使用eof()函数检查是否到达文件末尾。

```cpp
ifstream in("hello.txt");
while(in.eof()==false){
    cout<<static_cast<char>(in.get());
}
```

#### 13.5.3 Opening a File for Input

```cpp
#include <iostream>
#include <fstream>
#include <iomanip>
#include <string>
#include <cstdlib>
using namespace std;

void outputLine(int,const string&,double);

int main() {
    // ifstream constructor opens the file
    ifstream inClientFile("clients.txt", ios::in);

    // exit program if ifstream could not open file
    if(!inClientFile){
        cerr<<"File could not be opened" << endl;
        exit(EXIT_FAILURE);
    }

    cout << left << setw(10) << "Account" << setw(13)
       <<"Name" << "Balance\n" << fixed << showpoint;

    int account;
    string name;
    double balance;

    // display each record in file
    while(inClientFile>>account>>name>>balance){
        outputLine(account, name, balance);
    }
}

// display single record from file
void outputLine(int account, const string& name, double balance){
    cout << left << setw(10) << account << setw(13) << name
       <<setw(7) << setprecision(2) << right << balance << endl;
}
```

```cpp
ifstream inClientFile("clients.txt");
```

上述语句打开文件。

#### 13.5.3 File-Position Pointers

程序通常从文件的开头按顺序读取，并连续读取所有数据，直到找到所需的数据。在程序执行期间，可能需要（从头开始）按顺序处理文件多次。istream and ostream提供了成员函数seekg和seekp。seekg重新定位文件位置指针（文件中要读取或写入的下一个字节的字节号）。每个 istream 对象都有一个 get 指针，该指针指示文件中下一个输入的字节号，每个 ostream 对象都有一个 put 指针，该指针指示文件中应放置下一个输出的字节号。例如：

```cpp
inClientFile.seekg(0);
```

将文件位置指针定位到文件的开始(位置0),并将文件附加给对象。seekg的成员函数的参数是整数。该函数还可以有第二个参数，可以指定第二个参数来指示搜索方向，该参数可以是 ios::beg（默认值）表示相对于流的开头进行定位，ios::cur 表示相对于流中的当前位置进行定位，或者 ios::end 表示相对于流的末尾向后定位。文件位置指针是一个整数值，用于将文件中的位置指定为距文件起始位置的字节数（也称为与文件开头的偏移量）。定位 file-position 指针的一些示例包括:

![image](assets/image-20231114203456-sbrv54u.png)​

ostream的成员函数seekp也可以执行相同的操作。成员函数tellg和tellp可以分别返回文件位置指针当前的位置。下列的语句将文件位置指针赋给long类型的变量location：

```cpp
location = fileObject.tellg();
```

### 13.6 C++14: Reading and Writing Quoted Text

C++14’s new stream manipulator—quoted (header \<iomanip>)—enables a program to read quoted text from a stream, including any white space characters in the quoted text, and discards the double quote delimiters.

### 13.7 Updating Sequential Files

如第 14.3 节所示，格式化并写入顺序文件的数据不能被修改，否则会有破坏文件中其他数据的风险。例如，如果需要将名称“White”更改为“Worthington”，则在不损坏文件的情况下无法覆盖旧名称。White 的记录被写入文件，如下所示：

```cpp
300 White 0.00
```

如果使用较长的名称从文件中的同一位置开始重写此记录，则该记录将为:

```cpp
300 Worthington 0.00
```

新记录包含的字符比原始记录多 6 个字符。因此，“Worthington”中“h”之外的字符将覆盖文件中下一个顺序记录的 0.00 和开头。问题在于，在使用流插入运算符 << 和流提取运算符 >> 的格式化输入/输出模型中，字段（以及记录）的大小可能会有所不同。例如，值 7、14、–117、2074 和 27383 都是整数，它们在内部存储相同数量的“原始数据”字节（在 32 位计算机上通常为 4 个字节，在某些 64 位计算机上可能为 8 个字节）。但是，当输出为格式化文本（字符序列）时，这些整数会根据其实际值成为不同大小的字段。因此，格式化的输入/输出模型通常不用于就地更新记录。第 14.7–14.11 节介绍如何使用固定长度的记录执行就地更新。

这样的更新是可以完成的，但很尴尬。例如，要进行前面的名称更改，可以将顺序文件中 300 White 0.00 之前的记录复制到新文件，然后将更新的记录写入新文件，并将 300 White 0.00 之后的记录复制到新文件。然后可以删除旧文件并重命名新文件。这需要处理文件中的每条记录以更新一条记录。但是，如果在一次文件传递中更新了许多记录，则此技术是可以接受的。

### 13.8 随机访问文件(Random-Access Files)

**随机访问意味着可以读写文件的任意位置。**

要实现随机访问文件，需要：

1.我们能知道文件定位器在什么位置

2.我们能在文件中移动文件定位器

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240416134524021.png" alt="image-20240416134524021" style="zoom:67%;" />

可以将数据插入到随机访问文件中，而不会破坏文件中的其他数据。以前存储的数据也可以更新或删除，而无需重写整个文件。在以下各节中，我们将介绍如何创建随机访问文件，将数据输入到文件中，按顺序和随机读取数据，更新数据并删除不再需要的数据。

![image](assets/image-20231114213036-af0agnh.png)​

#### 13.8.1 seek的用法

2.1. seek的原型

```cpp
xxx_stream& seekg/seekp( pos_type pos );
xxx_stream& seekg/seekp( off_type off, std::ios_base::seekdir dir);
```

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240416134853938.png" alt="image-20240416134853938" style="zoom:67%;" />











#### 13.8.2 文件指针

**1.File Positioner (文件位置指示器)**

 1.1. file positioner (fp):

 A file consists of a sequence of bytes.(文件由字节序列构成)

File positioner is a special *marker* that is positioned at one of these bytes. (一个特殊标记指向其中一个字节)

 1.2. A read or write operation takes place at the location of the file positioner. (读写操作都是从文件位置指示器所标记的位置开始)

When a file is opened, the fp is set at the beginning. (打开文件，fp指向文件头)

When you read or write data to the file, the file pointer moves forward to the next data item. (读写文件时，文件位置指示器会向后移动到下一个**数据项**)

1.3. File Positioner(文件位置指示器)的其它说法

File Pointer(文件指针)：易与C语言的FILE* 混淆

File Cursor(文件光标)：借用数据库中的“光标”概念

**2.Example of File Positioner**

调用aFileStream.get()函数，会导致fp = fp + 1;

 <img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240416134008190.png" alt="image-20240416134008190" style="zoom:67%;" />



### 13.9 Creating a Random-Access File

ostream 成员函数write从内存中的特定位置开始，将固定数量的字节写入到指定的流。当流与文件关联时，函数写入将数据写入 put file-position 指针指定的文件中的位置。istream 成员函数read将输入从指定流读取到内存中从指定地址开始的区域的固定字节数。如果流与文件关联，则函数在“get”文件位置指针指定的文件中的位置读取输入字节。

#### 13.9.1 Writing Bytes with ostream Member Function write

将整数写入文件使用下列语句：

```cpp
outFile << number;
```

### 13.10 向字符串输出

![image-20231227220927436](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231227220927436.png)

### 13.11 C++17引入的文件系统库

#### 13.11.1 简介

文件系统库放在名字空间std::filesystem中。标准库的filesystem提供在文件系统与其组件，例如路径、常规文件与目录上进行操作的方法。

文件：持有数据的文件系统对象，能被写入或读取。文件有名称和属性，属性之一是文件类型

路径：标识文件所处位置的一系列元素，可能包含文件名。

路径类：

```cpp
namespace fs=std::filesystem;
fs::path p{"checkPath.cpp"};
```

**路径的概念：**

绝对路径：包含完整的路径和驱动器符号

相对路径：不包含驱动器以及**/**符号。文件存在于相对于当前路径的位置。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240415111010842.png" alt="image-20240415111010842" style="zoom:67%;" />

![image-20240415111218986](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240415111218986.png)



<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240415113511267.png" alt="image-20240415113511267" style="zoom:67%;" />

使用std::filesystem::path::prefered_separator,可以得知当前系统使用哪一种路径名分隔符。

#### 13.11.2 路径类及操作

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240415115854690.png" alt="image-20240415115854690" style="zoom:67%;" />

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240415115909499.png" alt="image-20240415115909499" style="zoom:67%;" />

### 13.12 二进制输入输出

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240416130924565.png" alt="image-20240416130924565" style="zoom:67%;" />

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240416131102417.png" alt="image-20240416131102417" style="zoom:67%;" />

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240416131205171.png" alt="image-20240416131205171" style="zoom:67%;" />

#### 13.2.1 如何实现二进制读写

**1.The *write* Function (write函数)**

  1.1. prototype (函数原型)

```cpp
ostream& write( const char* s, std::streamsize count );
```

 1.2. 可直接将字符串写入文件

```cpp
fstream fs("GreatWall.dat", ios::binary|ios::trunc);
char s[] = "ShanHaiGuan\nJuYongGuan";
fs.write(s, sizeof(s));
```

 1.3. 如何将非字符数据写入文件

(1)   Convert any data into a sequence of bytes (byte stream) (先将数据转换为字节序列，即字节流)

(2)   Write the sequence of bytes to file with write() (再用write函数将字节序列写入文件)

**2.How to convert any data into byte stream? (如何将信息转换为字节流)**

 2.1. reinterpret_cast

该运算符有两种用途：

(1)   cast the address of a type to another type (将一种类型的地址转为另一种类型的地址)

(2)   cast the address to a number, i.e. integer (将地址转换为数值，比如转换为整数)

2.2. 语法: 

```cpp
 reinterpret_cast<dataType>(address)
```

address is the starting address of the data (address是待转换的数据的起始地址)

dataType is the data type you are converting to. (dataType是要转至的目标类型)

对于二进制I/O来说，dataType是 char*

2.3. 例子

```cpp
long int x {0};
int a[3] {21,42,63};
std::string str{"Hello"};
char* p1 = reinterpret_cast<char*>(&x); // variable address
char* p2 = reinterpret_cast<char*>(a); // array address
char* p3 = reinterpret_cast<char*>(&str); // object address
```

 **3.The *read* Function (read成员函数)**

 3.1. prototype (函数原型)

```cpp
istream& read ( char* s, std::streamsize count);
```

 3.2. 例子

```cpp
// 读字符串

fstream bio("GreatWall.dat", ios::in | ios::binary);
char s[10];
bio.read(s, 5);
s[5] = '\0';
cout << s;
bio.close();
```

```cpp
// 读其它类型数据（整数），需要使用 reinterpret_cast

fstream bio("temp.dat", ios::in | ios::binary);
int value;
bio.read(reinterpret_cast<char *>(&value), sizeof(value));
cout << value; 
```





## 14. 容器和迭代器

### 14.1 引言

标准库定义了功能强大的、基于模板的、可重用的组件，这些组件实现了许多用于处理这些数据结构的常见数据结构和算法。这一章介绍的特性经常被称作标准模板库(STL)。

标准库的三个关键组件---容器(模板化的数据结构)，迭代器以及算法。容器是能够存储几乎任何数据类型的对象的数据结构（有一些限制）。

迭代器具有类似于指 针的属性，用于操作容器元素 。内置数组也可以由标准库算法操作，使用指针作为迭代器。

标准库算法是执行常见数据操作（如搜索、排序和比较元素或整个容器）的函数模板。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231208162124039.png" alt="image-20231208162124039" style="zoom:80%;" />

**避免重新发明轮子;如果可能，请使用C++标准库的组件进行编程。**

#### 14.1.1 泛型程序设计

1.编写不依赖于具体数据类型的程序

2.将算法从特定的数据结构中抽象出来，成为通用的

3.C++的STL为泛型程序设计奠定了基础

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231208160305445.png" alt="image-20231208160305445" style="zoom:80%;" />

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231208160513666.png" alt="image-20231208160513666" style="zoom:80%;" />

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231208161433454.png" alt="image-20231208161433454" style="zoom:80%;" />



### 14.2 容器的介绍

容器被分为四个主要的类别：sequence containers(顺序容器), ordered associative containers(顺序关联容器), unordered associative containers(无序关联容器) and container adapters(容器适配器).

![image](assets/image-20231115131823-i5hzdxd.png)​

顺序容器代表线性数据结构(即，它们的所有元素在概念上都是“排成一排的")，例如arrays,vectors和链表。关联容器是非线性数据结构，通常可以快速定位存储在容器中的元素。

key–value pairs(键值对)：键-值对(key- value pair)是编程语言对数学概念中映射的实现。键(key)用作元素的索引，值(value)则表示所存储和读取的数据。

**顺序容器和关联容器被称为first-class containers**.堆栈和队列通常是序列容器的约束版本。因此，标准库将类模板stack,queue和priority_queue实现为容器适配器，使程序能够以受约束的方式查看序列容器。

string类支持与顺序容器相同的功能，但是仅支持存储字符数据。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231209213142628.png" alt="image-20231209213142628" style="zoom:80%;" />

#### 常用容器函数：

大多数容器都提供类似的功能。许多操作适用于所有容器，而其他操作适用于类似容器的子集。

![image](assets/image-20231115133033-trs5p57.png)​​![image](assets/image-20231115133102-2gv9kqz.png)​

Overloaded operators <, <=, >, >=, == and != are not provided for priority_queues. Overloaded operators <, <=, > and >= are not provided for the unordered associative containers. Member functions rbegin, rend, crbegin and crend are not available in a forward_list.

#### First-Class Container Common Nested Types

下图显示了常见的first-class container嵌套类型（在每个容器类定义中定义的类型）。

![image](assets/image-20231115133443-9jt1d13.png)​

#### 容器元素的要求

在使用标准库容器之前，请务必确保容器中存储的对象类型支持一组最少的功能。将对象插入容器时，将创建该对象的副本。对象类型应提供复制构造函数和复制赋值运算符（自定义版本或默认版本，具体取决于类是否使用动态内存）。此外，有序关联容器和许多算法需要比较元素，因此，对象类型应提供小于 （<） 和相等 （==） 运算符。

### 14.3 迭代器介绍

迭代器是专门用来遍历容器的。迭代器是专门用来遍历容器的对象(是容器类的内部类型)

假设v是一个容器，比如 vector\<int> v;

v的迭代器的类型为：vector\<int>::iterator

所以，定义一个迭代器变量的写法为：

```cpp
vector<int>::iterator itr;
```

迭代器与指针有许多相似之处，用于指向first-class container的元素以及用于其他目的。迭代器保存对它们所操作的特定容器敏感的状态信息;因此，为每种类型的容器实现了迭代器。某些迭代器操作在容器之间是统一的。例如，取消引用运算符 （*） 取消引用迭代器，以便您可以使用它指向的元素。迭代器上的 ++ 操作将其移动到容器的下一个元素（就像将指针递增到内置数组中会将指针指向下一个数组元素一样）。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231208162722685.png" alt="image-20231208162722685" style="zoom:80%;" />

First-class containers提供成员函数begin和end。begin函数返回一个指向容器第一个元素的迭代器。函数 end 返回一个迭代器，该迭代器指向容器末尾之后的第一个元素（一个末尾），这是一个不存在的元素，经常用于确定何时到达容器末尾。

容器iterator类型的对象是指可以修改的容器元素。容器const_iterator类型的对象是指无法修改的容器元素。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231209210716473.png" alt="image-20231209210716473" style="zoom:80%;" />

#### Using istream_iterator for Input and ostream_iterator for Output

我们使用带有sequences（也称为ranges）的迭代器。istream_iterator/ostream_iterator

```cpp
#include <iostream>
#include <iterator>
using namespace std;

int main() {
   cout<<"Enter two integers: ";

    // create istream_iterator for reading int values from cin
    istream_iterator<int> inputInt{cin};

    int number1{*inputInt};
    ++inputInt;
    int number2{*inputInt};

    // create ostream_iterator for writing int values to cout
    ostream_iterator<int> outputInt{cout};

    cout<<"The sum is: ";
    *outputInt = number1 + number2;//output result to cout
    cout<<endl;
}
```

上述代码创建一个能够从标准输入对象 cin 中提取（输入）int 值的istream_iterator。上述代码表示能够在标准输出对象cout 中插入（输出）int 值的ostream_iterator。

![image](assets/image-20231115143831-7ha5hdq.png)​

#### Iterator Categories and Iterator Category Hierarchy

![image](assets/image-20231115143849-ff1w5y3.png)​​![image](assets/image-20231115143857-mlkuw83.png)​

As you follow the hierarchy from bottom to top, each iterator category supports all the functionality of the categories below it in the figure. Thus the “weakest” iterator types are at the bottom and the most powerful one is at the top. Note that this is not an inheritance hierarchy.

![image](assets/image-20231115144356-kf99vtg.png)

#### Container Support for Iterators(容器对迭代器的支持)

每个容器支持的迭代器类别决定了该容器是否可以与特定算法一起使用。支持随机访问迭代器的容器可以与所有标准库算法一起使用，但如果算法需要更改容器的大小，则该算法不能用于内置数组或数组对象。大多数算法都可以使用指向内置数组的指针来代替迭代器。下图显示了每个容器的迭代器类别。first-class containers、字符串和内置数组都可以使用迭代器进行遍历。

![image](assets/image-20231115144730-szkfvqu.png)​

#### Predefined Iterator typedefs

并非每个 typedef 都是为每个容器定义的。

![image](assets/image-20231115145304-jm648sb.png)​

#### Iterator Operations

下图显示了每个迭代器类型可以执行的操作。

![image](assets/image-20231115145758-u7kbz47.png)​​![image](assets/image-20231115145811-6im24gz.png)​

### 14.4 算法的介绍

标准库提供了大量算法，您将经常使用这些算法来操作各种容器。插入、删除、搜索、排序等适用于部分或全部顺序和关联容器。**这些算法仅通过迭代器间接对容器元素进行操作。**

### 14.5 顺序容器

C++提供五种顺序容器，array,vector,deque,list和forward_list。类模板array,vector和deque通常基于内置数组。类模板list和forward_list实现链表数据结构。

![image](assets/image-20231115133033-trs5p57.png)​

![image](assets/image-20231115133102-2gv9kqz.png)​

**通常更倾向于重用标准库容器，而不是开发自定义模板化数据结构。对于大多数应用程序来说，Vector 通常是令人满意的。**

**需要在容器两端频繁插入和删除的应用程序通常使用 deque 而不是 vector。虽然我们可以在vector和 deque 的前面和后面插入和删除元素，但类 deque 在前面进行插入和删除比vector更有效。**

**在容器的中间和/或极端处频繁插入和删除的应用程序通常使用list，因为它可以有效地实现在数据结构中的任何位置插入和删除。**

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231210132454743.png" alt="image-20231210132454743" style="zoom:67%;" />

#### 14.5.1 顺序容器-vector

我们在之前介绍的类模板vector提供了一个具有连续内存位置的动态数据结构。这样就可以通过下标运算符 [] 高效、直接地访问向量的任何元素，就像使用内置数组一样。当容器中的数据必须通过下标轻松访问或将要排序时，以及元素的数量可能需要增加时，最常使用类模板vector。当向量的内存耗尽时，向量会分配一个更大的内置数组，复制（或移动）将原始元素放入新的内置数组中，并解除分配旧的内置数组。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231209215311404.png" alt="image-20231209215311404" style="zoom:80%;" />

```cpp
#include <iostream>
#include <vector>// vector class-template definition
using namespace std;

// prototype for function template printVector
template <typename T> void printVector(const vector<T>& integers2);

int main() {
   vector<int> integers;

   cout<<"The initial size of integers is: "<<integers.size()
      <<"\nThe initial capacity of integers is: "<<integers.capacity();

   //function push_back is in vector, deque and list
   integers.push_back(2);
   integers.push_back(3);
   integers.push_back(4);

   cout<<"\nThe size of integers is: "<<integers.size()
      <<"\nThe capacity of integers is: "<<integers.capacity();
   cout<<"\n\nOutput built-in array using pointer notation: ";
   const size_t SIZE{6};
   int values[SIZE]{1,2,3,4,5,6};// initialize values

    // display array using pointer notation
    for(const int* ptr = cbegin(values); ptr!= cend(values);++ptr){
        cout<<*ptr<<' ';
    }

    cout<<"\nOutput vector using iterator notation: ";
    printVector(integers);
    cout << "\nReversed contents of vector integers: ";

    // display vector in reverse order using const_reverse_iterator
    for(auto reverseIterator=integers.crbegin();reverseIterator != integers.crend(); ++reverseIterator){
        cout << *reverseIterator << ' ';
    }

    cout<<endl;
}

// function template for outputting vector elements
template <typename T> void printVector(const vector<T>& integers2){
    // display vector elements using const_iterator
    for(auto constIterator=integers2.cbegin();constIterator != integers2.cend();++constIterator){
        cout << *constIterator << ' ';
    }
}
```

![image](assets/image-20231115163155-jfumlgy.png)​

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231209213452701.png" alt="image-20231209213452701" style="zoom:80%;" />

##### **创建vector：**

下列语句生成了一个类模板vector的名为integers的对象，用以存储int类型的值。vector的默认构造函数创造一个空的vector，没有存储任何元素(即，vector的size为0)，并且没有存储元素的空间(即，它的capacity为0)。所以向vector中添加元素时，需要分配内存。

```cpp
vector<int> integers;
```

##### **vector的成员函数size和capacity：**

size函数可以在处除了forward_list之外的所有容器中使用，此函数返回容器中当前存储的元素个数。capacity函数(只在vector和deque中使用)，返回在向量需要动态调整自身大小以容纳更多元素之前可以存储在向量中的元素数。

##### **vector的成员函数push_back:**

push_back函数(在array和forward_list之外的顺序容器中可以使用)将元素附加到vector中。如果vector的容量已满（即其capacity等于其size），则vector会增加其大小 - 某些实现将vector的容量增加一倍。array和vector以外的顺序容器也提供push_front函数。

![image](assets/image-20231115222005-lkn8ju5.png)

‍

##### **在修改vector后更新size和capacity:**

当我们向vector中添加一个元素时，vector会为这一个元素分配空间，size函数会返回1，以说明当前vector中存储了一个元素。

当我们向vector中添加第二个元素时，vector的capacity会翻倍，即，变为2。size函数的返回值也会变成2。

当我们向vector中添加第三个元素时，vector的capacity会翻倍，即，变为4。size函数的返回值为3。

当vector中被元素填满以后，再试图添加元素，vector的capacity会变成8。

##### **使用指针输出内置数组的内容：**

指向内置数组的指针可用作迭代器。使用 C++14 的全局 cbegin 和 cend 函数，它们的工作方式与函数begin和end的方式相同，但返回不能用于修改数据的const迭代器。C++14提供了rbegin,rend,crbegin和crend函数用以遍历整个内置数组或者容器。rbegin和rend返回的迭代器可以用来修改数据，crbegin和crend返回的const迭代器不可以修改数据。

##### **使用迭代器输出vector的内容：**

上述代码调用函数printVector使用迭代器输出vector中的内容。函数接收const vector的引用。vector的成员函数cbegin返回指向vector首元素的const_iterator。vector的成员函数cend返回指向vector最后一个元素下一个位置的const_iterator。

**函数 cbegin、begin、cend 和 end 可用于所有first-class containers。**

**请记住，迭代器的作用类似于指向元素的指针，并且运算符 * 被重载以返回对元素的引用。**

```cpp
// function template for outputting vector elements
template <typename T> void printVector(const vector<T>& integers2){
    // display vector elements using const_iterator
    for(auto constIterator=integers2.cbegin();constIterator != integers2.cend();++constIterator){
        cout << *constIterator << ' ';
    }
}
```

上述代码中的for循环可以使用基于范围的for循环替换：

```cpp
for (auto const& item : integers2) { 
    cout << item << ' '; 
}
```

**试图解引用一个位于容器外的迭代器会导致错误---即由end或cend函数返回的迭代器不能解引用以及进行递增操作。**

##### **使用const_reverse_iterator反向输出vector中的元素：**

C++11 添加了vector成员函数 crbegin 和 crend，它们在反向遍历容器时返回表示起点和终点的const_reverse_iterators。大部分first-class containers支持这种类型的迭代器。vector类还提供了成员函数rbegin rend以获得non-const reverse_iterator。

##### **C++11:shrink_to_fit:**

在C++11中，可以使vector和deque调用成员函数shrink_to_fit以返回系统不需要的内存。这要求容器将其容量减少到容器中的元素数。根据 C++ 标准，实现可以忽略此请求，以便它们可以执行特定于实现的优化。

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
#include <iterator>
#include <stdexcept>
using namespace std;

int main(){
    vector<int> values{1, 2, 3, 4, 5, 6};
    vector<int> integers{values.cbegin(), values.cend()};
    ostream_iterator<int> output{cout, " "};

    cout << "Vector integers contains: ";
    copy(integers.cbegin(), integers.cend(), output);

    cout << "\nFirst element of integers: "<<integers.front()
       <<"\nLast element of integers: "<<integers.back();

    integers[0] = 7;//set first element to 7
    integers.at(2) = 10;// set element at position 2 to 10

    // insert 22 as 2nd element
    integers.insert(integers.cbegin() + 1, 22);

    cout << "\n\nContents of vector integers after changes: ";
    copy(integers.cbegin(), integers.cend(), output);

    // access out-of-range element
    try{
        integers.at(100) = 777;
    }
    catch(out_of_range &outOfRange){// out_of_range exception
        cout << "\n\nException: " << outOfRange.what();
    }

    integers.erase(integers.cbegin());// erase first element
    cout << "\n\nVector integers after erasing first element: ";
    copy(integers.cbegin(), integers.cend(), output);

    // erase remaining elements
    integers.erase(integers.cbegin(), integers.cend());
    cout << "\nAfter erasing all elements, vector integers "
       <<(integers.empty() ? "is" : "is not")<<" empty";

    // insert elements from the vector values
    integers.insert(integers.cbegin(), values.cbegin(), values.cend());
    cout << "\n\nContents of vector integers before clear: ";
    copy(integers.cbegin(), integers.cend(), output);

    // empty integers; clear calls erase to empty a collection
    integers.clear();
    cout << "\nAfter clear, vector integers "
       <<(integers.empty()?"is":"is not")<<" empty" << endl;
}
```

![image](assets/image-20231116135044-yxq50ce.png)​

```cpp
 ostream_iterator<int> output{cout, " "};
```

上述代码定义了一个名为output的ostream_iterator，可以通过cout输出以单个空格分隔的整数。一个ostream_iterator<int>只能输出int类型的或者与int类型兼容的类型的整数。构造函数的第一个参数指定了输出流，第二个参数指定了用来分隔数字的字符。

##### **copy算法：**

```cpp
copy(integers.cbegin(), integers.cend(), output);
```

上述代码使用了copy算法，来自头文件<algorithm>。copy算法将integers的全部内容输出到标准输出。

##### **vector的成员函数front和back：**

```cpp
 cout << "\nFirst element of integers: "<<integers.front()
    <<"\nLast element of integers: "<<integers.back();
```

上述代码使用的函数front和back分别决定vector的第一个和最后一个元素。front返回vector中第一个元素的引用，begin函数返回指向vector第一个元素的random-access iterator。back函数返回vector最后一个元素的引用，而end函数返回指向vector最后一个元素下一个位置的random-access iterator。

**The results of front and back are undefined when called on an empty vector.**

##### **访问vector的元素：**

```cpp
integers[0] = 7;//set first element to 7
integers.at(2) = 10;// set element at position 2 to 10
```

上述访问vector元素的方式也可以用在deque容器中。第一行代码使用重载的下标运算符返回对指定位置值的引用或对该 const 值的引用，具体取决于容器是否为 const。at函数具有相同的功能，但是此函数会执行边界检查。如果元素不在容器内，函数会抛出异常(out_of_range)。下图为一些标准库异常类型。

![image](assets/image-20231116193616-2zyveu3.png)

‍

##### **vector的成员函数insert:**

```cpp
    // insert 22 as 2nd element
    integers.insert(integers.cbegin() + 1, 22);
```

每个顺序容器都提供了重载的insert函数(数组除外，它具有固定大小，forward_list除外，它具有函数 insert_after)。在上述语句中，迭代器指向容器中的第二个元素，所以将22插入容器作为新的第二个元素，原先的第二个元素就变为了第三个元素。此函数返回指向插入元素的迭代器。

##### **vector的成员函数erase:**

```cpp
    integers.erase(integers.cbegin());// erase first element
    cout << "\n\nVector integers after erasing first element: ";
    copy(integers.cbegin(), integers.cend(), output);

    // erase remaining elements
    integers.erase(integers.cbegin(), integers.cend());
    cout << "\nAfter erasing all elements, vector integers "
       <<(integers.empty() ? "is" : "is not")<<" empty";
```

每个first-class containers都提供了erase函数(数组除外，它具有固定大小，forward_list除外，它具有函数 erase_after)。第一行代码擦除了容器中第一个元素。第二个erase函数擦除两个迭代器指明的元素位置之间的所有元素。empty函数(所有的容器和适配器都可用)用以证明容器已经为空。

**通常，“擦除”会销毁从容器中擦除的对象。但是，擦除作为指向动态分配对象的指针的元素不会删除动态分配的内存，这可能会导致内存泄漏。如果该元素是unique_ptr（第 17.9 节），则unique_ptr将被销毁，动态分配的内存将被删除。如果元素是shared_ptr（第 24 章），则动态分配对象的引用计数将递减，并且仅当引用计数达到 0 时才会删除内存。**

##### **vector的成员函数insert(三个参数):**

```cpp
integers.insert(integers.cbegin(), values.cbegin(), values.cend());
```

上述代码将values的全部元素都插入到vector中，从vector的第二个元素的位置开始插入。函数返回第一个插入的元素的迭代器，如果没有插入任何元素，则返回函数的第一个参数。

##### **vector的成员函数clear：**

clear函数(在除了array以外的所有first-class containers均可以找到)清空vector---这不一定将vector的任何内存返回给系统。

#### 14.5.2 顺序容器-list

顺序容器list，来自头文件\<list>。允许在容器的任意位置进行插入和删除操作。如果大部分插入和删除操作都出现在容器的最后，deque容器会更加有效。类模板list是作为双向链表实现的，即列表中的每个节点都包含指向列表中前一个节点和列表中下一个节点的指针。这使类模板列表能够支持双向迭代器，这些迭代器允许向前和向后遍历容器。任何需要输入、输出、正向或双向迭代器的算法都可以对列表进行操作。许多列表成员函数将容器的元素作为一组有序的元素进行操作。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231210123735175.png" alt="image-20231210123735175" style="zoom:80%;" />

##### **C++11：forward_list容器：**

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231210132236959.png" alt="image-20231210132236959" style="zoom:80%;" />

forward_list的头文件为<forward_list>实现为单向链表，即列表中的每个节点都包含指向list中下一个节点的指针。这使类模板list能够支持正向迭代器，这些迭代器允许容器在正向遍历。任何需要输入、输出或正向迭代器的算法都可以在forward_list

**list成员函数：**

```cpp
#include <iostream>
#include <vector>
#include <list>
#include <algorithm>
#include <iterator>
using namespace std;

//prototype for function template printList
template <typename T> void printList(const list<T>& listRef);

int main(){
    list<int> values;
    list<int> otherValues;

    //insert items in values
    values.push_front(1);
    values.push_front(2);
    values.push_back(4);
    values.push_back(3);

    cout << "values contains: ";
    printList(values);

    values.sort(); // sort values
    cout << "\nvalues after sorting contains: ";
    printList(values);

    // insert elements of ints into otherValues
    vector<int> ints{2, 6, 4, 8};
    otherValues.insert(otherValues.cbegin(), ints.cbegin(), ints.cend());
    cout << "\nAfter insert, otherValues contains: ";
    printList(otherValues);

    // remove otherValues elements and insert at end of values
    values.splice(values.cend(), otherValues);
    cout << "\nAfter splice, values contains: ";
    printList(values);

    values.sort(); // sort values
    cout << "\nAfter sort, values contains: ";
    printList(values);

    // insert elements of ints into otherValues
    otherValues.insert(otherValues.cbegin(), ints.cbegin(), ints.cend());
    otherValues.sort(); // sort the list
    cout << "\nAfter insert and sort, otherValues contains: ";
    printList(otherValues);

    // remove otherValues elements and insert into values in sorted order
    values.merge(otherValues);
    cout << "\nAfter merge:\n values contains: ";
    printList(values);
    cout << "\n otherValues contains: ";
    printList(otherValues);

    values.pop_front(); // remove element from front
    values.pop_back(); // remove element from back
    cout << "\nAfter pop_front and pop_back:\n values contains: ";
    printList(values);

    values.unique(); // remove duplicate elements
    cout << "\nAfter unique, values contains: ";
    printList(values);

    values.swap(otherValues);// swap elements of values and otherValues
    cout << "\nAfter swap:\n values contains: ";
    printList(values);
    cout << "\n otherValues contains: ";
    printList(otherValues);

    // replace contents of values with elements of otherValues
    values.assign(otherValues.cbegin(), otherValues.cend());
    cout << "\nAfter assign, values contains: ";
    printList(values);

    // remove otherValues elements and insert into values in sorted order
    values.merge(otherValues);
    cout << "\nAfter merge, values contains: ";
    printList(values);

    values.remove(4);// remove all 4s
    cout << "\nAfter remove(4), values contains: ";
    cout << "\nAfter remove(4), values contains: ";
    printList(values);
    cout << endl;
}

// printList function template definition; uses
// ostream_iterator and copy algorithm to output list elements
template <typename T> void printList(const list<T>& listRef){
    if (listRef.empty()){
        cout << "List is empty";
    }
    else{
        ostream_iterator<T> output{cout, " "};
        copy(listRef.cbegin(), listRef.cend(), output);
    }
}
```

![image](assets/image-20231116215033-su3itac.png)​

##### 创建list对象：

```cpp
    list<int> values;
    list<int> otherValues;
```

上述代码创建了两个list对象，可以存储int类型的值。

```cpp
    values.push_front(1);
    values.push_front(2);
```

上述代码使用函数push_front将整数插入到values的起始位置。push_front函数只能在forward_list,list和deque中使用。push_back函数将值插入到容器的末尾位置。push_back函数在除了array和forward_list之外的所有顺序容器中都可以使用。

##### list的成员函数sort:

成员函数sort将list中的元素以升序排列。

```cpp
 values.sort(); // sort values
```

##### **list的成员函数splice：**

splice函数删除otherValues中的元素并将这些元素插入到values指定位置的前面。

```cpp
 // remove otherValues elements and insert at end of values
    values.splice(values.cend(), otherValues);
```

##### **list的成员函数merge:**

```cpp
// remove otherValues elements and insert into values in sorted order
    values.merge(otherValues);
```

merge函数移除otherValues的所有元素，并将他们排序后插入到values中。进行操作的两个list必须先进行相同的排序后再使用merge函数。

##### **list成员函数pop_front：**

```cpp
    values.pop_front(); // remove element from front
    values.pop_back(); // remove element from back
```

pop_front函数移除list中的第一个元素。pop_back移除list中的最后一个函数。

##### **list的成员函数unique：**

unique函数移除list中的重复元素。在进行此操作之前，需要先将list排序。

```cpp
values.unique(); // remove duplicate elements
```

##### **list成员函数swap：**

swap函数(available to all first-class containers)交换两个list中的元素。

```cpp
 values.swap(otherValues);// swap elements of values and otherValues
```

##### **list成员函数assign和remove：**

assign函数(available to all sequence containers)将指定范围的otherValues中的元素插入到values中。

```cpp
// replace contents of values with elements of otherValues
    values.assign(otherValues.cbegin(), otherValues.cend());
```

```cpp
 values.remove(4);// remove all 4s
```

remove函数将values中的数值4删除。

#### 14.5.3 顺序容器-deque

The term deque is short for “double-ended queue.”类 deque 提供对随机访问迭代器的支持，因此 deque 可以与所有标准库算法一起使用。**One of the most common uses of a deque is to maintain a first-in, first-out queue of elements.**   事实上，deque 是queue适配器的默认底层实现

deque 的额外存储可以在 deque 的任一端以内存块的形式分配，这些内存块通常作为指向这些块的指针的内置数组进行维护。由于 deque 的内存布局不连续，deque 迭代器必须比用于遍历向量，arrays和内置数组的指针更“智能”。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231209215351615.png" alt="image-20231209215351615" style="zoom:80%;" />

一般的，使用deque的开销比vector更大。

在deque中间的插入和删除经过优化，以最大程度地减少复制的元素数量，因此它比向量更有效，但比列表的效率逊色。

使用类deque时必须包含头文件\<deque>

```cpp
#include <iostream>
#include <deque>
#include <algorithm>
#include <iterator>
using namespace std;

int main() {
    deque<double> values;
    ostream_iterator<double> output{cout," "};

    //insert elements in values
    values.push_front(2.2);
    values.push_front(3.5);
    values.push_back(1.1);

    cout << "values contains: ";

    // use subscript operator to obtain elements of values
    for (size_t i{0}; i < values.size(); ++i){
        cout <<values[i] << ' ';
    }

    values.pop_front();// remove first element
    cout << "\nAfter pop_front, values contains: ";
    copy(values.cbegin(), values.cend(), output);

    // use subscript operator to modify element at location 1
    values[1] = 5.4;
    cout << "\nAfter values[1] = 5.4, values contains: ";
    copy(values.cbegin(), values.cend(), output);
    cout << endl;

}
```

![image](assets/image-20231117112554-qmxmq95.png)​



#### 14.5.4 顺序容器的插入迭代器

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231210132827798.png" alt="image-20231210132827798" style="zoom:67%;" />

### 14.6 关联容器

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231210165501416.png" alt="image-20231210165501416" style="zoom:80%;" />

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231210165514533.png" alt="image-20231210165514533" style="zoom:80%;" />

关联容器通过key（通常称为search keys）提供对存储和检索元素的直接访问。四种有序关联容器为multiset,set,multimap和map。还有四种无序关联容器，unordered_multiset, unordered_set, unordered_multimap 和 unordered_map。

![image](assets/image-20231117122914-7p3dnzt.png)​Classes multiset and set provide operations for manipulating sets of values where the values themselves are the keys.The primary difference between a multiset and a set is that a multiset allows duplicate keys and a set does not.Classes multimap and map provide operations for manipulating values associated with keys (these values are sometimes referred to as mapped values).The primary difference between a multimap and a map is that a multimap allows duplicate keys with associated values to be stored and a map allows only unique keys with associated values.

#### 14.6.1 关联容器-multiset

multiset来自头文件\<set>。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231210165801403.png" alt="image-20231210165801403" style="zoom:67%;" />

```cpp
#include <array>
#include <iostream>
#include <set>
#include <algorithm>
#include <iterator>
#include <vector>
using namespace std;

int main(){
    multiset<int,less<int>> intMultiset;//multiset of ints

    cout<<"There are currently "<<intMultiset.count(15)
       <<" values of 15 in the multiset\n";

    intMultiset.insert(15);// insert 15 in intMultiset
    intMultiset.insert(15);// insert 15 in intMultiset
    cout << "After inserts, there are "<<intMultiset.count(15)
       <<" values of 15 in the multiset\n\n";

    // find 15 in intMultiset; find returns iterator
    auto result{intMultiset.find(15)};

    if (result != intMultiset.end()){// if iterator not at end
        cout << "Found value 15\n"; // found search value 15
    }

    // find 20 in intMultiset; find returns iterator
    result = intMultiset.find(20);

    if (result == intMultiset.end()){// will be true hence
        cout << "Did not find value 20\n"; // did not find 20
    }

    // insert elements of array a into intMultiset
    vector<int> a{7, 22, 9, 1, 18, 30, 100, 22, 85, 13};
    intMultiset.insert(a.cbegin(), a.cend());
    cout << "\nAfter insert, intMultiset contains:\n";
    ostream_iterator<int> output{cout, " "};
    copy(intMultiset.begin(), intMultiset.end(), output);

    // determine lower and upper bound of 22 in intMultiset
    cout << "\n\nLower bound of 22: "
       <<*(intMultiset.lower_bound(22));
    cout << "\nUpper bound of 22: "<<*(intMultiset.upper_bound(22));

    // use equal_range to determine lower and upper bound
    // of 22 in intMultiset
    auto p{intMultiset.equal_range(22)};

    cout << "\n\nequal_range of 22:"<<"\nlower bound: "
    <<*(p.first)<<"\n Upper bound: "<<*(p.second);
    cout<<endl;

}
```

![image](assets/image-20231117140408-qsd4llv.png)​​

**创建multiset：**

下述语句创建了multiset，存储Int类型的值，以升序存储。升序存储是此容器的默认设置，所以可以省略less<int>。

```cpp
 multiset<int,less<int>> intMultiset;//multiset of ints
```

上述语句可以写为：

```cpp
multiset<int> intMultiset; // multiset of ints
```

##### **multiset成员函数count：**

count函数对所有关联容器可用。

```cpp
 cout<<"There are currently "<<intMultiset.count(15)
       <<" values of 15 in the multiset\n";
```

上述count函数用以返回intMultiset中数值15的个数。

##### **multiset成员函数insert：**

```cpp
intMultiset.insert(15);// insert 15 in intMultiset
```

上述函数将15插入到intMultiset中。

```cpp
    vector<int> a{7, 22, 9, 1, 18, 30, 100, 22, 85, 13};
    intMultiset.insert(a.cbegin(), a.cend());
```

上述语句将a中的元素从开始到末尾，插入到intMultiset中，插入后为排序完成的容器。

##### **multiset成员函数find：**

find函数(对所有关联容器可用)用以确定容器中元素的位置。

```cpp
auto result{intMultiset.find(15)};
```

返回一个iterator 或者  const_iterator(取决于容器是否为const的)。如果没有找到元素的位置，则返回一个和end函数返回的迭代器一样的迭代器。

##### **multiset成员函数lower_bound和upper_bound**

lower_bound 和 upper_bound对所有关联容器可用。

```cpp
// determine lower and upper bound of 22 in intMultiset
    cout << "\n\nLower bound of 22: "
       <<*(intMultiset.lower_bound(22));
    cout << "\nUpper bound of 22: "<<*(intMultiset.upper_bound(22));
```

使用函数 lower_bound 和 upper_bound来查找intMultiset中最早出现值 22 以及值 22 最后一次出现之后的元素。

lower_bound 和 upper_bound返回iterators 或者 const_iterators指向恰当的位置，或者在没有相应元素的情况下，指向和end函数返回结果一样的位置。

##### **multiset成员函数equal_range：**

```cpp
    auto p{intMultiset.equal_range(22)};

    cout << "\n\nequal_range of 22:"<<"\nlower bound: "
    <<*(p.first)<<"\n Upper bound: "<<*(p.second);
    cout<<endl;
```

equal_range会返回一个pair类型的值，包含两个迭代器。此处p的值将会是两个const_iterators。两个const_iterators分别是函数lower_bound 和 upper_bound返回的迭代器。pair类包含两个public数据成员，first和second。如果需要解引用lower_bound 和 upper_bound返回的迭代器，则需要提前保证返回的迭代器在容器的范围之内。

#### 14.6.2 关联容器-set

set关联容器，需要头文件\<set>。用于快速存储和检索容器中的唯一的键。set容器的实现和multiset的实现一样，除了set容器要求容器中的键是各不相同的。set支持bidirectional iterators(不支持random-access iterators)。集合可以用来存储一组无重复的元素。由于集合元素本身是有序的，可以高效的查找指定元素，也可以方便的得到指定大小范围的元素在容器中所处得空间。

```cpp
#include <iostream>
#include <vector>
#include <set>
#include <algorithm>
#include <iterator>
using namespace std;

int main(){
    vector<double> a{2.1, 4.2, 9.5, 2.1, 3.7};
    set<double, less<double>> doubleSet{a.begin(), a.end()};

    cout << "doubleSet contains: ";
    ostream_iterator<double> output{cout," "};
    copy(doubleSet.begin(),doubleSet.end(),output);

    //insert 13.8 in doubleSet; insert returns pair in which
    // p.first represents location of 13.8 in doubleSet and
    // p.second represents whether 13.8 was inserted
    auto p{doubleSet.insert(13.8)}; // value not in set
    cout<<"\n\n"<<*(p.first)
       <<(p.second?"was":"was not")<<" inserted";
    cout<<"\ndoubleSet contains: ";
    copy(doubleSet.begin(),doubleSet.end(),output);

    // insert 9.5 in doubleSet
    p = doubleSet.insert(9.5); // value already in set
    cout << "\n\n"<<*(p.first)
       <<(p.second?"was":"was not")<<" inserted";
    cout<<"\ndoubleSet contains: ";
    copy(doubleSet.begin(), doubleSet.end(), output);
    cout << endl;
}
```

‍

![image](assets/image-20231117151910-lultto6.png)​

#### 14.6.3 关联容器-multimap

The elements of multimaps and maps are pairs of keys and values instead of individual values.multimap来自头文件<map>。multimap 容器用于存储 pair<const K, T> 类型的键值对（其中 K 表示键的类型，T 表示值的类型），其中各个键值对的键的值不能做修改；并且，该容器也会自行根据键的大小对存储的所有键值对做排序操作。和 map 容器的区别在于，multimap 容器中可以同时存储多（≥2）个键相同的键值对。This is called a one-to-many relationship.

```cpp
#include <iostream>
#include <map>
using namespace std;

int main(){
    multimap<int, double, less<int> > pairs; // create multimap

    cout << "There are currently "<< pairs.count(15)
       <<" pairs with key 15 in the multimap\n";

    // insert two value_type objects in pairs
    pairs.insert(make_pair(15, 99.3));
    pairs.insert(make_pair(15, 2.7));
    cout << "After inserts, there are "<<pairs.count(15)
       <<" pairs with key 15\n\n";

    // insert five value_type objects in pairs
    pairs.insert(make_pair(30, 111.11));
    pairs.insert(make_pair(10, 22.22));
    pairs.insert(make_pair(25, 33.333));
    pairs.insert(make_pair(20, 9.345));
    pairs.insert(make_pair(5, 77.54));

    cout << "Multimap pairs contains:\nKey\tValue\n";

    // walk through elements of pairs
    for (auto mapItem : pairs){
        cout << mapItem.first << '\t' << mapItem.second << '\n';
    }

    cout<<endl;

}
```

‍

![image](assets/image-20231117153028-igqbyfe.png)​

```cpp
multimap<int, double, less<int> > pairs; // create multimap
```

```cpp
    pairs.insert(make_pair(15, 99.3));
    pairs.insert(make_pair(15, 2.7));
```

上述语句使用insert函数向pairs中插入新的键值对。标准库函数make_pair创造键值pair对象。在此种情况下，first成员代表int类型的键(15),second成员代表值(99.3)。make_pair函数会自动使用用户指定的键值对的类型。也可以使用列表初始化将上述代码简化如下：

```cpp
pairs.insert({15, 2.7});
```

#### 14.6.4 关联容器-map

Duplicate keys are not allowed—a single value can be associated with each key.This is called a one-to-one mapping.头文件\<map>必须包含。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231210170229865.png" alt="image-20231210170229865" style="zoom:67%;" />

```cpp
#include <iostream>
#include <map>
using namespace std;

int main(){
    map<int, double, less<int>> pairs;

    // insert eight value_type objects in pairs
    pairs.insert(make_pair(15, 2.7));
    pairs.insert(make_pair(30, 111.11));
    pairs.insert(make_pair(5, 1010.1));
    pairs.insert(make_pair(10, 22.22));
    pairs.insert(make_pair(25, 33.333));
    pairs.insert(make_pair(5, 77.54)); // dup ignored
    pairs.insert(make_pair(20, 9.345));
    pairs.insert(make_pair(15, 99.3)); // dup ignored

    cout << "pairs contains:\nKey\tValue\n";

    // walk through elements of pairs
    for (auto mapItem : pairs){
        cout << mapItem.first << '\t' << mapItem.second << '\n';
    }

    pairs[25] = 9999.99;// use subscripting to change value for key 25
    pairs[40] = 8765.43;// use subscripting to insert value for key 40

    cout << "\nAfter subscript operations, pairs contains:\nKey\tValue\n";

    // use const_iterator to walk through elements of pairs
    for (auto mapItem : pairs){
        cout << mapItem.first << '\t' << mapItem.second << '\n';
    }

    cout<<endl;
}
```

‍

![image](assets/image-20231117163228-ai17zs4.png)​

### 14.7 容器适配器

三种容器适配器分别为：stack,queue和priority_queue。容器适配器不支持迭代器。适配器类的好处是可以选择适当的基础数据结构。三种适配器都提供push和pop函数。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231210133253236.png" alt="image-20231210133253236" style="zoom:67%;" />

栈和队列的模板：

```cpp
template <class T,class Sequence=deque<T> > class stack;//栈

template <class T,class FrontInsertionSequence=deque<T> > class queue;//队列
```

栈可以用任何一种顺序容器作为基础容器，而队列只允许使用前插顺序容器(双端队列deque或列表list)

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231210135442670.png" alt="image-20231210135442670" style="zoom:67%;" />

#### 14.7.1 stack

stack类来自头文件\<stack>。允许在称为顶部的一端插入和删除，因此堆栈通常称为后进先出数据结构。

```cpp
#include <iostream>
#include <stack>
#include <vector>
#include <list>
using namespace std;

// pushElements function-template prototype
template<typename T> void pushElements(T& stackRef);

// popElements function-template prototype
template<typename T> void popElements(T& stackRef);

int main(){
    // stack with default underlying deque
    stack<int> intDequeStack;

    // stack with underlying vector
    stack<int, vector<int>> intVectorStack;

    // stack with underlying list
    stack<int, list<int>> intListStack;

    // push the values 0-9 onto each stack
    cout << "Pushing onto intDequeStack: ";
    pushElements(intDequeStack);
    cout << "\nPushing onto intVectorStack: ";
    pushElements(intVectorStack);
    cout << "\nPushing onto intListStack: ";
    pushElements(intListStack);
    cout << endl << endl;

    // display and remove elements from each stack
    cout << "Popping from intDequeStack: ";
    popElements(intDequeStack);
    cout << "\nPopping from intVectorStack: ";
    popElements(intVectorStack);
    cout << "\nPopping from intListStack: ";
    popElements(intListStack);
    cout << endl;
}

// push elements onto stack object to which stackRef refers
template<typename T> void pushElements(T& stackRef){
    for (int i{0}; i < 10; ++i){
        stackRef.push(i); // push element onto stack
        cout << stackRef.top() << ' '; // view (and display) top element
    }
}

// pop elements from stack object to which stackRef refers
template<typename T> void popElements(T& stackRef){
    while(!stackRef.empty()){
        cout << stackRef.top() << ' '; // view (and display) top element
        stackRef.pop(); // remove top element
    }
}
```

‍

![image](assets/image-20231117170454-0mh2ygo.png)​

top函数并没有移除栈中的元素。pop函数移除位于栈顶部的元素，并不返回任何值。push函数向栈中添加元素，top函数显示位于栈顶的元素，pop函数移除位于栈顶部的元素。

#### 14.7.2 queue

queue来自头文件\<queue>，queue中停留时间最长的元素是下一个删除的元素，因此队列称为先进先出 （FIFO） 数据结构。queue只允许从后面插入新元素，从前面删除元素。

![image](assets/image-20231117201553-ukb3n1y.png)

‍

```cpp
#include <iostream>
#include <queue>
using namespace std;

int main(){
    queue<double> values; // queue with doubles

    // push elements onto queue values
    values.push(3.2);
    values.push(9.8);
    values.push(5.4);

    cout << "Popping from values: ";

    // pop elements from queue
    while(!values.empty()){
        cout << values.front() << ' '; // view front element
        values.pop(); // remove element
    }
    cout<<endl;
}
```

‍

![image](assets/image-20231117202607-0nspja7.png)​

#### 14.7.3 priority_queue

priority_queue来自头文件\<queue>。允许按排序后的顺序将元素插入到容器中，并从前面删除元素。默认情况下，priority_queue的元素存储在向量中。将元素添加到priority_queue时，它们将按优先级顺序插入，这样优先级最高的元素（即最大值）将成为从priority_queue中删除的第一个元素。这通常是通过在称为堆的数据结构中排列元素来实现的（不要与动态分配的内存的堆混淆），该堆始终在数据结构的前面保持最大值（即最高优先级的元素）。默认情况下，元素的比较是使用comparator function object less\<T>，但您可以提供不同的比较器。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231210135731803.png" alt="image-20231210135731803" style="zoom:67%;" />

有几种常见的priority_queue操作。函数push根据priority_queue的优先级顺序在适当的位置插入元素，然后按优先级顺序对元素进行重新排序。函数 pop 删除priority_queue中优先级最高的元素。top 获取对 priority_queue 的 top 元素的引用（通过调用基础容器的函数 front 来实现）。empty 确定priority_queue是否为空（通过调用基础容器的函数 empty 来实现）。size 获取priority_queue中的元素数（通过调用基础容器的函数 size 实现）。

```cpp
#include <iostream>
#include <queue>
using namespace std;

int main(){
    priority_queue<double> priorities; // create priority_queue

    // push elements onto priorities
    priorities.push(3.2);
    priorities.push(9.8);
    priorities.push(5.4);

    cout << "Popping from priorities: ";

    // pop element from priority_queue
    while(!priorities.empty()){
        cout << priorities.top() << ' '; // view top element
        priorities.pop(); // remove top element
    }
    cout<<endl;
}
```

![image](assets/image-20231117203415-82cy5mz.png)​

‍

### 14.8 bitset类

bitset是 C++ 标准库中的一个类，用于表示二进制位序列。它提供了一种方便的方式来处理二进制数据，尤其适用于位运算操作。表示一个固定长度的位序列，每个位都只能是 0 或 1。这个固定长度在创建对象时指定，并且不能在运行时更改。类似于整数类型，`std::bitset`​ 支持多种操作，包括位运算、位查询和位设置。

```cpp
 #include <bitset>
 ​
 std::bitset<N> bitset1; // 创建一个长度为 N 的 bitset，所有位都被初始化为 0
 std::bitset<N> bitset2(value); // 使用二进制整数 value 初始化一个长度为 N 的 bitset
 std::bitset<N> bitset3(string); // 使用二进制字符串 string 初始化一个长度为 N 的 bitset
 std::bitset<N> bitset4(bitset); // 使用另一个 bitset 初始化一个长度为 N 的 bitset
```

其中，`value`​ 是一个无符号整数，`string`​ 是一个只包含 `'0'`​ 和 `'1'`​ 的字符串，`bitset`​ 是另一个 `std::bitset`​ 对象。

* `size()`​ 返回 `std::bitset`​ 的长度
* `count()`​ 返回 `std::bitset`​ 中值为 1 的位的数量
* `any()`​ 返回 `std::bitset`​ 中是否存在值为 1 的位
* `none()`​ 返回 `std::bitset`​ 中是否所有位都是 0
* `all()`​ 返回 `std::bitset`​ 中是否所有位都是 1
* `test(pos)`​ 返回 `std::bitset`​ 中位于 `pos`​ 位置的值
* `set(pos)`​ 将 `std::bitset`​ 中位于 `pos`​ 位置的值设为 1
* `reset(pos)`​ 将 `std::bitset`​ 中位于 `pos`​ 位置的值设为 0
* `flip(pos)`​ 将 `std::bitset`​ 中位于 `pos`​ 位置的值取反
* `to_ulong()`​ 返回 `std::bitset`​ 转换成的无符号整数值
* `to_ullong()`​ 返回 `std::bitset`​ 转换成的无符号长整数值

`std::bitset`​ 重载了许多二进制运算符，如 `&`​、`|`​、`^`​、`~`​ 等，使其支持类似于整数类型的位运算操作。例如：

```cpp
 std::bitset<4> bitset1("1010");
 std::bitset<4> bitset2("0110");
 
 std::bitset<4> bitset3 = bitset1 & bitset2; // 按位与运算
 std::bitset<4> bitset4 = bitset1 | bitset2; // 按位或运算
 std::bitset<4> bitset5 = bitset1 ^ bitset2; // 按位异或运算
 std::bitset<4> bitset6 = ~bitset
```

还可以使用左移、右移运算符进行位移操作：

```cpp
 std::bitset<4> bitset1("0101");
 
 std::bitset<4> bitset2 = bitset1 << 2; // 左移 2 位，结果为 "010100"
 std::bitset<4> bitset3 = bitset1 >> 1; // 右移 1 位，结果为 "0010"
```

`std::bitset`​ 还支持 `to_string()`​ 方法，将其转换成二进制字符串表示：

```cpp
 std::bitset<4> bitset1("1010");
 std::string str = bitset1.to_string(); // "1010"
```

`std::bitset`​ 可以作为容器类型使用，可以使用下标访问、迭代器等方式访问其元素。



### 14.9 auto关键字

auto 是在变量定义的时候，用别人的类型作为自己类型的一种定义变量的方式。也叫做**类型自动推断。** 

1.auto必须在定义的时候初始化。

```cpp
int  a = 1;
auto b = a;//b的类型为a的类型 int
auto b1;//编译器无法推导b1的类型
b1=10;//错误！
```

2.定义在一个auto序列的变量必须始终推导成同一类型

```cpp
auto a1=10,a2=20;//正确
auto b1=20,b2=2.5//错误,没有推导为同一类型
```

3.如果初始化表达式是引用或const,则去除引用或cons语义。auto不管&和const

```cpp
int a{10};int& b=a;
auto c=b;//c的类型为int而非int&

const int a1{90};
auto b1=a1;//b1的类型为int而非const int
```

4.如果auto关键字带上&号，则不去除引用或const语义。

```cpp
int a{10};int& b=a;
auto& c=b;//c的类型为int&

const int a1{90};
auto& b1=a1;//b1的类型为const int
```

5.初始化表达式为数组时，auto关键字推导类型为指针。

```cpp
int a3[3]={1,3,4};
auto b3=a3;
cout<<typeid(b3).name()<<endl;//输出为int*
```

6.若表达式为数组且auto带上&，则推导类型为数组类型。

```cpp
int a3[3]={2,4,5};
auto& b7=a3;
cout<<typeid(b7).name()<<endl;//输出int [3]
```

7.C++14中，auto可以作为函数的返回值类型和参数类型。

8.要避免在一行中使用直接列表初始化和拷贝列表初始化。

```cpp
auto x{1},y={2};//有问题，不要同时使用直接和拷贝列表初始化
```

示例：

![image-20240407122519859](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240407122519859.png)

auto最常用的场景是对于复杂类型的简化。

```cpp
#include <iostream>
#include <typeinfo>
using std::cout;
using std::cin;
using std::endl;


auto max(int x,int y){
    return x>y?x:y;
}

int main() {
    //auto变量必须在定义时初始化
    auto x=3;
    auto y{42};//初始化列表的方式
    //定义在一个auto序列的变量必须始终推导成为同一类型
    auto x1{2},x2{7},x3{4};
    //如果初始表达式是引用或者const，则去除引用或者const
    int y1{4},&y2{y1};
    auto y3{y2};
    cout<<typeid(y3).name()<<endl;
    //如果auto关键字带上&，则不去除引用或const语义
    auto& z1{y2};
    cout<<typeid(z1).name()<<endl;
    //初始化表达式为数组时，auto关键字推导类型为指针
    int p[3]{1,2,3};
    auto p1=p;
    cout<<typeid(p1).name()<<endl;
    //若表达式为数组且auto带上&，则推导类型为是数组类型
    auto& p2=p;
    cout<<typeid(p2).name()<<endl;
    //C++14中，auto可以作为函数的返回值类型和参数类型
    cout<<max(x1,x2)<<endl;

    return 0;
}

```

**尽量使用auto关键字：**

使用auto是为了代码的正确性、性能、可维护性、健壮性和方便性。

对于C++的原生数组，是不能使用auto直接做类型推断的。不可以使用auto关键字来定义数组的类型。

```cpp
auto a[3]{1,4,6};//错误！
```



### 14.10 decltype关键字

利用已知类型声明新变量，在编译时期推导一个表达式的类型，而不用初始化，语法格式有些像sizeof

decltype主要用于泛型编程

代码示例:

```cpp
#include <iostream>
using namespace std;

int fun1(){
	return 10;
}

auto fun2(){
	return 'g';
}//C++14

int main(){
    decltype(fun1()) x;//不会执行fun1()函数
    decltype(fun2()) y=fun2();
    cout<<typeid(x).name()<<endl;
    cout<<typeid(y).name()<<endl;
    
    return 0;
}
```

![image-20240407113434235](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20240407113434235.png)

decltype和auto都是C++11自动类型推导的关键字。它们有很多差别：

1. auto忽略最上层的const，decltype则保留最上层的const
2. auto忽略原有类型的引用，decltype则保留原有类型的引用
3. 对解引用操作，auto推断出原有类型，decltype推断出引用；
4. **auto推断时会实际执行，decltype不会执行，只做分析。**
5. 总之在使用中过程中和const、引用和指针结合时需要特别小心。



## 15.标准库算法

### 15.1 引言

无事可记

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231227200557556.png" alt="image-20231227200557556" style="zoom:80%;" />



### 15.2 最低迭代器要求(Minimum Iterator Requirements)

容器的一个重要的部分就是它所支持的迭代器类型。这决定了容器可以使用哪种算法。例如，vector和array都支持random-access iterators。所有的标准库算法都可以用于vector，不改变容器大小的算法也可以用于array。采用迭代器参数的每个标准库算法都要求这些迭代器提供最低级别的功能。例如，如果算法需要前向迭代器，则该算法可以在支持前向迭代器、双向迭代器或随机访问迭代器的任何容器上运行。

**标准库算法不依赖于它们所操作的容器的实现细节。只要容器（或内置数组）的迭代器满足算法的要求，算法就可以在容器上运行。**

标准库容器的实现非常简洁。这些算法与容器分离，仅通过迭代器间接对容器的元素进行操作。这种分离使得编写适用于各种容器类的泛型算法变得更加容易。

**使用产生可接受性能的“最弱迭代器”有助于生成最大可重用的组件。例如，如果算法只需要正向迭代器，则可以将其与任何支持正向迭代器、双向迭代器或随机访问迭代器的容器一起使用。但是，需要随机访问迭代器的算法只能与具有随机访问迭代器的容器一起使用。**

#### 15.2.1 迭代器失效

迭代器仅指向容器元素，因此当发生某些容器修改时，迭代器可能会失效。例如，如果在向量上调用 clear，则其所有元素都将被销毁。在调用 clear 之前指向该向量元素的任何迭代器现在都将无效。

在这里，我们总结了迭代器在insert和erase操作期间何时失效。

![image](assets/image-20231117212320-bp5d1jo.png)​

When erasing from a container, iterators to the erased elements are invalidated. In addition:

![image](assets/image-20231117212351-rtfbxbk.png)

### 15.3 Lambda表达式

lambda表达式允许自定义匿名函数，并将它们传递给函数。表达式在函数内部定义，可以使用和操作封闭函数的局部变量。

```cpp
#include <iostream>
#include <array>
#include <algorithm>
#include <iterator>
using namespace std;

int main(){
    const size_t SIZE{4};
    array<int,SIZE> values{1,2,3,4};
    ostream_iterator<int> output{cout," "};

    cout<<"values contains: ";
    copy(values.cbegin(), values.cend(), output);
    cout << "\nDisplay each element multiplied by two: ";

    // output each element multiplied by two
    for_each(values.cbegin(), values.cend(),
             [](auto i) {cout << i * 2 << " ";});

    // add each element to sum
    int sum = 0; // initialize sum to zero
    for_each(values.cbegin(), values.cend(), [&sum](auto i) {sum += i;});

    cout << "\nSum of value's elements is: " << sum << endl; // output sum
}
```

![image](assets/image-20231118090658-z08co6d.png)​

#### 15.3.1 for_each算法

for_each的前两个参数代表要处理的元素的范围。

```cpp
    const size_t SIZE{4};
    array<int,SIZE> values{1,2,3,4};
    ostream_iterator<int> output{cout," "};

    cout<<"values contains: ";
    copy(values.cbegin(), values.cend(), output);
    cout << "\nDisplay each element multiplied by two: ";

    // output each element multiplied by two
    for_each(values.cbegin(), values.cend(),
             [](auto i) {cout << i * 2 << " ";});
```

上述代码中，处理范围从values的第一个元素到最后一个元素。第三个参数指定范围内每个元素要调用的函数。对于上例，for_each将当前的每个元素传递给lambda表达式作为lambda表达式的参数，然后表达式使用这些元素执行它的功能。

#### 15.3.2 Lambda with an Empty Introducer

```cpp
[](auto i) {cout << i * 2 << " ";}
```

([ ])此方括号为lambda introducer，后面跟参数列表和函数体。lambda表达式可以使用表达式定义位置的函数的变量。lambda introducer允许指定表达式使用的变量。在C++11中必须将参数的类型明确指定，在C++14中可以使用自动类型推断(auto)。

```cpp
void timesTwo(int i){
    cout << i * 2 << " ";
}
```

如果我们实现定义了如上所述的函数，for_each函数就可以将上述函数作为第三个参数，如下所示：

```cpp
for_each(values.cbegin(), values.cend(), timesTwo);
```

#### 15.3.3 Lambda with a Nonempty Introducer—Capturing Local Variables

```cpp
 for_each(values.cbegin(), values.cend(), [&sum](auto i) {sum += i;});
```

第二次调用for_each函数，再次使用lambda表达式：

```cpp
[&sum](auto i) {sum += i;}
```

此表达式通过引用捕获局部变量sum。

#### 15.3.4 Lambda表达式的返回类型

如果lambda的函数体包含如下类型的语句，编译器可以推断lambda表达式的返回类型：

```cpp
return expression;
```

其他情况下，lambda表达式的返回类型为void，除非显式的指定表达式的返回类型：

```cpp
[](parameterList) -> type {lambdaBody}
```

### 15.4 算法

下述为C++中的几个算法

#### 15.4.1 fill, fill_n, generate and generate_n

‍

```cpp
#include <iostream>
#include <algorithm>
#include <array>
#include <iterator>
using namespace std;

// generator function returns next letter (starts with A)
char nextLetter(){
    static char letter{'A'};
    return letter++;
}

int main(){
    array<char,10> chars;
    fill(chars.begin(),chars.end(),'5');//fill chars with 5s

    cout<<"chars after filling with 5s:\n";
    ostream_iterator<char> output{cout," "};
    copy(chars.cbegin(),chars.cend(),output);

    //fill first five elements of chars with As
    fill_n(chars.begin(),5,'A');

    cout << "\n\nchars after filling five elements with As:\n";
    copy(chars.cbegin(), chars.cend(), output);

    // generate values for all elements of chars with nextLetter
    generate(chars.begin(), chars.end(), nextLetter);

    cout << "\n\nchars after generating letters A-J:\n";
    copy(chars.cbegin(), chars.cend(), output);

    // generate values for first five elements of chars with nextLetter
    generate_n(chars.begin(), 5, nextLetter);

    cout << "\n\nchars after generating K-O for the"
       <<" first five elements:\n";
    copy(chars.cbegin(), chars.cend(), output);
    cout << endl;

    // generate values for first three elements of chars with a lambda
    generate_n(chars.begin(),3,[](){
        static char letter{'A'};
        return letter++;
    });

    cout << "\nchars after using a lambda to generate A-C "
       <<"for the first three elements:\n";
    copy(chars.cbegin(), chars.cend(), output);
    cout << endl;

}
```

![image](assets/image-20231118183428-6av80ez.png)​

##### **fill算法：**

```cpp
fill(chars.begin(),chars.end(),'5');//fill chars with 5s
```

上述代码，将字符5放置到从chars.begin()开始到chars.end()结束的每个位置上。两个参数都至少应该是forward iterators。

##### fill_n算法：

```cpp
    //fill first five elements of chars with As
    fill_n(chars.begin(),5,'A');
```

上述代码将字符A放入到chars的前五个元素的位置。第一个参数至少应该是output iterator。第二个参数指明了应该插入几个元素。第三个参数指明了插入的元素。

##### generate算法：

```cpp
    // generate values for all elements of chars with nextLetter
    generate(chars.begin(), chars.end(), nextLetter);
```

generate 算法将对生成器函数 nextLetter 的调用结果放在从 chars.begin（） 到 chars.end（） 的每个 chars 元素中，但不包括 chars.end（）。作为第一个和第二个参数提供的迭代器必须至少是正向迭代器。函数 nextLetter定义一个名为 letter 的静态局部 char 变量，并将其初始化为“A”。第 12 行中的语句返回 letter 的当前值，然后对其值进行后递增，以便在下次调用该函数时使用。

##### **generate_n算法：**

```cpp
    // generate values for first five elements of chars with nextLetter
    generate_n(chars.begin(), 5, nextLetter);
```

使用 generate_n 算法将对生成器函数 nextLetter 的调用结果放在chars的五个元素中，从 chars.begin（） 开始。作为第一个参数提供的迭代器必须至少是输出迭代器。

##### 在generate_n算法中使用lambda表达式：

```cpp
    // generate values for first three elements of chars with a lambda
    generate_n(chars.begin(),3,[](){
        static char letter{'A'};
        return letter++;
    });
```

#### equal, mismatch and lexicographical_compare

### 15.5 函数对象(仿函数)

![image](assets/image-20231118194905-0vzngkl.png)​

重载函数调用操作符的类，其对象常称为函数对象（function object），即它们是行为类似函数的对象，也叫仿函数(functor)。其实就是重载“()”操作符，使得类对象可以像函数那样调用。函数对象可以没有参数，也可以带有若干参数，其功能是获取一个值，或者改变操作的状态。

<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231208162902566.png" alt="image-20231208162902566" style="zoom:80%;" />



<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231227153344385.png" alt="image-20231227153344385" style="zoom:80%;" />

如果一个类将`()`​运算符重载为成员函数，这个类就称为函数对象类，这个类的对象就是函数对象。函数对象是一个对象，但是使用的形式看起来像函数调用，实际上也执行了函数调用，因而得名。**返回值为bool类型的一元函数对象，就称之为一元谓词。二元谓词同理。**

```cpp
#include <iostream>
using namespace std;

class CAverage
{
public:
    double operator()(int a1, int a2, int a3)
    {  //重载()运算符
        return (double)(a1 + a2 + a3) / 3;
    }
};

int main()
{
    CAverage average;  //能够求三个整数平均数的函数对象
    cout << average(3, 2, 3);  //等价于 cout << average.operator(3, 2, 3);
    return 0;
}
```

`()`​是目数不限的运算符，因此重载为成员函数时，有多少个参数都可以。average 是一个对象，average(3, 2, 3) 实际上就是 average.operator(3, 2, 3)，这使得 average 看上去像函数的名字，故称其为函数对象。

#### 15.5.1 函数对象应用示例

C++STL中有以下实现“累加”功能的算法（函数模板）:

```cpp
template <class InIt, class T, class Pred>
T accumulate(InIt first, InIt last, T val, Pred op);
```

```cpp
#include <iostream>
#include <array>
#include <algorithm>
#include <numeric>
#include <functional>
#include <iterator>
using namespace std;

// binary function adds square of its second argument and the
// running total in its first argument, then returns the sum
int sumSquares(int total,int value){
    return total + value * value;
}

// Class template SumSquaresClass defines overloaded operator()
// that adds the square of its second argument and running
// total in its first argument, then returns sum
template<typename T>
class SumSquaresClass{
public:
    // add square of value to total and return result
    T operator()(const T& total, const T& value){
        return total + value * value;
    }
};

int main() {
    const size_t SIZE{10};
    array<int, SIZE> integers{1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    ostream_iterator<int> output{cout, " "};//why? ostream_iterator 迭代器

    cout << "array integers contains: ";
    copy(integers.cbegin(), integers.cend(), output);

    // calculate sum of squares of elements of array integers
    // using binary function sumSquares
    int result{accumulate(integers.cbegin(), integers.cend(),0, sumSquares)};

    cout << "\n\nSum of squares of integers' elements using "
            << "binary function sumSquares: " << result;

    // calculate sum of squares of elements of array integers
    // using binary function object
    result = accumulate(integers.cbegin(), integers.cend(),0, SumSquaresClass<int>{});

    cout << "\n\nSum of squares of integers' elements using binary"
            << "\nfunction object of type SumSquaresClass<int>: "
            <<result;

    // calculate sum of squares array's elements using a lambda
    result = accumulate(integers.cbegin(), integers.cend(),0,
                        [](auto total, auto value){return total + value * value;});

    cout << "\n\nSum of squares of integer's elements using a lambda: "
            << result << endl;
}
```

![image](assets/image-20231124213130-ul020tr.png)​

‍

## 16. 异常处理

### 16.1 引言

异常处理使您能够创建可以处理（即解决）异常的应用程序，并在发生无法或不应处理的异常时执行适当的清理。

‍![image-20231229200927238](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231229200927238.png)

‍![image-20231229201154058](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231229201154058.png)

‍![image-20231229202347409](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231229202347409.png)

‍

‍![image-20231229202700899](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231229202700899.png)

‍![image-20231229203624740](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231229203624740.png)

‍

‍![image-20231229203653706](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231229203653706.png)



### 16.2 C++ throw(抛出异常用法详解)

异常处理是许多现代编程语言中不可或缺的一部分，C++ 也不例外。通过使用 throw、try、和 catch 关键字，C++ 为程序员提供了强大的异常处理机制。

#### 16.2.1 throw的基础用法

throw 是 C++ 异常处理机制中的一个关键字，用于在检测到异常情况时触发异常，语法格式如下：

```c++
throw 异常信息
```

异常信息可以是一个变量，也可以是一个表达式，表示要抛出的异常对象。

```c++
throw 1; // 抛出一个整数的异常
throw “abced”; // 抛出一个字符串的异常
throw int; // 错误，异常信息不能是类型，必须是具体的值
```

当在代码中检测到一个异常情况（如非法输入、资源耗尽等）时，可以使用 throw 关键字来抛出一个异常。这通常会中断当前函数的执行，并将控制权转交给最近的 catch 块。

下列是一个完整的示例：

```c++
#include <iostream>

void testFunction(int choice) {
    if (choice == 1) {
        throw 42;
    }
    else if (choice == 2) {
        throw "String type exception";
    }
    else {
        throw 1.23;
    }
}

int main() {
    try {
        testFunction(2);
    }
    catch (int e) {
        std::cout << "Caught an integer exception: " << e << std::endl;
    }
    catch (const char* e) {
        std::cout << "Caught a string exception: " << e << std::endl;
    }
    catch (const double& e) {
        std::cout << "Caught a standard exception: " << e << std::endl;
    }

    return 0;
}
```

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231022144706421.png" alt="image-20231022144706421" style="zoom:50%;" />
</div>

#### 16.2.2 C++异常类

throw 抛出的异常值，可以是基本数据类型，也可以是类类型。C++ 标准库中提供了一些常见的异常类，它们定义在`<stdexcept>`头文件中。

如下是从\<stdexcept> 头文件中摘录的一部分异常类：

```c++
namespace std
{
    class logic_error; // logic_error: 表示程序逻辑错误的基类。
    class domain_error; // 当数学函数的输入参数不在函数的定义域内时抛出。
    class invalid_argument; // 当函数的一个参数无效时抛出。
    class length_error; //当操作导致容器超过其最大允许大小时抛出。
    class out_of_range; // 当数组或其他数据结构访问越界时抛出。
   
    class runtime_error;// 表示运行时错误的基类。
    class range_error; // 当数学计算的结果不可表示时抛出。
    class overflow_error; // 当算术运算导致溢出时抛出。
    class underflow_error; // 当算术运算导致下溢时抛出。
}
```

```c++
#include <iostream>
#include <stdexcept>

void divideNumbers(double num1, double num2) {
    if (num2 == 0) {
        throw std::invalid_argument("Denominator cannot be zero");
    }
    std::cout << "Result: " << num1 / num2 << std::endl;
}

int main() {
    try {
        divideNumbers(10, 2);
        divideNumbers(10, 0);
    } catch (const std::invalid_argument& e) {
        std::cerr << "Caught exception: " << e.what() << std::endl;
    }

    return 0;
}
```

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231022145640506.png" alt="image-20231022145640506" style="zoom:50%;" />
</div>


在上述代码中，divideNumbers() 函数接受两个浮点数，并尝试进行除法。如果除数（denominator）是 0，则通过 throw 关键字抛出一个 std::invalid_argument 异常。这个异常会被 main() 函数中的 catch 块捕获，并输出相应的错误消息。

### 16.3 C++异常处理(try和catch)

程序运行时常会碰到一些错误，例如除数为 0、年龄为负数、数组下标越界等，这些错误如果不能发现并加以处理，很可能会导致程序崩溃。C++ 异常处理机制就可以让我们捕获并处理这些错误，然后我们可以让程序沿着一条不会出错的路径继续执行，或者不得不结束程序，但在结束前可以做一些必要的工作，例如将内存中的数据写入文件、关闭打开的文件、释放分配的内存等。

运行时错误如果放任不管，系统就会执行默认的操作，终止程序运行，也就是我们常说的程序崩溃（Crash）。

一个发生运行时错误的程序：

```c++
#include <iostream>
#include <string>
using namespace std;

int main(){
    string str = "http://c.biancheng.net";
    char ch1 = str[100];  //下标越界，ch1为垃圾值
    cout<<ch1<<endl;
    char ch2 = str.at(100);  //下标越界，抛出异常
    cout<<ch2<<endl;
    return 0;
}
```

运行代码，在控制台输出 ch1 的值后程序崩溃。下面我们来分析一下原因。

at() 是 string 类的一个成员函数，它会根据下标来返回字符串的一个字符。与`[ ]`不同，at() 会检查下标是否越界，如果越界就抛出一个异常；而`[ ]`不做检查，不管下标是多少都会照常访问。

> 所谓抛出异常，就是报告一个运行时错误，程序员可以根据错误信息来进一步处理。

上面的代码中，下标 100 显然超出了字符串 str 的长度。由于第 6 行代码不会检查下标越界，虽然有逻辑错误，但是程序能够正常运行。而第 8 行代码则不同，at() 函数检测到下标越界会抛出一个异常，这个异常可以由程序员处理，但是我们在代码中并没有处理，所以系统只能执行默认的操作，也即终止程序执行。

#### 16.3.1 捕获异常

我们可以借助 C++ 异常机制来捕获上面的异常，避免程序崩溃。捕获异常的语法为：

```c++
try{
    //可能抛出异常的语句
}
catch(exceptionType variable){
    //处理异常的语句
}
```

`try`和`catch`都是 C++ 中的关键字，后跟语句块，不能省略`{ }`。try 中包含可能会抛出异常的语句，一旦有异常抛出就会被后面的 catch 捕获。从 try 的意思可以看出，它只是“检测”语句块有没有异常，如果没有发生异常，它就“检测”不到。catch 是“抓住”的意思，用来捕获并处理 try 检测到的异常；如果 try 语句块没有检测到异常（没有异常抛出），那么就不会执行 catch 中的语句。

catch 关键字后面的`exceptionType variable`指明了当前 catch 可以处理的异常类型，以及具体的出错信息。稍后再对异常类型展开讲解，当务之急是演示一下 try-catch 的用法，先有一个整体上的认识。

```c++
#include <iostream>
#include <string>
#include <exception>
using namespace std;

int main(){
    string str = "http://c.biancheng.net";
  
    try{
        char ch1 = str[100];
        cout<<ch1<<endl;
    }catch(exception e){
        cout<<"[1]out of bound!"<<endl;
    }

    try{
        char ch2 = str.at(100);
        cout<<ch2<<endl;
    }catch(exception &e){  //exception类位于<exception>头文件中
        cout<<"[2]out of bound!"<<endl;
    }

    return 0;
}
```

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231022192916483.png" alt="image-20231022192916483" style="zoom:50%;" />
</div>


可以看出，第一个 try 没有捕获到异常，输出了一个没有意义的字符（垃圾值）。因为`[ ]`不会检查下标越界，不会抛出异常，所以即使有错误，try 也检测不到。换句话说，发生异常时必须将异常明确地抛出，try 才能检测到；如果不抛出来，即使有异常 try 也检测不到。所谓抛出异常，就是明确地告诉程序发生了什么错误。

第二个 try 检测到了异常，并交给 catch 处理，执行 catch 中的语句。需要说明的是，异常一旦抛出，会立刻被 try 检测到，并且不会再执行异常点（异常发生位置）后面的语句。本例中抛出异常的位置是第 17 行的 at() 函数，它后面的 cout 语句就不会再被执行，所以看不到它的输出。

说得直接一点，检测到异常后程序的执行流会发生跳转，从异常点跳转到 catch 所在的位置，位于异常点之后的、并且在当前 try 块内的语句就都不会再执行了；即使 catch 语句成功地处理了错误，程序的执行流也不会再回退到异常点，所以这些语句永远都没有执行的机会了。本例中，第 18 行代码就是被跳过的代码。

执行完 catch 块所包含的代码后，程序会继续执行 catch 块后面的代码，就恢复了正常的执行流。

为了演示「不明确地抛出异常就检测不到异常」，大家不妨将第 10 行代码改为`char ch1 = str[100000000];`，访问第 100 个字符可能不会发生异常，但是访问第 1 亿个字符肯定会发生异常了，这个异常就是内存访问错误。运行更改后的程序，会发现第 10 行代码产生了异常，导致程序崩溃了，这说明 try-catch 并没有捕获到这个异常。

#### 16.3.2 发生异常的位置

异常可以发生在当前的 try 块中，也可以发生在 try 块所调用的某个函数中，或者是所调用的函数又调用了另外的一个函数，这个另外的函数中发生了异常。这些异常，都可以被 try 检测到。

下述代码为try块中直接发生的异常：

```c++
#include <iostream>
#include <string>
#include <exception>
using namespace std;

int main(){
    try{
        throw "Unknown Exception";  //抛出异常
        cout<<"This statement will not be executed."<<endl;
    }catch(const char* &e){
        cout<<e<<endl;
    }

    return 0;
}
```

下述代码为try块中调用的某个函数发生了异常：

```c++
#include <iostream>
#include <string>
#include <exception>
using namespace std;

void func(){
    throw "Unknown Exception";  //抛出异常
    cout<<"[1]This statement will not be executed."<<endl;
}

int main(){
    try{
        func();
        cout<<"[2]This statement will not be executed."<<endl;
    }catch(const char* &e){
        cout<<e<<endl;
    }

    return 0;
}
```

func() 在 try 块中被调用，它抛出的异常会被 try 检测到，进而被 catch 捕获。从运行结果可以看出，func() 中的 cout 和 try 中的 cout 都没有被执行。

下述代码为 try 块中调用了某个函数，该函数又调用了另外的一个函数，这个另外的函数抛出了异常：

```c++
#include <iostream>
#include <string>
#include <exception>
using namespace std;

void func_inner(){
    throw "Unknown Exception";  //抛出异常
    cout<<"[1]This statement will not be executed."<<endl;
}

void func_outer(){
    func_inner();
    cout<<"[2]This statement will not be executed."<<endl;
}

int main(){
    try{
        func_outer();
        cout<<"[3]This statement will not be executed."<<endl;
    }catch(const char* &e){
        cout<<e<<endl;
    }

    return 0;
}
```

发生异常后，程序的执行流会沿着函数的调用链往前回退，直到遇见 try 才停止。在这个回退过程中，调用链中剩下的代码（所有函数中未被执行的代码）都会被跳过，没有执行的机会了。

`exceptionType`是异常类型，它指明了当前的 catch 可以处理什么类型的异常；`variable`是一个变量，用来接收异常信息。当程序抛出异常时，会创建一份数据，这份数据包含了错误信息，程序员可以根据这些信息来判断到底出了什么问题，接下来怎么处理。

异常既然是一份数据，那么就应该有数据类型。C++规定，异常类型可以是 int、char、float、bool 等基本类型，也可以是指针、数组、字符串、结构体、类等聚合类型。C++ 语言本身以及标准库中的函数抛出的异常，都是 exception 类或其子类的异常。也就是说，抛出异常时，会创建一个 exception 类或其子类的对象。

`exceptionType variable`和函数的形参非常类似，当异常发生后，会将异常数据传递给 variable 这个变量，这和函数传参的过程类似。当然，只有跟 exceptionType 类型匹配的异常数据才会被传递给 variable，否则 catch 不会接收这份异常数据，也不会执行 catch 块中的语句。换句话说，catch 不会处理当前的异常。

我们可以将 catch 看做一个没有返回值的函数，当异常发生后 catch 会被调用，并且会接收实参（异常数据）。

但是 catch 和真正的函数调用又有区别：

- 真正的函数调用，形参和实参的类型必须要匹配，或者可以自动转换，否则在编译阶段就报错了。
- 而对于 catch，异常是在运行阶段产生的，它可以是任何类型，没法提前预测，所以不能在编译阶段判断类型是否正确，只能等到程序运行后，真的抛出异常了，再将异常类型和 catch 能处理的类型进行匹配，匹配成功的话就“调用”当前的 catch，否则就忽略当前的 catch。

总起来说，catch 和真正的函数调用相比，多了一个「在运行阶段将实参和形参匹配」的过程。另外需要注意的是，如果不希望 catch 处理异常数据，也可以将 variable 省略掉，也即写作：

```c++
try{
    // 可能抛出异常的语句
}catch(exceptionType){
    // 处理异常的语句
}
```

这样只会将异常类型和 catch 所能处理的类型进行匹配，不会传递异常数据了。

#### 16.3.3 多级catch

```c++
try{
    //可能抛出异常的语句
}catch (exception_type_1 e){
    //处理异常的语句
}catch (exception_type_2 e){
    //处理异常的语句
}
//其他的catch
catch (exception_type_n e){
    //处理异常的语句
}
```

当异常发生时，程序会按照从上到下的顺序，将异常类型和 catch 所能接收的类型逐个匹配。一旦找到类型匹配的 catch 就停止检索，并将异常交给当前的 catch 处理（其他的 catch 不会被执行）。如果最终也没有找到匹配的 catch，就只能交给系统处理，终止程序的运行。

```c++
#include <iostream>
#include <string>
using namespace std;

class Base{ };
class Derived: public Base{ };

int main(){
    try{
        throw Derived();  //抛出自己的异常类型，实际上是创建一个Derived类型的匿名对象
        cout<<"This statement will not be executed."<<endl;
    }catch(int){
        cout<<"Exception type: int"<<endl;
    }catch(char *){
        cout<<"Exception type: cahr *"<<endl;
    }catch(Base){  //匹配成功（向上转型）
        cout<<"Exception type: Base"<<endl;
    }catch(Derived){
        cout<<"Exception type: Derived"<<endl;
    }

    return 0;
}
```

> 在 catch 中，我们只给出了异常类型，没有给出接收异常信息的变量。

本例中，我们定义了一个基类 Base，又从 Base 派生类出了 Derived。抛出异常时，我们创建了一个 Derived 类的匿名对象，也就是说，异常的类型是 Derived。

我们期望的是，异常被`catch(Derived)`​捕获，但是从输出结果可以看出，异常提前被`catch(Base)`​捕获了，这说明 catch 在匹配异常类型时发生了向上转型（Upcasting）。

#### 16.3.4 catch 在匹配过程中的类型转换

C/C++ 中存在多种多样的类型转换，以普通函数（非模板函数）为例，发生函数调用时，如果实参和形参的类型不是严格匹配，那么会将实参的类型进行适当的转换，以适应形参的类型，这些转换包括：

- 算数转换：例如 int 转换为 float，char 转换为 int，double 转换为 int 等。
- 向上转型：也就是派生类向基类的转换，请猛击《[C++向上转型（将派生类赋值给基类）](https://c.biancheng.net/view/2284.html)》了解详情。
- const 转换：也即将非 const 类型转换为 const 类型，例如将 char * 转换为 const char *。
- 数组或函数指针转换：如果函数形参不是引用类型，那么数组名会转换为数组指针，函数名也会转换为函数指针。
- 用户自定的类型转换。

catch 在匹配异常类型的过程中，也会进行类型转换，但是这种转换受到了更多的限制，仅能进行「向上转型」、「const 转换」和「数组或函数指针转换」，其他的都不能应用于 catch。

向上转型在上面的例子中已经发生了，下面的例子演示了 const 转换以及数组和指针的转换：

```c++
#include <iostream>
using namespace std;

int main(){
    int nums[] = {1, 2, 3};
    try{
        throw nums;
        cout<<"This statement will not be executed."<<endl;
    }catch(const int *){
        cout<<"Exception type: const int *"<<endl;
    }

    return 0;
}
```

运行结果：
Exception type: const int *

nums 本来的类型是`int [3]`，但是 catch 中没有严格匹配的类型，所以先转换为`int *`，再转换为`const int *`。

> 数组也是一种类型，数组并不等价于指针，这点已在《[数组和指针绝不等价，数组是另外一种类型](https://c.biancheng.net/view/vip_2018.html)》和《[数组到底在什么时候会转换为指针](https://c.biancheng.net/view/vip_2019.html)》中进行了详细讲解。

### 16.4 C++ exception类：C++标准异常的基类

C++语言本身或者标准库抛出的异常都是 exception 的子类，称为标准异常（Standard Exception）。你可以通过下面的语句来捕获所有的标准异常：

```c++
try{
    //可能抛出异常的语句
}catch(exception &e){
    //处理异常的语句
}
```

之所以使用引用，是为了提高效率。如果不使用引用，就要经历一次对象拷贝（要调用拷贝构造函数）的过程。

exception 类位于\<exception> 头文件中，它被声明为：

```c++
class exception{
public:
    exception () throw();  //构造函数
    exception (const exception&) throw();  //拷贝构造函数
    exception& operator= (const exception&) throw();  //运算符重载
    virtual ~exception() throw();  //虚析构函数
    virtual const char* what() const throw();  //虚函数
}
```

这里需要说明的是 what() 函数。what() 函数返回一个能识别异常的字符串，正如它的名字“what”一样，可以粗略地告诉你这是什么异常。不过C++标准并没有规定这个字符串的格式，各个编译器的实现也不同，所以 what() 的返回值仅供参考。

下图展示了 exception 类的继承层次：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231022203032872.png" alt="image-20231022203032872" style="zoom:50%;" />
</div>


先来看一下 exception 类的直接派生类：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231022203113413.png" alt="image-20231022203113413" style="zoom:50%;" />
</div>


logic_error 的派生类：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231022203136087.png" alt="image-20231022203136087" style="zoom:50%;" />
</div>


runtime_error 的派生类：

<div>
<img src="C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231022203153077.png" alt="image-20231022203153077" style="zoom:50%;" />
</div>
![image-20231229203728961](C:\Users\22364\AppData\Roaming\Typora\typora-user-images\image-20231229203728961.png)

### 16.4 自定义异常类







## 17. 模板

### 17.1 函数模板(Function Template )

1.Function template (函数模板)

 C++引入了带有泛型的函数模板

1.1. How to specify a type parameter? (如何声明类型参数)？ 

```
<typename T> : 描述性强，较好

<class T> : 易与类声明混淆，不推荐
```

 

<img src="https://edu-image.nosdn.127.net/6624DA8B3BC36817154DD38DF7F70F44.jpg?imageView&thumbnail=890x0&quality=100" alt="img" style="zoom:67%;" />



2.Multiple type parameters (多个类型参数)

 **若函数模板有多于一个类型参数该怎么处理？**

 应该类型参数间用逗号分隔

```cpp
template < typename  T, typename  S >

auto add (T x1, S x2) { //C++14

  return (x1 + x2);

}
```

 2.2. 编码规范

Names representing template types should be a single uppercase letter.

用于表示模板类型的名字应该使用一个大写字母

例如：

```cpp
template<class T> ... 

template<class C, class D> ...
```

3.Using Function Template (使用函数模板)

```cpp
template <typename T, typename S>

auto add (T x1, S x2) { //C++14

  return (x1 + x2);

}

int main () {
    auto y = add ( 1, 2.0 );
    return 0;
} 
```

编译器根据函数调用的**实参**，生成函数模板的实例：

<img src="https://edu-image.nosdn.127.net/F042E42F299D32DF683CAD747545F204.jpg?imageView&thumbnail=890x0&quality=100" alt="img" style="zoom:67%;" />

### 17.2 函数模版实例化

**1.什么是函数模板实例化**

1.1. 实例化：

 函数模板只是蓝图，本身不是不是类型、函数。编译器扫描代码，遇到模版定义时，并不立即产生代码。确定模板实参后，编译器生成实际函数代码

1.2. 两种实例化方法 (确定模板实参的方法)

Explicit instantiation (显式实例化)

Implicit instantiation (隐式实例化)

**2.Explicit instantiation (显式实例化)**

强制某些函数实例化，可出现于程序中模板定义后的任何位置。

```cpp
template < typename T >
void f(T s){
    std::cout << s << '\n';
}

template void f<double>(double); // 实例化，编译器生成代码
                 // void f(*double* s) {  // *T*: *double*

                //   std::cout << s << '\n';

               // }

template void f<>(char);  // 实例化 f<char>(char) ，推导出模板实参
template void f(int);    // 实例化 f<int>(int) ，推导出模板实参
```

**3.Implicit instantiation (隐式实例化)**

编译器查看函数调用，推断模版实参，实现隐式实例化。 

```cpp
#include <iostream>

template<typename T>

void f(T s) {

  std::cout << s << '**\n**';

}

int main(){

  f<double>(1); // 实例化并调用 f<double>(double)

  f<>('a'); // 实例化并调用 f<char>(char)

  f(7); // 实例化并调用 f<int>(int)

  void (*ptr)(std::string) = f; // 实例化 f<string>(string)

}
```

**4.Instantiated function/class (实例函数/实例类)**

**4.1. C++11 (Section:14.7)** 

A function instantiated from a function template is called an ***instantiated function\***. A class instantiated from a class template is called an ***instantiated class\***.(由函数模板实例化得到的函数叫做“实例函数”，由类模板实例化得到的类叫做“实例类”)

非正规称呼:template function / template class

### 17.3 类模板

**1.Class Template (类模板)**

1.1类模板是将类中某些类型变为泛型，从而定义一个模板

1.2. Generic types of class members (类成员的泛型)

Data field member(数据域成员) : can be of a generic data ***type\*** (可以成为泛型数据)

Function  member(函数成员): return ***type\***, parameter ***type\***, local var ***type\*** (返回值类型、参数类型、局部变量都可以成为泛型)

**2.Class Templates**

![img](https://edu-image.nosdn.127.net/8B4408A7FD82F254AAB4EF6B6F144F7F.jpg?imageView&thumbnail=890x0&quality=100)

**3.Syntax for class template (类模板的语法)** 

```cpp
template<typename T>
class Stack{
public:
    Stack();
    bool empty();
    T peek();
    T push(T value);
    T pop();
    int getSize(); 

private:
    T elements[100];
    int size;
};
//模板前面放

//类型名后跟
template<typename T>
bool Stack<T>::empty()
{
    return (size ==0);
}
//对比non-template class
//  int Stack::peek()
template<typename T>
  T Stack<T>::peek()
{
    return elements[size - 1]; 
}
```

**创建使用类模板时，类的声明和实现要放在同一个文件中，不能分离。**

### 17.4 类模板实例化

**1.显式实例化**

```cpp
template class Stack<int>; // 将类模板实例化为一个处理int类型的Stack类
```

**2.隐式实例化**

```cpp
Stack<char> charStack;  // 先实例化一个CharStack类(名字由编译器按规则生成)

             			// class CharStack { … char elements[100]; … };

             			// 然后用 CharStack charStack; 创建一个对象

Stack<int> intStack;  // 实例化一个IntStack类

                      // class IntStack{ … int elements[100]; … };

                      // 然后用 IntStack intStack; 创建一个对象

 

vector intVector{1, 2, 3}; // C++17，模板类型参数根据初始化语句自动推导

                           // 实例化为 vector<int>
```

 

### 17.5 默认类型与非类型参数

**1.Default type (默认类型)**

1.1. Review: default parameter value (复习：参数的默认值)

```cpp
int circle (int x, int y, int r=100);
```

1.2.  Default type parameter (默认类型参数)

可以为类模板的类型参数指定一个默认类型

例如，指定泛型Stack的默认类型参数为 int

```cpp
template<typename T = int>
class Stack{
 ...
};
```

1.3. 用默认类型定义一个对象

```cpp
//a stack for int values

Stack<> stack;
```

函数模板不能使用默认类型参数。

**2.Non-type Parameters (非类型参数)**

在模板前缀中使用非类型参数，实例化模板时，非类型实参应该是对象 

```cpp
template<typename T, int capacity>
class Stack{
 ...
private:
   T elements[capacity];
   int size;
};

Stack<char, 100> charStack;



//对象作为非类型参数
template<typename T, Color c>
class Label{
 ……
};

Color color(0, 0, 255);
Label<char, color> label;
```

### 17.6 模板与继承

普通类可以从类模板实例继承

模板可以从普通类继承

类模板可以继承类模板

 



















 

 







































