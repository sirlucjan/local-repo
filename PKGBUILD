# Maintainer: Piotr Górski <lucjan.lucjanov@gmail.com>
# Contributor: ushi <ushi@porkbox.net>

pkgname=local-repo-git
_pkgname=local-repo
pkgver=1.6.5.5.g5b648b0
pkgrel=1
pkgdesc="Local repository manager"
arch=('any')
url="https://github.com/sirlucjan/local-repo/"
license=('GPL')
depends=('pacman' 'python>=3.3')
makedepends=('gettext')
provides=('local-repo')
conflitcs=('local-repo')
install=local-repo.install
source=("git://github.com/sirlucjan/local-repo.git")
md5sums=('SKIP')

pkgver() {
  cd ${_pkgname}
  git describe --tags --long | sed 's/^v//;s/-/./g'
}

package() {
  cd ${_pkgname}
  python setup.py install --prefix="${pkgdir}/usr"
  install -D -m644 bash-completion "${pkgdir}/usr/share/bash-completion/completions/local-repo"
  install -D -m644 share/config.example "${pkgdir}/usr/share/local-repo/config.example"
}

# vim:set ts=2 sw=2 et:
