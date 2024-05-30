# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Pellegrino Prevete <pellegrinoprevete@gmail.com>
# Maintainer: Truocolo <truocolo@aol.com>
# # Maintainer: Johannes Löthberg <johannes@kyriasis.com>
# Maintainer: BlackIkeEagle <ike DOT devolder AT gmail DOT com>
# Contributor: Ivan Shapovalov <intelfx@intelfx.name>

_py="python"
_pkg="wa-crypt-tools"
pkgname="${_pkg}"
_commit="c0cf95b6acda292215e33d467f13aa5a8d35cc20"
pkgver="0.0.9.r0.${_commit}"
pkgrel=1
pkgdesc='Manage WhatsApp .crypt12, .crypt14 and .crypt15 files.'
_http="https://github.com"
_ns="ElDavoo"
url="${_http}/${_ns}/${_pkg}"
arch=(
  'x86_64'
  'arm'
  'aarch64'
  'i686'
  'powerpc'
)
license=(
  'BSD'
)
depends=(
  "${_py}"
)
makedepends=(
  "${_py}-setuptools"
  "${_py}-setuptools-scm"
  "${_py}-build"
  "${_py}-installer"
)
provides=(
  "${_py}-${_pkg}"
)
source=(
  "${pkgname}-${pkgver}.tar.gz::${url}/archive/${_commit}.zip"
)
sha512sums=(
  'a9657c706f4e030012c3b6d18f61b4fda5a830e8bd04d9569eb902a76f0ad648e27739b2fb4a74c70e3a4904f3c4744ef99e70a5b3a50841479e9f8b4bb1da94'
)

build() {
  cd \
    "${_pkg}-${_commit}"
  # CC="gcc" \
  "${_py}" \
    -m \
      build \
    --no-isolation
}

package() {
  cd \
    "${_pkg}-${_commit}"
  # CC="gcc" \
  "${_py}" \
    -m \
      installer \
      --destdir="${pkgdir}" \
      dist/*.whl
  install \
    -Dm644 \
    LICENSE \
    "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
