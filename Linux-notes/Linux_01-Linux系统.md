# Linux系统 

### 一、简介

### 1、操作系统

操作系统（Operating System，简称OS）是管理和控制计算机硬件与软件资源的计算机程序，是直接运行在“裸机”上的最基本的系统软件，任何其它软件都必须在操作系统的支持下才能运行。 

操作系统身负诸如管理与配置内存、决定系统资源供需的优先次序、控制输入与输出设备、操作网络与管理文件系统等基本事务。 



### 2、Linux系统 

Linux是一套免费使用和自由传播的类Unix操作系统，是一个基于POSIX和UNIX的多用户、多任务、支持多线程和多CPU的操作系统。 Linux继承了Unix以网络为核心的设计思想，是一个性能稳定的多用户网络操作系统。 

操作系统分两大阵营：Windows系统 和 Unix的衍生系统（Linux、Mac os x等）



Linux包含了Unix的全部功能和特性。Linux具有以下主要特性:   

- 开放性：系统遵循世界标准规范。
- 多用户：系统资源可以被不同用户各自拥有使用,每个用户可以对自己的资源进行管理，设置权限等。 
- 多任务：同时执行多个程序,而且各个程序的运行互相独立。Linux系统调度每一个进程,平等地访问微处理器。
- 良好的界面：Linux同时具有字符界面和图形界面。      
- 丰富的网络功能：Linux在通信和网络功能方面优于其它操作系统。 Linux 内置了很丰富的免费网络服务器软件、数据库和网页的开发工具 。
- 可靠的系统安全：Linux采取了许多安全技术措施，包括对读、写控制、带保护的子系统、审计跟踪、核心授权等，这为网络多用户环境中的用户提供了必要的安全保障。  
- 良好的可移植性：将操作系统从一个平台转移到另一个平台使它仍然能按其自身的方式运行的能力。 

总结：免费、安全、可靠、稳定、多平台。    

