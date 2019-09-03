cmake_minimum_required(VERSION 3.14)
project(myrealsense)

set(CMAKE_CXX_STANDARD 14)
set(realsense2_DIR "/usr/local/lib/cmake/realsense2")

find_package(OpenCV REQUIRED)
#find_package(realsense2 REQUIRED)

include_directories(${realsense2_INCLUDE_DIRS})
#include_directories(/usr/local/include)

link_directories(/usr/local/lib)

add_executable(myrealsense
        camera.cpp)

target_link_libraries(myrealsense
        ${OpenCV_LIBS}
#        realsense2
        realsense2
        )

add_executable(measure
        measure.cpp)

target_link_libraries(measure
        ${OpenCV_LIBS}
        #        realsense2
        realsense2
        )
