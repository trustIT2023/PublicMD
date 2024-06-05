# マークダウンからHTMLへの変換作業

```css
handleScroll(e) {
    return e.target.offset.top / e.target.innerHeight;
}

shouldScroll(percentage) {
    var target = React.findDOMNode(this.refs.previewer);
    target.scrollTop = target.innerHeight * percentage;
}
```


## 結論

> [!IMPORTANT]  
> **PandocというOSSのソフトを利用する**

## Pandoc

### 環境構築

- [Pandocのインストール](https://docs.zettlr.com/ja/installing-pandoc/)

### マニュアル

- [PandocUsersGuide日本語版](https://pandoc-doc-ja.readthedocs.io/ja/latest/users-guide.html)

### マークダウンからHTMLにCSSを指定して変換する方法

- [pandocでMarkdown形式をHTML/CSSに一発変換(https://qiita.com/fk_2000/items/d9ba2984349728bb5609)
  - pandoc -c style.css input.md -o output.html



### その他変換候補



### コマンド

pandoc ./1_Doc/11_Mdn/401_DevPolicy.md -s --embed-resources --standalone -t html5 -c ./3_Dat/41_Mdn/MkdnTrust.css -o ./3_Dat/42_MdToHtml/401_DevPolicyV6.html



pandoc 401_DevPolicy.md -s --embed-resources --standalone  -t html5 -c MkdnTrust.css -o 401_DevPolicyV5.html



pandoc 401_DevPolicy.md -s --embed-resources --standalone  --metadata title="401_DevPolicy" -t html5 -c MkdnTrust.css -o 401_DevPolicyV5.html



pandoc ./1_Doc/11_Mdn/401_DevPolicy.md -s --embed-resources --standalone  --metadata title="401_DevPolicy" -t html5 -c ./1_Doc/11_Mdn/MkdnTrust.css -o ./3_Dat/42_MdToHtml/401_DevPolicyV5.html

pandoc ./1_Doc/11_Mdn/401_DevPolicy.md -s --embed-resources --standalone  --metadata title="401_DevPolicy" -t html5 -c ./3_Dat/41_Mdn/MkdnTrust.css -o ./3_Dat/42_MdToHtml/401_DevPolicyV6.html


pandoc ./1_Doc/11_Mdn/414_一般_コーディングルール_クリーン_01_introduction.md -s --embed-resources --standalone  --metadata title="401_DevPolicy" -t html5 -c ./3_Dat/41_Mdn/MkdnTrust.css -o ./3_Dat/42_MdToHtml/414_一般_コーディングルール_クリーン_01_introductionV1.html





#### 参考コマンド

pandoc -o 401_DevPolicy.html 401_DevPolicy.md
pandoc -s -o 401_DevPolicyV2.html 401_DevPolicy.md
pandoc -c MkdnTrust.css MkdnTrust.css 401_DevPolicy.md -o 401_DevPolicyV4.html


pandoc -s -o --data-dir="C:\aIT\1_Doc\11_Mdn" 401_DevPolicyV3.html 401_DevPolicy.md


