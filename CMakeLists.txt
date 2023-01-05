cmake_minimum_required(VERSION 3.2)
PROJECT( tutors )

SET( PROGRAMS fog lightmaterial lightposition projection shapes texture
transformation )

FIND_PACKAGE( GLUT )
find_package(OpenGL REQUIRED)


FOREACH( program ${PROGRAMS} )
  ADD_EXECUTABLE( ${program} ${program}.c glm.c )
  TARGET_LINK_LIBRARIES( ${program} ${GLUT_LIBRARY} ${OPENGL_LIBRARY} -lm)
ENDFOREACH( program )
