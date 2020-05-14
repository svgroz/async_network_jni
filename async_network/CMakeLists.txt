# CMakeList.txt : CMake project for async_network, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

find_package(JNI REQUIRED)
include_directories(${JNI_INCLUDE_DIRS})

set(Boost_USE_STATIC_LIBS ON)
find_package(Boost 1.71.0 REQUIRED COMPONENTS
             date_time regex)

include_directories(${Boost_INCLUDE_DIRS})

# Add source to this project's executable.
add_executable (async_network
	"async_network.cpp" "async_network.h" 
	)


target_link_libraries(async_network Boost::date_time Boost::regex)

# TODO: Add tests and install targets if needed.
