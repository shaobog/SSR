关于SSR应该很多人都不陌生。SSR其实是SS的升级版。接下来我要说的就是如何搭建SSR的服务器。

最下方有SSR客户端的下载链接,百度网盘可直接下载

# 一.购买服务器，或者准备一台服务器
#### （一）注意：
1. 这一台服务器必须处于公网，拥有公网IP
2. 这一台服务器必须可以访问外网（你知道为什么）
3.这一台服务器系统是Ubuntu或者CentOS系统（只要是Linux应该都行，但是我只会这两种系统的一些基础）
#### （二）如何购买服务器
这个我就不想多说了。服务器购买有一大把。我用的是阿里云香港服务器。
##### 关于阿里云服务器的一些注意：
###### 1. 安全规则配置。
因为我第一次使用阿里云。所以第一次配置的时候没有成功还以为是配置错了。折腾了两天才发现原来是设置了安全规则过滤了外网对其的访问。
###### 2. 没有更多了了
# 二. 配置服务器
### Ubuntu:
##### 安装 wget,如果服务器本身已经安装了wget可以跳过这一步
Ubuntu 16以上
```terminal
apt install wget
```
Ubuntu 16之前
```terminal
apt-get install wget
```
CentOS
```terminal
yum -y install wget
```
##### 安装ssr配置脚本

```terminal
wget -N --no-check-certificate https://softs.fun/Bash/ssr.sh
chmod +x ssr.sh
bash ssr.sh
```
##### 备用地址

```terminal
wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/ssr.sh
chmod +x ssr.sh
bash ssr.sh
```
上方命令执行完毕之后效果应该是这样的：

