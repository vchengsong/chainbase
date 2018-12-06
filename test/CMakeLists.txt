file(GLOB UNIT_TESTS "*.cpp")
add_executable( chainbase_test ${UNIT_TESTS}  )

find_package(Boost 1.57 REQUIRED COMPONENTS unit_test_framework)

target_link_libraries( chainbase_test  chainbase Boost::boost ${Boost_LIBRARIES} ${PLATFORM_SPECIFIC_LIBS} )
if(NOT Boost_USE_STATIC_LIBS)
  target_compile_definitions(chainbase_test PRIVATE "BOOST_TEST_DYN_LINK=1")
endif()
