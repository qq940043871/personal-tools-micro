# personal-tools-micro

个人小工具集，目前包含两个独立的 Python 工具。

## 目录结构

```
personal-tools-micro/
├── meeting_minutes/      # 会议纪要智能工具
├── doubao_multi_login/   # 豆包多账号登录管理工具
└── .gitignore
```

## 工具列表

### 1. meeting_minutes — 会议纪要智能工具

自动生成会议纪要：实时录制会议音频 → Whisper 本地转写为文字 → 调用智谱 GLM API 生成结构化会议纪要，并支持历史记录管理与屏幕录制。

- 🎤 实时麦克风录音，支持屏幕录制
- 🎯 Whisper 本地语音转文字
- 📝 智谱 GLM 生成结构化会议纪要
- 📋 历史录音与纪要管理
- 🖥️ 提供 GUI（tkinter）与 CLI 两种界面

**技术栈**：Python 3.9+ / PyAudio / OpenAI-Whisper / 智谱 GLM API / OpenCV / Nuitka 打包

**快速开始**：

```bash
cd meeting_minutes
pip install -r requirements.txt
copy .env.example .env        # 填入你的 API Key
run_gui.bat                   # 或 run_cli.bat
```

详细说明见 [meeting_minutes/README.md](meeting_minutes/README.md)。

### 2. doubao_multi_login — 豆包多账号登录管理工具

管理豆包等多个网站的账号，使用内嵌浏览器实现多账号隔离登录与自动化操作。

- 👥 账号增删改查，密码加密存储
- 🌐 内嵌浏览器（PyQtWebEngine）多账号隔离登录
- 🔁 支持单账号或批量登录
- 🖥️ 提供 GUI（PyQt5）、CLI、Web 三种界面

**技术栈**：Python / PyQt5 + PyQtWebEngine / pycryptodome

**快速开始**：

```bash
cd doubao_multi_login/multi_login_app
pip install -r requirements.txt
python gui.py                 # 或 python cli.py / python web/app.py
```

## 安全说明

- 所有密钥（API Key）只存放在本地 `.env` 文件中，已通过 `.gitignore` 排除，仓库中仅保留 `.env.example` 模板
- 账号数据库 `accounts.db`（含加密的账号密码）、会议录音、构建产物、日志均不入库
- 克隆后请先复制 `.env.example` 为 `.env` 并填入自己的配置
