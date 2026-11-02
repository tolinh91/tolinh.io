# Linh Thi To Tran — academic portfolio

A static, responsive homepage built with semantic HTML and CSS. No package manager, build step, JavaScript, third-party fonts, or backend is required.

## Preview

From this directory:

```bash
python3 -m http.server 8000 --bind 127.0.0.1
```

Open http://localhost:8000. Stop with Ctrl+C. This server is only for local preview.

## Edit content

All public content is in `index.html`. The profile is in `<aside class="profile">`. Sections use the IDs `about`, `education`, `experience`, `projects`, `skills`, `awards`, and `credentials`. Edit the corresponding HTML directly; keep heading levels and navigation links consistent. Projects use individual `<article>` elements under industrial and personal group headings.

News, publications, and teaching are omitted because no content was supplied. To add publications, insert a section like the following inside `main`, then add a navigation link to `#publications`. Duplicate the article for each verified entry, replacing every illustrative field before publication:

```html
<section id="publications" aria-labelledby="publications-heading">
  <h2 id="publications-heading">Publications</h2>
  <article>
    <h3>Confirmed paper title</h3>
    <p>Authors in their published order</p>
    <p class="meta">Venue · Year · Publication status</p>
  </article>
</section>
```

Add descriptive paper/code links only when real URLs are supplied. Bold Linh's name only after confirming author identity. An optional local thumbnail should have meaningful alt text, explicit width and height, and `loading="lazy"`. For news, create a `news` section with dated entries using `<time datetime="YYYY-MM-DD">`; add its navigation link only once there are confirmed announcements.

## Portrait, CV, and styling

The profile uses the supplied `assets/images/portrait.jpg`, with descriptive alt text and a circular crop sized for desktop and mobile. Replace that file to update the portrait, or change the relative image path in `index.html`. Adjust `.avatar` and its `object-position` in the CSS to change the crop. Add the actual, public-safe CV PDF to `assets/files/`, then add a descriptive profile link such as `<a href="./assets/files/linh-tran-cv.pdf">Download CV (PDF)</a>`. No CV link is displayed until the file is supplied.

The four personal project titles link to the supplied GitHub repositories. Document Retrieval using GraphRAG replaces Clinic Management Platform. Its description is intentionally limited to the supplied project topic.

Colors, typography, page width, column gap, and section spacing are CSS variables at the top of `assets/css/styles.css`. The mobile layout begins at 800px. The favicon is an original LT SVG. No reference-site code or assets were reused.

The title and description are in the HTML head. Once the public destination is confirmed, add an absolute canonical URL and matching `og:url`, `og:title`, and `og:description` metadata. Add `og:image` only when an actual public preview image exists. Update the copyright year when appropriate.

## Publish on GitHub Pages

The repository is [tolinh91/tolinh.io](https://github.com/tolinh91/tolinh.io), with source on `main`. The existing initial commit and license are preserved. The local guide, TODO, and source DOCX are excluded by `.gitignore`.

GitHub Pages deployment has not been verified. This is a project repository, so its default Pages address, once enabled, is `https://tolinh91.github.io/tolinh.io/`. All asset references are relative to support this path.

In GitHub repository **Settings → Pages**, select **Deploy from a branch**, branch **main**, folder **/(root)**, and save. Keep `index.html` and `.nojekyll` at the root. Check the deployment result and visit the URL GitHub reports. Verify assets, email, anchors, and mobile layout on the live site.

For subsequent edits, preview and review changes, then:

```bash
git add index.html assets README.md
git diff --cached
git commit -m "Update portfolio content"
git push
```

These instructions follow [GitHub's site creation documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site) and [publishing-source documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

## Verification and remaining work

Local structural and HTTP checks are recorded below. Content follows the supplied build guide; résumé facts were not independently verified. Missing optional content and factual confirmations are tracked in local `CONTENT_TODO.md`.

The reference homepage's content hierarchy was inspected through the web reader. Exact visual matching was not verified. No browser automation or browser executable was available, so screenshots, rendered viewport checks (1440px, 768px, 375px), actual keyboard interaction, browser console/network checks, and 200% browser zoom still require manual verification. Open the local preview and check for overflow, readable text, visible keyboard focus, skip-link behavior, and correct anchor positioning at each width. Main content is static HTML and does not rely on JavaScript.

Completed checks: Python HTML parsing confirmed 15 unique IDs, 11 valid anchors/local asset/email references, one primary heading, logical heading levels, all seven required sections, eight project articles, and no script dependency. Local HTTP requests returned 200 for the homepage, CSS, SVG favicon, and `.nojekyll`; HTML/CSS/SVG MIME types were checked. These checks do not replace the manual browser checks above.

Certificate and scholarship images are linked thumbnails in `#credentials` and `#awards`; clicking opens the original image. Image paths containing spaces are URL-encoded. `.certificate-photo` controls preview sizing without cropping. Contact icons are inline SVG with visible link labels. The TOPIK Level 5 photo uses `assets/images/topik5.jpg`. “AI in Project Management” uses the AWS image per the requested mapping.
