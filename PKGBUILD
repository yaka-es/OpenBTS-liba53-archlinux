# Maintainer :
# Contributor:

#validpgpkeys=('')
_pkgname=OpenBTS-liba53
pkgname=liba53
pkgver=4.0.1
pkgrel=1
pkgdesc="A5/3 Call Encryption Library"
arch=('i686' 'x86_64' 'armv7h')
url="https://github.com/yaka-es/OpenBTS-liba53"
license=('GPL')
provides=('liba53')
conflicts=('liba53')
#install=openbts.install

source=("git+https://github.com/yaka-es/OpenBTS-liba53.git")
sha256sums=('SKIP')

build() {
  cd ${srcdir}/${_pkgname}

  for patchfile in ${source}; do
    case "${patchfile}" in
    *.patch)
      patch -p1 -i "${patchfile}"
      ;;
    esac
  done

  make
}

package() {
  cd ${srcdir}/${_pkgname}

  mkdir -p "${pkgdir}/usr/include"
  mkdir -p "${pkgdir}/usr/lib"
  make DESTDIR="${pkgdir}" install
}
