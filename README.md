# 慧治 Agent 安装包

本仓库用于发布慧治 Agent 的安装包、校验文件和安装说明，源码不包含在此仓库中。

## 当前版本

- 版本：0.1.4
- 目标系统：统信 UOS，ARM64（`aarch64`）
- 安装包：`huizhi-agent-0.1.4-linux-arm64.deb`
- 下载入口：[Releases](https://github.com/yr9077/huizhi-agent-releases/releases/latest)

## 安装

从 Release 下载 `.deb` 和同名 `.sha256` 文件，放在同一目录。完全退出旧版应用后运行：

```sh
sha256sum -c huizhi-agent-0.1.4-linux-arm64.deb.sha256
sudo apt install ./huizhi-agent-0.1.4-linux-arm64.deb
```

安装后从应用菜单打开“慧治 Agent”。如需从终端启动，可运行：

```sh
huizhi-agent --ozone-platform=x11 --disable-gpu
```

使用普通桌面用户运行。首次启动需要填写模型服务地址、模型 ID 和 API Key。0.1.4 使用独立的模型配置目录；升级后需重新填写模型配置和密钥，历史记录与工作文件保留。

## 完整性

0.1.4 ARM64 安装包大小为 202,483,196 字节，SHA256 为：

```text
f4bb9055ef10d21b4b32328ffab45e06e57aea46c4c11971ea8b9b8ed4e88b25
```

## 验证范围

构建、自动化测试与包内资源校验通过；本版仍需统信 ARM64 真机启动和真实业务验收。模型服务需支持 OpenAI-compatible Chat Completions、流式响应和工具调用，具体容量以服务商为准。
