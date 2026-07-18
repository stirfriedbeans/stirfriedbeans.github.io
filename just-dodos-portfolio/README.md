# just dodos — artist circle portfolio

Static single-page site. No build step. Deploys to Cloudflare Pages / GitHub Pages as-is.

## Structure
```
index.html      ← the whole site (HTML + CSS + JS inline)
images/         ← all artwork, merch, and profile icons
README.md
```

## Adding your real images
Drop files into `images/` using these exact names:

**Profile icons**
- `lillie-icon.png`, `tauge-icon.png`, `henley-icon.png`

**Galleries** (up to 18 each, 6 to start)
- `lillie-art1.png … lillie-art6.png`  /  `lillie-merch1.png …`
- `tauge-art1.png …`  /  `tauge-merch1.png …`
- `henley-art1.png …`  /  `henley-merch1.png …`

Any grid slot whose image is missing just shows an empty placeholder — safe to leave gaps.
To add MORE than 6, open `index.html`, find the `ARTISTS` block near the top of `<script>`,
and add filenames to the `artwork:` / `merch:` arrays (max 18).

## Adding social links
In `index.html`, in the same `ARTISTS` block, replace the `"#"` values with real URLs.
Each artist's `socials` is clearly commented. Supported: instagram, twitter, website.

## Deploy (Cloudflare Pages)
1. Push this folder to a GitHub repo.
2. Cloudflare Pages → Create project → connect the repo.
3. Framework preset: **None**. Build command: *(leave blank)*. Output dir: `/`.
4. Deploy. Every push auto-redeploys.

## Tips for fast loading
- Export images as **WebP** (or compressed PNG/JPG) before adding — big raw files are the main slowdown.
- Keep them roughly ≤1600px on the long edge; the lightbox doesn't need more.
- Lazy-loading is already on, so off-screen images won't load until scrolled to.
