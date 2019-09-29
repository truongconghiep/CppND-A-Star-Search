cmake_minimum_required(VERSION 2.6)
project(A_Star_Search)

find_package(Curses REQUIRED)
include_directories(${CURSES_INCLUDE_DIRS})

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} ${_FORTIFY_SOURCE_PREFIX}-U_FORTIFY_SOURCE ${_FORTIFY_SOURCE_PREFIX}-D_FORTIFY_SOURCE=1")

include_directories(include)
set(sources src/main.cpp)

add_executable(A_Star_Search ${sources} )

set_property(TARGET A_Star_Search PROPERTY CXX_STANDARD 17)
target_link_libraries(A_Star_Search ${CURSES_LIBRARIES})
