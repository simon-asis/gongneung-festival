# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

Static single-page website for the 2026 공능교회 어린이 축제 (Gongneung Church Children's Festival). No build system, no dependencies — everything is in one `index.html` file with inline CSS and JS.

## Development

Open `index.html` directly in a browser, or serve it locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Architecture

All code lives in `index.html`:

- **CSS** (`<style>` block): CSS custom properties (`--red`, `--orange`, etc.) define the color palette. Responsive breakpoint at `max-width: 600px`.
- **HTML sections** (in order): `.hero` → `.programs-section` → `.video-section` → `.map-section` → `.worship-section` → `footer`
- **JS** (`<script>` block at bottom): star particle generator, slideshow logic (`goSlide`/`changeSlide`), and IntersectionObserver for scroll animations on `.program-card` and `.worship-card`.

Images are in `img/` (booth, food, kidroom, air bounce photos).

## Known placeholders

- **Slideshow**: The `.video-section` slideshow uses CSS gradient placeholder slides. The actual festival photos in `img/` are not yet wired up — replace `.slide` backgrounds with `<img>` tags pointing to `img/`.
- **YouTube embed**: There is a commented guide inside `.video-section` for replacing `VIDEO_ID` with a real YouTube video ID in an `<iframe>`.
- **Map**: Uses a hand-drawn inline SVG. The destination is 공능교회 제1 주차장 (서울특별시 노원구 동일로186길 27), 도보 5분 from 공릉역 2번출구 (Seoul Metro Line 7).
