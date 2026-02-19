# APA WebGPU Accelerated Automated Parking Simulator

[![WebGPU](https://img.shields.io/badge/WebGPU-Accelerated-blueviolet?style=for-the-badge&logo=webgpu)](https://developer.chrome.com/docs/webgpu/)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

一个基于 WebGPU 加速的高性能自动泊车（APA）仿真器，集成遗传算法进化路径优化、12路超声波雷达（USS）+ LiDAR 仿真。

[**立即在线体验**](https://woodyhouse.github.io/APA_Wviz/apa-webgpu.html) *(需使用支持 WebGPU 的浏览器)*

---

## 🚀 核心特性

- **⚡ WebGPU 加速碰撞检测**: 利用 GPU 计算着色器生成构型空间（C-Space），在 RTX 4090 上仅需 2~5ms 即可处理百万级格点碰撞地图，支持流畅的实时动态重规划。
- **🎮 多场景支持**: 预设侧方位、垂直位、斜向位以及包含移动障碍物（行人、自行车）的复杂压力测试场景。
- **📡 传感器阵列**:
  - **12路超声波雷达 (USS)**: 行业标准布置（4前4后4侧），支持 60°~70° FOV 及 5m 探测。
  - **前向 LiDAR**: 180° FOV，25m 探测范围。
- **⚡ 遗传算法进化优化**: 内置遗传算法，可针对时间、路径长度、揉库次数、停靠偏差等多维度权重自动进化最优泊车策略。
- **🎯 严格验证体系**: 自动计算航向偏差（≤2°）、横向偏差（≤15cm）及压线检测。
- **🛠️ 零依赖**: 单个 HTML 文件，包含所有逻辑（着色器、算法、UI），双击即用。

---

## 🛠️ 环境要求

- **浏览器**: Chrome 113+ / Edge 113+ (必须支持 WebGPU)
- **硬件**: 任何支持 WebGPU 的显卡（如 GPU 不可用将自动降级至 CPU，但性能会大幅下降）
- **配置**: 若未生效，请访问 `chrome://flags/#enable-unsafe-webgpu` 开启。

---

## 📖 快速上手

1.  克隆仓库或直接下载 `apa-webgpu.html`。
2.  使用兼容浏览器打开该文件。
3.  **开始仿真**: 点击左侧面板中的 **▶ 开始** 按钮查看默认规划。
4.  **进化优化**:
    - 在进化设置中调整权重（如：增加“揉库权重”以减少调头次数）。
    - 点击 **⚡ 启动进化**。
    - 进化完成后点击 **✓ 应用最优**。

---

## 🕹️ 操作说明

| 操作 | 方法 |
| :--- | :--- |
| **移动视图** | 按住 `Space` + 鼠标左键拖拽 |
| **缩放** | 鼠标滚轮 |
| **编辑物体** | 选择工具（车辆/矩形/车位）后在画布点击放置 |
| **删除物体** | 选中物体后按 `Delete` |

---

## 📷 预览

![APA Simulation Preview](preview.gif)

---

## 📄 开源协议

本项目采用 MIT 协议。

---

## 🔗 相关资源

- [详细技术说明文档 (README-APA.md)](README-APA.md)
