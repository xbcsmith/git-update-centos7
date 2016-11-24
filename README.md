# git-update-centos7
Updating git for CentOS 7 machines

Rebuild git 2.9.x for C7 from Fedora 25 sources.

## install deps 
  sudo yum install xmlto desktop-file-utils emacs expat-devel gettext gnupg2 libcurl-devel libgnome-keyring-devel pcre-devel perl-generators perl-Test openssl-devel pkgconfig-bash-completion systemd python perl-ExtUtils-MakeMaker

## install rpm-build
  sudo yum install rpm-build rpmdevtools

## install source
  rpm -ivh http://ftp.linux.ncsu.edu/pub/fedora/linux/releases/25/Everything/source/tree/Packages/g/git-2.9.3-1.fc25.src.rpm


## build sources
  rpmbuild -ba rpmbuild/SPECS/git.spec

## only install basics
  cp ~/rpmbuild/RPMS/noarch/perl-Git-*.centos.noarch.rpm install/
  cp ~/rpmbuild/RPMS/x86_64/git-core-* install/
  cp ~/rpmbuild/RPMS/x86_64/git-daemon-*.x86_64.rpm install/
  cp ~/rpmbuild/RPMS/x86_64/git-2.9.3-1.el7.centos.x86_64.rpm install/

  rpm -ivh *.rpm

