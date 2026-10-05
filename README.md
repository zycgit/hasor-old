# Hasor（旧仓库，已停止维护）

> **本仓库已停止维护。** 这里仅保留旧版 Hasor 的源码与历史记录，不再进行功能开发、问题修复和版本发布。后续使用、问题反馈与代码贡献，请前往下列独立项目。

原 Hasor 仓库中的能力已按职责拆分为 **6 个项目**。各项目围绕自身领域独立演进，应用可以按需选用，也可以组合使用。

## 模块归属与仓库地址

| 原模块 | 新项目 | Gitee | GitHub |
| --- | --- | --- | --- |
| `hasor-commons` | **Cobble** | [zycgit/cobble](https://gitee.com/zycgit/cobble) | [zycgit/cobble](https://github.com/zycgit/cobble) |
| `hasor-core`、`hasor-web` | **Hasor** | [zycgit/hasor](https://gitee.com/zycgit/hasor) | [zycgit/hasor](https://github.com/zycgit/hasor) |
| `hasor-dataql` | **DataQL / Dataway** | [zycgit/dataql](https://gitee.com/zycgit/dataql) | [zycgit/dataql](https://github.com/zycgit/dataql) |
| `hasor-db` | **dbVisitor** | [zycgit/dbvisitor](https://gitee.com/zycgit/dbvisitor) | [zycgit/dbvisitor](https://github.com/zycgit/dbvisitor) |
| `hasor-rsf` | **Meteor** | [zycgit/meteor](https://gitee.com/zycgit/meteor) | [zycgit/meteor](https://github.com/zycgit/meteor) |
| `hasor-tconsole` | **Neta** | [zycgit/neta](https://gitee.com/zycgit/neta) | [zycgit/neta](https://github.com/zycgit/neta) |

## 拆分后的项目

### Cobble：通用 Java 工具与基础组件

承接原 `hasor-commons` 的通用工具能力，包含 `cobble-lang` 工具与组件、`cobble-dynamic` 动态代理、`cobble-loader` 资源扫描与类加载，以及 `cobble-settings` 配置访问。

**价值：** 将通用能力沉淀为可独立复用的基础库，为普通 Java 应用和其他框架提供工具、动态代理、资源加载与配置支持，减少重复实现。

### Hasor：应用容器与 Web 开发框架

承接原 `hasor-core` 和 `hasor-web`，提供 IoC / 依赖注入、AOP、模块扩展、事件与生命周期管理，以及 Web MVC、参数绑定和响应渲染。新项目还包含 `hasor-config` 声明式配置、`hasor-boot` 应用启动、可执行 JAR 打包与内嵌 Web 容器集成。

**价值：** 围绕 Java 应用的对象管理、模块装配和 Web 开发提供统一开发方式。应用可以从核心容器起步，按需增加配置、Web 与启动能力。

### DataQL / Dataway：数据查询、聚合与 API 开发

承接原 `hasor-dataql`，包含 DataQL 查询语言与执行引擎、SQL 查询支持，以及 Dataway 数据接口开发与管理能力。可完成数据查询、结构转换、多来源聚合，并通过控制台编辑、调试和发布接口，也可通过 Java API 调用。

**价值：** 将数据处理逻辑与接口开发结合，减少查询、转换和接口封装的重复代码。引擎可独立使用，Dataway 可嵌入已有应用，复用数据源与业务服务。

### dbVisitor：统一数据访问

承接原 `hasor-db`，提供基于 JDBC 的数据访问、对象映射、动态 SQL、分页、会话与事务管理，包含 JdbcTemplate、声明式 Mapper、通用 Mapper 和 Lambda 查询构造器，并通过 JDBC 适配器接入 Redis、MongoDB、Elasticsearch、Milvus 等数据源。

**价值：** 以一致的数据访问方式连接关系型数据库与已适配的非关系型数据库，在减少常见 CRUD 代码的同时保留原生 SQL / DSL 的灵活性。可独立使用，也可集成 Spring、Solon、Hasor 等应用框架。

### Meteor：分布式 RPC 与服务通信

承接原 `hasor-rsf`，包含 RSF 的 RPC 调用与服务管理、调用过滤器、地址管理、路由与流控、序列化，以及 RSF/TCP、HTTP/Hprose 协议连接器。主要模块包括 `rsf-framework`、`rsf-final` 和协议连接器模块。

**价值：** 将远程服务调用与通信能力发展为可独立嵌入应用的 RPC 框架。服务调用、序列化和协议连接器各有明确职责，便于扩展协议并接入不同的应用运行环境。

### Neta：网络应用框架与交互控制台

承接原 `hasor-tconsole`，tConsole 位于 Neta 的 `neta-lab/tconsole`，包含 Telnet 服务端、客户端和基于标准输入输出的交互控制台。Neta 同时提供异步网络通信、TCP / UDP、编解码管线及 HTTP 等协议支持。

**价值：** 为网络服务和协议开发提供可组合的通信与编解码能力，并通过 tConsole 为应用增加命令交互、调试和管理入口。

## 迁移与后续使用

请按上表定位所用模块，前往对应项目查看当前文档、版本和接入方式。依赖坐标、包名、配置与启动方式以新项目文档为准，迁移时应逐项核对。

本仓库中的说明和示例仅对应旧版代码。新功能需求、问题报告和 Pull Request 请提交到相应的新项目。

## 许可证

本仓库历史代码继续遵循 [Apache License 2.0](LICENSE.txt)。各新项目的许可证请参阅对应仓库。
