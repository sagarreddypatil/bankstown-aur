# SPDX-License-Identifier: MIT
# Maintainer: Sagar Patil <fntneerqqlcngvy@tznvy.pbz>

pkgname=bankstown
pkgver=1.1.0
pkgrel=2
pkgdesc="Bankstown LV2 Plugin"
url="https://github.com/chadmed/bankstown"

arch=('x86_64')
license=('MIT')
makedepends=('cargo')
depends=('lv2' 'git')

_gitroot="https://github.com/chadmed/bankstown"
_gitname="${pkgname}-${pkgver}"
source=("${_gitname}::git+${_gitroot}.git#tag=${pkgver}")
sha256sums=('SKIP') # Generate this with 'updpkgsums'

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    cargo build --release
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make
    make DESTDIR="${pkgdir}" LIBDIR="/usr/lib" install
}