# Copilot Instructions for quachrich.github.io

## Project Overview
This is a personal portfolio website for Richard Quach, a health science student and data science researcher. It's a **static HTML/CSS website** deployed via GitHub Pages that showcases projects, publications, experience, and educational background with a focus on public health, AI safety, and biosecurity.

## Architecture & Key Patterns

### File Structure
- **index.html** (315 lines): Single-page application with semantic HTML sections (hero, projects, publications, experience, education, contact)
- **style.css** (572 lines): Comprehensive styling with CSS custom properties (variables) for theming and spacing
- **files/**: Contains Resume.pdf and papers (paper1-4.pdf)
- **images/**: Project thumbnails and profile image

### Design System
Uses CSS custom properties extensively (defined in `:root`):
- **Colors**: `--primary-color: #2563eb`, `--text-dark`, `--text-light`, `--bg-light`
- **Spacing scale**: `--spacing-xs` through `--spacing-2xl` for consistent layouts
- **Responsive breakpoint**: 768px media query for mobile optimization

### Layout Patterns
1. **Navigation**: Sticky header + sticky secondary menu bar (offset z-indices: header `z-index: 100`, menu `z-index: 99`)
2. **Cards**: Consistent grid-based cards for projects, publications, and experience items with hover animations (box-shadow lift, `transform: translateY(-2px)`)
3. **Sections**: Alternating background colors (`section:nth-child(even)` uses `--bg-light`)
4. **Flexbox spacing**: Sections use `gap` instead of margins to avoid collapsing margins (modern layout best practice)

## Common Tasks

### Adding New Content
- **New project**: Add `<div class="project-card">` inside appropriate `.project-category` with structure: image, title, description, tech stack, link
- **New publication**: Follow `.publication-item` structure with pub-header (title + badge), journal name, description, and pub-links
- **New experience entry**: Add `.experience-item` with exp-header (role + company + date) and description paragraph

### Styling Considerations
- Always use CSS variables from `:root` for colors/spacing—avoid hardcoded values
- New components should use flexbox/grid with `gap` instead of margin-bottom for spacing
- Hover states typically include: color transition (0.2s), box-shadow lift, and `transform: translateY(-2px)`
- Responsive design: Reorder grid columns to `1fr` at 768px breakpoint; adjust font sizes and padding for mobile

### Modifying Navigation/Menu
- Navigation appears in two places: `<nav>` (sticky top, z-index 100) and `.menu-bar` (sticky below nav, z-index 99)
- Menu bar links are anchor references to section IDs (`id="home"`, `id="projects"`, etc.)

## Data & External References
- Resume link: `files/resume.pdf`
- Publications: `files/paper1-4.pdf` referenced in HTML
- Images: All stored in `images/` directory with descriptive names (e.g., `project-epistorm.png`)
- External links: LinkedIn, GitHub, Email use standard `<a>` tags with target="_blank" for external URLs

## Deployment & Build
This is a **static site**—no build process required. Changes to HTML/CSS are immediately live when pushed to GitHub Pages. The repo is configured as a GitHub Pages site serving from the root directory.

## Conventions to Follow
1. **Semantic HTML**: Use section elements with meaningful IDs for anchor navigation
2. **Accessibility**: Images include alt text; links have clear labels
3. **Class naming**: BEM-inspired (`.project-card`, `.category-title`, `.pub-badge`)
4. **Color consistency**: In-process projects use `--warning-color` to distinguish status
5. **Font family**: Inter (from Google Fonts) with fallback system fonts

## Quick Reference: CSS Variable Keys
- Colors: `primary`, `text-dark`, `text-light`, `bg-light`, `border-color`, `white`, `hover-color`, `success-color`, `warning-color`
- Spacing: `xs` (0.5rem), `sm` (1rem), `md` (1.5rem), `lg` (2rem), `xl` (3rem), `2xl` (4rem)
