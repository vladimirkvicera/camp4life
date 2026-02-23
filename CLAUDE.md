# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Camp4Life is a Czech-language static travel blog about RV/campervan trips across France, built with Eleventy (11ty).

## Commands

```bash
npm run build   # Generate static site to _site/
npm run serve   # Start dev server with hot reload
```

No test or lint commands are configured.

## Architecture

**Static site generator**: Eleventy v3.1.1 with Nunjucks as the primary templating engine.

**Build flow**: Source HTML/Markdown files with YAML front matter → Nunjucks processes templates → static output in `_site/`.

**Layout system**: All pages use `_includes/sablona-header-footer.njk` as the master layout via front matter:
```yaml
---
layout: sablona-header-footer.njk
title: Page Title
---
```

**Asset handling** (`.eleventy.js`): `images/` and `css/` are passthrough-copied to `_site/` without processing.

**Template formats**: `njk`, `html`, `md`, `liquid`.

## Content Structure

- `index.html` — Homepage with trip cards (tile grid)
- `roadtrips/roadtrip2021.html` — Detailed trip itinerary with GPS coordinates and copy-to-clipboard buttons
- `CestovaniVeFrancii.html` — Practical travel guide (tolls, parking, camping tips)
- `napisnam.html` — Contact/contribution form (submits to submit-form.com)

Unpublished trips use the CSS class `tile--coming-soon`.

## Design System

**CSS variables** (in `css/style.css`):
- Primary: `rgb(69, 26, 98)` (deep purple)
- Secondary: `rgb(113, 55, 150)` (light purple)
- Dark: `rgb(27, 11, 38)`
- Light: `#F0E5DE` (cream)
- Accent: `rgb(138, 180, 178)` (turquoise)

**Fonts**: "Indie Flower" (headings, cursive), "Quicksand" (body) — loaded from Google Fonts CDN. Icons via Font Awesome 6 CDN.

**Layout**: Max-width 1200px container, flexbox, responsive breakpoint at 768px.

## Language

All site content is in Czech. Comments in `.eleventy.js` are also in Czech.
