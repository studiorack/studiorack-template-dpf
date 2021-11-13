# studiorack-plugin-dpf
![Release](https://github.com/studiorack/studiorack-plugin-dpf/workflows/Release/badge.svg)

Audio plugin starter template using [DPF framework](https://github.com/DISTRHO/DPF) to build binaries using:

* Bash
* CMake 3.15.x
* DPF


## Installation

Install CMake and Xcode using:

    brew install cmake
    xcode-select --install

Check you have the correct dependencies installed:

    cmake -version
    xcodebuild -version

Ensure all git submodules are initialized:

    git submodule update --init --recursive


## Usage

Make all your plugin development changes in the source folder at:

    ./src

Ensure you also update the preview image and audio files:

    ./src/assets/name.png
    ./src/assets/name.wav


## Testing your plugin

Todo


## Build (manual)

Compile the DPF framework example plugins using:

    make -C ./dpfsdk

View the built plugin files at:

    ./dpfsdk/bin

Copy any additional metadata files:

    cp -v ./src/assets/* ./dpfsdk/bin

For metadata generation as json use the studiorack-cli:

    npm install @studiorack/cli -g

Validate your plugin:

    studiorack validate "./dpfsdk/bin/**/*.{vst,vst3}"

Convert and enrich validator report metadata into json:

    studiorack validate "./dpfsdk/bin/**/*.{vst,vst3}" --json


## Build (automatic)

Release a plugin version on GitHub by simply creating a version tag:

    git tag v0.0.1
    git push && git push origin --tags

This will run an automated build and release process on GitHub Actions:

    .github/workflows/release.yml


## Resources & guides

* [DPF framework source code and examples](https://github.com/DISTRHO/DPF)
* [Official DPF guide to creating VST audio plugins](https://distrho.github.io/DPF/)


## Contact

For more information please contact kmturley
