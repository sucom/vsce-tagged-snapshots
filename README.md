# Tagged Snapshots

<p align="center">
  <img src="images/icon.png" alt="Tagged Snapshots Logo" width="120"/>
</p>

Never lose your progress — instantly back up your work before taking the next step, whether by you or your AI. During learning, complex problem solving, complex feature development, or just want to look back how you got here.

With a few keystrokes or clicks, you can snapshot your your experiments on selected working files with a tag quickly — no Git required.

You don't really require complex git repository/setup/commands before making every step. For personal learning/experiments, you can keep all your learning/experiment history local.

Tagged Snapshots keeps your progress record simple, fast, and easy for future reference without any complex setup/commands.

##### Other related extensions
- [Backup File](https://marketplace.visualstudio.com/items?itemName=spajs.backup-file) - For single file snapshots.
- [Backup Folder](https://marketplace.visualstudio.com/items?itemName=spajs.backup-folder) - For entire project folder snapshots.
- [Git Snapshots](https://marketplace.visualstudio.com/items?itemName=spajs.git-snapshots) - For Git based snapshots.

## Install
Install this extension from the VSCode Marketplace

[Tagged Snapshot](https://marketplace.visualstudio.com/items?itemName=SPAjs.tagged-snapshots)

## Features

> Snapshot all open editor files with an optional tag name. Browse, diff, and restore from the sidebar.
>
> No Git. No build step. No dependencies. Just fast, labelled backups of exactly what you're working on right now.
>
---

- **📷 One-action snapshots** — capture all open files across all tab groups (live buffer, including unsaved edits)
- **🏷️ Tagged names** — label your snapshot (`before-refactor`, `wip-dark-mode`) with a timestamp auto-appended
- **📁 Plain file storage** — snapshots live in `.vscode/tagged-snapshots/` as real files, no proprietary formats
- **🔍 Diff view** — click any file in the sidebar to compare the snapshot version against the current file
- **↔️ Swappable diff layout** — choose which side shows current vs snapshot; swap instantly from the editor title bar
- **♻️ Flexible restore** — restore an entire snapshot or cherry-pick individual files
- **🗑️ Full management** — delete individual snapshots or clear all at once

---

## Usage

### Taking a Snapshot
Use any of these methods:
- `Ctrl+Shift+S` / `Cmd+Shift+S`
- Click `🏷️(TAg)Snapshot` in the status bar
- Click `🏷️(Tag)` icon in the Tagged Snapshots sidebar
- Open the Command Palette → `Tagged Snapshots: Take Snapshot`

Type a label (or leave blank for a timestamp-only name) and press Enter.

### Browsing Snapshots
Click the **Tagged Snapshots** icon in the Activity Bar. Snapshots are listed newest-first. Expand any snapshot to see its files.

### Diffing a File
Click any file inside an expanded snapshot to open a diff editor comparing it against the current version.

Use the `↔` button in the editor title bar to swap left/right sides instantly.

### Restoring
- **All files**: right-click a snapshot → `Restore All Files`
- **One file**: right-click a file inside a snapshot → `Restore This File`

### Deleting
- **One snapshot**: right-click a snapshot → `Delete Snapshot`
- **All snapshots**: Command Palette → `Tagged Snapshots: Clear All Snapshots`

---

## Settings

| Setting | Default | Description |
|---|---|---|
| `taggedSnapshots.showStatusBarButton` | `both` | Controls the status bar button display: `both` (icon + label), `icon` (camera only), `text` (label only) |
| `taggedSnapshots.source` | `all-opened` | `all-opened`: snapshot every open file across all tab groups. `active-tabgroup`: snapshot only files in the currently active tab group. |
| `taggedSnapshots.confirmOnRestore` | `true` | Confirm before restoring |
| `taggedSnapshots.confirmOnDelete` | `true` | Confirm before deleting |
| `taggedSnapshots.addToGitignore` | `true` | Offer to add snapshots folder to `.gitignore` on first use |
| `taggedSnapshots.diffLayout` | `currentVsSnapshot` | `currentVsSnapshot`: Left=current, Right=snapshot. `snapshotVsCurrent`: Left=snapshot, Right=current. |

---

## Storage Format

```
.vscode/
  tagged-snapshots/
    20260225-143210-before-refactor/
      src/
        index.ts
      components/
        Button.tsx
      _external/          ← files opened from outside the workspace
        home/user/notes.md
```

- No metadata files — the folder name and directory structure are the only metadata
- Files opened from outside the workspace are stored under `_external/`

---

## License

MIT