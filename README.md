# -php-
好客php在线客服源码搭建教程可对接网页/小程序/微信公众号等
​
当你的网站做大以后肯定少不了会添加自己的联系方式，像很多大的网站其实在首页在线客服。今天这个源码可以满足你。

我在网上也找了很多，终于找到了源码，看到很多拿着别人的辛苦成果出来收费真够恶心的。

站点设置
首先下载源码解压到宝塔网站根目录。我这里php是7.3。

1.伪静态--thinkphp

2.关闭防盗链

3.网站运行目录为............./public/

站点安装
访问网址http://你的域名/install.php进入安装程序：



 

数据库信息

Host:数据库服务器的IP，如果数据库和站点是同一服务器则可填写127.0.0.1或localhost；

Database name:您的数据库名称；

Username:对应数据库的用户名；

Password:数据库的密码；

超级管理员注册

Username：管理中心超级用户账号

Password：管理中心超级用户密码

服务器端口配置

App_key：推送服务的app_key(一般默认即可)

App_secret:推送服务的app_secret(一般默认即可)

App_id: 推送服务的app_id(一般默认即可)

websocket 地址：推送服务的websocket地址(自动获取，一般默认即可)

Api地址：推送服务器的api地址（自动获取，一般默认即可）

websocket 端口：推送服务的websocket端口（默认即可，注意：防火墙必须允许该端口）

Api端口：推送服务的api端口号（默认即可， 注意：防火墙必须允许该端口）

registToken:默认即可

开启防火墙端口
开启2080和9090端口



 

如果您的服务器是阿里云或腾讯云或华为云的服务器，需要配置安全组，公网入方向和出方向都允许2080和9090端口

开启推送服务
进入网站目录，打开终端进入网站文件夹ymwl_pusher下（在黑窗口执行如下命令切换进入，切记换成自己网站的真实路径）

 cd /www/wwwroot/suyinwl.top/ymwl_pusher

（ suyinwl.top改为自己的网站目录名）

执行

php start.php start -d



 如果出现某函数被禁用（has been disabled）比如像上图错误 进入软件管理-php禁用函数里删除：pcntl_signal 、pcntl_signal_dispatch、 pcntl_fork、pcntl_wait、pcntl_alarm即可）php先把

如果php启动还是有提示错误，看看是不是以前运行过的端口然后  kill -9 进程号 

就可以了

php start.php restart -d

再次执行  重新启动推送服务



 出现上述就成功了

管理平台登陆地址：域名/platform/passport/login.html

问题
无法及时收到消息，需要刷新才能看到新消息：   推送服务没成功

如果开启了https访问也请一定按要求配置正确，否则也无法及时接收到信息，并且客服显示离线状态

端口检测工具：tool.chinaz.com/port（端口是否正确开启检查工具）

源码下载
​https://www.suyin66.com/phpkefuyuanma.html
