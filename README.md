# weiboCrawler

微博爬虫，可以抓取某条微博的转发、评论、点赞，还可以抓取某个用户发布的所有微博。通过命令行执行，不需要修改代码，抓取结果自动保存成文件。

为不会编程但是有抓取需求的朋友开发，也希望感兴趣的朋友一起开发完善它。


##使用环境：

目前已经测试过win7和Mac OS 10.10.3 。 


##安装方法

1、安装python2.7（Mac已自带python）

2、安装依赖库bs4，具体方法：pip install bs4（Mac： sudo pip install bs4）

3、下载weiboCrawler.py到一个文件夹



##使用方法

weiboCrawler的抓取分两种，一种是抓具体某条微博相关的信息（转发、评论、点赞），一种是具体某个用户发布的所有微博。进入weiboCrawler.py所在目录（命令行命令：cd 文件夹路径，如到mac桌面：cd desktop），然后按照下面所示的方法输入要抓取的命令。

注：在开始抓取时，会提示输入用户名和密码，请输入您的或者是您的微博小号的账号和密码进行登录，然后系统会打开验证码图片，请输入图片所示的验证码。


####抓取某一条微博相关信息的命令

1、抓取某条微博相关的信息时，首先要获取这条微博的ID，具体方法：点击这条微博的发布时间，然后到达这条微博的页面，在这条微博的URL里，如：http://weibo.com/1852855013/DpZz5BRRn?ref=home&rid=0_0_0_2666928219837039753&type=comment ，最后一个斜杠和问号中间的部分，就是这条微博的ID，比如这个例子里，微博ID=DpZz5BRRn；

2、获取ID之后，通过参数 -w 就可以传递微博ID， -r 表示抓取转发， -c 表示抓取评论，-a表示抓取点赞；
>* 示例：为抓取上面这条微博的转发列表，在命令行里输入： python weiboCrawler.py -w 微博ID -r
>* 同理，抓取评论的命令为： python weiboCrawler.py -w 微博ID -c
>* 抓取点赞的命令为： python weiboCrawler.py -w 微博ID -a
>* 也可以一起抓： python weiboCrawler.py -w 微博ID -r -c -a

3、程序会自动将抓取结果保存成txt，文件名为：微博ID_repost 或 微博ID_comment 或 微博ID_attitude


####抓取某个用户所有微博的命令

1、同理，抓取某个用户，首先需要获得该用户的用户ID，用户的用户ID通过该用户主页的URL即可得到；微博ID分两种，有的微博用户启用了个性域名，如：http://weibo.com/xieixiaoyuan?is_all=1 ，则用户ID=xieixiaoyuan；有的用户没有启用个性域名，如：http://weibo.com/u/2759941935?is_hot=1 ，则用户ID=2759941935；

2、获取用户ID之后，通过输入命令行： python weiboCrawler.py -u 用户ID ，即可抓取该用户发布的所有微博，结果自动保存成文件，文件名为： user_用户ID。


最后，抓完的数据，可以直接复制到excel里，或者从excel里打开。






