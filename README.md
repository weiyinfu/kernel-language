* 本程序为大三时编译原理课程设计,内容是实现一个编译器.也不知道实现是否跟正规的一样,完全凭着感觉实现的.
* 本程序语言名叫kernel,意为只实现了程序语言的内核部分,没有任何语法糖.
* 本程序分为编译器,虚拟机两部分,编译器大概700行,虚拟机大概400行.
* 本程序没啥意义,只是能够加深对编译原理的理解,能够体验自己设计语言的感觉.

关于kernel语言
===================
* 设计原则:简单,实现容易
* 没有运算符,运算符只不过是特殊的函数
* 只有类,像java一样
* 函数中变量定义只能放在函数开头部分
* 原始数据类型只有byte,像int,double可以用byte来实现.
* 没有数组,这点是最差的地方.但是有链表
* 全部库函数都在lib.txt中

关于文件和目录的说明:
=======
* compiler/文件夹是编译器
* machine/文件夹是虚拟机
* source.txt:源文件默认是当前路径下的source.txt
* asm.txt:编译器生成汇编代码,在asm.txt中
* lib.txt是库函数,每一次编译都会把它和source.txt拼接起来
* process.txt:虚拟机的传入文件为asm.txt,输出执行顺序到process.txt中 
* 给出了两个示例程序,一个打印127以内的全部质数,另一个计算从1加到9的和.

如何运行本程序
=================
* 因为compiler和machine中有class有同名冲突,所以要在不同文件夹下编译,即
	
	cd compiler
	javac Box.java Kernel.java
	cd ../machine
	javac Machine.java
	cd ..
	java -cp compiler Kernel
	java -cp machine Machine