SUBDIRS = perl src doc man
PACKAGE = info-dynamic-scheduler-lsf
VERSION = $(shell cat info-dynamic-scheduler-lsf.spec| grep "Version:"| cut -f 2 -d " ")
SOURCES=aclocal.m4 btools README AUTHORS src doc man autogen.sh ChangeLog configure.in ${PACKAGE}.spec Makefile.am   NEWS  TODO COPYING INSTALL perl btools.src.tgz

####################################################################
# Prepare
####################################################################
all: dist

dist: 
	@tar  --gzip -cf btools.src.tgz btools/
	@tar  --gzip -cf ${PACKAGE}-${VERSION}.tar.gz ${SOURCES}

rpm: dist
	@rpmbuild -ta ${PACKAGE}-${VERSION}.tar.gz

sources: dist

srpm: dist 
	@rpmbuild -ts ${PACKAGE}-${VERSION}.tar.gz

ai5: dist 
	@rpmbuild -ts --define 'dist .ai5' ${PACKAGE}-${VERSION}.tar.gz

ai6: dist 
	@rpmbuild -ts --define 'dist .ai6' ${PACKAGE}-${VERSION}.tar.gz

el6: dist 
	@rpmbuild -ts --define 'dist .el6' ${PACKAGE}-${VERSION}.tar.gz

clean:
	rm -f btools.src.tgz ${PACKAGE}-${VERSION}.tar.gz

distclean: clean
####################################################################
# Documentation
####################################################################

doc: man html

man: prepare

html: prepare
