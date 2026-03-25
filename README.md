# 🎬 私の部屋が映画になったら？

> お部屋の写真1枚で十分です。
> AIがあなたのお部屋を映画にします。

おうちでゴロゴロしてる時、ふと思ったことありませんか？

*「この部屋が映画の舞台だったら…タイトルは何だろう？」*

そのくだらないけど大切な疑問、私たちが解決します。 🍿

<br>

## 📋 こんなものを作ります

お部屋の写真をアップロードすると、AIが分析して**映画チケット**を発券します。

| 項目 | 説明 |
|------|------|
| 🎞️ 映画タイトル | お部屋の雰囲気にぴったりな余韻のあるタイトル |
| 🏷️ ジャンル | ロマンス / ミステリー / ヒーリング など |
| 🎭 VIBE | お部屋から感じるキーワード3つ |
| 🧑 CAST | この部屋に住む主人公の性格と描写 |
| 🎥 KEY SCENES | この映画の名シーン3つ |
| 🛋️ おすすめアイテム | 映画の雰囲気を完成させるOhouseアイテム |

> チケット画像の保存もできます。お友達に自慢しちゃいましょう。

<br>

## 🧐 どうやって動いてるの？

```
┌─────────────────────────────────────────┐
│                                         │
│  📸 お部屋の写真をアップロード              │
│       ↓                                 │
│  🤖 AIが写真を分析 (Groq API)             │
│       ↓                                 │
│  🎬 映画チケット生成                       │
│       ↓                                 │
│  💾 画像として保存 (任意)                   │
│                                         │
└─────────────────────────────────────────┘
```

- **フロントエンド**: 純粋なHTML/CSS/JS単一ファイル (フレームワークなし、軽いです)
- **AI**: Groq API + Llama 4 Scout (ビジョンモデル、画像分析可能)
- **サーバーレス**: Vercel Serverless Functions (APIキー保護用)
- **画像キャプチャ**: dom-to-image-more → SVG → Canvas 3xレンダリング

<br>

## 🚀 自分で動かしたい方へ

### 1. クローン

```bash
git clone https://github.com/yui-Ohouse/ohouse-movie-jp.git
cd ohouse-movie-jp
```

### 2. Groq APIキーの発行

[Groq Console](https://console.groq.com)で無料で発行できます。

### 3. Vercelでデプロイ

```bash
npm i -g vercel
vercel link
vercel env add GROQ_API_KEY    # 発行したキーを入力
vercel --prod
```

> ローカルでテストするなら `vercel dev` で実行できます。

<br>

## 🗂️ プロジェクト構造

```
ohouse-movie-jp/
├── index.html          # 全部ここにあります (HTML + CSS + JS)
├── api/
│   └── analyze.js      # Vercelサーバーレス関数 (Groq APIプロキシ)
└── .gitignore
```

はい、ファイル3つです。シンプルが一番。

<br>

## 🌏 多言語バージョン

| バージョン | リポジトリ | サイト |
|------|------|--------|
| 🇰🇷 韓国語 | [ohouse-movie](https://github.com/yui-Ohouse/ohouse-movie) | [ohouse-movie.vercel.app](https://ohouse-movie.vercel.app) |
| 🇯🇵 日本語 | [ohouse-movie-jp](https://github.com/yui-Ohouse/ohouse-movie-jp) | [ohouse-movie-jp.vercel.app](https://ohouse-movie-jp.vercel.app) |

<br>

---

*作った人: Ohouse QA Team*
*「テストだけするにはもったいない腕前なので…」* 🎬
