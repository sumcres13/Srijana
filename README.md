# Indian Asian Kitchen Srijana

A static Japanese/English website for four Tokyo restaurants: Srijana Mejiro, Srijana Nakamurabashi, Srijana Oizumi-gakuen, and Real Shakujii-kōen.

- `index.html` — Restaurant introduction and all four locations
- `about.html` — A message from Representative Director Bijay Bhandari
- `access.html` — Branch photo galleries, addresses, hours, phone numbers, and directions
- `reservation.html` — Four restaurant cards with booking and delivery links

Open `index.html` in a browser, or serve this folder with `python3 -m http.server 8000`. There is no build step. To deploy to static hosting, upload the entire folder, including `assets/` and `vendor/`. Keep the relative file paths intact.

Japanese is the default language. Edit the text in each HTML page and its corresponding key in the `english` dictionary in `script.js` together. The local BudouX parser handles Japanese phrase-aware wrapping. Its license is in `vendor/BUDOUX-LICENSE.txt`.

The site sends visitors to restaurant listings and delivery providers. Their availability depends on the provider and, for delivery, the visitor’s address.

## Import and hosting

This repository contains the complete editable website, including every local image, logo, illustration, stylesheet, script, and the BudouX license. No source files have been bundled, minified, flattened, or recompressed for this export.

- Import the repository's `main` branch into Manus or another static hosting service.
- Keep the repository root as the website root, with `index.html` as the entry page.
- No dependency installation, build command, environment variables, or backend are required.
- Publish all four HTML files together with `styles.css`, `script.js`, `assets/`, and `vendor/`.
- Preserve filenames and folder structure; page links and assets use relative paths.
- For a local HTTP preview, run `python3 -m http.server 8000` from this folder and open `http://localhost:8000`.

The language selector works in place, updates internal page links, and remembers the selected language. Japanese and English pages can also be opened with `?lang=ja` and `?lang=en`. Google Fonts is the only external styling dependency; Japanese system-font fallbacks are defined in the stylesheet.

## Verify the exact files

`SHA256SUMS` records every exported file except the checksum manifest itself. Git is configured by `.gitattributes` to preserve file bytes without line-ending conversion.

On macOS, verify a downloaded or cloned copy with:

```sh
shasum -a 256 -c SHA256SUMS
```

On Linux, use `sha256sum -c SHA256SUMS` instead. All entries should report `OK`.

## Restaurant data and photographs

The website includes four restaurants. See `STORE_INFORMATION.md` for the source listings and the date on which new branch details were checked.

The six supplied Oizumi-gakuen and Real photographs are stored as lossless WebP images. Their decoded RGB pixels were checked against the supplied PNG files and matched exactly; they were not resized or retouched. Existing images are retained unchanged.

Booking links open the relevant third-party listings. Delivery links use the supplied store IDs; preset customer delivery addresses and tracking parameters have been removed. Availability is determined by each provider.
