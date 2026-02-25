# Chirpy Juncture Starter

This repository powers a Jekyll site built on the **[Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy)** theme, extended with a set of Juncture components for creating rich, interactive content.

At its core, this is a standard Chirpy-based site. If you are already familiar with Chirpy, most of the structure will look familiar. What makes this repository different is the addition of reusable viewer components and supporting scripts that allow content authors to build more visual, interactive essays without writing custom HTML or JavaScript.

---

## What This Repository Contains

### 1. The Chirpy Foundation

The site follows the normal Chirpy conventions for:

* Posts in `_posts`
* Configuration in `_config.yml`
* Data files in `_data`
* Static assets in `assets/`

If you are new to Chirpy, review:

* **[Getting Started](https://rsnyder.github.io/chirpy-juncture-starter/admin/getting-started)** 
* **[Writing a New Post](https://rsnyder.github.io/chirpy-juncture-starter/admin/write-a-new-post)** 
* **[Text and Typography](https://rsnyder.github.io/chirpy-juncture-starter/admin/text-and-typography)** 

Those documents describe the baseline structure and expectations for posts.

---

### 2. Juncture Extensions

On top of Chirpy, this repository adds:

* Single-page iframe viewer components (image viewer, map viewer, etc.)
* Liquid include wrappers that simplify usage
* Supporting JavaScript for:

  * DOM restructuring where needed
  * Communication between the parent page and iframe components
  * Action links that trigger component behavior

The design goal is separation of concerns:

* Content authors work in Markdown.
* Viewer logic lives in self-contained iframe pages.
* Liquid includes bridge the two.

Authors should not need to understand how the components are implemented — only how to invoke them.

---

## Who This Repository Is For

There are two primary audiences:

### Content Authors

You primarily need to:

* Create Markdown posts
* Use front matter correctly
* Insert Juncture components using documented include syntax

You do **not** need to modify theme files or JavaScript.

---

### Maintainers / Developers

If you are extending or modifying the Juncture components, you will be working with:

* Liquid include files
* Single-page viewer HTML/CSS/JS
* Parent/iframe messaging logic
* Site-wide configuration and layout files

Changes to these areas affect how all content renders.

---

Here’s a revised version of that section that clearly defines the two workflows without being overly verbose.

---

## Authoring Workflows

Juncture supports two primary authoring workflows:

* **Local Development Workflow** — best for users comfortable with Jekyll and Git.
* **Web-Based Workflow** — designed for non-technical authors using GitHub’s web editor and the Juncture Preview Tool.

Choose the approach that fits your level of comfort and setup.

---

### Option 1: Local Development (Full Jekyll Environment)

Recommended for users who want complete control and fast iteration.

1. Create a new post in `_posts`.

2. Add required front matter.

3. Write content in Markdown.

4. Insert Juncture components using documented include tags.

5. Preview locally with:

   ```bash
   bundle exec jekyll serve
   ```

6. Review at `http://127.0.0.1:4000`.

7. Commit and push changes to deploy.

**Advantages**

* Instant rebuilds
* Full theme rendering
* Works offline
* Ideal for advanced customization

---

### Option 2: Web-Based Workflow (GitHub + Juncture Preview Tool)

Designed for authors who prefer not to install Jekyll locally.

1. Navigate to your repository on GitHub.
2. Create or edit a post directly in the `_posts` directory.
3. Add required front matter.
4. Write content in Markdown.
5. Commit changes in GitHub.

Because GitHub Pages must rebuild the site after each commit, there is normally a delay before changes appear on the live site.

To avoid waiting:

6. While viewing the post in GitHub’s editor, click the **Juncture Preview bookmarklet** previously added to your browser.
7. The preview opens in a new tab and renders the post using the production theme.
8. Position the preview next to the editor.
9. After each commit, simply refresh the preview tab.

**Advantages**

* No local setup required
* Works from any device
* Suitable for non-technical contributors
* Avoids GitHub Pages rebuild delay during editing

---

### Which Should You Use?

* If you are modifying layouts, includes, or theme files → use **Local Development**.
* If you are primarily writing content → the **Web-Based Workflow** is usually sufficient.

Both workflows produce identical published results.

---

## Design Principles

This repository follows a few clear principles:

* **Keep posts readable.** Markdown should remain the primary authoring format.
* **Encapsulate complexity.** Interactive behavior lives in isolated components.
* **Favor reuse over duplication.** Liquid includes act as stable interfaces.
* **Minimize coupling to theme internals.** Juncture additions extend Chirpy rather than rewriting it.

---

## Admin Documentation

This repository includes an **Admin** section containing practical guides for maintaining the site and authoring posts.

The Admin area includes:

* Chirpy documentation adapted for this repository
* Juncture-specific authoring guides
* Workflow documentation (including the Preview tool)
* Maintenance and configuration references

You can access the Admin section directly from the site interface:

1. Look at the **left sidebar footer**.
2. Click the **README icon** ![README icon](assets/posts/juncture/readme-icon.png) icon in the left sidebar footer..
3. This opens the `/admin` section of the site.

The Admin area is intended for:

* Content authors who need step-by-step guidance
* Maintainers configuring the site
* Anyone learning how Juncture extends Chirpy

If you are new to the system, start there.

---

If you want it slightly tighter and more minimal (more in keeping with the current README tone), here’s a leaner version:

---

## Admin Section

The site includes an `/admin` section containing authoring and maintenance documentation, including both Chirpy basics and Juncture-specific guides.

Access it by clicking the **README icon** ![README icon](assets/posts/juncture/readme-icon.png) in the left sidebar footer.

Content authors should begin there before creating posts.

---

## Important Notes

* Some features depend on specific front matter variables.
* File paths must be accurate — most issues stem from incorrect paths.
* If action links are used, components may require an `id` attribute.
* The admin documentation section explains usage in detail.

---

## Summary

This is a Chirpy-based publishing platform with enhanced capabilities for interactive storytelling.

If you are writing content, focus on the documentation and examples.
If you are extending the system, treat the viewer components and include files as the primary integration layer.

The goal is straightforward: make it easy to create visually rich content without making authors learn the underlying implementation.
