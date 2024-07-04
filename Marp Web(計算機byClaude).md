---
marp: true
theme: default
---

# Java簡易計算機プログラム解説

---

## プログラムの概要

- 名前: SimpleCalculator.java
- 機能: 基本的な四則演算を行う計算機
- 入力: 2つの数値と1つの演算子
- 出力: 計算結果

---

## ポイント

1.google colabでjavaを使うためのマジックコード
2. Scanner クラス
3. main メソッド
4. 変数宣言
5. ユーザー入力の取得
6. switch 文による演算処理
7. 結果の出力

---

## Google colaboratoryでJavaを使うマジックコード
google colaboratoryは元々Pythonを使うことを前提にしているサービスなので、Javaを使う際には専用のコードを入れる必要がある

%%writefile SimpleCalculator.java

---

## Scanner クラス

import java.util.Scanner;
Scanner scanner = new Scanner(System.in);

ユーザーからの入力を受け取るために使用
System.in: 標準入力からデータを読み込む

---

## 変数宣言
javaCopydouble num1, num2, result;
char operator;

num1, num2: 計算に使用する2つの数値
result: 計算結果
operator: 演算子 (+, -, *, /)

---

## ユーザー入力の取得
javaCopynum1 = scanner.nextDouble();
operator = scanner.next().charAt(0);
num2 = scanner.nextDouble();

nextDouble(): double型の値を読み取る
next().charAt(0): 入力された文字列の最初の文字を取得

---

## switch文による演算処理
javaCopyswitch(operator) {
    case '+':
        result = num1 + num2;
        break;
    case '-':
        result = num1 - num2;
        break;
    // ... 他の演算子も同様
}

入力された演算子に応じて適切な計算を実行

---

## エラー処理
javaCopycase '/':
    if(num2 != 0) {
        result = num1 / num2;
    } else {
        System.out.println("エラー: 0で除算はできません");
        return;
    }
    break;

0による除算を防ぐためのエラーチェック

---

## プログラムの拡張性

より複雑な数学関数の実装、そのほかの機能(暗号機、複合機など)
ユーザーインターフェースの改善の余地あり(かなりシンプルなので
、今後改善していくならこちらか)
