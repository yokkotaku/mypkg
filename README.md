# mypkg
[![test](https://github.com/yokkotaku/mypkg/actions/workflows/test.yml/badge.svg)](https://github.com/yokkotaku/mypkg/actions/workflows/test.yml)
* これはROS2のパッケージなので、事前にROS2をインストールする必要がある。

## talker
数字をカウントし、topic(countup)を通じてメッセージを送信する。

## listener
topic(countup)から送信されたメッセージを受信し、表示する。

## talk_listen.launch
talkerとlistenerを同時に立ち上げることができる。

## 使用方法・実行結果
* talker&listener  
端末１側
```
$ ros2 run mypkg talker
```
端末２側
```
$ ros2 run mypkg listener
```
結果  
端末２に表示される（端末１には何も表示されない）
```
$ [INFO] [1704016475.666206381] [listener]: Listen: 3
  [INFO] [1704016476.139536989] [listener]: Listen: 4
  [INFO] [1704016476.639527996] [listener]: Listen: 5
  [INFO] [1704016477.139660670] [listener]: Listen: 6
  ...
```
* talk_listen.launch
```
$ ros2 launch mypkg talk_listen.launch.py
```
結果
```
[INFO] [launch]: All log files can be found below /home/yoko/.ros/log/2023-12-31-18-59-56-137883-LAPTOP-2SB8J40D-11820
[INFO] [launch]: Default logging verbosity is set to INFO
[INFO] [talker-1]: process started with pid [11821]
[INFO] [listener-2]: process started with pid [11823]
[listener-2] [INFO] [1704016797.009003038] [listener]: Listen: 0
[listener-2] [INFO] [1704016797.487084882] [listener]: Listen: 1
[listener-2] [INFO] [1704016797.986928826] [listener]: Listen: 2
[listener-2] [INFO] [1704016798.486939190] [listener]: Listen: 3
[listener-2] [INFO] [1704016798.986871085] [listener]: Listen: 4
[listener-2] [INFO] [1704016799.487219499] [listener]: Listen: 5
...
```

## 必要なソフトウェア
* Python
  * テスト済み: 3.7〜3.10
* ROS2
  * バージョン humble

## テスト環境
* Ubuntu22.04

## 著作権・ライセンス
* このソフトウェアパッケージは、3か条項BSDライセンスの下、再頒布および使用が許可されます。
* このパッケージのコードは、下記のスライド（CC-BY-SA 4.0 by Ryuichi Ueda）のものを，本人の許可を得て自身の著作としたものです。
	* [ryuichiueda/my_slides robosys_2022](https://github.com/ryuichiueda/my_slides/tree/master/robosys_2022)
* © 2023 Takumi Yokoo
