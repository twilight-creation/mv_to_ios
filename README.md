# mv_to_ios


## 概要
* RPGツクールMV/RPGツクールMZで作成されたプロジェクトをiOSアプリ化するためのXcode プロジェクトです。
* プラグインは不要、RPGツクールMV(MZ)でデプロイメントしたファイルを所定の場所に配置するだけです。
* iOS側でWKWebViewを表示し、RPGツクールMV(MZ)で出力されたhtml/javascriptを読み込みます。
* ローカル(`file://`)で実行される `XMLHttpRequest`等のCORSを回避するために、[WKURLSchemeHandler](https://developer.apple.com/documentation/webkit/wkurlschemehandler)を使用しています。



## 必要なもの

* [RPGツクールMV](https://tkool.jp/mv/)(または、[RPGツクールMZ](https://tkool.jp/mz/))
* [Xcode](https://apps.apple.com/jp/app/xcode/id497799835?mt=12)
* [CocoaPods](https://guides.cocoapods.org/using/getting-started)
* iOS13以上



## 動作確認

- RPGツクールMV
  - Xcode 11.5
  - RPGツクールMV 1.6.2
  - iOS 13.5.1
- RPGツクールMZ
  - Xcode 11.6
  - RPGツクールMZ 1.0.1
  - iOS 13.5.1
  - CocoaPods 1.10.1


## 使い方

1. githubよりCloneもしくは[zipをダウンロード](https://github.com/waffs702/mv_to_ios/archive/master.zip)します。
    - 広告機能などが無いバージョンもあります。こちらから[zipをダウンロード](https://github.com/waffs702/mv_to_ios/archive/vanilla.zip)できます。

2. ダウンロードした場合は、zipを解凍します。

3. RPGツクールMVプロジェクトをAndroid/iOS用にデプロイメントします。

    ![ss1](https://raw.githubusercontent.com/wiki/waffs702/mv_to_ios/images/ss1.jpg)

    - RPGツクールMZの場合は、ウェブブラウザでデプロイメントします。

    ![ss5](https://raw.githubusercontent.com/wiki/waffs702/mv_to_ios/images/ss5.jpg)

4. デプロイメントされたwwwフォルダ配下のファイルを、mv_to_iosの`htmlSource`フォルダ配下に配置します。

    ![ss2](https://raw.githubusercontent.com/wiki/waffs702/mv_to_ios/images/ss2.jpg)

5. ターミナルを起動して、mv_to_iosのフォルダまで移動します。その後、`CocoaPods`のインストールコマンドを実行します。

    - この手順は、広告機能などが無いバージョンでは不要です。
    ```
    $ cd /mv_to_ios  # mv_to_iosのフォルダまで移動、パスは適宜置き換えてください
    $ pod install
    ```

6. Xcodeを起動します。

7. mv_to_iosのXocdeプロジェクトを開く時は、`mv_to_ios.xcworkspace`(白いアイコン)を選択します。広告機能などが無いバージョンでは`mv_to_ios.xcodeproj`(青いアイコン)を選択します。

8. Xcodeの画面上部メニューから、`Product` > `Build`をクリックしてビルドを実行します。

9. 左側ツリーから、`mv_to_ios` をクリック、TARGETSの`mv_to_ios` をクリック、`Signing & Capabilities` をクリック、TeamがNoneとなっているので適切なDeveloper Accountを選択します。（Apple Developer Programへの登録が必要です。/iOSシミュレータで実行する場合はこの操作は不要です。）

    ![ss3](https://raw.githubusercontent.com/wiki/waffs702/mv_to_ios/images/ss3.jpg)

10. PCにiOS端末を接続し、`再生ボタン`アイコンをクリックすると、iOSにアプリがインストールされデバッグモードで起動します。

    ![ss4](https://raw.githubusercontent.com/wiki/waffs702/mv_to_ios/images/ss4.jpg)


## 今後追加予定の機能

- バナー広告
- push通知(Firebase)
- アプリ内課金
- Twitter画面スクリーンショットシェア



## License
MIT