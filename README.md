# 🖐️ Gesture Slice 3D - 网页版手势切水果游戏

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Three.js](https://img.shields.io/badge/Three.js-r160-black)
![MediaPipe](https://img.shields.io/badge/MediaPipe-Vision-teal)

> **注意**：这是一个基于 Web 摄像头的增强现实（AR）网页游戏，无需安装任何 APP，打开浏览器即可体验“徒手”切水果的快感！



## 📖 项目介绍

**Gesture Slice 3D** 是一款运行在浏览器中的体感动作游戏。它利用 Google MediaPipe 强大的手部追踪技术捕捉玩家的食指动作，结合 Three.js 构建 3D 物理场景，实现了类似《水果忍者》的玩法体验。

本项目是一个单文件（Single-file）应用，非常适合作为学习 WebGL、计算机视觉集成以及 Web 游戏开发的案例。

## ✨ 核心特性

* **⚡ 实时手势追踪**：基于 MediaPipe Hand Landmarker，极低延迟精准识别食指指尖。
* **🗡️ 炫酷刀光特效**：自定义几何体生成的动态光剑轨迹，跟随手指流畅移动。
* **🍎 3D 物理引擎**：
    * 包含重力模拟、抛物线轨迹计算。
    * **动态难度系统**：难度越高，重力越强，物体抛射速度越快，挑战性倍增。
* **🎮 丰富的游戏元素**：
    * 多种水果（+10分）
    * 陷阱物品（💩 扣分 / 💣 炸弹结束）
    * 特殊道具（❄️ **时间凝滞**：触发全屏冻结特效与子弹时间）
* **🎵 沉浸式音效**：使用 Web Audio API 生成的程序化音效，无需加载外部音频文件。

## 🛠️ 技术栈

* **核心语言**: HTML5, CSS3, JavaScript (ES6 Modules)
* **3D 渲染**: [Three.js](https://threejs.org/)
* **计算机视觉**: [MediaPipe Tasks Vision](https://developers.google.com/mediapipe)
* **部署方式**: CDN 引入依赖，无需 Node.js 编译构建

## 🚀 快速开始 (How to Run)

由于项目使用了 ES Modules 和摄像头权限，**不能直接双击 HTML 文件打开**（`file://` 协议无效）。你需要一个本地服务器。

### 使用 VS Code (推荐)
1. 安装 VS Code 插件 **Live Server**。
2. 右键点击 `index.html`。
3. 选择 `Open with Live Server`。
## 🕹️ 游戏操作指南

1. **允许权限**：进入网页时，请允许浏览器访问摄像头。
2. **手势准备**：站在摄像头前，伸出**食指**。你会看到屏幕上出现跟随手指的光剑。
3. **菜单选择**：
   * 切碎下方的 🟢 **Easy**、🔵 **Normal** 或 🔴 **Hard** 球体开始游戏。
   > **提示**：进入菜单有 2 秒的安全冷却时间，防止误触。
4. **游戏目标**：
   * 切碎 🍉 水果得分。
   * 避开 💣 炸弹（游戏结束）。
   * 避开 💩 便便（扣 50 分）。
   * 切碎 ❄️ 雪花触发“时间冻结”，所有物体变慢，助你高分。

## 📂 代码结构概览

本项目将所有逻辑整合在一个 HTML 文件中，主要包含以下类：

* **`VisionSystem`**: 处理摄像头流，初始化 MediaPipe，进行坐标平滑转换。
* **`BladeRenderer`**: 使用 Three.js 创建动态网格（Mesh），渲染刀光拖尾特效。
* **`SoundManager`**: 基于 Web Audio API 的合成器，程序化生成切击、爆炸、背景音效。
* **`Game`**: 核心控制器。管理游戏状态（MENU/PLAYING）、物体生成（Spawn）、物理更新循环（Animate）及碰撞检测。

## 🐛 已知问题与优化

* **光照环境**：请确保环境光线充足，且背景不要过于杂乱，以免干扰手部识别。
* **浏览器兼容性**：推荐使用 Chrome、Edge 或 Safari 等现代浏览器以获得最佳 WebGL 性能。

## 📝 许可证

本项目基于 **MIT License** 开源。欢迎用于学习、修改和二次分发。

**如果觉得这个项目有趣，请给它一个 ⭐️ Star！**
