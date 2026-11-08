# bot-backup-info

Static homepage and privacy notice for **Bot Backup**, a personal desktop application maintained by Tiange Ye. He uses rclone on a schedule to copy his own non-secret bot configuration and work state to his own Google Drive.

This repository is the public description of that utility. It is not the backup program. It does not contain OAuth client credentials, tokens, rclone configuration, or backup files. The pages do not sign anyone in and do not collect Google Drive data.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | Homepage |
| `privacy.html` | Privacy notice (the privacy policy for Bot Backup) |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are, without Jekyll |

Links between the pages are relative (`./index.html`, `./privacy.html`). They stay inside the project path `/bot-backup-info/` when the site is opened with that path's trailing slash. There is no build step and no dependency file.

`.nojekyll` is included because this is plain HTML. With it, Pages does not run Jekyll, so the files are published unchanged.

## Enable GitHub Pages

Pages is not turned on by merging a pull request. After these files are on the default branch (`main`):

1. Open the repository on GitHub and go to **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Choose branch **main** and folder **/ (root)**.
4. Save.

No GitHub Actions workflow is required for that source, and this repository does not add one.

Wait until **Settings → Pages** shows a published site URL and the deployment finishes. Confirm the pages load in a browser before using them. A deployment from the `main` root of `tiangeye/bot-backup-info` is expected to publish:

- Homepage: https://tiangeye.github.io/bot-backup-info/
- Privacy notice: https://tiangeye.github.io/bot-backup-info/privacy.html

Those addresses are the expected project-site URLs. They are not live until Pages is enabled and the deployment succeeds.

Open the homepage with the trailing slash (`/bot-backup-info/`). GitHub Pages redirects the path without a slash to that address. The privacy link on the homepage and the privacy policy URL on the Google OAuth consent screen should be the same `privacy.html` address.

Google's OAuth branding rules ask for the homepage and privacy policy to be hosted on a domain you verify that you own, and they warn against some third-party hosts. `github.io` is GitHub's domain. This repository only adds the requested GitHub Pages files. It does not register a domain and it does not change Google Cloud or GitHub Pages settings.

## Local check

From a parent directory that contains this repository as `bot-backup-info`:

```bash
python3 -m http.server 8765
```

Then open:

- http://127.0.0.1:8765/bot-backup-info/
- http://127.0.0.1:8765/bot-backup-info/privacy.html

Follow **Privacy notice** and **Home**. Both should stay under `/bot-backup-info/`.
