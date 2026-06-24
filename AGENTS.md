# ToonFlow 二开规则

本仓库是 ToonFlow 的二次开发仓库。开发时请遵守以下规则。

## 沟通规则

- 用户没有编程基础，回复必须简单清楚。
- 先说结论，再说原因和下一步。
- 能直接完成的本地操作，不要只让用户自己执行命令。

## 仓库规则

- `origin` 是用户自己的 GitHub fork，用来保存二开代码。
- `upstream` 是原作者 GitHub 仓库，只用于同步官方更新。
- `gitee` 是备用镜像，只在 GitHub 网络不稳定时拉取。
- 禁止向 `upstream` 和 `gitee` 推送代码。

## 分支规则

- `master` 保持接近官方原版。
- `develop` 是二开主分支，日常开发都在这里进行。
- 新功能使用 `feature/*` 分支。
- 修复问题使用 `fix/*` 分支。
- 不要直接在 `master` 上做二开改动。

## 环境规则

- 使用 Node.js 和 Yarn。
- Yarn 固定为 `1.22.22`。
- 安装依赖使用：

```powershell
corepack yarn@1.22.22 install --frozen-lockfile
```

- 不要提交 `node_modules/`、`.env`、数据库文件、日志、构建产物。

## 修改规则

- 修改前先看相关代码和 `git status`。
- 小步修改，不做无关重构。
- 不删除用户已有改动。
- 不把密钥、Token、Cookie 写入代码。

## 验证规则

每次改代码后至少运行：

```powershell
corepack yarn@1.22.22 lint
```

如果改到启动、Electron、打包逻辑，还要额外运行对应启动或打包命令。

