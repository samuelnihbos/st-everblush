# Maintainer: SamuelNihBos
pkgname=st-uwu-git
pkgver=0.8.4.r32.835d7b3
pkgrel=1
pkgdesc="A patched and customized build of st"
arch=(x86_64)
url="https://github.com/samuelnihbos/st-uwu.git"
license=('MIT')
groups=()
depends=(ttf-hack ttf-joypixels ttf-iosevka-nerd)
makedepends=(git)
checkdepends=()
optdepends=()
provides=(st)
conflicts=(st)
replaces=()
backup=()
options=()
source=("git+$url")
noextract=()
md5sums=('SKIP')
validpgpkeys=()

pkgver() {
  cd "${_pkgname}"
  printf "0.8.4.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd st-uwu
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  cd st-uwu  
  mkdir -p ${pkgdir}/opt/${pkgname}
  cp -rf * ${pkgdir}/opt/${pkgname}
  make PREFIX=/usr DESTDIR="${pkgdir}" install
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  install -Dm644 README.org "${pkgdir}/usr/share/doc/${pkgname}/README.org"
}

