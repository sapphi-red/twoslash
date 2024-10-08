# Syntax Highlighting with Twoslash

The core of Twoslash is relatively low-level and focusing on getting the type information for the given code snippet. It does not handles syntax highlighting nor how those information should be rendered.

To get the beautiful result you see on this website, you can use [Shiki](https://shiki.style/) - a powerful syntax highlighter using the same grammars and themes as VS Code.

It provides [`@shikijs/twoslash`](https://shiki.style/packages/twoslash) that integrates the type information into your code snippets.

```ts twoslash
import { transformerTwoslash } from '@shikijs/twoslash' // [!code hl]
import { codeToHtml } from 'shiki'

const html = await codeToHtml(`console.log()`, {
  lang: 'ts',
  theme: 'vitesse-dark',
  transformers: [
    transformerTwoslash(), // [!code hl]
  ],
})
```

If you are using [VitePress](https://vitepress.dev/), you can directly use [`@shikijs/vitepress-twoslash`](https://shiki.style/packages/vitepress) to get the same result as this website.
