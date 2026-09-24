# effective-barnacle
请帮忙来6楼电子车间看下电脑，中病毒了导致好多台开机都黑屏，谢谢！

6楼车间电脑需要按ctrl+alt+delete---->任务管理器---->文件---->新建任务,输入explorer.exe才能进入桌面。
<img width="380" height="200" alt="image" src="https://github.com/user-attachments/assets/efb3fb77-b8ff-444c-aa60-69bbfb528804" />

原因：注册表 Shell 项被篡改
第一步：win+R（管理员身份启动）输入msconfig,点启动选项卡，把无关的反选，如下图：
<img width="670" height="427" alt="ff61fa68278d1f3450f07be5936565c8" src="https://github.com/user-attachments/assets/582c8206-31e1-4235-9292-aa4777f461b4" />
点应用，点确定！

第二步：在任务管理器中新建任务，输入：gpedit.msc
1. 左侧：**用户配置 → 管理模板 → 系统**
2. 右侧找到：**阻止访问注册表编辑工具**，双击
3. 设置为：**未配置 / 已禁用** → 应用 → 确定，重启电脑

第三步：调出任务管理器（ctrl+shift+esc）-->文件-->运行新任务-->输入：regedit，勾选管理员权限，确定打开注册表编辑器，
```HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon```
在右侧找到名称Shell，双击编辑它：**数值数据必须是 explorer.exe**，删掉里面其他多余文字，只写 `explorer.exe`，点确定
### 重启


