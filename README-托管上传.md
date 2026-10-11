# 运行时包托管上传说明（issue-262）

1. **ModelScope（主源）**：建模型仓（如 `<你的空间名>/zhixu-runtimes`），把本目录整体上传
   （保持相对路径：manifest.json + llama-generic/… + llama-mtk/… + llama-qcom/… + mnn/… + stt/…）。
2. **GitHub Releases（镜像源）**：建 release（tag 如 `runtime-v1`），上传同批文件；manifest.json
   一并附到 release 资产。
3. 上传完成后把两个基准 URL 发我（ModelScope 仓页 URL + GitHub release 页 URL），写入
   `ai/runtime/RuntimeSources.kt` 缺省源即告接通。
4. 后续换包：ZHIXU_PACK_VERSION=N 重跑本脚本（versionCode 递增），重传覆盖，App 端版本门控
   自动提示更新。