![image.png](http://upload-images.jianshu.io/upload_images/6245842-c61be6d239fd67b8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
接下来按照脚本提示输入对应的编号就可以了。
##### 安装SSR
根据提示，安装SSR，输入1

![image.png](http://upload-images.jianshu.io/upload_images/6245842-60fd159675c8042b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##### 设置SSR服务器的端口
这个端口用于SSR客户端与SSR服务器建立链接的时候使用。默认2333.在这里我直接使用默认（直接敲回车）

![image.png](http://upload-images.jianshu.io/upload_images/6245842-66b14c7d81e6ded1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##### 设置SSR链接时候的密码。
这里我设置的是1234

![image.png](http://upload-images.jianshu.io/upload_images/6245842-5cba2d1cd6acd98e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##### 设置加密方式
这里我为了能兼容SS，加密方式我选择的是3

![image.png](http://upload-images.jianshu.io/upload_images/6245842-18f33a5b3fac95ad.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##### 设置协议插件
同样为了兼容SS，我选择了1

![image.png](http://upload-images.jianshu.io/upload_images/6245842-ee8e3943d44afb5d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##### 设置混淆插件
同样为了兼容SS，我选择了1

![image.png](http://upload-images.jianshu.io/upload_images/6245842-de7bbcd207d35201.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##### 限制登陆设备个数
我不需要限制，所以直接回车

![image.png](http://upload-images.jianshu.io/upload_images/6245842-8c0fac4bca1c8a78.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##### 设置单个端口限速
不需要，直接回车

![image.png](http://upload-images.jianshu.io/upload_images/6245842-ae7fe036f74bca1d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##### 设置端口限速（所有端口的总速度，多端口模式下更能体现，个人使用一般是单端口，不需要理会）
不需要，直接回车

![image.png](http://upload-images.jianshu.io/upload_images/6245842-b11c869d20319366.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这个回车之后就会有一大堆乱七八糟的东西，等一等，让它自己配置。结束之后如图：

![image.png](http://upload-images.jianshu.io/upload_images/6245842-a0f12abc144bf3ac.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

为了保密，我把IP，SS和SSR链接P掉了。毕竟我的服务器只是一个很小的服务器，不敢拿出来共享。在此说一声抱歉。
# 三.配置加速
这一步其实可以不要。但是为了从此之后不再忧心与SSR服务器的重启（服务器重启后SSR服务会被关闭，需要重新手动启动）和SSR代理网络速度更快，推荐大家往下看。
##### 安装谷歌BBR加速
```terminal
wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh
chmod +x bbr.sh
./bbr.sh
```
把上述的代码依次执行一遍，执行完之后是这样的

![image.png](http://upload-images.jianshu.io/upload_images/6245842-efa9703df1b9363b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这时只需要按一下键盘上任意一个按键即可（按一下就行，不需要多按，等一下就会有反应了）
等安装完之后是这样的

![image.png](http://upload-images.jianshu.io/upload_images/6245842-5bf4cb40ea037fa8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这里是在询问是否重启系统。我们输入y.回车之后会发现已经与服务器断开链接了。不必担心，这是服务器在重启。等一下再次连接即可。
如果想再次配置SSR，只需要输入命令
```terminal
bash ssr.sh
```
就会重新回到安装的界面

![image.png](http://upload-images.jianshu.io/upload_images/6245842-e5b70e039cb0b0d5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

输入7即可根据需要自己修改配置了。怎么样，很简单吧。
不过服务器这东西一般人还是很难拥有的。感谢阅读。

SSR客户端百度网盘下载链接：[链接：https://pan.baidu.com/s/1QcYs8pmH3FehWj4XEs88XA?pwd=7f6k](链接：https://pan.baidu.com/s/1QcYs8pmH3FehWj4XEs88XA?pwd=7f6k)

# SSTAP规则编写
本来也是来这里找SSTAP规则编写方法的，不过没有找到。经过测试研究后总算弄清楚了，看到很多网友也在找规则编写教程，在这里分享给有需要的人。

注：我用的是1.1.0.1，其它版本的应该 是通用的。

一，启动程序后，点模式最后边的小按扭，附件中的图1，打开规则管理器

二，在规则管理器中点‘添加’，新建一个规则

三，最关键的就是这个新建规则这里，很多人不会填写。

这里我以代理www.ip.cn为例来说明如何填写

English name of rule: 这里随便填一个规则英文名，我填了“ip.cn”

Chinese name of rule: 这里填一个规则中文名，我填了”ip.cn”

Proxify DNS Request：这里 Auto就行了

Action Type: 这个最重要，如果你是想代理某个（或者某段IP)就选”Proxify”，如果你是想某些IP或者某段IP跳过代理也就是直连，那么就选Direct.  当然这里我们要选Proxify

Remarks：这里随便填个备注就行了

最后是下边的Rules list: 这里也是很关键 的大家不会填

因为我想代理www.ip.cn所以我先 PING http://www.ip.cn 得到IP地址是：198.41.215.99，这里可能大家PING到的地址不相同，我用的8.8.8.8的DNS，所以ping出来的是国外的IP地址

得到这个IP到底要怎么填入进去了，如果我只想代理这个IP那么就写：198.41.215.99/32

当然很多时候只代理一个具体IP可能不会生效，因为有时候域名PING到的IP可能会变化。

所以这里写198.41.215.0/24会比较保险

那个IP后边的/32, /24到底是什么意思呢？我们应该 怎么填呢，其实这是一个网段的表示方法，后边的/32, /24是掩码

198.41.215.99/32意思是仅有一个IP地址 198.41.215.99

198.41.215.0/24 的意思是 198.41.215.1 – 198.41.215.254 一共254个IP地址

198.41.0.0/16 的意思就是 198.41.0.1 – 198.41.255.254 一共65534个IP地址

一般情况下，你如果要代理某个IP地址，直接将这个IP地址将这个IP地址最后一位写成0（数字0）再加上/24就可以了

再宽一点将后2个IP位写成0，再加/16就可以了，建议最好不要将IP后3位都写0再加/8这样所表示的IP范围就太宽了，就可能导至代理了本来不想代理的IP了。

其实搞清楚后是不是觉得写规则好简单？

例如你要代理8.8.8.8，那么将最后一位写成0再加/24那就是：8.8.8.0/24写在SSTAP中就可以了

三，填写好这些信息后，保存，选中刚才添加的代理规则，点连接就可以了。这里一定要记得切换规则再连接哦，否则不会生效的。

连接后再打开www.ip.cn看到已经是代理的IP了

关于大家都在问的最新版如何加上代理全局的功能，其实也可以通过添加规则来做到的，我抽空再做一个教程教大家吧。
