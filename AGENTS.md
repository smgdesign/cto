# AGENTS.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview
This is a simple marketing website for SMG Digital (Fractional CTO services) built with Alpine.js loaded via CDN. The project has no build process, bundler, or package dependencies.

## Development Commands

### Running the Development Server
```bash
npm run dev
```
This starts a Python HTTP server on port 8000 (binds to 0.0.0.0). Access at `http://localhost:8000`.

Alternative:
```bash
npm run serve
```

### Opening the Site
You can also open `index.html` directly in a browser without running a server.

## Project Structure

- `index.html` - Single-page HTML file with all content
- `css/style.css` - All styling (custom fonts, responsive design, layout)
- `fonts/` - Custom fonts (Rosellia cursive, TT Bluescreens)
- `img/` - Images used throughout the site (PNGs for photos, arrows, etc.)
- `js/` - Empty directory (no custom JavaScript; Alpine.js loaded from CDN)
- `prep/` - Design reference JPGs showing artboards/mockups

## Architecture Notes

### Styling Approach
- Uses **custom CSS only** (no Tailwind or CSS frameworks)
- Responsive design with `clamp()` for fluid typography and sizing
- Custom `@font-face` declarations for brand fonts
- SVG curves for visual transitions between sections
- Grayscale filters applied to images for consistent aesthetic

### Alpine.js Usage
- Alpine.js 3.x loaded via CDN (`https://unpkg.com/alpinejs@3.x.x/dist/cdn.min.js`)
- Currently no Alpine.js components or reactivity implemented in HTML (imported but not actively used)
- If adding Alpine.js functionality, use inline directives (x-data, x-show, etc.)

### Layout Structure
The single-page site consists of sequential sections:
1. Hero section with overlaid "Hello" text and image
2. "On Demand Experts" section with curved transition
3. "Signs that you need a Fractional CTO" section with numbered reasons
4. Continued reasons section with two-column layout

### Color Palette
- Primary red: `#f45b69`
- Purple accent: `#a09be7`
- Yellow: `#f3c677`
- Blue: `#4b88a2`
- Dark text: `#3d3a4b`
- Background: `#fefcfa`

## Making Changes

When editing this project:
- All content changes go in `index.html`
- All style changes go in `css/style.css`
- No build step required - changes are immediately reflected
- Test responsiveness at mobile (480px), tablet (768px), and desktop breakpoints
- Images in `img/` are grayscale-filtered via CSS (`filter: grayscale(100%)`)
