Better_Vitals
====================================

Better_Vitals is a GNOME Shell extension for displaying your computer's temperature, voltage, fan speed, memory usage, processor load, system resources, network speed and storage stats in your GNOME Shell's top menu bar. This is a one stop shop to monitor all of your vital sensors. Better_Vitals uses asynchronous polling to provide a smooth user experience.

![How it works](https://raw.githubusercontent.com/spailll/Better_Vitals/main/howtouse.gif)

## Installation

### 1) Install support packages

#### Ubuntu/Debian

    sudo apt install gnome-shell-extension-manager gir1.2-gtop-2.0 lm-sensors

#### Fedora

    sudo dnf install libgtop2-devel lm_sensors

#### Arch/Manjaro

    sudo pacman -Syu libgtop lm_sensors gnome-icon-theme-symbolic gnome-icon-theme git

#### openSUSE

    sudo zypper install libgtop-devel

### 2) Install extension

#### Ubuntu/Debian

#### &nbsp;&nbsp;&nbsp;&nbsp;Open the Extension Manager (installed above), search for Better_Vitals and click Install.

#### Fedora

##### &nbsp;&nbsp;&nbsp;&nbsp;Visit [Better_Vitals on GitHub](https://github.com/spailll/Better_Vitals), clone it locally, and install it under your extension UUID path.

#### Arch/Manjaro

    git clone https://aur.archlinux.org/gnome-shell-extension-vitals-git.git/
    cd gnome-shell-extension-vitals-git

    # always verify content before installing
    less PKGBUILD
    makepkg

    # example filename, different each release
    pacman -U gnome-shell-extension-vitals-git-v52.0.4.r0.gb446cfc-1-any.pkg.tar.zst

### 3) Activate after installation

#### Ubuntu/Debian/Fedora

##### &nbsp;&nbsp;&nbsp;&nbsp;At this point, Better_Vitals should be running. If you reversed steps 1 and 2 above, you will need to restart your session by logging out and then back in.

#### Arch/Manjaro

##### &nbsp;&nbsp;&nbsp;&nbsp;Open the Extensions application and toggle on Better_Vitals

## Beta testing

##### Advanced users requesting bug fixes or asking for new features may occasionally be asked to help QA.

### 1) Remove existing copy of Better_Vitals

##### &nbsp;&nbsp;&nbsp;&nbsp;Remove existing copy of Better_Vitals - expert users only!

    rm -rI ~/.local/share/gnome-shell/extensions/Better_Vitals@spail

### 2) Clone from GitHub

    mkdir -p ~/.local/share/gnome-shell/extensions
    git clone https://github.com/spailll/Better_Vitals.git ~/.local/share/gnome-shell/extensions/Better_Vitals@spail -b main

### 3) Compile Schemas

    glib-compile-schemas --strict ~/.local/share/gnome-shell/extensions/Better_Vitals@spail/schemas/

### 4) Activate develop version

#### Ubuntu/Debian/Fedora

##### &nbsp;&nbsp;&nbsp;&nbsp;You will need to restart your session by logging out and then back in.

#### Arch/Manjaro

##### &nbsp;&nbsp;&nbsp;&nbsp;Open the Extensions application and toggle on Better_Vitals

## Credits
Better_Vitals was originally forked from [Vitals](https://github.com/corecoding/Vitals), which itself was originally forked from [gnome-shell-extension-freon](https://github.com/UshakovVasilii/gnome-shell-extension-freon).

## Original Creator Credit
Primary credit for the original Vitals extension design and implementation goes to Chris Monahan (Core Coding) and project contributors. Better_Vitals builds on that foundation.

## Icons

### Original Theme
* (voltage|fan)-symbolic.svg - inherited from Freon project.
* (system|storage)-symbolic.svg - from Pop! OS theme.
* temperature-symbolic.svg - [iconnice studio](https://www.iconfinder.com/iconnice).
* (cpu|memory)-symbolic.svg - [DinosoftLabs](https://www.iconfinder.com/dinosoftlabs).
* network\*.svg - [Yannick Lung](https://www.iconfinder.com/yanlu).
* Health icon - [Dod Cosmin](https://www.iconfinder.com/icons/458267/cross_doctor_drug_health_healthcare_hospital_icon).

### GNOME Theme
* (battery | storage)-symbolic.svg - from [Adwaita Icon Theme](https://gitlab.gnome.org/GNOME/adwaita-icon-theme).
* (memory | network* | system | voltage)-symbolic.svg - from [Icon Development Kit](https://gitlab.gnome.org/Teams/Design/icon-development-kit).
* fan-symbolic.svg - inherited from [Freon](https://github.com/UshakovVasilii/gnome-shell-extension-freon) project, with mild modifications.
* (temperature | cpu)-symbolic.svg - designed by [daudix](https://github.com/daudix).

## Disclaimer
Sensor data is obtained from the system using hwmon and GTop. Better_Vitals and upstream contributors are not responsible for improperly represented data. No warranty expressed or implied.

## Development Commands

| Description | Command |
| --- | --- |
| Launch preferences | `gnome-shell-extension-prefs Better_Vitals@spail` |
| View logs | ``journalctl --since="`date '+%Y-%m-%d %H:%M'`" -f \| grep Better_Vitals`` |
| Compile schemas | `glib-compile-schemas --strict schemas/` |
| Compile translation file | `msgfmt vitals.po -o vitals.mo` |
| Launch Wayland virtual window | `dbus-run-session -- gnome-shell --nested --wayland` |
| Read hot-sensors value | `dconf read /org/gnome/shell/extensions/better_vitals/hot-sensors` |
| Write hot-sensors value | `dconf write /org/gnome/shell/extensions/better_vitals/hot-sensors "['_memory_usage_', '_system_load_1m_']"`<br/>This value configures the list of sensors that show up in the panel. To specify a sensor name, click on the extension to show the drop-down menu, then take the category label and the label of the individual sensor, convert them to `snake_case`, and format them like this: `_category_sensor_`.| 

## Donations
[Please consider donating if you find this extension useful.](https://corecoding.com/donate.php)

[gextension]: https://github.com/spailll/Better_Vitals
