add_executable( generate_empty_blocks main.cpp )
if( UNIX AND NOT APPLE )
  set(rt_library rt )
endif()

target_link_libraries( generate_empty_blocks
                       PRIVATE graphene_app graphene_chain graphene_egenesis_none fc ${CMAKE_DL_LIBS} ${PLATFORM_SPECIFIC_LIBS} )
################################################yp add#############################################################
target_include_directories( generate_empty_blocks
                            PUBLIC "${CMAKE_SOURCE_DIR}/libraries/fc/include" )
###################################################################################################################

install( TARGETS
   generate_empty_blocks

   RUNTIME DESTINATION bin
   LIBRARY DESTINATION lib
   ARCHIVE DESTINATION lib
)
