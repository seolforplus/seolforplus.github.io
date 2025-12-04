# AI Coding Agent Instructions for seolforplus.github.io

## Project Overview
This is a **GitHub Pages portfolio website** (static HTML + CSS) for Ivor Mosquera. It's a web development learning project showcasing research and academic work. No build process, no backend, no JavaScript logic—purely semantic HTML with CSS styling.

## Architecture Patterns

### Page Structure
- **Landing page** (`index.html`): Main entry point with header, navigation, contact info, and footer
- **Project pages** (`project7.html`, `exam.html`, `nwd.html`, `quiz7.html`, `quiz8.html`): Individual research/assignment pages
- **Navigation pages** (`menu.html`): Content organization pages with table of contents sidebars

**Pattern**: Each page is self-contained with:
```html
<header>   <!-- Logo and title -->
<main/article>  <!-- Primary content -->
<aside>    <!-- Supplementary content, TOC, or sidebar -->
<footer>   <!-- Copyright and links -->
```

### CSS Strategy (Multiple Stylesheets)
- `main.css`: Global styling for `index.html` (1000px fixed width, header with image float, decorative borders)
- `exam.css`: Two-column layout with nav bar, left article (75%), right sidebar
- `project7.css`, `quiz7.css`, `nwd.css`: Specialized layouts for individual pages
- **Style pattern**: Consistent use of `box-shadow: 3px 3px 4px 4px red`, `border-radius: 20px`, gradient backgrounds
- **Color scheme**: Orangered (#FF6347) for primary text, dark red (#800000) for headings, navy borders

**Important**: Each HTML file references its own CSS file via relative path:
```html
<link rel="stylesheet" href="styles/main.css">  <!-- index.html -->
<link rel="stylesheet" href="/styles/exam.css"> <!-- exam.html (absolute path) -->
```
Mix of relative and absolute paths—be consistent with the pattern used in each file.

### Asset Management
- `images/`: Contains `.webp` and `.svg` files (Sage.svg icon, NasaObs.webp background)
- `files/`: Contains downloadable resources (classlab.docx)
- Background images are **fixed attachment** (`background-attachment: fixed`) for parallax effect

## Development Conventions

### Semantic HTML
- Use `<article>` for main content, `<aside>` for sidebars/supplementary content
- Use `<nav>` for navigation menus with semantic `<ul>` lists
- Use `<header>` and `<footer>` for page sections
- ID anchors for table of contents linking (e.g., `id="introduction"`, `id="method"`)

### CSS Patterns to Preserve
- **Text shadows**: `.shadow` class applies `text-shadow: 2px 2px 2px rgb(128, 0, 0)`
- **Decorative borders**: Use `border-style: double`, `dashed`, or `dotted` with `border-radius`
- **Box shadows**: Consistent `box-shadow: 3px 3px 4px 4px red` across content sections
- **Responsive meta tag**: All pages include `<meta name="viewport" content="width=device-width, initial-scale=1.0">`

### Navigation Links
- Internal links use fragment identifiers: `<a href="#introduction">Introduction</a>`
- Home link: Always `href="index.html"` for consistency
- External links open in new tab: `target="_blank"` (see index.html LinkedIn/Google examples)

## Workflow & Maintenance

### When Adding New Pages
1. Create new `.html` file in root directory
2. Use the semantic structure template (header → main/article → aside → footer)
3. Create corresponding `.css` file in `styles/` directory with page-specific styling
4. Link CSS via `<link rel="stylesheet" href="styles/[pagename].css">`
5. Add navigation entry in relevant navigation menus

### When Modifying Styling
- Edit the **page-specific** CSS file, not `main.css` (unless it's a global change)
- Preserve existing decorative patterns (borders, shadows, text effects)
- Test color consistency with existing palette (orangered, dark red, navy)

### Asset Guidelines
- Use `.webp` format for images when possible (better compression)
- Place images in `images/` directory with descriptive filenames
- Use `alt` text for all images (accessibility)
- Background images should use `background-attachment: fixed` for consistency

## Cross-Component Communication
No backend or API calls. All communication is:
- **Navigation**: HTML anchor links and file references
- **Content linking**: Relative paths for local resources, absolute URLs for external sites
- **Downloads**: Files in `files/` directory linked via `<a>` tags

## Key Files Reference
- `index.html` + `styles/main.css`: Main landing page pattern
- `exam.html` + `styles/exam.css`: Two-column layout template
- `project7.html`: Standalone project showcase example
- `menu.html`: Content organization with TOC sidebar pattern
