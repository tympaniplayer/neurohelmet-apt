# Neurohelmet APT Repository

A GPG-signed APT repository for [Neurohelmet](https://github.com/tympaniplayer/neurohelmet) —
a keyboard-driven terminal BattleTech record-sheet tracker. Works on Debian/Ubuntu and
Raspberry Pi OS (64-bit), for both `amd64` and `arm64`.

## Install

```sh
sudo mkdir -p /usr/share/keyrings
curl -fsSL https://tympaniplayer.github.io/neurohelmet-apt/neurohelmet.gpg \
  | sudo tee /usr/share/keyrings/neurohelmet.gpg >/dev/null
echo "deb [signed-by=/usr/share/keyrings/neurohelmet.gpg] https://tympaniplayer.github.io/neurohelmet-apt stable main" \
  | sudo tee /etc/apt/sources.list.d/neurohelmet.list
sudo apt update && sudo apt install neurohelmet
```

Update with `sudo apt update && sudo apt upgrade neurohelmet`.

## Notes

The repository metadata (`dists/`, `pool/`) and the public signing key (`neurohelmet.gpg`)
are generated automatically on each Neurohelmet release by its
[release workflow](https://github.com/tympaniplayer/neurohelmet/blob/main/.github/workflows/release.yml)
using `reprepro`. Don't commit here by hand. (`.nojekyll` keeps GitHub Pages from
processing the repo files.)
