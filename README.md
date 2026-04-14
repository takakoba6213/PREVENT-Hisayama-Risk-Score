# 🫀 ASCVDリスク計算機（PREVENT + 久山町スコア）

日本人向けに最適化した **動脈硬化性心血管疾患（ASCVD）リスク評価ツール**です。
米国AHA 2026年脂質異常症ガイドラインの **PREVENT** 計算式と、日本人コホートに基づく **久山町スコア** を並列評価でき、**患者説明リーフレット（NNT/NNH可視化）** まで1つのページで完結します。

---

<!-- ↓↓↓ ここが「ワンクリック起動ボタン」です ↓↓↓ -->

<p align="center">
  <a href="https://YOUR_USERNAME.github.io/REPO_NAME/">
    <img src="https://img.shields.io/badge/▶️%20計算機を開く-LAUNCH-1a5490?style=for-the-badge&logo=heart&logoColor=white" alt="計算機を開く" />
  </a>
</p>

<p align="center">
  <a href="https://YOUR_USERNAME.github.io/REPO_NAME/">
    <img src="https://img.shields.io/badge/_ブラウザで即起動-GitHub%20Pages-success?style=for-the-badge" />
  </a>
  <a href="./index.html">
    <img src="https://img.shields.io/badge/ローカルHTMLを開く-📄-gray?style=for-the-badge" />
  </a>
</p>

<!-- ↑↑↑ リンクの `YOUR_USERNAME` と `REPO_NAME` を自分のものに置き換えてください -->

---

## 🎯 このツールでできること

| タブ | 機能 |
| --- | --- |
| 🧮 **PREVENT計算機** | 2026年ACC/AHAガイドライン準拠の10年 ASCVD / 総CVD / 心不全リスクを計算 |
| 🗾 **久山町スコア** | 日本人コホート（Honda et al. 2022）の簡易ポイント制スコア。原著表と±0.3%以内で一致 |
| 📘 **ガイドライン解説** | 2018→2026年版の主要変更点、COR推奨、閾値変更の根拠 |
| 🎯 **リスク閾値と治療方針** | 低/境界/中等度/高リスク別の推奨、スタチン強度分類（日本用量対応） |
| 🌏 **アジア人・日本人注意点** | ロスバスタチン感受性、BMI基準、JSH2019、JAS 2022など日本固有の考慮事項 |
| ✅ **使い方と検証** | サンプル症例、AHA公式計算機との比較手順 |
| 📝 **患者説明リーフレット** | 10年リスクからNNT/NNHを自動計算。100人アイコングリッドで視覚化、印刷対応 |

---

## 🚀 GitHub Pages で公開する手順

このページをブラウザで即座に開けるようにするための3ステップです。

### 1. リポジトリを作成

GitHub上で新規リポジトリ（例: `ascvd-calc-jp`）を作成し、以下のファイルを追加:

```
├── index.html      ← 計算機本体（これをルートに置く）
└── README.md       ← このファイル
```

ローカルで実施する場合:

```bash
git init
git add index.html README.md
git commit -m "初回コミット: ASCVDリスク計算機"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git
git push -u origin main
```

### 2. GitHub Pages を有効化

1. リポジトリのページで **Settings** → **Pages** を開く
2. **Source** を `Deploy from a branch` に設定
3. **Branch** を `main` / `(root)` に設定して **Save**
4. 数分後、`https://takakoba6213.github.io/PREVENT-Hisayama-Risk-Score/` で公開されます

### 3. README のリンクを自分のURLに書き換え

このREADMEの冒頭の `YOUR_USERNAME` と `REPO_NAME` を、あなたのGitHubユーザー名とリポジトリ名に置き換えてください。
これで README の **▶️ 計算機を開く** ボタンから直接ツールが起動します。

---

## 📖 エビデンスと出典

| スコア / 推奨 | 文献 |
| --- | --- |
| PREVENT方程式 | Khan SS, Matsushita K, Sang Y, et al. *Circulation*. 2024;149:430–449. |
| 2026年ガイドライン | Blumenthal RS et al. *Circulation*. 2026;153:e00–e00. |
| 久山町スコア | Honda T, Chen S, Hata J, et al. *J Atheroscler Thromb*. 2022;29:345–361. |
| NNT根拠（RRR） | Cholesterol Treatment Trialists. *Lancet*. 2012;380:581–590. |
| 新規糖尿病NNH | Sattar N et al. *Lancet*. 2010;375:735. |
| 筋症状ノセボ | SAMSON trial. *NEJM*. 2020. |
| 日本人エビデンス | MEGA study (Nakamura H, *Lancet* 2006), JELIS (Yokoyama M, *Lancet* 2007) |
| 国内ガイドライン | 動脈硬化性疾患予防ガイドライン2022年版（日本動脈硬化学会） |

---

## ⚠️ ご利用上の注意

- 本ツールは**教育・診療補助目的**の参考実装です。臨床判断の最終確認は必ず担当医および [AHA公式PREVENT計算機](https://professional.heart.org/en/guidelines-and-statements/prevent-calculator) で行ってください。
- PREVENT式の係数は Khan SS et al. Circulation 2024 の公表値に基づく**参考実装**です。数値に軽微な誤差の可能性があるため、サンプル症例タブで公式計算機との整合性を確認してから運用してください。
- 二次予防、家族性高コレステロール血症、透析、LDL-C ≥190 mg/dL などは PREVENT の適用対象外です。
- 本ツールは個人情報を一切サーバに送信しません（すべてブラウザ内で完結する静的HTML）。

---

## 🛠️ カスタマイズ

`index.html` は外部依存なしの単一ファイルです。CSS・JavaScriptもすべてインラインで、約87KB。
テキスト・色・係数は HTML 内で直接編集できます。

- リスク閾値の調整 → `<script>` 内の判定ロジック
- スタチンRRRの調整 → リーフレット生成関数 `lf-gen-btn` のハンドラ内
- 久山町スコアの式 → `hisayamaRisk()` 関数

---

## 📄 ライセンス

本ツールは教育・臨床支援目的で自由にご利用いただけます。
使用による診療結果への責任は各医療従事者に帰属します。
