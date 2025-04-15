# Windows系统搭建Minecraft 1.19.4服务器完整教程（基于雨云VPS）

本教程将详细介绍如何使用Windows系统在雨云VPS上搭建支持模组和插件的Minecraft 1.19.4服务器，采用Mohist服务端，适合新手操作。

## Mohist服务端优势

Mohist是一个高性能的Minecraft Forge服务端，完美融合了Bukkit/Spigot插件系统和Forge模组系统：

- **双系统支持**：同时运行Forge模组和Bukkit/Spigot插件
- **性能优化**：基于Paper核心，确保高版本服务器流畅运行
- **持续更新**：活跃的开发社区保持与最新Minecraft版本同步
- **简易管理**：提供友好的控制台和管理命令

👉 [【点击查看】2025年最新雨云优惠码及特价云服务器方案汇总](https://bit.ly/RainYun)

## 准备工作

### 服务器配置建议
- **CPU**：4核及以上（推荐Ryzen 7950X或Intel 13900KF）
- **内存**：8GB起步（Windows系统本身占用约2GB）
- **系统**：Windows Server 2019
- **网络**：NAT端口映射（需开放25565端口）

### 必要软件准备
1. Java运行环境（推荐Java 17）
2. Mohist服务端程序
3. 远程桌面连接工具

## 详细搭建步骤

### 第一步：连接服务器
1. 使用Windows自带的远程桌面连接（mstsc）
2. 输入服务器IP和端口
3. 使用默认账号Administrator登录

### 第二步：环境配置
1. **关闭防火墙**（或单独放行25565端口）
   - 控制面板→系统和安全→Windows Defender防火墙→关闭所有网络类型的防火墙
2. **配置端口映射**
   - 在雨云控制台创建NAT规则
   - 将内网25565端口映射到公网端口

### 第三步：安装Java环境
1. 下载JDK 17（推荐阿里Dragonwell）
2. 解压到D盘指定目录
3. 配置系统环境变量：
   - 将JDK的bin目录路径添加到Path变量
4. 验证安装：`java -version`

### 第四步：部署Mohist服务端
1. 创建专用目录（如D:\mcserver）
2. 下载Mohist 1.19.4服务端jar文件
3. 创建启动脚本run.bat：
batch
java -Xms128M -XX:MaxRAMPercentage=95.0 -Dfile.encoding=UTF-8 -jar mohist-1.19.4-192-server.jar
pause

### 第五步：启动与配置
1. 首次运行会生成eula.txt，需同意EULA协议
2. 修改server.properties配置：
   - online-mode=false（关闭正版验证）
   - 其他参数按需调整
3. 使用stop命令安全关闭服务器

## 客户端连接指南
1. 获取服务器公网地址（IP:映射端口）
2. 在MC客户端添加服务器
3. 使用op命令获取管理员权限

## 常见问题解决
- **连接失败**：检查防火墙和端口映射
- **内存不足**：调整启动参数中的-Xmx值
- **模组冲突**：检查服务端日志报错

## 服务器维护技巧
1. 定期备份world目录
2. 使用定时任务自动重启
3. 安装基础保护插件

通过本教程，您已经成功搭建了支持模组和插件的Minecraft服务器。如需更高性能的云服务器方案，可以参考：

[雨云高性能云服务器限时特惠](https://bit.ly/RainYun)