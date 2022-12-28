# MSVC Manifest Archive

This repository archives the Microsoft Visual Studio installer manifest,
allowing a user to install old versions of visual studio, or to download old
versions of the Windows SDK for diffing purposes.

This repository has one branch per MSVC version:

- [release-17](https://github.com/roblabla/msvc-manifest-history/tree/release-17)
  tracks Visual Studio 2022.
- [pre-17](https://github.com/roblabla/msvc-manifest-history/tree/pre-17) tracks
  Visual Studio 2022 preview.
- [release-16](https://github.com/roblabla/msvc-manifest-history/tree/release-16)
  tracks Visual Studio 2019.
- [pre-16](https://github.com/roblabla/msvc-manifest-history/tree/pre-16)
  tracks Visual Studio 2019 Preview (note - this version is currently dead.
  The manifest is currently located on a microsoft-internal domain).
- [release-15](https://github.com/roblabla/msvc-manifest-history/tree/release-15)
  tracks Visual Studio 2017.
- [pre-15](https://github.com/roblabla/msvc-manifest-history/tree/pre-15) tracks
  Visual Studio 2017 preview.

# How it works

Each branch has two files:

- `channel.json` is the top-level descriptor used by the Visual Studio
  installer. It describes the different editions of Visual Studio that can be
  installed for this release, the current version, and most importantly, a link
  to a `vsman`, short for Visual Studio Manifest.
- `manifest.json` is that `vsman` file, which is a manifest giving instructions
  on how to download and install each of the individual components that make up
  a visual studio installation.
  
Each of those files is provided in two flavours:

- The `raw_` file is the file as it was downloaded by the microsoft server. This
  may be necessary for some use-cases involving verifying the signatures of the
  manifests.
- The unprefixed files are formatted using `jq` for easy diffing and viewing.
