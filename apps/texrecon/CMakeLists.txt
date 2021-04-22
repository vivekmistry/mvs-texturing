file (GLOB HEADERS "*.h")
file (GLOB SOURCES "[^_]*.cpp")

set(BIN texrecon)

add_executable(${BIN} ${SOURCES})
set_property(TARGET ${BIN} PROPERTY INTERPROCEDURAL_OPTIMIZATION True)
include_directories(${TBB_INCLUDE_DIRS})
target_link_libraries(${BIN} tex ${TBB_LIBRARIES} ${MVE_MVE_LIBRARY} ${MVE_UTIL_LIBRARY})
install(TARGETS ${BIN} RUNTIME DESTINATION bin)