![1532349080616](https://github.com/DeerKing007/Linux_Notes/blob/master/Linux-notes/Linux_pic/1532349080616.png)

- 双系统（Linux和Windows同时存在  开机时选择操作系统）  
- 虚拟机（借助VMware workstation来运行虚拟系统-Linux） 

### 3、Linux的目录结构（了解）

![1532349391932](https://github.com/DeerKing007/Linux_Notes/blob/master/Linux-notes/Linux_pic/1532349391932.png)

- bin  (binaries)存放二进制可执行文件
- sbin  (super user binaries)存放二进制可执行文件，只有root才能访问
- etc (etcetera)存放系统配置文件
- usr  (unix shared resources)用于存放共享的系统资源
- home 存放用户文件的根目录
- root  超级用户目录
- dev (devices)用于存放设备文件
- lib  (library)存放跟文件系统中的程序运行所需要的共享库及内核模块
- mnt  (mount)系统管理员安装临时文件系统的安装点
- boot 存放用于系统引导时使用的各种文件
- tmp  (temporary)用于存放各种临时文件
- var  (variable)用于存放运行时需要改变数据的文件

 

### 4、Linux的Shell

Shell是系统的用户界面，提供了用户与内核进行交互操作的一种接口。它接收用户输入的命令并把它送入内核去执行。 

Shell是一个命令行解释器。 它解释由用户输入的命令并且把它们送到内核。 

同Linux本身一样，Shell也有多种不同的版本。主要有下列版本的Shell：　

- Bourne Shell：是贝尔实验室开发的。

- BASH：是GNU的Bourne Again Shell，是GNU操作系统上默认的shell。

- Korn Shell：是对Bourne SHell的发展，在大部分内容上与Bourne Shell兼容。

- C Shell：是SUN公司Shell的BSD版本。

  

### 二、基本命令 

#### 1、简单的几个命令

- ls：显示指定目录下的文件目录清单（list）
- cd：切换目录，改变当前的工作目录（change directory）
  - cd ~   或  cd  切换到用户主目录（用户家目录）
  - cd  /   切换到根目录
  - cd .. 上一级目录
  - cd . 当前目录
- pwd：显示当前的工作目录  （print working directory）
- man：查看帮助 -- （命令行界面无该命令）-- `yum install man` 安装

补充：在windows和虚拟机之前切换鼠标：`Ctrl + Alt`



#### 2、文件基本操作命令

##### 2.1 ls 命令

作用：显示指定目录下的文件清单

- 不带参数：显示指定目录中的文件清单，如果没有指定任何目录，则默认为当前目录
  - [root@Server ~]# ls               显示当前目录下的文件
  - [root@Server ~]# ls  etc        显示etc目录下的文件
- ls -a 显示所有文件 包含隐藏文件（以.开头的文件）
- ls -l   显示文件的详细信息
- ls -R  递归显示目录下的文件包括子文件
- ls -laR   多个参数结合使用



##### 2.2 mkdir / rmdir 命令

作用：创建目录/删除目录

- mkdir 创建目录
  - mkdir homework 创建一个homework目录
  - mkdir -p homework/a/b/c/d  连续创建多级目录    （了解）
  - mkdir d{1..9}   同时创建d1、d2..d9目录 （了解）
- rmdir 删除目录（只能删除空目录）

补充：创建文件 touch 文件名 --- `touch 1.txt`

##### 2.3 rm命令

作用：删除文件或目录

- rm  文件名
- rm -i  文件名  ：提示是否删除 （与用户交互）
- rm -f  文件名 ：强制删除    （force）
- rm -r 目录名 ：删除目录
  - rm -rf 目录名  强制删除目录，不会有提示



##### 2.4  cp命令 

作用：拷贝文件或目录

- cp 原文件名 新文件名
  - cp 1.txt  11.txt  
  - cp 1.txt   homework/1.txt 
- cp -r 原目录名 新目录名    （拷贝目录必须加-r参数）
  - cp -r homework homework2



##### 2.5  mv命令

作用：移动文件或目录

- mv 原文件名/目录名  新文件名/目录名 
  - mv 1.txt  homework/1.txt   移动文件（剪切）
  - mv 1.txt  1.md  重命名



##### 2.6 通配符

- ` *` 匹配任意多个字符 
  - rm *.txt 删除所有的后缀为txt的文件
  - rm  a* 删除所有的以a开头的文件
- `?`匹配一个字符
  - rm ?.txt 删除文件名只有一个字符的txt文件



#### 3、显示文件内容

##### 3.1 cat命令

作用：显示文件内容在屏幕中

- cat 1.txt 在屏幕上显示1.txt的内容



##### 3.2 more和less命令

作用：分屏显示，非常适合显示超过一屏的文本文件。   按空格翻页

- more  /etc/httpd/conf/httpd.conf

- less    /etc/httpd/conf/httpd.conf

  - 按q键退出显示    

  - 在less下  输入`/关键字` 可以搜索

      

##### 3.2 head/tail命令

作用：显示文件头/尾10行内容

- head httpd.conf 显示头10行
- tail httpd.conf 显示尾10行



#### 4、搜索文件内容grep

作用：根据关键字搜索并显示关键字所在的行

用法：grep [参数] 关键字 文件名

- grep l 1.txt 		显示出l所在的行
- grep "o w" 1.txt  如果要查找中间有空格的 需要加''或“”
- grep -i L 1.txt   忽略大小写查找 即大写L和小写l都可查找到  
- grep -v l 1.txt   显示不匹配的行
- grep -n l 1.txt   显示匹配的行的行号
- grep -c l 1.txt   显示匹配的总行数  



### 三、管理用户、组的命令

Linux采用组来组织和管理用户

在Linux中每个用户有唯一的用户标识符UID，该UID是一个无符号整数。

同时每个用户也必须至少属于一个组，也有组标识符GID。

其中UID与GID独立编号。



#### 1、groupadd 添加组

`[root@server ~]# groupadd  group1`  新增组

`[root@server ~]# groupadd -g 888 group1`  新增组并指定GID   一般不建议手动指定id

功能：创建一个新组group1,其GID号为已存在GID号的下一个顺序编号

说明：创建一个组的同时会在/etc/group文件中为该组增加相应的一行，用来记录该组的名称、GID号及成员等信息。



#### 2、groupdel 删除组

- `[root@server1 ~]# groupdel group2`

  功能：删除指定的组

  注意：当某个组是某现有用户的主要组时，则不能被删除。 



#### 3、useradd 添加用户

- `[root@server1 ~]# useradd  user1`   新增用户   如果没有指定用户组，则用户自己成为一组

  功能：创建一个用户user1，同时在/etc/passwd文件和/etc/shadow文件增加一行，并自动为用户创建相应的主目录：/home/user1。

  说明：/etc/passwd文件记录了系统中每个用户的用户名、UID号、 GID号、主目录、shell等信息。



- `[root@server1 ~]# useradd  -u 600  -g group1  -G group2  -d  /home/student1  user1`

  功能：创建用户user1，其中参数
  - -u指定UID号为600；
  - -g指定用户的主要组为group1(或ID)；
  - -G指定用户的附加组为group2，每个用户可以有多个附加组；
  - -d 指定用户的主目录为/home/student1。

 切换用户：`# su user1`



- 查看用户所在的组

  `[root@server1 ~]# groups user1`

- 修改用户所在的组

  `[root@server1 ~]# usermod -g group2 user1`

  

#### 4、passwd 密码管理

- `[root@server1 ~]# passwd  user1 `        改变口令

  =>输入两次密码即可

  功能：root管理员为用户指定密码 。

  ​        

- `[user1@server1 ~]$ passwd `    改变用户自身密码

  =>输入当前密码

  =>输入两次新密码即可

  功能：用户为自己修改密码。(字母+数字+符号)

  普通用户只能修改自己的密码

  

- ` [root@server1 ~]# passwd  -d  user1`  删除密码

​        Removing password for user user1.

​        passwd: Success

​        功能：参数-d 可以删除指定的用户user1口令，即以user1登录时无需口令。



- `[root@server ~]# passwd  -l  user1 `   禁止用户登录     

  Locking password for user user1.

  passwd: Success

  功能：参数-l 可以给指定的用户user1加锁，即禁止该用户登录,用户密码失效。



- `[root@server1 ~]# passwd  –u  user1`   恢复该用户登录 

  Unlocking password for user user1.

  passwd: Success.

  功能：参数-u 可以给指定的用户user1解锁，即恢复该用户登录。





#### 5、userdel 删除用户

- `[root@server1 ~]# userdel  user1 ` 删除用户

  功能：删除指定的用户user1。 

- `[root@server1 ~]# userdel  -r  user2`

  功能：删除指定的用户user2，同时删除其主目录。



#### 6、id 显示用户信息

- `[root@server1 ~]# id  user1`

  uid=501(user1) gid=501(user1) groups=501(user1)

  功能：显示用户的UID、GID及所属的组信息。



### 四、文件属性

#### 1、chown 改变文件的所有者

- ` [root@server1 ~]# chown  user1 hello.txt`

  功能：将指定文件hello.txt的所有者改为user1。 

- `[root@server1 ~] chown  -R user1 homework`

  功能：参数-R表示递归 将目录下的所有文件的所有者改为user1



#### 2、chgrp 改变文件的所属组

- ` [root@server1 ~]# chown  group1 hello.txt`

  功能：将指定文件hello.txt的属组改为group1。 

- `[root@server1 ~] chown  -R group1 homework`

  功能：参数-R表示递归



#### 3、chmod 改变文件权限

` [root@server1 ~]# ls -l`

```shell
-rw-r--r--    1  Mr_lee  staff    29 12 14 16:15  1.txt
drwxr-xr-x    4  Mr_lee  staff   136 10 11 18:44 Applications
```

第1列：表示是否是目录或文件  -代表文件  d代表目录
第2-4列：表示用户权限 user
第5-7列：表示所在的组权限 group
第8-10列：表示其他人权限 other

r : read     可读
w : write    可写
x : execution 可执行
u : user
g : group
o : other
a : all

=： 表示赋予（设置）指定权限，要注意它会覆盖原权限 

+： add permission 添加权限

-： take away permission 移除权限

示例：

- `chmod a+rwx 1.h`  给所有人(ugo)添加可读可写可执行权限
- `chmod go-wx 1.h`  给所在的组和其他人移除写和执行权限

**数字表示法：**
` chmod 755 1.h`   等价于 用户:rwx 所在组:r-x 其他人:r-x 
即r = 2^2 , w = 2^1 , x =  2^0 ,而 "-" = 0



### 五、查看进程

#### 1、ps命令

- 不带参数

  `[user1@server ~]$ ps`

  功能：查询在当前控制台上运行的进程。 

- 查看所有进程

  `[user1@server ~]$ ps -aux`

  功能：查询系统中所有运行的进程，包括后台进程，其中参数a是所有进程，参数x包括不占用控制台的进程，参数u显示用户。 

- 查看所有进程

  `[user1@server ~]$ ps -ef`

  功能：查询系统中所有运行的进程，包括后台进程，而且可以显示出每个进程的父进程号。 



#### 2、pstree命令 （了解）

- 树状格式显示进程列表

  `[user1@server ~]$ pstree`

- 带进程号的树状格式显示进程列表

  `[user1@server ~]$ pstree -p`



#### 3、top命令（了解）

- `[user1@server ~]$ top`

  功能：动态地显示系统中的进程。 

#### 4、查看端口被哪个进程所占用
 `lsof -i:端口号`

#### 5、kill命令

- 杀掉指定进程  

   `[user1@server ~]$ kill  3029`

- 强制杀掉指定进程

   `[user1@server ~]$ kill -9 3029`

补充：| 管道 -- 连接两个命令的输入和输出，将一个命令的输出作为另一个命令的输入

​            `ps -ef |  grep bash  查找包含bash的进程`

### 六、文本编辑器vi命令

#### 1、简介

vi命令是UNIX操作系统和类UNIX操作系统中最通用的全屏幕纯文本编辑器。

VI编辑器二种模式:编辑模式、命令行模式

vi abc.txt 进入编辑器，此时并不能编辑文本，

需要通过输入【i/I、o/O、a/A、r/R】进入编辑模式，可修改文本文件，

在编辑模式中修改完毕后，输入【esc】切换回命令行模式，

在命令行模式中输入【:w、:q、:x】即退出



#### 2、保存/退出

-  :w  保存文本
-  :q   不保存文本并退出vi
-  :q!  不保存文本并强制退出vi （常用）
-  :wq 保存文本并退出vi （常用）
-  :x    保存文本并退出vi



#### 3、编辑模式

进入文本编辑器，输入【i/I、o/O、a/A、r/R】进入编辑模式：

- ​ i：在光标处插入(常用)
- ​ I：在光标所在行第一个非空格字符处插入 -- 行首 (常用)
-    o：在光标所在行的下一行插入新的一行(常用)   -- Other
-    O：在光标所在行的上一行插入新的一行
-    a：在光标所在位置的下一个字符处开始插入
-    A：在光标所在行的最后一个位置开始插入 -- 行尾 (常用)
- r：替换光标所在位置的字符(只替换一次)  
- R：一直替换光标所在位置的字符，直到按(esc)键为止



#### 4、删除、复制、粘贴、撤消

- ​    dd：删除(剪切)光标所在行
- ​    ndd: 删除(剪切)光标所在的向下n行   5dd
- ​    yy: 复制当前行
- ​    nyy: 复制光标所在的向下n行     6yy
- ​    p: 将已复制的数据在光标下一行粘贴
- ​    P: 将已复制的数据在光标上一行粘贴
- ​    u: 撤消删除



### 七、网络

#### 1、查看ip地址

![1532360437823](https://github.com/DeerKing007/Linux_Notes/blob/master/Linux-notes/Linux_pic/1532360437823.png) 



#### 2、设置ip

- `vi  /etc/sysconfig/network-scripts/ifcfg-eth0`     将其中的 `ONBOOT=yes`        
  - `（按i键进入insert 修改完后 按esc 再输入:wq 回车）`
- `service network restart` 重启网络服务
- 在真实主机和虚拟机之间 ping 测试



#### 3、设置防火墙

- 查看防火墙状态

  `service iptables status`

- 关闭防火墙

  `service iptables stop`

- 启动防火墙

  `service iptables start`



#### 4、网卡设置

- 禁用网卡

  `ifconfig eth0 down`

- 启用网卡

  `ifconfig eth0 up`



#### 5、hosts设置

`vi /etc/hosts`

```shell
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6
192.168.1.100 Mr_lee
```

将ip为192.168.1.100 的设置为Mr_zhang

此时可以这样使用：  

```
ping Mr_zhang   # ping 192.168.1.100 
```



#### 6、主机名设置 

`vi /etc/sysconfig/network`

```shell
NETWORKING=yes
HOSTNAME=Server   #主机名
```



### 八、服务

#### 1、服务设置

`[service   服务名   status/stop/start/restart]  `

#### 2、服务开机自动启动

- 列出所有系统服务

  `[root@Server ~]# chkconfig --list` 

- 服务开机不启动

  `[root@Server ~]# chkconfig iptables off` 

- 服务开机启动 

  `[root@Server ~]# chkconfig iptables on` 



### 九、软件安装

#### 1、rpm命令 

这种软件包就像windows的EXE安装文件一样，各种文件已经编译好，并打了包，哪个文件该 放到哪个文件夹，都指定好了，安装非常方便，在图形界面里你只需要双击就能自动安装。

- 查询所有已安装的软件包的包名 （q:查询   a:所有） 

  `[root@Server ~]# rpm -qa`

- 查询python软件包的安装位置（q:查询 l:位置 python软件包名）

  `[root@Server ~]# rpm -ql python`

- 查看已安装的软件的信息（i: info 信息）

  `[root@Server ~]# rpm -qi python`

  ```shell
  Name        : python                       Relocations: (not relocatable)
  Version     : 2.6.6                             Vendor: CentOS
  Release     : 51.el6                        Build Date: Fri 22 Nov 2013 08:18:53 PM CST
  ```

- 安装软件 （i:安装   v:显示安装过程   h:显示安装细节）

​       ` rpm –ivh xxxx.rpm`

- 查看安装的软件的包名

​      ` rpm –qa| grep  python`

- 卸载软件 (e:卸载)

​        `rpm –e 包名`



#### 2、tar命令

参数 

- c 压缩文件
- x 解压文件
- z 格式为gzip
- v 显示执行文件列表
- f 要操作的文件

直接解压 

​       tar –zxvf xxx.tar   / xxx.tar.gz

解压后，编译安装

​     一般tar包中已经是编译好的文件，解压即可直接使用；也存在一些tar包，在解压后需要   

​    进行编译，则需要经过 configure -> make -> make install



#### 3、Yum命令 

基于RPM包管理，能够从指定的服务器自动下载RPM包并且安装。

Yum是centOS独有的安装命令，需要外网环境，可以自动加载安装文件，及其所有依赖资源，并自动完成软件安装。

安装redis 和 nginx时可以采用。
