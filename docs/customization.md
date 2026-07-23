# Customization Guide

How to personalize this GitHub profile for your own use.

---

## Quick Start

1. Fork the repository or create a new one named `{your-username}/{your-username}`
2. Replace `ramm8469` with your GitHub username throughout
3. Update links to your own portfolio, LinkedIn, and social profiles
4. Replace the featured projects section with your own work
5. Commit and push — GitHub will render `README.md` on your profile automatically

---

## File Map

```
.
├── README.md              # Main profile (everything renders from here)
├── assets/
│   ├── banner.svg         # Hero banner at the top of the README
│   ├── architecture.svg   # Platform architecture diagram
│   └── icons/             # Custom icons (optional)
├── snippets/
│   ├── projects.md        # Featured projects section
│   ├── socials.md         # Social link badges
│   ├── tech.md            # Tech stack grouped by category
│   └── widgets.md         # GitHub stats widgets
├── .github/workflows/
│   ├── blog.yml           # Auto-fetches latest blog posts
│   ├── activity.yml       # Auto-updates recent GitHub activity
│   └── metrics.yml        # Generates metrics SVG
└── docs/
    └── customization.md   # This guide
```

---

## Customizing SVGs

### banner.svg

Edit the text elements to change:
- Name (line with "Ram Mohan Kunwar")
- Title (line with "Technical Lead • Platform Engineer • Backend Architect")
- Subtitle tags (Cloud Native, Distributed Systems, etc.)
- Footer quote

Colors use CSS variables or hex values — change `#58a6ff` (blue) and `#8b5cf6` (purple) to match your palette.

### architecture.svg

This diagram shows your platform's architecture layers. Modify:
- Layer labels (PRESENTATION, APPLICATION, INFRASTRUCTURE, DATA)
- Component names and descriptions within each layer
- Connection lines between components
- Add or remove components as needed

---

## Typing Animation

The README uses [readme-typing-svg](https://github.com/denvercoder1/readme-typing-svg) for the animated text rotation. Edit the `lines` parameter in the URL to customize the rotating titles:

```
https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=22&duration=3000&pause=1000&color=58A6FF&center=true&vCenter=true&width=600&lines=Technical+Lead;Platform+Engineer;Backend+Engineer;Distributed+Systems;Cloud+Native;AI+Infrastructure;Open+Source
```

Replace with your own titles separated by `;` (URL-encoded as `%3B`).

---

## GitHub Actions

### Blog Posts (`blog.yml`)

1. Update `feed_list` to point to your blog's RSS/Atom feed
2. The workflow runs daily at 6 AM UTC
3. Posts appear between `<!-- BLOG-POST-LIST:START -->` and `<!-- BLOG-POST-LIST:END -->` markers

### Activity (`activity.yml`)

1. No configuration needed — uses your GitHub token automatically
2. Shows 10 most recent public GitHub events
3. Updates daily at 6 AM UTC

### Metrics (`metrics.yml`)

1. Generate a personal access token with `read:user` scope
2. Add it as `METRICS_TOKEN` in your repository secrets
3. The workflow generates `metrics.svg` — reference it in your README as needed

To enable workflows, go to your repository **Settings → Actions → General** and ensure actions are allowed.

---

## Snippets

Snippets are optional modular files. You can include them in your README via URL references or copy-paste their contents. They exist to keep the main README clean and organized.

---

## Color Reference

| Element       | Hex       | Usage                     |
|---------------|-----------|---------------------------|
| Background    | `#0d1117` | Dark background           |
| Surface       | `#161b22` | Card/section backgrounds  |
| Border        | `#30363d` | Dividers and borders      |
| Blue accent   | `#58a6ff` | Primary accent            |
| Purple accent | `#8b5cf6` | Secondary accent          |
| Text primary  | `#f0f6fc` | Headings and emphasis     |
| Text secondary| `#8b949e` | Body text                 |
| Text muted    | `#484f58` | Metadata and footnotes    |

---

## Tips

- Keep the README under 200 lines for fast rendering
- Use SVG badges sparingly — grouped sections look cleaner than badge walls
- Test on both GitHub dark and light themes
- Avoid tracking scripts, visitor counters, or heavy external dependencies
- Update project cards when you ship something new
