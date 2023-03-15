第一个标题 | 第二个标题
--- | ---
内容单元格 | 内容单元格
内容单元格 | 内容单元格

第一个标题 | 第二个标题
--- | ---
内容单元格 | 内容单元格
内容单元格 | 内容单元格

![堡垒](https://vignette.wikia.nocookie.net/masseffect/images/d/d7/MassEffect2Citadel.jpg/revision/latest?cb=20100721191415)

左对齐 | 居中对齐 | 右对齐
:-- | :-: | --:
第 3 栏是 | 一些冗长的文字 | **$1600**
第 2 栏是 | 居中 | 12美元
斑马条纹 | 很整洁 | ~~$1~~

Dillinger 是一个支持云、移动就绪、离线存储、AngularJS 支持的 HTML5 Markdown 编辑器。

- 在左边输入一些 Markdown
- 看右边的 HTML
- 魔法

# 真的

- 导入 HTML 文件并观看它神奇地转换为 Markdown
- 拖放图像（需要链接您的 Dropbox 帐户）

你也可以：

- 从 GitHub、Dropbox、Google Drive 和 One Drive 导入和保存文件
- 将 markdown 和 HTML 文件拖放到 Dillinger 中
- 将文档导出为 Markdown、HTML 和 PDF

Markdown 是一种基于人们在电子邮件中自然使用的格式约定的轻量级标记语言。正如 [John Gruber] 在 [Markdown 网站] [df1] 上所写

> Markdown 格式化语法的首要设计目标是使其尽可能具有可读性。这个想法是，一个 Markdown 格式的文档应该可以按原样发布，作为纯文本，而不是看起来像是用标签或格式说明标记的。

你在这里看到的这段文字*实际上*是用 Markdown 写的！要感受 Markdown 的语法，请在左侧窗口中键入一些文本并在右侧观察结果。

### 错误的

Dillinger 使用了一些开源项目来正常工作：

- [AngularJS] - 为网络应用程序增强的 HTML！
- [Ace Editor] - 很棒的基于网络的文本编辑器
- [markdown-it] - Markdown 解析器做对了。快速且易于扩展。
- [Twitter Bootstrap] - 现代网络应用程序的优秀 UI 样板
- [node.js] - 后端的事件 I/O
- [Express] - 快速的 node.js 网络应用程序框架 [@tjholowaychuk]
- [Gulp] - 流构建系统
- [Breakdance](https://breakdance.github.io/breakdance/) - HTML 到 Markdown 转换器
- [jQuery] - 呃

当然，Dillinger 本身是开源的，在 GitHub 上有一个 [public repository][dill]。

### 安装

![伊洛斯](https://lh3.googleusercontent.com/proxy/DDV8a7sLIWurhJtW8Ego9bq-JlwpfFFoR0tkLJQKKYXEXoWHB6ZUP5jGKD2VcYt3z1QVsgcn6L3GoU1ns8m9fvi3U51GzddA70ZUMHgzHvjl4-i7YOJY9cShBPrfjUhMQhxaJ97WFBp612XmjMXVGypfGkiBarN4PWxhiHkiYYNW7HGbtTpOcyt9GQ4Q23C2noxLTWFXZMcQZhRpQA_qzu2n6_H6CPViBnhSHpEl4JZAPaGCSJqgZg)

Dillinger 需要[Node.js](https://nodejs.org/) v4+ 才能运行。

安装依赖项和 devDependencies 并启动服务器。

```sh
$ cd dillinger
$ npm install -d
$ node app
```

对于生产环境...

```sh
$ npm install --production
$ NODE_ENV=production node app
```

### 插件

Dillinger 目前扩展了以下插件。下面链接了有关如何在您自己的应用程序中使用它们的说明。

插入 | 自述文件
--- | ---
投递箱 | [plugins/dropbox/README.md][PlDb]
GitHub | [plugins/github/README.md][PlGh]
谷歌云端硬盘 | [插件/googledrive/README.md][PlGd]
一个驱动器 | [plugins/onedrive/README.md][PlOd]
中等的 | [plugins/medium/README.md][PlMe]
谷歌分析 | [plugins/googleanalytics/README.md][PlGa]

### 发展

想贡献吗？伟大的！

Dillinger 使用 Gulp + Webpack 进行快速开发。更改您的文件并立即看到您的更新！

打开您最喜欢的终端并运行这些命令。

第一个选项卡：

```sh
$ node app
```

第二个标签：

```sh
$ gulp watch
```

（可选）第三：

```sh
$ karma test
```

#### 源码构建

对于生产发布：

```sh
$ gulp build --prod
```

生成用于分发的预构建 zip 存档：

```sh
$ gulp build dist --prod
```

### 码头工人

Dillinger 非常容易在 Docker 容器中安装和部署。

默认情况下，Docker 将公开端口 8080，因此如有必要，请在 Dockerfile 中更改它。准备就绪后，只需使用 Dockerfile 构建映像即可。

```sh
cd dillinger
docker build -t joemccann/dillinger:${package.json.version} .
```

这将创建 dillinger 图像并引入必要的依赖项。请务必将`${package.json.version}`替换为 Dillinger 的实际版本。

完成后，运行 Docker 映像并将端口映射到主机上您希望的任何端口。在此示例中，我们只是将主机的端口 8000 映射到 Docker 的端口 8080（或 Dockerfile 中公开的任何端口）：

```sh
docker run -d -p 8000:8080 --restart="always" <youruser>/dillinger:${package.json.version}
```

通过在首选浏览器中导航到服务器地址来验证部署。

```sh
127.0.0.1:8000
```

#### Kubernetes + 谷歌云

请参见[KUBERNETES.md](https://github.com/joemccann/dillinger/blob/master/KUBERNETES.md)

### 待办事项
