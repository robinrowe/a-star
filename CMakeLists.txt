# astar/CMakeLists.txt
# Copyright 2018 Robin.Rowe@cinepaint.org
# License open source MIT

cmake_minimum_required(VERSION 3.8)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

set(NAME astar)
project(${NAME})

set(SOURCES
	astar.cpp
	main.cpp
)

set(FLTK_DIR /Code/fltk)
include_directories(${FLTK_DIR} ${FLTK_DIR}/build)
link_directories(${FLTK_DIR}/build/lib/Debug)
if(win32)
add_definitions(-DWIN32)
endif()

add_executable(${NAME} ${SOURCES})

set(FLTK_LIBS
	fltk_formsd
	fltk_gld
	fltk_imagesd
	fltk_jpegd
	fltk_pngd
	fltk_zd
	fltkd
)

target_link_libraries(${NAME} ${FLTK_LIBS})

