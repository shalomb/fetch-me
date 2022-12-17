# install-cmd

Install (CLI) applications directly from their github releases.

e.g.

```
install-cmd sharkdp/bat          # Install the latest release of bat
install-cmd sharkdp/fd -t 8.6    # Install a specific version
install-cmd httpie/httpie -a .   # Install httpie but list all archs
```

`install-cmd` finds the latest tagged version of a command
using the [Github Releases API]
(https://docs.github.com/en/rest/releases/releases?apiVersion=2022-11-28).

If multiple candidates are found, a prompt is displayed to select the asset needed.

Once downloaded, a best-effort is made to detect the file type and invoke the
appropriate installation method.

```
$ install-cmd sharkdp/fd

repo:    sharkdp/fd (https://github.com/sharkdp/fd)
command: fd
tag:     v8.6.0
arch:    aarch64|arch64|arm64

Multiple candidates found
  0 - v8.6.0/fd_8.6.0_arm64.deb
  1 - v8.6.0/fd-v8.6.0-aarch64-unknown-linux-gnu.tar.gz
Which one? [0] 0

Installing https://github.com/sharkdp/fd/releases/download/v8.6.0/fd_8.6.0_arm64.deb
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Note, selecting 'fd' instead of '/home/unop/.cache/install-cmd/sharkdp/fd/v8.6.0/fd_8.6.0_arm64.deb'
The following NEW packages will be installed:
  fd
0 upgraded, 1 newly installed, 0 to remove and 4 not upgraded.
Need to get 0 B/924 kB of archives.
After this operation, 0 B of additional disk space will be used.
Get:1 /home/unop/.cache/install-cmd/sharkdp/fd/v8.6.0/fd_8.6.0_arm64.deb fd arm64 8.6.0 [924 kB]
Selecting previously unselected package fd.
(Reading database ... 175520 files and directories currently installed.)
Preparing to unpack .../fd/v8.6.0/fd_8.6.0_arm64.deb ...
Unpacking fd (8.6.0) ...
Setting up fd (8.6.0) ...
Processing triggers for man-db (2.9.4-2) ...
```
