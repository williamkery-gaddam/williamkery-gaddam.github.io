# Your website — setup instructions

Everything is written. You need to install two programs, paste these files into
a folder, and click publish. Budget about an hour the first time.

---

## Step 1 — GitHub account

Sign up at <https://github.com>.

**Your username becomes your web address.** If you pick `williamkery`, your site
lives at `williamkery.github.io`. Choose something you'd put on a CV.

## Step 2 — Install two programs

| Program | Where | What it does |
|---|---|---|
| **Quarto** | <https://quarto.org/docs/get-started> | Turns these text files into a website |
| **GitHub Desktop** | <https://desktop.github.com> | Uploads the site. No command line. |

Optional but recommended: **VS Code** (<https://code.visualstudio.com>) for
editing. Install its "Quarto" extension from the Extensions tab.

## Step 3 — Make the repository

On GitHub, click **New repository**.

- Name it **exactly** `yourusername.github.io` — your real username, all lowercase
- Set it to **Public**
- Tick "Add a README file"
- Create repository

Then open GitHub Desktop → **File → Clone repository** → pick it → note the folder
it saves into.

## Step 4 — Copy these files in

Copy everything from this folder into the folder GitHub Desktop just made. You
should end up with `_quarto.yml`, `custom.scss`, five `.qmd` files, and `files/`
sitting next to the `README.md` GitHub created.

## Step 5 — Fill in your details

Search for `YOUR-LINKEDIN-HANDLE` and `YOUR-GITHUB-USERNAME` and replace them.
They appear in `_quarto.yml`, `about.qmd` and `cv.qmd`.

In `_quarto.yml`, also change `site-url` to your real address.

Then drop your CV PDF into `files/`, named `Williamkery-Gaddam-CV.pdf`, and
delete the placeholder text file in there.

## Step 6 — Look at it

Open a terminal in the folder. (In VS Code: Terminal → New Terminal. On Windows
without VS Code: open the folder in File Explorer, type `cmd` in the address bar,
press Enter.)

```
quarto preview
```

Your site opens in a browser and refreshes every time you save a file. Press
`Ctrl+C` in the terminal to stop.

When you're happy:

```
quarto render
```

This builds the finished site into a new `docs` folder.

## Step 7 — Publish

1. Open GitHub Desktop. It lists your new files. Type "first version" in the
   summary box → **Commit to main** → **Push origin**.
2. On GitHub.com go to your repository → **Settings** → **Pages**.
3. Under *Build and deployment*: Source = **Deploy from a branch**,
   Branch = **main**, Folder = **/docs**. Click Save.

Wait two or three minutes, then open `yourusername.github.io`.

---

## Changing things later

The loop is always the same:

1. Edit a `.qmd` file
2. Run `quarto render`
3. Commit and push in GitHub Desktop

## The files, briefly

| File | What it is |
|---|---|
| `_quarto.yml` | Settings: site title, menu, social links |
| `custom.scss` | All the styling — colours, fonts, spacing |
| `index.qmd` | Homepage |
| `about.qmd` | Background, education, methods |
| `research.qmd` | Positions, fieldwork, talks, awards |
| `writing.qmd` | Publications |
| `cv.qmd` | CV download page |

The `.qmd` files are plain text. `# Heading`, `**bold**`, `*italic*`,
`[link text](https://url.com)`. Everything between the `---` lines at the top is
settings for that page.

## If something breaks

**"quarto: command not found"** — Quarto isn't installed, or you need to close
and reopen the terminal after installing it.

**Site is live but has no styling** — Create an empty file called `.nojekyll`
inside the `docs` folder, then commit and push again. GitHub otherwise strips
folders beginning with an underscore.

**404 after publishing** — Check the repository name matches your username
exactly, that it's Public, and that Pages is pointed at `main` / `/docs`. Give it
five minutes.

**YAML error on render** — Almost always indentation in `_quarto.yml`. It uses
spaces, never tabs, and the nesting matters.
