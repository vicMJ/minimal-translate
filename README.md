# translate-popup.py

A slightly vibecoded minimal floating translation widget optimized for wayland Arch but should work on any distro. Type in either language and the translation appears instantly below.

## Dependencies

- Python 3
- GTK 3 (`python3-gi`)
- [`trans`](https://github.com/soimort/translate-shell) (translate-shell)

## Usage

```bash
python3 translate-popup.py
```

The window floats above all other windows with no taskbar entry. Press **Escape** to close.

On first run a language picker appears. Selected languages are saved to `~/.config/translator/config.json` and remembered on future runs. To change languages at any time, click the **⚙ languages** button in the bottom-right corner.

Translation triggers automatically after you stop typing (500 ms debounce). The direction is detected from the script of what you typed — Greek, Cyrillic, Arabic, CJK, Hebrew, Devanagari, and many others are recognised automatically, so you can switch languages mid-session without doing anything.

## Binding to a hotkey

The intended workflow is to bind it to a keyboard shortcut so it pops up on demand. In most desktop environments this is under *Settings → Keyboard → Custom Shortcuts*. Set the command to the full path:

```
python3 /path/to/translate-popup.py
```
### Hyprland keybinds.conf entry that I use to trigger the script:
```
bindd = $mainMod ALT, T, Translate, exec, uwsm-app -- python3 ~/.config/hypr/scripts/translate-popup.py
```
