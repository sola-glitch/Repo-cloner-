# Repo-cloner-
GitHub repo downloader, zipper and copier with a live timeline. Web page and Termux script.

# Repo Cloner

Download, zip, or copy a GitHub repository and watch every step on a live timeline. It runs as a clean, minimal web page on your phone and as a Python script for Termux.

## Features

- **Three ways to take a repo:** download files as a zip, grab GitHub's quick zip, or copy a repo into your own account.
- **Choose exactly what you want:** one branch, several, or all, and only the files you need, by ticking them from a list or typing patterns such as `src/**/*.py`.
- **Live timeline:** stages with timings, plus progress bars for the current file and overall.
- **Public and private repos** using an optional GitHub token.
- **Full history in Termux:** the script can clone or copy with every commit, branch, and tag.
- **Built-in tutorials:** tap **Help** and pick a spotlight tour, an auto-playing demo, or animated welcome slides.
- **Works offline:** no server, no accounts, and no downloads at startup. JSZip is included.

## Project structure

```
repo-cloner/
├── index.html            The web page
├── repo_cloner.py        The Termux script (Python, standard library only)
├── README.md             This file
├── GUIDE.md              Full instructions and explanations
├── LICENSE               MIT license
├── .gitignore
├── assets/
│   └── favicon.svg
├── css/
│   ├── styles.css        Page styles (light and dark)
│   └── tutorial.css      Styles for the Help tutorials
└── js/
    ├── app.js            App logic: download, zip, copy, timeline
    ├── tutorial.js       Help button and tutorial chooser
    ├── tutorial-tour.js  Spotlight tour
    ├── tutorial-demo.js  Auto-playing demo
    ├── tutorial-slides.js  Welcome slides
    └── vendor/
        ├── jszip.min.js  JSZip 3.10.1 (zip creation)
        └── JSZIP-LICENSE.markdown
```

## Quick start

**Web page:** open `index.html` in Chrome. If your file manager opens it in a viewer, long-press the file and choose Chrome. You can also serve it from Termux:

```
cd repo-cloner
python -m http.server 8000
```

Then visit `http://localhost:8000`.

**Termux script:**

```
pkg install python git
python repo_cloner.py clone owner/repo
python repo_cloner.py zip owner/repo --all-branches -f "*.md"
python repo_cloner.py copy owner/repo --dest-token TOKEN --private
```

New here? Tap **Help** on the page to learn it in under a minute. See [GUIDE.md](GUIDE.md) for tokens, patterns, every command, and troubleshooting.

## Credits and license

Repo Cloner is released under the [MIT License](LICENSE). It includes [JSZip](https://stuk.github.io/jszip/) 3.10.1, used under the MIT license (see `js/vendor/JSZIP-LICENSE.markdown`).
