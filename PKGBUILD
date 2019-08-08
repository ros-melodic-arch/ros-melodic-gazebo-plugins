# Script generated with import_catkin_packages.py
# For more information: https://github.com/bchretien/arch-ros-stacks
pkgdesc="ROS - Robot-independent Gazebo plugins for sensors, motors and dynamic reconfigurable components."
url='http://gazebosim.org/tutorials?cat=connect_ros'

pkgname='ros-melodic-gazebo-plugins'
pkgver='2.8.5'
arch=('any')
pkgrel=1
license=('BSD, Apache 2.0')

ros_makedepends=(ros-melodic-diagnostic-updater
  ros-melodic-rosgraph-msgs
  ros-melodic-std-srvs
  ros-melodic-cv-bridge
  ros-melodic-rosconsole
  ros-melodic-tf
  ros-melodic-std-msgs
  ros-melodic-gazebo-msgs
  ros-melodic-catkin
  ros-melodic-gazebo-dev
  ros-melodic-geometry-msgs
  ros-melodic-dynamic-reconfigure
  ros-melodic-trajectory-msgs
  ros-melodic-nodelet
  ros-melodic-tf2-ros
  ros-melodic-urdf
  ros-melodic-nav-msgs
  ros-melodic-sensor-msgs
  ros-melodic-camera-info-manager
  ros-melodic-angles
  ros-melodic-roscpp
  ros-melodic-polled-camera
  ros-melodic-image-transport
  ros-melodic-message-generation
  ros-melodic-rospy)
makedepends=('cmake' 'ros-build-tools'
  ${ros_makedepends[@]})

ros_depends=(ros-melodic-diagnostic-updater
  ros-melodic-rosgraph-msgs
  ros-melodic-std-srvs
  ros-melodic-cv-bridge
  ros-melodic-rosconsole
  ros-melodic-tf
  ros-melodic-std-msgs
  ros-melodic-gazebo-msgs
  ros-melodic-geometry-msgs
  ros-melodic-trajectory-msgs
  ros-melodic-dynamic-reconfigure
  ros-melodic-message-runtime
  ros-melodic-nodelet
  ros-melodic-tf2-ros
  ros-melodic-urdf
  ros-melodic-nav-msgs
  ros-melodic-sensor-msgs
  ros-melodic-camera-info-manager
  ros-melodic-angles
  ros-melodic-roscpp
  ros-melodic-polled-camera
  ros-melodic-image-transport
  ros-melodic-gazebo-dev
  ros-melodic-rospy)
depends=(${ros_depends[@]})

_dir="gazebo_ros_pkgs-${pkgver}/gazebo_plugins"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros-simulation/gazebo_ros_pkgs/archive/${pkgver}.tar.gz")
sha256sums=('0b0f6eeaeca611ebe12ec0ea4388121098fdafee5ecc8d76c6ae69b8b8f14aed')

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/melodic/setup.bash ] && source /opt/ros/melodic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 3 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/melodic \
        -DPYTHON_EXECUTABLE=/usr/bin/python3 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python3.7m \
        -DPYTHON_LIBRARY=/usr/lib/libpython3.7m.so \
        -DPYTHON_BASENAME=.cpython-37m \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}
