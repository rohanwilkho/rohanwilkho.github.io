# rohanwilkho.github.io — academic site of Rohan Singh Wilkho

Single-page faculty-style site. Pure static HTML + CSS, no JavaScript build step
(only a small inline script for the light/dark theme toggle).
Light is the default theme; dark is available via the header toggle.
Typography: IBM Plex Sans throughout. Single institutional-blue accent (`#2451A4`).
Machine-readable throughout: llms.txt, JSON-LD, Highwire citation meta tags,
BibTeX/JSON publication exports, AI-welcoming robots.txt.

## File tree

```
├── index.html            The site: About, Research, Publications, Funding,
│                          Teaching, Speaking, Milestones, Collaboration
├── 404.html              Not-found page
├── styles.css            Single stylesheet (sticky header, light + dark theme)
├── llms.txt              Concise Markdown summary for AI agents
├── llms-full.txt         Full site content as Markdown
├── robots.txt            Welcomes AI crawlers; points to sitemap
├── sitemap.xml
├── publications.bib      BibTeX for the complete publication record
├── publications.json     Same data as JSON
└── assets/
    ├── favicon.svg            "W" monogram, institutional blue
    ├── portrait.jpg           Photo used on the site
    ├── portrait_original.jpg  Unedited backup of the portrait — keep, not linked from any page
    └── Wilkho_RohanSingh_CV.pdf
```

The header is sticky; nav items scroll to sections on the same page. The CV item
downloads `assets/Wilkho_RohanSingh_CV.pdf` directly.

## Deploy to GitHub Pages

1. Create a repository named exactly `<username>.github.io`.
2. Copy every file in this folder into the repository root.
3. ```
   git init
   git add .
   git commit -m "Launch academic site"
   git branch -M main
   git remote add origin https://github.com/<username>/<username>.github.io.git
   git push -u origin main
   ```
4. Settings → Pages → deploy from branch `main`, folder `/ (root)`.

## Before launch — placeholders (search for TODO)

| Placeholder | Replace with |
|---|---|
| `doi = {TODO}` in `publications.bib` / `publications.json` | remaining real DOIs (the 4 published papers in Selected Publications already have theirs; several older/non-curated entries still say TODO) |
| `TODO_FLOODFINDER_URL`, `https://github.com/TODO_GITHUB` | if the Systems & code section is ever restored — it isn't currently part of the live page |
| `rohanwilkho.github.io` | your actual GitHub Pages domain, if different |

Phone number deliberately omitted from the public site; email only.

## Fonts

IBM Plex Sans loads from Google Fonts (one family, several weights, used for both
headings and body) — the only external dependency. To self-host: download the
weights used as woff2 into `assets/fonts/` and replace the `<link>` tag with
`@font-face` rules. System fallbacks are already in place.

## Cache-busting

`styles.css` is linked with a `?v=` query string (currently `v=3`). Bump that
number any time you edit `styles.css` so visitors don't get served a stale
cached copy after a deploy.

## Keeping it current

- New paper: add to Selected Publications in `index.html` (keep the list short —
  swap out, don't pile on), plus `publications.bib`, `publications.json`, `llms-full.txt`.
- Update `sitemap.xml` `<lastmod>` when the page changes.
