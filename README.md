# 炫音 GitHub Releases 发布仓库
#
# App 通过以下接口检查更新：
# GET https://api.github.com/repos/wansxsy/xuanyin-releases/releases/latest

App 会读取 `tag_name`（去掉 `v` 前缀）作为最新版本号，并在 `assets` 中找到 `.apk` 附件自动下载安装。

## 每次发版步骤

1. 进入 **Releases** → **Draft a new release**
2. **Choose a tag**：填写版本号，必须以 `v` 开头，例如 `v1.1.25`（数字与 Gradle 中的 `versionName` 完全一致）
3. **Release title**：`炫音 Android 1.1.25`
4. 把 `炫音-Android-1.1.25.apk` 拖到附件区
5. 点 **Publish release**

发布后无需改动 App，下次启动或回到前台时会自动检测并弹窗提示升级。

## 注意

- tag 必须是 `v` + 版本号，缺了 `v` 也能识别，但请保持统一
- Release 不要勾选 **Set as a pre-release**，`latest` 接口会跳过预发布版本
- APK 附件名必须以 `.apk` 结尾
