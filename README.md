# 💩🌪️ Shitstorm

A small [Poops](https://github.com/stamat/poops/) template for static sites with JS + SCSS bundling and Markdown-based page generation.

## Scaffold a new project

```bash
npm create poops@latest my-app
```

This uses [`create-poops`](https://github.com/stamat/create-poops) to pull the latest template. Pick a flavor as the second argument (default `base`):

| Template    | Ships with                                |
| ----------- | ----------------------------------------- |
| `base`      | this repo — clean poops starter           |
| `sulphuris` | + sulphuris CSS framework, book-of-spells |
| `hat`       | + htmx, Alpine.js, Tailwind               |

```bash
npm create poops my-app base
```

Or clone this repo directly without `create-poops`:

```bash
npx degit stamat/shitstorm my-app
```

## Out-of-the-box stack

| Layer         | Included                                                  |
| ------------- | --------------------------------------------------------- |
| Runtime       | Node.js + npm                                             |
| Build tool    | `poops` (`npm run dev`, `npm run build`)                  |
| Scripts       | ES modules from `src/scripts/script.js`                   |
| Styles        | SCSS entry points in `src/styles/`                        |
| Markup        | Markdown content + layout templating in `src/markup/`     |
| Data          | YAML data files (example: `src/markup/_data/fonts.yaml`)  |
| Static assets | Copied from `src/static` to `dist`                        |
| Dev UX        | Local server on port `4040` + live reload                 |
| Lint          | ESLint (JS) + Stylelint (SCSS)                            |
| Tests         | Jest (`npm test`)                                         |
| CI            | GitHub Actions — lint + test on push/PR, deploy on `main` |
| Output        | Built site in `dist/` with minified assets + source maps  |

## Project structure

```text
src/
  markup/     # pages, layouts, data
  scripts/    # JavaScript entry points
  styles/     # SCSS entry point
  static/     # copied as-is to dist
dist/         # generated output
poops.json    # build + serve config
```

## Quick start

```bash
npm install
npm run dev
```

Build for production:

```bash
npm run build
```

## Checks

```bash
npm run lint   # ESLint (JS) + Stylelint (SCSS)
npm test       # Jest — builds and asserts dist/ output
```

CI runs both on every push and pull request ([`.github/workflows/ci.yml`](.github/workflows/ci.yml)); pushes to `main` also deploy to GitHub Pages ([`.github/workflows/pages.yml`](.github/workflows/pages.yml)).
