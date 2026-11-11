# ElectroHub - four-page GitHub Pages website

## Files
- `index.html`: Home
- `products.html`: Six products with category filters
- `about.html`: Brand story
- `contact.html`: Demonstration contact and newsletter forms
- `style.css`: Responsive styling
- `script.js`: Menu, filters, demo forms, GA4 events
- `images/`: Optional local image directory (current images load from Unsplash)

## Deploy to GitHub Pages
1. Create/sign in to a GitHub account at https://github.com.
2. Create a **public** repository. For the exact URL `https://testwebsite.github.io/`, the GitHub username must be `testwebsite` and the repository must be named `testwebsite.github.io`. If your username differs, use a repository such as `my-website`, resulting in `https://YOUR-USERNAME.github.io/my-website/`.
3. Upload the **contents** of this folder to the repository root (not a nested `my-website` folder), including all six web files.
4. Commit the files, then go to **Settings > Pages > Build and deployment**.
5. Choose **Deploy from a branch**, branch **main**, folder **/(root)**, then Save.
6. Wait for publication, open the published URL, and test all four navigation links.

## Google Analytics 4
1. Open https://analytics.google.com and go to Admin > Create > Property; set name, time zone and currency.
2. Create a Web data stream for your published GitHub Pages URL.
3. Copy the Measurement ID shown in the stream details (`G-XXXXXXXXXX`).
4. In **each of the four HTML files**, replace both occurrences of `G-XXXXXXXXXX` with your real ID. The Google tag is already inside each `<head>`.
5. Commit the updated files and wait for Pages to republish.
6. Visit the site (with analytics consent as appropriate), navigate between pages and inspect **Reports > Realtime** in GA4. For detailed testing use **Admin > DebugView** with debug mode enabled via Tag Assistant or browser debug setup.

## Tracked events
- `page_view`: GA4 automatic page views when navigating the four HTML pages (with default enhanced measurement).
- `select_item`: Product View Details button, with an `items` array containing item_id, item_name, item_category, price and currency.
- `demo_form_submit`: Successful client-side validation of contact or newsletter demo forms, with `form_type` of `contact` or `newsletter`.

No `generate_lead` or `sign_up` event is emitted because no backend or subscription provider is configured. Do not enter sensitive personal information in demonstration forms. Events do not include form field values.

## Testing checklist
- [ ] All four pages open from the published URL
- [ ] Navigation and mobile menu work
- [ ] Product category filters and buttons work
- [ ] External images load (internet required)
- [ ] Mobile, tablet and desktop layouts are readable
- [ ] Invalid form entries are rejected; valid demo entries show a demo confirmation
- [ ] GA4 Measurement ID is installed on all four pages
- [ ] Page visits appear in GA4 Realtime (allow for processing and blockers)
- [ ] `select_item` and `demo_form_submit` appear during event testing

Note: The Google tag is initially configured with a placeholder and cannot send valid GA4 events until replaced. Image availability depends on the third-party image host.
