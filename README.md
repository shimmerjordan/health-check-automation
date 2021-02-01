# Are u ok
> 支持Github Action的NEU形式主义自动化打卡python脚本


## 目录

- [使用须知](#使用须知)
- [功能](#功能)
- [手动打卡步骤](#手动打卡步骤)
- [自动打卡步骤](#自动打卡步骤)
- [更新步骤](#更新步骤)
  - [手动打卡](#手动打卡)
  - [自动打卡](#自动打卡)
- [停止使用](#停止使用)
- [开源协议](#开源协议)

## 使用须知

一切风险与后果由使用者自己承担，与作者无关。

## 功能

1. 只需要账号和密码
2. 定时每天的北京时间8点、13点、20点打卡并上报体温
3. 支持打卡/上报体温后邮件通知(非SSL)

## 手动打卡步骤

系统要求: 已安装`python`

第一次使用流程:

1. 下载本项目 `git@github.com:shimmerjordan/health-check-automation.git`
2. 进入项目目录`cd health-check-automation`
3. 安装依赖`pip install -r requirements.txt`
4. 执行`python ./main.py 学号 密码`

之后日常打卡只需要执行`python ./main.py 学号 密码`

或者发送提示邮件并指定ip，可以使用`python ./main.py USER PASS IP MAIL_HOST MAIL_USER MAIL_PASS MAIL_RECEIVER`

其中，各参数之间空格隔开，且各参数为：

- `USER`: 学号
- `PASS`: 密码
- `IP`: ip地址

- `MAIL_HOST`: SMTP服务器地址，带上端口，如`smtp.ym.163.com:25` **不支持SSL**
- `MAIL_USER`: SMTP登陆用的用户名
- `MAIL_PASS`: SMTP登陆用的密码
- `MAIL_RECEIVER`:接收通知邮件的邮箱地址


## 自动打卡步骤
1. Fork本项目

2. 前往Fork后的项目的`Settings`页面

3. 侧边栏点击`Secrets`

4. 通过`add a new secret`添加自己的如下信息（冒号前面的是需要添加的secret的`Name`，后面是对应的`Value`的含义）

    - AUTOMATION_USER01: `USER PASS IP MAIL_HOST MAIL_USER MAIL_PASS MAIL_RECEIVER`

    - [可选的多个账号打卡]AUTOMATION_USER02: `USER PASS IP MAIL_HOST MAIL_USER MAIL_PASS MAIL_RECEIVER`

      其中，各参数之间空格隔开，且各参数为：

      - `USER`: 学号
      - `PASS`: 密码
      - `IP`: ip地址

      - `MAIL_HOST`: SMTP服务器地址，带上端口，如`smtp.ym.163.com:25` **不支持SSL**
      - `MAIL_USER`: SMTP登陆用的用户名
      - `MAIL_PASS`: SMTP登陆用的密码
      - `MAIL_RECEIVER`:接收通知邮件的邮箱地址
    
    **进入Fork后的项目的`Actions`页面，如果有 `I understand my workflows, go ahead and run them`按钮，请点击确认**
    
5. 为了激活自动签到，还需要提交一次commit，流程如下: 

    1. 点击`README.md`的编辑按钮;

    2. 对内容随意做修改，只要有改动就行;

    3. 点击编辑框下方的绿色按钮提交改动，就可以激活自动签到任务。

6. 完成，以防万一还是需要关注邮件或导员通知

## 停止使用

1. 进入Fork后的项目的`Settings`页面
2. 点击左侧侧边栏的 `Actions`进入设置页面
3. 选择`Disable Actions for this repository `即可禁用掉自动打卡

当然，也可以直接删除Fork后的仓库.

## 开源协议

MIT License.
