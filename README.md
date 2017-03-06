# yii2-payment
payment system

1. composer require weijianghu/yii2-qrcode: "*"

2. migration 恢复数据结构

3. add modules like this
```
        'payment' => [
            'class' => 'yii\payment\Module',
        ],
```
4. add components like this 
```
        'qrcode' => [
            'class' => 'yii\qrcode\Manager',
        ],
        'payment' => [
            'class' => 'yii\payment\Manager',
            'modes' => [
                'wxpay'=>[
                    'disabled'=>false,
                    'qrcodeRoute' => '',//二维码展示页
                    'appid' =>'',
                    'secret' =>'',
                    'key' => '',
                    'mch_id' => ''
                ],
                'alipay'=>[
                    'disabled'=>false,
                    'partner' => '',
                    'key' => ''
                ]
            ]
        ],
```
##说明

1. 本库已经添加微信二维码扫描支付模式二
2. 使用主要是用Manager.php文件，此文件是支付的入口
3. apis里面是各支付的sdk
4. controllers是各个支付同步和异步回调