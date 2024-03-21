# Building a custom Debian ISO image

The live/ISO image build process is managed by [live-build](https://packages.debian/bookwom/live-build).

* [Live Systems manual](https://live-team.pages.debian.net/live-manual/html/live-manual/index.en.html)
* [`man lb config`](https://manpages.debian.org/bookworm/live-build/lb_config.1.en.html)
* [`man lb build`](https://manpages.debian.org/bookworm/live-build/lb_build.1.en.html)
* [`man lb clean`](https://manpages.debian.org/bookworm/live-build/lb_clean.1.en.html)
* [`man live-build`](https://manpages.debian.org/bookworm/live-build/live-build.7.en.html)
* `/usr/share/doc/live-manual/pdf/live-manual.portrait.en.a4.pdf.gz` ([live-manual](https://packages.debian.org/bookworm/live-manual) package)

## Building with tiler

## Build using the default configuration

Install [Debian](https://www.debian.org). You must build from the same distribution as the target distribution (build *bookworm* systems on a build machine running Debian *bookworm*, *testing* systems on a machine running Debian *testing*...). Then run the following commands:

'''bash
# Clone the tiler repsitoroy
git clone https://github.com/zulcss/tiler/
# build the docker container
sudo tools/build-container
# Run the container
sudo tools/run-dev.sh
# Inside the container clone live-config repository
git clone https://github.com/zulcss/pablo-live-config
# Create the ISO
sudo tiler iso build --config pablo-lvie-config

