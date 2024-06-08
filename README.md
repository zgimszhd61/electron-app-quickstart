## 部署教程总结
```
git clone --depth 1 https://github.com/zgimszhd61/electron-app-quickstart
cd electron-app-quickstart
rm -rf node_modules package-lock.json
npm install
npm start
```

## 基本文件结构
Electron应用的文件结构通常包括以下几个主要部分：

### 1. 主进程（Main Process）
主进程负责管理整个应用的生命周期，包括创建和管理应用窗口。主进程在Node.js环境中运行，具有使用所有Node.js API的能力。

- **main.js**：主进程的入口文件，负责初始化应用和创建窗口。
- **package.json**：项目的配置文件，定义了应用的元数据和依赖项。

### 2. 渲染进程（Renderer Process）
渲染进程负责显示用户界面，每个窗口实例都是一个独立的渲染进程。渲染进程可以使用Node.js的API与操作系统进行交互。

- **index.html**：渲染进程加载的HTML文件。
- **renderer.js**：渲染进程的JavaScript文件，负责处理用户界面逻辑。

### 3. 进程间通信（IPC）
Electron提供了`ipcMain`和`ipcRenderer`模块，用于主进程和渲染进程之间的通信。

### 4. 其他文件和目录
- **node_modules**：存放通过npm安装的依赖项。
- **static/**：存放静态资源，如图片、样式表等。
- **src/**：源代码目录，通常包含主进程和渲染进程的代码。

### 示例文件结构
以下是一个典型的Electron应用的文件结构示例：

```
my-electron-app/
├── package.json
├── main.js
├── index.html
├── renderer.js
├── node_modules/
├── static/
│   ├── images/
│   ├── styles/
│   └── scripts/
└── src/
    ├── main/
    │   └── main.js
    ├── renderer/
    │   └── renderer.js
    └── common/
        └── utils.js
```

### 详细说明
- **package.json**：定义了应用的名称、版本、入口文件等信息。
- **main.js**：主进程的入口文件，负责创建和管理应用窗口。
- **index.html**：渲染进程加载的HTML文件，定义了用户界面。
- **renderer.js**：渲染进程的JavaScript文件，处理用户界面逻辑。
- **node_modules/**：存放通过npm安装的依赖项。
- **static/**：存放静态资源，如图片、样式表等。
- **src/**：源代码目录，包含主进程和渲染进程的代码。

### 参考资料
- [Electron构建一个文件浏览器应用](https://www.cnblogs.com/tugenhua0707/p/11080473.html)[1]
- [Electron系列文章-程序目录结构](https://juejin.cn/post/6844903779670687751)[2]
- [electron开发记录(三)：应用基本框架解析](https://blog.csdn.net/u014595019/article/details/53436296)[3]
- [流程模型 - Electron](https://www.electronjs.org/zh/docs/latest/tutorial/process-model)[4]
