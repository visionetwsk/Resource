# iOS 证书 设置指南
## 创建应用程序ID

* 登陆 [iOS Dev Center](https://developer.apple.com/devcenter/ios/index.action) 选择进入iOS Provisioning Portal。  

![WSK_SDK_iOS](https://raw.githubusercontent.com/visionetwsk/Resource/master/image/login.png)

* 在 iOS Provisioning Portal中，点击App IDs进入App ID列表。

![WSK_SDK_iOS](https://raw.githubusercontent.com/visionetwsk/Resource/master/image/appid.png)

* 创建 App ID，如果 ID 已经存在可以直接跳过此步骤

![WSK_SDK_iOS](https://raw.githubusercontent.com/visionetwsk/Resource/master/image/appid2.png)

* 为 App 开启 Push Notification 功能。如果是已经创建的 App ID 也可以通过设置开启 Push Notification 功能。

![WSK_SDK_iOS](https://raw.githubusercontent.com/visionetwsk/Resource/master/image/appservice.png)

根据实际情况完善 App ID 信息并提交,注意此处需要指定具体的 Bundle ID 不要使用通配符。

![WSK_SDK_iOS](https://raw.githubusercontent.com/visionetwsk/Resource/master/image/appid3.png)

## 配置和下载证书
* 如果你之前没有创建过 Push 证书或者是要重新创建一个新的，请在证书列表下面新建。

![WSK_SDK_iOS](https://raw.githubusercontent.com/visionetwsk/Resource/master/image/cer0.png)

* 新建证书需要注意选择证书种类（开发证书用于开发和调试使用，生产证书用于 App Store 发布）

![WSK_SDK_iOS](https://raw.githubusercontent.com/visionetwsk/Resource/master/image/cer1.png)

* 点击 Continue 后选择证书对应的应用ID，然后继续会出现“About Creating a Certificate Signing Request (CSR)”。

![WSK_SDK_iOS](https://raw.githubusercontent.com/visionetwsk/Resource/master/image/cer2.png)

* 根据它的说明创建打开KeychainAccess 创建 Certificate Signing Request。

![WSK_SDK_iOS](https://raw.githubusercontent.com/visionetwsk/Resource/master/image/Screenshot_13-4-1_5_22.png)

* 填写“User Email Address”和“Common Name” 后选择 Saved to disk 进行保存 。

![WSK_SDK_iOS](https://raw.githubusercontent.com/visionetwsk/Resource/master/image/Snip20140122_7.png)

* 继续返回Apple developer 网站点击 Continue ，上传刚刚生成的 .certSigningRequest 文件生成 APNs Push Certificate。
* 下载并双击打开证书，证书打开时会启动“钥匙串访问”工具。
* 在“钥匙串访问”中你的证书会显示在“我的证书”中，注意选择“My Certificates” 和"login" 

![WSK_SDK_iOS](https://raw.githubusercontent.com/visionetwsk/Resource/master/image/keychain_cert.png)

## 导出 .p12 证书文件
> 注意要选“login”和“My Certificates” 导出证书时要选中证书文件，不要展开private key。

![WSK_SDK_iOS](https://raw.githubusercontent.com/visionetwsk/Resource/master/image/export_p12.png)

* 将文件保存为Personal Information Exchange (.p12)格式。

![WSK_SDK_iOS](https://raw.githubusercontent.com/visionetwsk/Resource/master/image/export_filename.png)

* 如果导出时设置了密码，则上传证书时需要填写密码。

![WSK_SDK_iOS](https://raw.githubusercontent.com/visionetwsk/Resource/master/image/pwd.png)


## 上传证书
在 微上客管理 Portal 上，针对某应用程序，上传上面步骤得到 .p12 证书文件。这是 iOS SDK 能够接收到 JPush 推送消息的必要步骤。
