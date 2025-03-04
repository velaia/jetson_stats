# Jetson stats
[![PyPI - Downloads](https://img.shields.io/pypi/dw/jetson-stats.svg)](https://pypistats.org/packages/jetson-stats) [![PyPI version](https://badge.fury.io/py/jetson-stats.svg)](https://badge.fury.io/py/jetson-stats) [![PyPI - Python Version](https://img.shields.io/pypi/pyversions/jetson-stats.svg)](https://www.python.org/) [![PyPI - Format](https://img.shields.io/pypi/format/jetson-stats.svg)](https://pypi.org/project/jetson-stats/)

![Build](https://github.com/rbonghi/jetson_stats/workflows/Build/badge.svg) ![Docs](https://github.com/rbonghi/jetson_stats/workflows/Docs/badge.svg) ![Publish](https://github.com/rbonghi/jetson_stats/workflows/Publish/badge.svg)

**jetson-stats** is a package to **monitoring** and **control** your [NVIDIA Jetson][NVIDIA Jetson] [Xavier NX, Nano, AGX Xavier, TX1, TX2] Works with all NVIDIA Jetson ecosystem.

When you install jetson-stats are included:
* [jtop](#jtop)
* [jetson_config](#jetson_config)
* [jetson_release](#jetson_release)
* [jetson_swap](#jetson_swap)
* [jetson variables](#jetson_variables)

Read the [Wiki](https://github.com/rbonghi/jetson_stat/wiki) for more detailed information or read the package [documentation](https://rbonghi.github.io/jetson_stats).

## Install

```elm
sudo -H pip install -U jetson-stats
```
**🚀 That's it! 🚀** 

_PS: Don't forget to **reboot** your board_

**You can run jtop in your python script [read here][library]**

## [**jtop**][jtop] 
It is a system monitoring utility that runs on the terminal and see and **control** realtime the status of your [NVIDIA Jetson][NVIDIA Jetson]. CPU, RAM, GPU status and frequency and other...

The prompt interface will be show like this image, **now clickable!**:
![jtop](https://github.com/rbonghi/jetson_stats/wiki/images/jtop.gif)

You can run the jtop simple using a simple command `jtop`

YES! Sudo is **not** more required!
```console
nvidia@jetson-xavier-nx:~/$ jtop
```

Other options are available with `-h` option:
```console
nvidia@jetson-xavier-nx:~/$ jtop -h
usage: jtop [-h] [--no-warnings] [--restore] [--loop] [-r REFRESH] [-p PAGE]
            [-v]

jtop is system monitoring utility and runs on terminal

optional arguments:
  -h, --help            show this help message and exit
  --no-warnings         Do not show warnings (default: False)
  --restore             Reset Jetson configuration (default: False)
  --loop                Automatically switch page every 5s (default: False)
  -r REFRESH, --refresh REFRESH
                        refresh interval (default: 500)
  -p PAGE, --page PAGE  Open fix page (default: 1)
  -v, --version         show program's version number and exit
```
You can change page using _left_, _right_ arrow or _TAB_ to change page.
### Pages
**jtop** have four different pages to control your NVIDIA Jetson:
1. **ALL** Are collected all information about your board: CPUs status, Memory, *GPU*, disk, fan and all status about jetson_clocks, NVPmodel and other
2. **GPU** A real time GPU history about your NVIDIA Jetson
3. **CPU** A real time CPU plot of NVIDIA Jetson
4. **MEM** A real time Memory chart and swap monitor
5. **CTRL** Enable/Disable **jetson_clocks**, **nvpmodel** or **fan** directly from here
6. **INFO** All information about libraries, CUDA, Serial Number, interfaces, ...
### Controls
To control the your NVIDIA Jetson are available this keyboard commands:

In page **4 MEM**:
* **c** Clear cache
* **s** Enable/Disable extra swap
* **+** and **-** Increase and decrease swap size

In page **5 CTRL**:
* **a** Start/Stop jetson_clocks service (Note: jetson_clocks start only after 60s from up time)
* **e** Enable/Disable jetson_clocks on board boot
* **+** and **-** Increase and decrease the NVPmodel
* **f** Manual/jetson_clocks mode for your fan
* **p** and **m** Increase and decrease the Fan speed

## [**jetson_config**][jetson_config]

Check _jetson-stats_ **health**, enable/disable **desktop**, enable/disable **jetson_clocks**, improve the performance of your **wifi** are available only in one click using **jetson_config**

![jetson_config](https://github.com/rbonghi/jetson_stats/wiki/images/jetson_config.png)
## [**jetson_release**][jetson_release]
The command show the status and all information about your [NVIDIA Jetson][NVIDIA Jetson]

![jtop](https://github.com/rbonghi/jetson_stats/wiki/images/jetso_release.png)
## [**jetson_swap**][jetson_swap]
Simple manager to switch on and switch off a swapfile in your jetson.

```elm
nvidia@jetson-nano:~/$ sudo jetson_swap -h
usage: createSwapFile [[[-d directory ] [-s size] -a] | [-h] | [--off]]
  -d | --dir    <directoryname> Directory to place swapfile
  -n | --name   <swapname> Name swap file
  -s | --size   <gigabytes>
  -a | --auto   Enable swap on boot in /etc/fstab 
  -t | --status Check if the swap is currently active
  --off         Switch off the swap
  -h | --help   This message
```

## [**jetson variables**][jetson_variables]
When you install jetson-stats in your bash will be available a list of new environment variables to know which which hardware version is available are you working, which Jetpack is installed and other variable show below

![jtop](https://github.com/rbonghi/jetson_stats/wiki/images/jetson_env.png)

[library]: https://github.com/rbonghi/jetson_stats/wiki/library
[jtop]: https://github.com/rbonghi/jetson_stats/wiki/jtop
[jetson_config]: https://github.com/rbonghi/jetson_stats/wiki/jetson_config
[jetson_swap]: https://github.com/rbonghi/jetson_stats/wiki/jetson_swap
[jetson_variables]: https://github.com/rbonghi/jetson_stats/wiki/jetson_variables
[jetson_release]: https://github.com/rbonghi/jetson_stats/wiki/jetson_release
[jetson_performance]: https://github.com/rbonghi/jetson_stats/wiki/jetson_performance
[jetson_docker]: https://github.com/rbonghi/jetson_stats/wiki/jetson_docker
[NVIDIA]: https://www.nvidia.com/
[NVIDIA Jetson]: http://www.nvidia.com/object/embedded-systems-dev-kits-modules.html
