####################################################################################
#     >>  Maintained by team Vitunix (https://github.com/vitunix)  <<              #
#             >> A Simple and lightweight Arch based distro <<                     #
#             -----> Mail us at (vitunix@proton.me) <-----                         #
#     ----> configured by heapbytes (https://github.com/heapbytes) <-----          #
####################################################################################
#
# Developer: G0urav <https://github.com/heapbytes>
#

pkgname=vitunix-bspwm
pkgver=1.0
pkgrel=1
pkgdesc="BSPWM Config For Vitunix"
arch=('any')
url="https://github.com/vitunix/vitunix-bspwm"
license=('GPL3')
install=${pkgname}.install

depends=(
	'bspwm' 'sxhkd' 'alacritty' 'thunar' 'neovim' 'xdo'
	'rofi' 'polybar' 'dunst' 'mpd' 'mpc' 'maim' 'xqp'
	'xclip' 'feh' 'ksuperkey' 'betterlockscreen'
	'xfce4-power-manager' 'xsettingsd' 'xorg-xsetroot'
	'wmname'
)

prepare() {

	cp -af ../config/. ${srcdir}

}

package() {

	local config_dir=${pkgdir}/etc/skel/.config
	local bspwm_dir=${config_dir}/bspwm
	local dunst_dir=${config_dir}/dunst
	local sxhkd_dir=${config_dir}/sxhkd
  local vitunix_dir=${config_dir}/vitunix-bin

	mkdir -p "$config_dir" "$bspwm_dir" "$dunst_dir" "$sxhkd_dir" "$vitunix_dir"

	cp -r ${srcdir}/*	"$config_dir"

	chmod +x "$vitunix_dir"/*.sh
	# chmod +x "$bspwm_dir"/rofi/bin/*

	install -Dm 755 ${srcdir}/bspwm/bspwmrc   			"$bspwm_dir"/bspwmrc
	#install -Dm 644 ${srcdir}/picom/picom.conf   		"${srcdir}"/picom.conf
	# install -Dm 644 ${srcdir}/dunst/dunstrc   			"$config_dir"/dunst/dunstrc
	install -Dm 644 ${srcdir}/bspwm/sxhkdrc        	    "$config_dir"/sxhkd/sxhkdrc
	
}
