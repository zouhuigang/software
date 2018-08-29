### 软件包作用及安装方法

### 如不想使用github仓库，可以自己前往服务器搭建，参考 [阿里云yum仓库搭建](http://zouhuigang.anooc.com/yum/practice/) !



软件默认安装位置：

	/usr/local/software

zexcel
>由于php的excel上传会导致内存无法及时的释放，所以用本软件替换，目前只支持xlsx格式。


ZsurnameServer
>检测输入的姓名是否合法



### 安装通用方法

下载安装：

	wget https://github.com/zouhuigang/software/raw/master/ZexcelServer-1.0.0-1.x86_64.rpm
	yum localinstall -y ZexcelServer-1.0.0-1.x86_64.rpm

启动软件：
	
	systemctl start ZexcelServer
	systemctl status ZexcelServer


### php客户端测试：

[点击查看源代码](https://github.com/zouhuigang/zouhuigang.github.io-md/tree/master/content/software/php-client)

只需要将其中的php文件复制到运行环境即可，然后运行下面的命令，自动安装依赖库。

	安装composer
	cmd-> cd D:\mnt\zouhuigang.github.io\content\software\php-client
	composer require "hprose/hprose:2.0.0"


例如，上面的步骤都完成了，然后将文件夹下的所有文件，上传到服务器，在浏览器打开:

	http://192.168.122.149/excel.php



	

### 问题汇总：

Q1：使用wget下载的时候，总是下载不全软件

	Length: unspecified [text/html]


A1：

检查发现，原来的是下载地址有问题

错误地址：

	wget https://github.com/zouhuigang/software/blob/master/ZexcelServer-1.0.0-1.x86_64.rpm 

正确地址:

	wget https://github.com/zouhuigang/software/raw/master/ZexcelServer-1.0.0-1.x86_64.rpm
	 
