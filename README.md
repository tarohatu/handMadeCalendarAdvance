# handMadeCalendarAdvance(CalculateCalendarLogic)
This library CalculateCalendarLogic (sample project name is handMadeCalendarAdvance) can judge a holiday in Japan.

### Notice

+ 2016/12/29:

This library is currently responding about CocoaPods / Cathage install. We can use this library with Manually. Copy all the files in CalculateCalendarLogic/CalculateCalendarLogic.swift file into your project. I'm sorry to trouble you.

### Description

This library 'CalculateCalendarLogic' can judge a holiday in Japan.
When you use this library, you can judge can judge a holiday in Japan very easily.
A method which named 'judgeJapaneseHoliday' method stores variables year, month, and day in an argument, it returns true or false.

### About CalculateCalendarLogic.swift

```swift
/* CalculateCalendarLogic.swift */

public func judgeJapaneseHoliday(year: Int, month: Int, day: Int) -> Bool {

    /**
     *
     * - Description judge japanese holiday
     * - parameter year: year value (Int)
     * - parameter month: month value (Int)
     * - parameter day: day value (Int)
     * - returns: result (Bool)
     */

     // judge holiday logic...
}
```

### Requirements

iOS8+

### Installation

We can use this library with Manually.

##### Manually

Copy all the files in CalculateCalendarLogic/CalculateCalendarLogic.swift file into your project.

### Author

fumiyasac(Fumiya Sakai)

### Example

It's as below.

```swift
/* ViewController.swift */

// Step1: create instance of CalculateCalendarLogic
let holiday = CalculateCalendarLogic()
...

// Step2: input year, month and day values into judgeJapaneseHoliday method.
let result: Bool = holiday.judgeJapaneseHoliday(year: 2016, month: 1, day: 1)

// Result:
print("2016 January 1：\(result)")

//You will display「2016 January 1：true」in your Xcode console.
```

### License

[MIT](https://github.com/fumiyasac/handMadeCalendarAdvance/blob/master/LICENSE)

### Contributor

Special Thanks to

+ [akio0911](https://github.com/akio0911): Technical Support & Refactoring
+ [akuraru](https://github.com/akuraru): Refactoring & Bugfix
+ [keygx](https://github.com/keygx): How to use CocoaPods

and more iOS developers.

# handMadeCalendarAdvance(CalculateCalendarLogic)
Swift版の日本の祝祭日判定コードとカレンダーライブラリとサンプル

![サンプル表示例](https://qiita-image-store.s3.amazonaws.com/0/17400/0d6ed6b2-6dc0-6a80-a2ea-4757bea94d4b.jpeg)

日本の祝祭日の判定ロジックとそのロジックを活用したカレンダーサンプルの例になります。
（※ 計算ロジックの実態部分はCalculateCalendarLogic.swiftを参照）

### アナウンス事項

+ 2016/12/29:

このライブラリに関してですが、CocoaPods / Cathageでのインストールに関しては現在対応中です。お手数ではありますが`CalculateCalendarLogic.swift`をご自身でお使いのプロジェクトに追加して対応を行って頂ければ幸いに思います。お手数をおかけしますが何卒宜しくお願い致します。

### 概要

日本の祝祭日(振替休日)を判定する構造体を作成しました。
使い方に関してはCalculateCalendarLogic.swiftをお使いのプロジェクトにコピーし、下記の「使い方」を参考に記述をして頂くとご利用になれます。
その他のカレンダーアプリを作成する際やお使いのアプリでご活用して頂ければ幸いです。

### このライブラリの内部仕様について

下記のようにjudgeJapaneseHolidayメソッドに年・月・日を引数として渡すことでその日が祝祭日(振替休日)であるかを判定します。
戻り値はBool型で返却して判定できるようにしています。

```swift
/* CalculateCalendarLogic.swift */

public func judgeJapaneseHoliday(year: Int, month: Int, day: Int) -> Bool {

    /**
     *
     * 祝日になる日を判定する
     * (引数) year: Int, month: Int, day: Int
     * weekdayIndexはWeekdayのenumに該当する値(0...6)が入る
     * 参考資料1. カレンダーロジックの参考                      ：http://p-ho.net/index.php?page=22
     * 参考資料2. 書き方（タプル）の参考                        ：http://blog.kitoko552.com/entry/2015/06/17/213553
     * 参考資料3. [Swift] 関数における引数/戻り値とタプルの関係 ：http://dev.classmethod.jp/smartphone/swift-function-tupsle/
     *
     */

     // 実装は実際のクラスを参照して頂ければ幸いです。
}
```

### 対応バージョン

IOS 8+

### 導入方法

手動でライブラリファイルを追加する方法で使用可能です。
`CalculateCalendarLogic.swift`ファイルをご自身のプロジェクトに追加して下さい。

導入例：[ライブラリを使わないカレンダーサンプル](https://github.com/fumiyasac/handMadeCalendarOfSwift)

※手動でプロジェクトに導入した際にはimport文が不要になります。

### プロジェクトでの実装例

下記のように判定したい年・月・日を引数にセットするだけでOKです。

```swift
/* ViewController.swift */

// Step1: CalculateCalendarLogicのインスタンスを作成
let holiday = CalculateCalendarLogic()
...

// Step2: 使用する際は引数を入れての判定を行う
let result: Bool = holiday.judgeJapaneseHoliday(year: 2016, month: 1, day: 1)

// 実行結果
print("2016年1月1日：\(result)")

//コンソールでは「2016年1月1日：true」と表示されます
```

本実装ではBool型での判定ではありますが、このメソッドをカスタマイズして戻り値を変更して「祝祭日の判定＆祝祭日名を返す」ようにする等の用途に応じてのカスタマイズも可能です。

### テストケース等その他

現行プログラムでCalculateCalendarLogic.swiftで考慮したテストケースは下記の通りです。

+ 今年(2016年)の祝祭日の判定が正しく行えていること
+ ゴールデンウィークの判定が正しく行えていること(※サンプル：2017年/2019年/2021年)
+ シルバーウィークの判定が正しく行えていること(※サンプル：2015年/2026年/2032年)
+ 春分の日・秋分の日の判定が正しく行えていること(※サンプル：2000年〜2030年)

テストケースに関しては今後追加予定です。

### ライセンス

[MIT](https://github.com/fumiyasac/handMadeCalendarAdvance/blob/master/LICENSE)

### 更新履歴

まだまだ甘い部分があるかもしれませんが、その際はPullRequest等を送っていただければ幸いです。アプリ開発の中でこのサンプルが少しでもお役にたつ事ができれば嬉しい限りです。

+ 2016.12.29: Swift3系への対応を行いました（CocoaPods & Cathageへの対応はこれから行います。すみません）
+ 2016.10.13: Swift2.3及びSwift3.0ブランチ作成
+ 2016.09.03: CocoaPodsへの対応をしました（ドキュメント修正や追記含む）
+ 2016.05.28: READMEに追記をしました（Carthageで導入する際の手順や文章の修正等）
+ 2016.05.09: カレンダーに実装した例を掲載しました（UICollectionViewを使用）
+ 2016.05.01: CalculateCalendarLogic.swiftの実装と祝祭日判定テストケースを追加

### 謝辞

このライブラリの作成にあたり[akio0911](https://github.com/akio0911)さん、[akuraru](https://github.com/akuraru)さん、[keygx](https://github.com/keygx)さんに多くのお力添えを頂きまして誠にありがとうございました。
