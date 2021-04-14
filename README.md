# 什么值得买每日签到脚本


## 1. 实现功能
- `什么值得买`每日签到
- `GitHub Actions`每日定时运行
- 通过`pushplus`推送运行结果到微信

## 2. 使用方法
- Secret新增`COOKIE`, 填入[什么值得买官网](https://www.smzdm.com/)获取的Cookie信息, [详见](#31-cookie获取方法)
- (可选) Secret新增`PUSH_PLUS_TOKEN`用于推送通知, [详见](https://www.pushplus.plus/)


## 3. 其它
### 3.1 Cookie获取方法
- 使用Chrome浏览器访问[什么值得买官网](https://www.smzdm.com/), 登录账号
- 打开开发者工具 (Windows快捷键`F12`, MacOS快捷键`option + command + i`)
- 选择Network, 刷新页面, 选择第一个`www.smzdm.com`, 找到`Requests Headers`里的`Cookie`

### 3.2 更改运行时间
在`.github/workflows/main.yml`中，找到
```yml
- cron: '0 23 * * *'
```
语法同crontab, 具体自行搜索; 默认为美区时间, 加8h为中国时间

