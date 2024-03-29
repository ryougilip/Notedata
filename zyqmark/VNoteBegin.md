# 1. VNoteBegin
this is real


## 1.1. Vnote的安装使用
[官网下载链接](https://tamlok.github.io/vnote/zh_cn/#!downloads.md)

## 1.2. 构建
Recommend[官方文档](https://tamlok.github.io/vnote/zh_cn/#!docs/开发者/构建VNote.md)
源代码需求：
```
git clone https://github.com/tamlok/vnote.git vnote.git
cd vnote.git
git submodule update --init
```
Qt  [Qt Downloads](http://info.qt.io/download-qt-for-application-development). 镜像下载 [TUNA Mirrors](https://mirrors4.tuna.tsinghua.edu.cn/qt/official_releases/qt/5.9/).

## 1.3. 使用
阅读编辑切换ctrl+T
舰长模式?
快捷键帮助
片段[支持纯文本]
幻词 日期 %da% 快捷键 Ctrl+E M %da%
模板(比如笔记名设作标题)
Vim编辑高亮

### 1.3.1. 特性
    界面简洁, 使用方便.
    纯文本, 不依赖数据库, 便于借助同步盘进行同步
    文件夹为独立笔记本, 无限层级文件夹.
    强大的搜索功能. 全文或关键词或标签搜索.
    支持自定义快捷键, 支持自定义主题和样式.
    语法块支持高亮(编辑/浏览模式)
    Vim模式.
    支持从剪贴板直接插入图片.
    支持Mermid, Flowchart, MathJax, PlantUML, Graphviz.
    支持标签和附件.

    缺点 (不是说不好, 总要知道有何不足) :

        没有历史记录 (可以借助Git解决).
        开放的笔记, 因此有安全性问题 (非公共电脑或者非官员不怕啥吧?).
        同步浏览(实时预览)功能缺乏(即使切割窗口也不能同时打开一个文件)
        不自带网络同步等功能, 不带WebDAV等.

**自动备份功能**
**重启生效：**
可选择恢复文件，vswp
主题
渲染
如果格式出现问题，多加个空行，一般就好了。

**代码块**

    ```java
    public class Vnote{
        
    }
    ```
行内代码   `touch`

**表格**
（1）简单的直接使用makedown语法
（2）复杂的可以使用html，html熟悉的可以直接用，不熟悉的可以使用execl做好后生成html，然后将文件中的html代码拷贝到makedown文件中使用。

|  5  |     |     |     |     |
| --- | --- | --- | --- | --- |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
**图片**
![三步同步](_v_images/20191030214322839_22102.png =350x)

VNote笔记本可以指定图片的储存地方(默认是该笔记所在的文件夹下的_v_images文件夹)
图片会以时间格式来命名, 默认是png文件.
可以指定图片显示的大小 (可以在链接后面使用=240x (前有空格) 指定大小)
文件保存后, 若修改了文件内容, 删掉了图片链接, 再次保存时会提示是否删除文件! (但是如果删除笔记好像不会删除图片).

**其他功能**

    小推车 : 在工具中有小推车标签. 小推车可以右键笔记加入到小推车. 小推车内的笔记一般是没完成的笔记.
    钉到历史 : 在左侧的窗口中的历史中, 会有一栏是钉住的, 右键笔记可以钉住
    快速访问 : 标题栏的快门图标对应快速访问, 可以右键笔记设置快速访问.
    通用入口 : 图标栏的闪电标记. 可以后续输入相应指令进行相应操作.
    分割窗口 : 在编辑器的右上方的三个点的地方, 可以选择分割模式. 分割后, 打开新的笔记后, 在笔记标签处右键, 可以将笔记移动到相应分割窗口. 不支持拖动是比较麻烦.
    舰长模式 : 说白了, 是扩展快捷键, 使用双字母快捷键. 开启舰长模式是使用Ctrl+E, (左上角图标栏的VNote高亮), 随后再按后续的快捷键, 常用的舰长模式:
        Ctrl +E, E : 扩展/缩小 编辑区域(隐藏左侧栏) (很重要)
        Ctrl +E, T : 显示/隐藏 工具窗口(右上)
        Ctrl +E, C : 显示/隐藏 搜索窗口(右下)
        Ctrl +E, X : 关闭当前标签页.
        Ctrl +E, 0 : 切换到上一次的标签页. 另外, 1-9可以跳到指定标签页, J/K是下一个和上一个标签页.
        Ctrl +E, W : 进入展览模式, 主要部件会显示至多两个字母, 输入相应字母就会跳转到相应插件, 快速切换焦点 (有点击该处的功能).

### 1.3.2. markdown使用指南
***工具栏帮助下拉菜单，打开文档***
右侧大纲
各种快捷键  标题4,5 渲染较好ctrl 4,5

### 1.3.3. 笔记注意事项
**段落之间必需空行**
**标题前空行**
**层级不要太多**
**少用图：** 方便，但打包麻烦，网络链接有可能网站不可用。不可追溯
**手动保存**



### 1.3.4. 导出
html（可另外编辑成CHM 软件powerCHM，有Vnote logo虽然可以注释掉）
pdf（直接，or辅助软件）
md
各种格式导出 [pandoc](http://pandoc.org) to export notes:免安装版要配置环境变量，才能使用下面占位符命令，记得重启

```sh
pandoc --resource-path=.:"%3" --css="%2" --css="%4" -s -o "%1" "%0"
```

Then if the output suffix is `pdf`, it will generate the PDF file; if it is `docx`, it will generate the DOCX file.

### 1.3.5. Github同步
* **已创建reposistories**
搜索用户：ryougilip
reposistories：Notedata
URL：https://github.com/ryougilip/Notedata.git

创建步骤

* 1. 在不同设备上需要各自的加密传输密钥，git bash，在本地创建密钥， SSH key，并在github账户添加SSH
```
ssh-keygen -t rsa -C "gana10007@163.com"  -f ~/.ssh/coding-rsa
#coding-rsa:生成公钥私钥对的文件名称
# ~/.ssh/表示生成的路径,windows下指向C:\Users\Administrator,Administrator表示当前的用户名
```
* 2. 验证登陆
```
ssh -T git@github.com
Hi ryougilip! You've successfully authenticated, but GitHub does not provide shell access.
```

* 3. 在github中创建仓库，复制URL，git bash本地自定义目录下，克隆URL,
```
cd F:/files/share
git clone https://github.com/ryougilip/Notedata.git
```
在Vnote本地 创建笔记本Notedata,其根路径为F:/files/share下的Notedata文件夹，新建笔记，保存，然后在git bash中同步。也可以下载github桌面应用进行同步。
* 4. **同步代码**
```
cd F:/files/share
git add -i
#列出所有修改过的文件及它们的状态
git add *
#添加到暂存区
git status
#查看修改文件的状态
$ git commit -m "注释xx"
#提交信息,纳入本地git HEAD区
git remote add origin https://github.com/xx/xx.git
#当使用的仓库是 git init 初始化了一个新的本地仓库，需要remote将本地仓库与远程仓库关联
git push
#推送到github
#下一次工作笔记需要拉取仓库更新时，
git pull
```

* 5. 用另一台设备获取仓库，同1.在不同设备上需要各自的加密传输密...
```
cd 目录
ssh-keygen -t rsa -C "gana10007@163.com"  -f ~/.ssh/coding-rsa
#密钥在家目录c盘..
```

* 6.  进入自定义目录，进行克隆，成功后可以看到账户密钥变绿色（正在使用）。
```
cd ///
git clone https://github.com/ryougilip/Notedata.git
```

* 7. 在VNote中添加目录中的笔记本，进行笔记，可以在**git所在的文件夹**中，git bash here, 查看 git status并进行添加提交推送，内容可以同步到github。当你克隆时建了一个新目录，里面会有仓库内容（`...Notedata.git xfolder`），工作完需要到原仓库目录下，拉取xfolder工作目录`git pull /.../xfolder master`，这样就xfolder合并到Notedata分支了。而前一个已用过的设备也可以进行同样的操作，进行拉取git pull修改（git pull 命令等同于执行两个操作: 先使用 git fetch 从远程分支抓取最新的分支修改信息，然后使用 git merge 把修改合并进当前的分支）。可以通过 git log 查看远程分支做的所有修改。
```
git config user.name "ryougilip"
git config user.email "zyqcarl@163.com"
局部设置身份标识
```
* 8. 一个 Git 仓库可以维护很多开发分支。现在我们来创建一个新的叫 experimental 的分支：
```
$ git branch experimental
```
运行 git branch 命令可以查看当前的分支列表，以及目前的开发环境处在哪个分支上：
```
$ git branch
 experimental
* master
```
experimental 分支是你刚才创建的，master 分支是 Git 系统默认创建的主分支。星号标识了你当工作在哪个分支下，输入 git checkout 分支名 可以切换到其他分支：
```
$ git checkout experimental
Switched to branch 'experimental'
```
切换到 experimental 分支，切换完成后，先编辑里面的一个文件，再提交（commit）改动，最后切换回 master 分支：查看下 file1 中的内容会发现刚才做的修改已经看不到了。因为刚才的修改时在 experimental 分支下，现在切换回了 master 分支，目录下的文件都是 master 分支上的文件了。
* Tips
commit:  
为 commit 做好了准备，你可以使用 git diff 命令再加上 --cached 参数，看看缓存区中哪些文件被修改了。进入到 git diff --cached 界面后需要输入 q 才可以退出;
需要使用 -m 添加本次修改的注释，完成后就会记录一个新的项目版本。除了用 git add 命令，我们还可以用下面的 -a 参数将所有没有加到缓存区的修改也一起提交，但 -a 命令不会添加新建的文件。
```
$ git commit -a -m "add 3 files"
```
再次输入 git status 查看状态，会发现当前的代码库已经没有待提交的文件了，缓存区已经被清空。
如果是修改文件，也需要使用 git add 命令添加到缓存区才可以提交。如果是删除文件，则直接使用 git rm 命令删除后会自动将已删除文件的信息添加到缓存区，git commit 提交后就会将本地仓库中的对应文件删除。


**公共仓库**
开发过程中，通常大家都会使用一个公共的仓库，并 clone 到自己的开发环境中，完成一个阶段的代码后可以告诉目标仓库的维护者来 pull 自己的代码。

如果你和维护者都在同一台机器上有帐号，那么你们可以互相从对 方的仓库目录里直接拉所作的修改，git 命令里的仓库地址也可以是本地的某个目录名：
```
$ git clone 仓库A的路径
$ git pull 仓库B的路径
```
也可以是一个ssh地址：
```
$ git clone ssh://服务器/账号/仓库名称
```

可以在你的顶层工作目录中添加一个叫 .gitignore 的文件，来告诉 Git 系统要忽略掉哪些文件
```
*.json
*.vswp
```