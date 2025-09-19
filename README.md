# Trinity Konsole little theme manager

*by seb3773*

A small shell script to manage color schemes for Konsole under the Trinity Desktop Environment (TDE). It allows listing, applying, installing, and randomly changing themes, either interactively or directly via the command line.

## Limitations and Prerequisites

### Main Limitation

This script is designed **only** for Konsole under the **Trinity Desktop Environment (TDE)**. It uses the legacy `dcop` communication system and will not work with modern versions of KDE Plasma which use D-Bus  :-p

### Dependencies

The script requires the following commands to be installed on your system (should be ok whithout needing to install anything, but just in case)
- `dcop`
- `whiptail`
- `find`
- `sed`
- `basename`
- `readlink`
- `sort`
- `shuf`

and Trinity Desktop (of course!)

## Installation

1.  Make the script executable:
    ```bash
    chmod +x set-konsole-theme
    ```

2.  (Optional) Place the script in a directory within your `$PATH` (e.g., `/usr/local/bin` (best place at my opinion) or `~/.local/bin`) to be able to call it by its name (`set-konsole-theme`) from anywhere. Otherwise, you can run it from its directory with `./set-konsole-theme`.

## Usage

The script uses a simple command-based interface.

### Show Help

To see the list of commands and options.

```bash
./set-konsole-theme help
# or simply
./set-konsole-theme
```

### List and Choose a Theme

Displays an interactive menu to choose a theme from all installed themes (system and user).

```bash
./set-konsole-theme list
```

To filter the list, add a keyword. The search is case-insensitive.

```bash
# Will only show themes containing "dark"
./set-konsole-theme list dark
```

### Apply a Theme Directly

Pass a theme name as an argument to apply it instantly.

```bash
# Apply the "Dracula" theme
./set-konsole-theme Dracula

# You can also include the extension; it will work
./set-konsole-theme Dracula.schema
```

### Apply a Random Theme

For a change of scenery, this command picks and applies a random theme.

```bash
./set-konsole-theme random
```

### Install a New Theme

This command allows you to install new themes (`.schema`) from any folder. The themes will be copied to your personal user configuration directory (`~/.trinity/share/apps/konsole/`).

```bash
# If you have themes in a "my-themes" folder
./set-konsole-theme install ./my-themes
```

An interactive menu will ask you which specific theme you want to install.


Enjoy :-)

| **Help** |  
 ![Main Interface](https://github.com/seb3773/Konsole-little-theme-manager/blob/main/screenshots/konsole_theme_manager_scr1.jpg?raw=true) |  
| **Selection in a list** |  
 ![Themes](https://github.com/seb3773/Konsole-little-theme-manager/blob/main/screenshots/konsole_theme_manager_scr2.jpg?raw=true) |  
| **Theme installation list** |  
 ![Selection Menu](https://github.com/seb3773/Konsole-little-theme-manager/blob/main/screenshots/konsole_theme_manager_scr3.jpg?raw=true) |  
