# Bash

## 設定

```bash
#!/bin/bash

# -e : エラー発生時、処理を終了する（ステータスコードが0以外）
# -u : 未定義の変数が参照された場合、終了する
# -o pipefail : パイプでつながれたコマンドのいずれかでエラー発生時、その終了コードが返される
set -eu
set -o pipefail
```

## 変数

変数は `declare` または `local` コマンドで宣言する。
関数内で宣言する場合、localを使用する。

```bash
# 宣言しない場合と同様に扱える
declare variable="value"

# 配列
declare -a array
array=(
  "value1"
  "value2"
)

# すべて出力
echo ${array[@]}
# > value1 value2

# 指定して出力
echo ${array[0]}
# > value1

# インデックス出力
echo ${!array[@]}
# > 0 1

# 連想配列
declare -A hash
hash=(
  [key1]="value1"
  [key2]="value2"
)

# すべて出力
echo "${hash[@]}"
# > value2 value1

# キーで出力
echo "${hash[key1]}"
# value1

# 数値
declare -i num=1

# すべて小文字に変換 (lower case)
declare -l str="aBCD"

# すべて大文字に変換 (upper case)
declare -u str="Abcd"
```

## 条件分岐

## ループ
