set(TEST_OPERATORS_SOURCES
    test_operators.cc
)

# build static libray
add_executable(test_operators ${TEST_OPERATORS_SOURCES})
add_dependencies(test_operators tensor)
target_link_libraries(test_operators tensor ${Boost_LIBRARIES})

set(TEST_SLICE_SOURCES
    test_slice.cc
)


add_executable(test_slice ${TEST_SLICE_SOURCES})
add_dependencies(test_slice tensor)
target_link_libraries(test_slice tensor ${Boost_LIBRARIES})

if(ENABLE_CYCLOPS)
    set(TEST_CYCLOPS_SOURCES
        test_cyclops.cc
    )

    add_executable(test_cyclops ${TEST_CYCLOPS_SOURCES})
    add_dependencies(test_cyclops tensor)
    target_link_libraries(test_cyclops tensor ${Boost_LIBRARIES})
endif()

set(TEST_HF_SOURCES
    test_hf.cc
)

# build static libray
add_executable(test_hf ${TEST_HF_SOURCES})
add_dependencies(test_hf tensor)
target_link_libraries(test_hf tensor ${Boost_LIBRARIES})

set(TEST_BLOCKS_SOURCES
    test_blocks.cc
)

# build static libray
add_executable(test_blocks ${TEST_BLOCKS_SOURCES})
add_dependencies(test_blocks tensor)
target_link_libraries(test_blocks tensor ${Boost_LIBRARIES})

configure_file(test.32 test.32 COPYONLY)
configure_file(test.33 test.33 COPYONLY)
configure_file(test.34 test.34 COPYONLY)
configure_file(test.35 test.35 COPYONLY)
