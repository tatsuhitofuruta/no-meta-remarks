# no-meta-remarks

AIが生成する文書、資料、スライド、UIモックから、プロンプトや修正過程の残留物、不要な断り書き、内容の水増しを除くAgent Skillです。成果物だけを読んだ人が、制作時の会話を知らなくても自然に理解できる状態へ整えます。

## 直す内容

- 「指示により変更しました」など、制作過程を説明する記述
- 読者レベルやスコープ指定を転記したラベル・断り書き
- 汎用トラブルシューティング、頼まれていない将来案、過剰な見出しや装飾
- 修正を重ねたことで生じた語調、用語、前提、見出しの不統一

事実、技術的な正しさ、必要な要件、固有名詞、数値、指定書式は保ちます。忠実な翻訳、コードレビュー、短い会話応答には使用しません。13種の検査項目と残す条件は [SKILL.md](SKILL.md) にあります。

## 使い方

Codexは、依頼内容がSkillのdescriptionと一致すると暗黙に選択できます。明示的に使う場合は、プロンプトで `$no-meta-remarks` を指定します。

```text
$no-meta-remarks を使って、この設計書から会話由来の説明と不要な断り書きを除いてください。
```

「検査して」と依頼した場合は指摘だけを返し、「修正して」「仕上げて」と依頼した場合は成果物を編集します。

## インストール

Codexのユーザースコープへ導入します。

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/tatsuhitofuruta/no-meta-remarks.git ~/.agents/skills/no-meta-remarks
```

Claude Codeへ導入する場合は、配置先を変更します。

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/tatsuhitofuruta/no-meta-remarks.git ~/.claude/skills/no-meta-remarks
```

Codexは追加されたSkillを自動検出します。Skill一覧に現れない場合はCodexを再起動します。

## License

[MIT](LICENSE)
