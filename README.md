# 【全栈之巅】 - 打造更顺手的 MacOS

> 如无特殊说明，所有命令均在 “终端” 中运行。(F4或四指捏合调出应用程序 - 输入term - return)

## 小技巧
- 快速打开软件： F4或触摸板四指捏合 - 打字搜索 (一般是英文)，如: 输入sys会高亮显示系统偏好设置, term 会显示终端；回车键打开软件
- command + ` 切换同一app的不同窗口，比如vscode的多个项目；command + tab 切换不同app，如vscode 和 chrome
- command + w 关闭一个tab, command + q 退出整个app
- 很多地方按住option(alt)键会有惊喜，比如左上角苹果图标点开，按住option“关于本机”会变成“系统信息”
- F4 - act - 活动监视器 - 可以看cpu、内存和磁盘使用情况
- 双击选中单词，三击选中整行; option + delete 删除单词，command + delete 删除整行

## 系统设置
- 触摸板轻触和右键: 系统偏好设置 - 触控板 - 光标与点按 - 勾选“轻点来点按” 和 “辅助点按”（双指点按或轻点）
- 三指拖移: 系统偏好设置 - 辅助功能 - 指针控制 - 触控板选项 - 启用拖移 - 三指拖移
- 键盘加速: 系统偏好设置 - 键盘 - 按键重复 - 调到最快；重复前延迟 - 适当调低
- 增强Tab键: 系统偏好设置 - 键盘 - 快捷键 - 使用键盘导航在控制间移动焦点
- 程序坞效果: 系统偏好设置 - 程序坞 - 适当调整“大小”和“放大”并勾选放大
- 修改密码: 系统偏好设置 - 用户与群组 - 更改密码
- 【危险】修改用户名: 系统偏好设置 - 用户与群组 - 点击左下角解锁 - 用户名上双指轻点 - 高级选项
- 电脑改名: 系统偏好设置 - 共享 - 电脑名称

## 常见问题
- “文件已损坏”?: 终端输入 `sudo spctl --master-disable` ，系统偏好设置 - 安全性与隐私 - 通用 - 允许“任何来源”

## 工具安装
```bash
# 【必装】使用全栈之巅国内安装器 安装 Homebrew - MacOS包管理器(命令行轻松装软件)
/usr/bin/ruby -e "$(curl -fsSL https://gitee.com/topfullstack/install/raw/cn/install)"

# 【推荐安装】 oh-my-zsh - 更强大的终端Shell，可显示git分支，z命令跳转，git别名等等
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# 【必装】node - 无论前后端开发都需要
brew install node

# 【必装】 npm源切换工具
npm i -g nrm
nrm use taobao
nrm use npm

# 【建议安装】 yarn
brew install yarn

# 【必装】MongoDB - 文档型数据库
brew tap mongodb/brew
brew install mongodb-community
brew services start mongodb-community

# 【必装】VSCode - 代码编辑器
brew cask install visual-studio-code

# 【必装】Chrome - 更适合开发的浏览器
brew cask install google-chrome

# 【可选】安装 iTerm2 - 更强大的终端工具，支持窗口分割，不过大多数直接用VSCode终端也够用
brew cask install iterm2
```


## 开发相关
```bash
# 全局安装nest cli, vue cli ，nodemon 和 serve
yarn global add @nestjs/cli @vue/cli nodemon serve

# 生成ssh key并加入git账户
ssh-keygen # 一路回车即可
cat ~/.ssh/id_rsa.pub | clipcopy
# 粘贴到自己git账号设置里的ssh-key

code ~/.zshrc # 添加插件 plugins=(git z)
z test # 跳转到最近包含test字符的目录
# 可使用git命令别名: gst gl gp gaa gcam gb gcb gco 等等
```

## VSCode

### 基本操作
- cmd + shift + p - Configure Display Languge - install... - 安装中文语言包
- cmd + j 打开终端，如果不是zsh的话，点击终端下拉菜单选择默认shell
- cmd + b 切换左侧边栏, cmd + shift + e 显示侧边栏文件夹
- cmd + f 搜索，cmd + option + f 替换，cmd + shift + f 全局搜索
- ctrl ( + shift) + - 切换光标位置
- ctrl ( + shift) + tab 切换打开的文件
- cmd + \ 拆分窗口
- cmd + k 松开再按 v，预览markdown文件

### 插件
- Material Theme - 主题
- Auto Rename Tag - 自动重命名成对标签
- Element UI Snippets - Element UI代码块
- Live Server - WEB服务器（可选）
- Prettier - 格式化工具
- vetur - vue 高亮
- REST Client - Vscode里的PostMan
- Remote - SSH - 用vscode打开服务器文件夹

## Chrome

- cmd + option + j 打开开发者工具
- 双指左右滑动 - 后退和前进


## 如何选择开发电脑？

> Johnny @ 全栈之巅

1. 为什么 MacOS 比 Windows 更适合做开发？
    - MacOS 底层是 unix，更接近服务器端上的 Linux
    - Windows 可能会有不一致的权限问题
    - MacOS 相对 Windows 来说更安全省心
    - MacOS 更加人性化：键盘、触控板、省电...

1. 为什么只选2012年末之后的 Macbook pro retina？
    - 视网膜显示屏
    - CPU 性能
    - 散热

1. MacOS 开发环境怎么配置？
    - github.com/topfullstack/mac

1. 怎么在 MacOS 上装 Windows？

1. 如何选择性价比最高的 Macbook pro?
    - 尺寸：13寸和15寸
    - 硬盘：128G、256G、512G、1T
    - 内存：4G、8G、16G
    - CPU：2.0GHz ~ 3.1GHz
    - 电池循环
    - 地区版本：国行、港版、其他

1. 全栈之巅官方淘宝店
    - qzzd.taobao.com
