---
layout: post
title:  "xv6 初章"
date:   2018-03-04 17:05:13 +0000
categories: operating system
---

###xv6 初章
####xv6是什么
>xv6是MIT为了教学操作系统课程([6.828](http://dspace.mit.edu/handle/1721.1/92292))而开发的一个简易的类unix系统. 通过设计实现一个小的操作系统深入的理解操作系统.

####如何获取xv6
>我们可以通过[课程主页](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-828-operating-system-engineering-fall-2012/index.htm)查看所有需要的资料：
>
> * 10k的[源代码](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-828-operating-system-engineering-fall-2012/lecture-notes-and-readings/MIT6_828F12_xv6-sourc-rev7.pdf),在多个操作系统课程使用的教学操作系统中属于代码量少的一批,代码提供pdf版本，排版精良，可以打印出来查看。
> * 22节[课程](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-828-operating-system-engineering-fall-2012/lecture-notes-and-readings/),详细的配套课件。
> * 5个[lab](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-828-operating-system-engineering-fall-2012/labs/)
> * ...

####环境搭建
我们需要使用指定的编译工具，按照[如下](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-828-operating-system-engineering-fall-2012/tools/)步骤可以编译出前缀为`i386-jos-elf`的一套编译工具，接下来无论是在lab还是其他需要编译代码时，`makefile`已经做了处理，安心的集中精力到代码本身就可以了。

为了可以执行编译出的镜像，需要使用模拟器qemu，具体的安装方式参照[官网](https://www.qemu.org/download/)。

下载[lab1](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-828-operating-system-engineering-fall-2012/labs/lab1.tar.gz)测试环境，在`lab-1`目录下执行`make qemu`,将会进入xv6的shell窗口，通过此窗口，可以执行两条命令`help`|`kerninfo`,执行结果如下

![](https://cl.ly/1y0O2N3K3I3d)

####lab1练习
> lab1有12个练习题目，说实话，有点多。

#####PC启动
> 此练习有两个任务
>
>  * 熟悉x86汇编和计算机的启动流程
>  * 熟悉编译调试工具
>
> 这一部分不需要写任何代码，但是工作量可以说是非常大的。

pc的物理地址分布如下：

![](https://cl.ly/2Y383Y471f0d)

由于设计的限制，此操作系统只能使用前256M的内存，具体原因要随着我们对系统的深入理解来解答。

在同目录下执行`gdb`命令就可以进行调试，目录下的`.gdbinit`已经配置好的调试所需要的目标环境。`si`命令可以逐条指令执行，我们只需要大致了解`BIOS`如何工作，不需要深入细节。

![](https://cl.ly/0U0E101G382G)

#####Boot Loader

#####加载内核

#####内核

初章结束，哈哈^_^

