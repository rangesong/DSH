# DSH
DeepSeek Harness Plugin, some plugins rely otherone.

本仓库用于组织DeepSeek Harness生态中的插件项目。各插件可以有自己的依赖、版本和发行流程；本仓库不包含DSH主程序或Aurabot本体。

## 插件

| 插件 | 源码位置 | 独立仓库 | 主要依赖 |
|---|---|---|---|
| Thinkstar记忆 | `plugins/thinkstar-memory`（Git子模块） | [DSHaurabot-memory](https://github.com/rangesong/DSHaurabot-memory) | DSH中的Aurabot；推荐与Aurabot内置记忆共同运行 |

Thinkstar提供分层原话存储、来源回查、相关记忆召回、反馈学习、夜间自省与行动及三维脑内星图。完整能力和限制见[项目说明](https://github.com/rangesong/DSHaurabot-memory/blob/main/docs/project-overview.md)。

## 获取插件源码

```sh
git clone --recurse-submodules https://github.com/rangesong/DSH.git
```

如果已经克隆本仓库，在仓库根目录执行：

```sh
git submodule update --init --recursive
```

子模块引用固定提交。普通拉取集合不会自动升级到插件的任意最新代码；依赖与安装要求以各插件README为准。这里的源码目录不是Aurabot的安装目录，Thinkstar实际安装到Aurabot数据目录下的 `modules/thinkstar-memory`。

## 更新与发行

Thinkstar在独立仓库维护代码、检查、版本及Release。维护者先提交并推送插件，再核对并更新本集合记录的子模块版本：

```sh
git submodule update --remote -- plugins/thinkstar-memory
git add plugins/thinkstar-memory
git commit -m "chore: update Thinkstar submodule"
git push
```

本集合不复制依赖插件的源码、聊天数据库、密钥、运行日志或私人女孩模型。每个插件的许可和第三方说明分别适用；公开仓库不自动授予其他使用许可。
