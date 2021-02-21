## 特别声明:

* 本仓库发布的 Actions_JX 项目中涉及的任何解锁和解密分析脚本，仅用于测试和学习研究，禁止用于商业用途，不能保证其合法性，准确性，完整性和有效性，请根据情况自行判断.

* 本项目内所有资源文件，禁止任何公众号、自媒体进行任何形式的转载、发布。

* jiegto 对任何脚本问题概不负责，包括但不限于由任何脚本错误导致的任何损失或损害.

* 间接使用脚本的任何用户，包括但不限于建立VPS或在某些行为违反国家/地区法律或相关法规的情况下进行传播, jiegto 对于由此引起的任何隐私泄漏或其他后果概不负责.

* 请勿将 Actions_JX 项目的任何内容用于商业或非法目的，否则后果自负.

* 如果任何单位或个人认为该项目的脚本可能涉嫌侵犯其权利，则应及时通知并提供身份证明，所有权证明，我们将在收到认证文件后删除相关脚本.

* 任何以任何方式查看此项目的人或直接或间接使用该 Actions_JX 项目的任何脚本的使用者都应仔细阅读此声明。jiegto 保留随时更改或补充此免责声明的权利。一旦使用并复制了任何相关脚本或 Actions_JX 项目的规则，则视为您已接受此免责声明.

 **您必须在下载后的24小时内从计算机或手机中完全删除以上内容.**  </br>
> ***您使用或者复制了本仓库且本人制作的任何脚本，则视为`已接受`此声明，请仔细阅读*** 

## 使用方式

**不再推荐使用 Fork 的方式同步代码**

