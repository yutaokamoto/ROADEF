# ROADEF
## 概要
[Challenge ROADEF/EURO 2020](https://www.roadef.org/challenge/2020/en/index.php)というコンテストに参加したときの記録です。

一度こちらにコードを上げていたのですが、手違いでリポジトリがコードもろとも消えてしまいました。

## ディレクトリ構成

    - Outputs : 与えられた問題例に対してその解を示したテキストファイルです。
    - ROADEF_Challenge_2020_J38_Abstract.pdf : アルゴリズムの概要をまとめたものです。
    - ROADEF_Challenge_2020_J38_Result_Table.pdf : 計算実験の結果をまとめた表です。
    - exec.out : 実行可能ファイルです。

## 解いた問題について
* [RTE](https://en.wikipedia.org/wiki/R%C3%A9seau_de_Transport_d%27%C3%89lectricit%C3%A9#:~:text=R%C3%A9seau%20de%20Transport%20d'%C3%89lectricit%C3%A9%20(Electricity%20Transmission%20Network)%2C,transmission%20system%20operator%20of%20France.&text=RTE%20is%20a%20wholly%20owned,EDF\)%2C%20headquartered%20in%20Paris.)というフランスの送電線網における、送電線の修理・点検を行うためのスケジュールを構築するという問題です。

* 具体的には、与えられたいくつかの送電線の修理・点検の仕事に対して、その開始時刻をコストや安全性を評価軸に決定していきます。修理・点検は送電線そのものではなく、それらが集まった**グリッド**と呼ばれる場所を行うそうです。

* スケジュールは**期間**と呼ばれるものに分割できます。例えば、期間数T=365だったら1日=1期間となります。

* スケジュールを構築する際、以下の3つの制約を満たすように気を付けなけれななりません

        1. スケジュールに関する制約 : 仕事はある期間の始まりとともに開始し、ある期間の終わりとともに終了する。全ての仕事はちょうど1回だけ行われるという制約です。
        2. 使用できる資源に関する制約 : 期間のうち使用できる資源の最大量と、使用しなければならない最低量が決められているという制約です。
        3. グリッドに関する制約 : あるグリッドを修理・点検している時に、他の一部のグリッドの修理・点検ができないという制約です。

問題の詳細につきましては、[こちら](https://github.com/rte-france/challenge-roadef-2020/blob/master/Challenge_Subject.pdf)からご覧になれます。

## 考案したアルゴリズムについて
* 考案したのは、ヒューリスティクスと呼ばれる近似解法を用いた方法です。

* 大きく2つのステップから成り立っています。

        1. 全ての制約条件を満たすようなスケジュールを構築する。
        2. 1.のスケジュールを改善する。

* アルゴリズムの詳細につきましては、[こちらのpdfファイル](https://github.com/yutaokamoto/ROADEF/blob/main/ROADEF_Challenge_2020_J38_Abstract.pdf)にまとめてあります。(これだけ別の場所にバックアップをとっていたので無事でした。)
