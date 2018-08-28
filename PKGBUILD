# Maintainer: Jan Boelsche <jan@lagomorph.de>

pkgname=ssb-autofollow-git
pkgver=1.0.0.r3.8c78f8f
pkgrel=1
pkgdesc="This Scuttlebot plugin automatically follows feeds specified in the config file"
arch=('any')
url=""
license=('GPL')
groups=()
depends=('scuttlebot')
makedepends=('git' 'npm')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
replaces=()
backup=()
options=()

source=('git+ssh://git@github.com/regular/ssb-autofollow.git')
sha256sums=('SKIP')

pkgver() {
	cd "$srcdir/${pkgname%-git}"
  printf "%s.r%s.%s" "$(node -e 'console.log(require("./package.json").version)')" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package () {
	cd "$srcdir/${pkgname%-git}"
  source "$HOME/.nvm/nvm.sh"
  nvm use 10.8.0
  local _npmdir="${pkgdir}/usr/lib/node_modules/"
  mkdir -p $_npmdir
  npm install -g --prefix "${pkgdir}/usr" regular/ssb-autofollow
}