**[建议使用 reposync 的方式进行同步代码，详细教程请点此查看](https://github.com/sazs34/MyActions/blob/master/backup/reposync.md)**

1. 使用 reposync 的方式进行同步代码

2. 点击 Settings -> Secrets -> 点击绿色按钮 (如无绿色按钮说明已激活。直接到第三步。)

3. 新增 new secret 并设置 Secrets:

4. 双击右上角自己仓库Star触发

5. [定时执行](##定时执行)

## 定时执行

1. 支持手动执行，具体在 Actions 中选中要执行的 Workflows 后再在右侧可以看到 Run workflow，点击即可运行 此workflow。

2. 如果嫌上一步麻烦的，也可以直接点击一下star，你会发现所有的workflow都已执行。

3. 如需修改执行时间自行修改`.github\workflows\`下面的yaml内的` cron:` 执行时间为国际标准时间 [时间转换](http://www.timebie.com/cn/universalbeijing.php) 分钟在前，小时在后，尽量提前半小时，因为触发和下载需要一定时间。

## Secrets 集合

> 参考：[环境变量说明](https://github.com/lxk0301/jd_scripts/blob/master/githubAction.md)

### 京东(必须)

| Name                    |   归属   | 属性   | 说明                                                         |
| :---------------------: | :----------: | --------- | ------------------------------------------------------------ |
| `JD_COOKIE`             |   京东   | 必须   | 京东cookie,多个账号的cookie使用`&`隔开或者换行。具体获取参考[浏览器获取京东cookie教程](https://github.com/lxk0301/jd_scripts/blob/master/backUp/GetJdCookie.md) 或者 [插件获取京东cookie教程](https://github.com/lxk0301/jd_scripts/blob/master/backUp/GetJdCookie2.md) |

### 京东隐私安全

| Name                    |   归属   | 属性   | 说明                                                         |
| :---------------------: | :----------: | --------- | ------------------------------------------------------------ |
| `JD_DEBUG`              |   脚本打印log   | 非必须   | 运行脚本时，是否显示log,默认显示。改成false表示不显示，注重隐私的人可以在设置secret -> `Name:JD_DEBUG,Value:false` |
| `JD_USER_AGENT`         |   京东   | 非必须   | 自定义此库里京东系列脚本的UserAgent，不懂不知不会UserAgent的请不要随意填写内容。具体获取参考此[issue](https://github.com/lxk0301/jd_scripts/issues/127) |

### 脚本功能变量

| Name                         | 归属                      | 属性 | 说明                                                                                                                                                                                                                                                   |
| ---------------------------- | --------------------------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `JD_BEAN_STOP`               | 京东                      | 非必须 | `jd_bean_sign.js`自定义延迟签到,单位毫秒.默认分批并发无延迟.延迟作用于每个签到接口,如填入延迟则切换顺序签到(耗时较长),如需填写建议输入数字`1`，详见[此处说明](https://github.com/NobyDa/Script/blob/master/JD-DailyBonus/JD_DailyBonus.js#L93) |
| `JOY_FEED_COUNT`             | 宠汪汪喂食数量             | 非必须 | 控制`jd_joy_feedPets.js`脚本喂食数量,可以填的数字10,20,40,80,其他数字不可.                                                                                                                                                           |
| `JOY_HELP_FEED`              | 宠汪汪帮好友喂食           | 非必须 | 控制`jd_joy_steal.js`脚本是否给好友喂食,`false`为否,`true`为是(给好友喂食)                                                                                                                                                           |
| `JOY_RUN_FLAG`               | 宠汪汪是否赛跑             | 非必须 | 控制`jd_joy.js`脚本是否参加赛跑(默认参加双人赛跑),`false`为否,`true`为是，脚本默认是`true`                                                                                                                                   |
| `JOY_TEAM_LEVEL`             | 宠汪汪参加什么级别的赛跑    | 非必须 | 控制`jd_joy.js`脚本参加几人的赛跑,可选数字为`2`,`10`,`50`，其中2代表参加双人PK赛，10代表参加10人突围赛，50代表参加50人挑战赛(注：此项功能在`JOY_RUN_FLAG`为true的时候才生效)，如若想设置不同账号参加不同类别的比赛则用&区分即可(如下三个账号：`2&10&50`) |
| `JD_JOY_REWARD_NAME`         | 宠汪汪积分兑换多少京豆      | 非必须 | 目前可填值为`20`或者`500`,脚本默认`20`,`0`表示不兑换京豆                                                                                                                                                                              |
| `MARKET_COIN_TO_BEANS`       | 京小超兑换京豆数量          | 非必须 | 控制`jd_blueCoin.js`兑换京豆数量,可输入值为`20`或者`1000`的数字或者其他商品的名称,例如`碧浪洗衣凝珠`                                                                                                                  |
| `SUPERMARKET_UPGRADE`        | 京小超自动升级             | 非必须 | 自动升级,顺序:解锁升级商品、升级货架,`true`表示自动升级,`false`表示关闭自动升级                                                                                                                                           |
| `BUSINESS_CIRCLE_JUMP`       | 京小超自动更换商圈         | 非必须 | 小于对方300热力值自动更换商圈队伍,`true`表示运行,`false`表示禁止                                                                                                                                                                  |
| `SUPERMARKET_LOTTERY`        | 京小超抽奖                 | 非必须 | 每天运行脚本是否使用金币去抽奖,`true`表示抽奖,`false`表示不抽奖                                                                                                                                                                  |
| `FRUIT_BEAN_CARD`            | 农场使用水滴换豆卡           | 非必须 | 农场使用水滴换豆卡(如果出现限时活动时100g水换20豆,此时比浇水划算,推荐换豆),`true`表示换豆(不浇水),`false`表示不换豆(继续浇水),脚本默认是浇水                                                      |
| `UN_SUBSCRIBES`              | jd_unsubscribe.js           | 非必须 | 共四个参数,换行隔开.四个参数分别表示`取关商品数量`,`取关店铺数量`,`遇到此商品不再进行取关`,`遇到此店铺不再进行取关`，[具体使用往下看](#取关店铺secret的说明)                           |
| `UN_BIND_CARD_NUM`           | jd_unbind.js                | 非必须 | 注销京东已开的店铺会员，不是注销京东plus会员，个别店铺无法注销。此参数控制每次运行脚本时注销多少个店铺会员，默认200。                                                                             |
| `UN_BIND_STOP_CARD`          | jd_unbind.js                | 非必须 | 注销京东已开的店铺会员，不是注销京东plus会员，个别店铺无法注销。遇到此参数设定的会员卡则跳过不注销，多个会员卡之间以`&`分隔，默认值"京东PLUS会员"。                                   |
| `JDJOY_HELPSELF`             | 疯狂的JOY                   | 非必须 | 疯狂的JOY循环助力，`true`表示循环助力,`false`表示不循环助力，默认不开启循环助力。                                                                                                                                        |
| `JDJOY_APPLYJDBEAN`          | 疯狂的JOY                   | 非必须 | 疯狂的JOY京豆兑换，目前最小值为500/1000京豆，默认不开启京豆兑换。                                                                                                                                                             |
| `BUY_JOY_LEVEL`              | 疯狂的JOY                   | 非必须 | 疯狂的JOY自动购买什么等级的JOY                                                                                                                                                                                                               |
| `MONEY_TREE_SELL_FRUIT`      | 摇钱树是否卖出金果           | 非必须 | 控制摇钱树脚本是否自动卖出金果兑换成金币，`true`卖出，`false`不卖出，默认`false`                                                                                                                                           |
| `FACTORAY_WANTPRODUCT_NAME`  | 东东工厂心仪商品             | 非必须 | 提供心仪商品名称(请尽量填写完整和别的商品有区分度)，达到条件后兑换，如不提供则会兑换当前所选商品                                                                                                          |
| `JXNCTOKENS`                 | 京喜农场TOKEN               | 非必须 | 每个账号 token 是一个 json，示例：{"farm_jstoken":"749a90f871adsfads8ffda7bf3b1576760","timestamp":"1610165423873","phoneid":"42c7e3dadfadsfdsaac-18f0e4f4a0cf"}，多账单间使用`&`或换行分开。                                    |

### 结果推送控制

| Name                    |   归属   | 属性   | 说明                                                         |
| ----------------------- | :------: | ------ | ------------------------------------------------------------ |
| `JD_BEAN_SIGN_STOP_NOTIFY`   |   京东   | 非必须   | jd_bean_sign.js脚本运行后不推送签到结果通知，默认推送，填true表示不发送通知 |
| `JD_BEAN_SIGN_NOTIFY_SIMPLE` |   京东   | 非必须   | jd_bean_sign.js脚本运行后推送签到结果简洁版通知，默认推送全部签到结果，填true表示推送简洁通知 |
| `PET_NOTIFY_CONTROL`         |   京东   | 非必须   | 控制京东萌宠是否静默运行,false为否(发送推送通知消息),true为是(即：不发送推送通知消息) |
| `FRUIT_NOTIFY_CONTROL`       |   京东   | 非必须   | 控制京东农场是否静默运行,false为否(发送推送通知消息),true为是(即：不发送推送通知消息) |
| `JD_JOY_REWARD_NOTIFY`       |   京东   | 非必须   | 控制jd_joy_reward.js脚本是否静默运行,false为否(发送推送通知消息),true为是(即：不发送推送通知消息) |
| `DREAMFACTORY_NOTIFY`        |   京东   | 非必须   | 控制jd_dreamFactory.js脚本是否静默运行,false为否(发送推送通知消息),true为是(即：不发送推送通知消息) |
| `MARKET_COIN_TO_BEANS `      |   京东   | 非必须   | 控制jd_blueCoin.js兑换京豆数量,可输入值为20或者1000的数字或者其他商品的名称,例如碧浪洗衣凝珠 |
| `MARKET_REWARD_NOTIFY `      |   京东   | 非必须   | 控制jd_blueCoin.js兑换奖品成功后是否静默运行, false为否(发送推送通知消息),true为是(即：不发送推送通知消息) |

### 互助码类环境变量

| Name                        | 归属             | 属性 | 说明                                                                                                                                                                |
| --------------------------- | ------------------ | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `FRUITSHARECODES`           | 东东农场互助码 | 非必须 | 填写规则请看[jdFruitShareCodes.js](https://github.com/lxk0301/jd_scripts/blob/master/jdFruitShareCodes.js)或见下方[互助码的填写规则](#互助码的填写规则) |
| `PETSHARECODES`             | 东东萌宠互助码 | 非必须 | 填写规则请看[jdPetShareCodes.js](https://github.com/lxk0301/jd_scripts/blob/master/jdPetShareCodes.js)或见下方[互助码的填写规则](#互助码的填写规则) |
| `PLANT_BEAN_SHARECODES`     | 种豆得豆互助码 | 非必须 | 填写规则请看[jdPlantBeanShareCodes.js](https://github.com/lxk0301/jd_scripts/blob/master/jdPlantBeanShareCodes.js)或见下方[互助码的填写规则](#互助码的填写规则) |
| `SUPERMARKET_SHARECODES`    | 东东超市商圈互助码 | 非必须 | 填写规则请看[jdSuperMarketShareCodes.js](https://github.com/lxk0301/jd_scripts/blob/master/jdSuperMarketShareCodes.js)或见下方[互助码的填写规则](#互助码的填写规则) |
| `DDFACTORY_SHARECODES`      | 东东工厂互助码 | 非必须 | 填写规则请看[jdFactoryShareCodes.js](https://github.com/lxk0301/jd_scripts/blob/master/jdFactoryShareCodes.js)或见下方[互助码的填写规则](#互助码的填写规则) |
| `DREAM_FACTORY_SHARE_CODES` | 京喜工厂互助码 | 非必须 | 填写规则请看[jdDreamFactoryShareCodes.js](https://github.com/lxk0301/jd_scripts/blob/master/jdDreamFactoryShareCodes.js)或见下方[互助码的填写规则](#互助码的填写规则) |
| `JDZZ_SHARECODES`           | 京东赚赚互助码 | 非必须 | 填写规则和上面类似，或见下方[互助码的填写规则](#互助码的填写规则)                                                                       |
| `JDJOY_SHARECODES`          | 疯狂的JOY互助码 | 非必须 | 填写规则和上面类似，或见下方[互助码的填写规则](#互助码的填写规则)                                                                       |
| `BOOKSHOP_SHARECODES`       | 京东书店互助码 | 非必须 | 填写规则和上面类似，或见下方[互助码的填写规则](#互助码的填写规则)                                                                       |
| `JD_CASH_SHARECODES`        | 签到领现金互助码 | 非必须 | 填写规则和上面类似，或见下方[互助码的填写规则](#互助码的填写规则)                                                                       |
| `JXNC_SHARECODES`           | 京喜农场互助码 | 非必须 | 填写规则和上面类似，或见下方[互助码的填写规则](#互助码的填写规则)                                                                       |
| `JD_FACTORY_CODE`            |   京东   | 非必须   | 填写东东工厂提交互助码的完整链接 `http://api.turinglabs.net/api/v1/jd/ddfactory/create/互助码/`|
| `JX_FACTORY_CODE`            |   京东   | 非必须   | 填写京喜工厂提交互助码的完整链接 `http://api.turinglabs.net/api/v1/jd/jxfactory/create/互助码/`|
| `JD_BEAN_CODE`               |   京东   | 非必须   | 填写种豆得豆提交互助码的完整链接 `http://api.turinglabs.net/api/v1/jd/bean/create/互助码/`|
| `JD_FARM_CODE`               |   京东   | 非必须   | 填写东东农场提交互助码的完整链接 `http://api.turinglabs.net/api/v1/jd/farm/create/互助码/`|
| `JD_PET_CODE`                |   京东   | 非必须   | 填写东东萌宠提交互助码的完整链接 `http://api.turinglabs.net/api/v1/jd/pet/create/互助码/`|

### 推送专用

| Name                    | 属性                   | 说明                                                         |
| ----------------------- | ---------------------- | ------------------------------------------------------------ |
| `PUSH_KEY`              |   Server酱SCKEY值      | cookie失效推送[server酱的微信通知](http://sc.ftqq.com/3.version) |
| `BARK_PUSH`             |   Bark推送值           | 此内容支持自建Bark添加整个链接即可(自建链接切记删除最后一个/  比如你的是https://a.a.com/ 只需要填写https://a.a.com 即可)|
| `BARK_SOUND`            |   BARK app推送铃声     |BARK app推送铃声,铃声列表去APP查看复制填写|
| `TG_BOT_TOKEN`          |   telegram推送        | tg推送,填写自己申请[@BotFather](https://t.me/BotFather)的Token,如`10xxx4:AAFcqxxxxgER5uw` , [具体教程](https://github.com/lxk0301/scripts/pull/37#issuecomment-692415594) |
| `TG_USER_ID`            |   telegram推送        | tg推送,填写[@getuseridbot](https://t.me/getuseridbot)中获取到的纯数字ID, [具体教程](https://github.com/lxk0301/scripts/pull/37#issuecomment-692415594) |
| `DD_BOT_TOKEN`          |   钉钉推送   | 钉钉推送[官方文档](https://ding-doc.dingtalk.com/doc#/serverapi2/qf2nxq) ,只需`https://oapi.dingtalk.com/robot/send?access_token=XXX` 等于符号后面的XXX， 注：如果钉钉推送只填写`DD_BOT_TOKEN`，那么安全设置需勾选`自定义关键词`，内容输入输入`账号`即可，其他安全设置不要勾选 |
| `DD_BOT_SECRET`         |   钉钉推送   | 密钥，机器人安全设置页面，加签一栏下面显示的SEC开头的字符串 , 注:填写了`DD_BOT_TOKEN`和`DD_BOT_SECRET`，钉钉机器人安全设置只需勾选`加签`即可，其他选项不要勾选,再不懂看 [这个图](icon/DD_bot.png) |
| `IGOT_PUSH_KEY`         |   iGot推送   | iGot聚合推送，支持多方式推送，确保消息可达。 [参考文档](https://wahao.github.io/Bark-MP-helper ) |


### Cookie获取和配置

> 具体如何取cookie如何配置,可参考 https://github.com/lxk0301/scripts/issues/8#issuecomment-675837338

```

针对京东cookie我们只需要
pt_key=****;
和
pt_pin=***;
的部分

我有两个京东账号,则我JD_COOKIE里面要填写的内容为
pt_key=****;pt_pin=***;&pt_key=****;pt_pin=***;
```

### 互助码的填写规则

> 互助码如何获取：运行相应脚本后，在日志里面可以找到。

同一个京东账号的好友互助码用@隔开,不同京东账号互助码用&或者换行隔开,下面给一个文字示例和具体互助码示例说明

两个账号各两个互助码的文字示例：

```
京东账号1的shareCode1@京东账号1的shareCode2&京东账号2的shareCode1@京东账号2的shareCode2
```

两个账号各两个互助码的真实示例：

```
0a74407df5df4fa99672a037eec61f7e@dbb21614667246fabcfd9685b6f448f3&6fbd26cc27ac44d6a7fed34092453f77@61ff5c624949454aa88561f2cd721bf6&6fbd26cc27ac44d6a7fed34092453f77@61ff5c624949454aa88561f2cd721bf6
```

### 取关店铺secret的说明

> ecret依次是取关商品数,取关店铺数,遇到此商品不再进行取关,遇到此店铺不再进行取关

例如我要取关 100个商品，100个店铺，商品遇到商品关键字 iPhone12 停止取关，店铺遇到 Apple京东自营旗舰店 不再取关 则使用换行或者&隔开即可, 下面给出换行隔开示例:

```
100
100
iPhone12
Apple京东自营旗舰店
```

下面给出&符号隔开示例:

```
100&100&iPhone12&Apple京东自营旗舰店
```

### 关于脚本推送通知频率

  > 如果你填写了推送通知方式中的某一种通知所需环境变量，那么脚本通知情况如下：

  > 目前默认只有jd_fruit.js,jd_pet.js,jd_bean_sign.js,jd_818.js四个脚本每次运行后都通知

  ```
jd_plantBean.js是每周一收集京豆后通知一次，
jd_joy_reward.js是每次兑换到了京豆通知一次，
jd_blueCoin.js是每次兑换到了奖品通知一次，
jd_818.js是每次获取新的互助码会通知一次，以帮助您快速上车，
其余的脚本平常运行都是不通知，只有在京东cookie失效后，才会推送通知    
  ```

## 鸣谢

[@lxk0301](https://github.com/lxk0301)  - 京东相关

[@Sunert](https://github.com/Sunert)  - 京喜签到

[@sazs34](https://github.com/sazs34)  - reposync 同步相关





