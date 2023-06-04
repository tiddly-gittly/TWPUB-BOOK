# TWPUB墨屉


## 快速进入渐进式阅读 + 多平台同步
supermemo导入电子书只适合纯文本书籍，TW有更好的更兼容的方式，所以我的渐进式阅读目标已经达成了，首先是找到自己想要渐进式阅读的电纸书epub。用TWPUB-Tools工具转换为TWPUB.json，然后拖放进墨屉，然后在墨屉**设置（小齿轮）-信息选项卡-基本组**重命名墨屉标题，设置为：**🦑墨屉+书名**。然后放进onedrive即可进入同步。

电脑端使用TiddlyStow.html打开墨屉进行渐进式阅读。（不要直接打开墨屉.html，这样保存时候你会得到很多html墨屉程序文件，这是因为墨屉与浏览器的保存机制导致的，是优点也是缺点。TiddlyStow.html可以让你始终保存一个墨屉书籍HTML文件。）

手机端使用tiddloid.apk继续阅读（手机端的onedrive要在后台保持一直运行这样tiddloid的对onedrive的连接才不会断开。并且要阅读的书籍要设置允许脱机使用，这时第一次阅读时候就不会去先下载文件然后打开）。

墨屉wiki导入书籍的流程：拖放**书籍.json**到墨屉（直接拖入浏览器），在墨屉的![图片](https://user-images.githubusercontent.com/32425955/166909870-f4871de5-c2f3-4c58-b7e4-cec6aeb66b0d.png)点击一下，选择倒三角形状的按钮，选择导入twpub书籍，然后会弹出一个条目，然后你就知道如何做啦。

墨屉是由条目（卡片组成），可以通过筛选器搭配标签使用，实现渐进式阅读。算法采用优于sm18的 FSRS 间隔重复算法。


## 一、回写式保存文件

免浏览器下载的保存方法webdav：
1. rclone（单文件软件）：执行 rclone serve webdav <包含wiki的目录>。
2. wsgidav（python软件）:软件官网：https://wsgidav.readthedocs.io/en/latest/index.html


免浏览器下载的保存方法：TiddlyStow.html
1. 打开该页面然后选择墨屉wiki.html，即可
2. 支持保存常用文件列表
3. 刷新返回TiddlyStow页面
4. 来源于https://github.com/btheado/tiddlystow



## 二、电子书转换（epub 到 twpub）

1. 安装nodejs
   nodejs官网下载链接：http://nodejs.cn/download/current/

2. 下载转换工具包
   
   - 下载转换工具并解压得到TWPUB-Tools文件夹：https://github.com/Zacharia2/TWPUB-BOOK/releases/download/0.1.0/TWPUB-Tools.zip

3. 在项目中安装所有软件需要的依赖项
   
   - 在TWPUB-Tools文件夹中打开powershell并在窗口中执行命令**npm install** 安装依赖项

4. 转换书籍：
    - 执行：node epub2twpub --epub <EPUB文件> --output <twpub文件输出路径>
    - 注意：必须得在刚刚下载的...\TWPUB-Tools 目录下执行！否则好像提示没有找到命令。
    - 例如：node epub2twpub --epub C:\月亮与六便士-毛姆.epub --output C:\月亮与六便士-毛姆.json