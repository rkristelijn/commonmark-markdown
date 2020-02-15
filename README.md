# commonmark-markdown

## Goals of this repo

Just some test what commonmark markdown can do for me. TLDR; not much. Mermaid is not supported by GFM

## Background

The problem with Markdown (`*.md`-files) is the lack of standardization on the most ambiguous details of the language. There are different implementations that do have some documentation (Github-Flavored-Markdown, Sundown, CommonMark, ...)

I'm also working with CommonMark on [Gitlab Community edition](https://about.gitlab.com/) that is [easily installed](https://hub.docker.com/r/gitlab/gitlab-ce/) using this docker image:

```docker
docker pull gitlab/gitlab-ce
```

Today I decided to play around with CommonMark at Github, specifically for technical documentation. Commonmark supports mermaid inline diagramming so this will help me a lot in writing efficient technical documentation in e.g. README.md files.

Here are some articles where I draw my information from:

- [Github is now using CommonMark](https://talk.commonmark.org/t/github-is-now-using-commonmark-and-a-modified-version-of-cmark/2365)
- [2017 blog of Github Flavored Markdown](https://github.blog/2017-03-14-a-formal-spec-for-github-markdown/)
- [Official specification of Github Flavored Markdown](https://github.github.com/gfm/)
- [sourcecode of Github's version of CommonMark](https://github.com/github/cmark-gfm)
- [Limited list of examples](https://guides.github.com/features/mastering-markdown/)

## Examples

A limited list of examples is already written [here](https://guides.github.com/features/mastering-markdown/) that include:

- Headers
- Emphasis: bold, strikethrough, italic
- Lists
- Images
- Links
- Blockquotes
- Inline code
- Syntax highlighting
- Hyperlinks
- Task lists
- Tables
- SHA references
- links with issues on github
- username @mentions
- emoji

But what about...

- Code hightling in depth
- Hyperlink tricks
- Table of contents
- Warnings
- Diagrams
- Possibilities of tables
- List of Emojis
- raw HTML

## Extended Examples

### Diagrams

- [Diagrams in Github Readme discussion](https://gist.github.com/rodneyrehm/40e7946c0cff68a31cea)

### Diagrams using [Mermaid](https://mermaid-js.github.io/mermaid/#/)

```mermaid
graph TD;
  A-->B;
  A-->C;
  B-->D;
  C-->D;
  click B "http://gius.nl" "This is a link"
```

> [Mermaid](https://mermaid-js.github.io/mermaid/#/) doesn't work. @see closed [feature request issue#533](https://github.com/github/markup/issues/533)

### Diagrams using yUML

```yuml
// {type:class}
// {direction:topDown}
// {generate:true}

[note: You can stick notes on diagrams too!{bg:cornsilk}]
[Customer]<>1-orders 0..*>[Order]
[Order]++*-*>[LineItem]
[Order]-1>[DeliveryMethod]
[Order]*-*>[Product|EAN_Code|promo_price()]
[Category]<->[Product]
[DeliveryMethod]^[National]
[DeliveryMethod]^[International]
```

### Diagrams using PlantUML

```puml
```

### Diagrams using Google

Abusing the image tag:

`![](https://chart.googleapis.com/chart?cht=gv&chl=graph{C_0--H_0[type=s];C_0--H_1[type=s];C_0--H_2[type=s];C_0--C_1[type=s];C_1--H_3[type=s];C_1--H_4[type=s];C_1--H_5[type=s]})`

Will generate:

![](https://chart.googleapis.com/chart?cht=gv&chl=graph{C_0--H_0[type=s];C_0--H_1[type=s];C_0--H_2[type=s];C_0--C_1[type=s];C_1--H_3[type=s];C_1--H_4[type=s];C_1--H_5[type=s]})

# Other mentions

| item | description |
|---|---|
| [stackedit.io](stackedit.io) | online markdown editor that supports scores, formula's, mermaid and more |
| [bramp.github.io](https://bramp.github.io/js-sequence-diagrams/) | online sequence diagrams to svg |
| [http://flowchart.js.org/](http://flowchart.js.org/) | online flowchart > you should use activity diagrams |
| [yUML suntax in VSC](https://github.com/jaime-olivares/yuml-diagram/wiki) | yUML for VSC, not supported by gitlab nor github |
