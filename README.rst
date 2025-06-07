## Building
1. checkout the latest "fedora" stream e.g. f42
2. Pull the sources and build an SRPM `fedpkg srpm`
3. Extract the SRPM `rpmbuild -Uvh <name>`
4. Build, my preference `time rpmbuild -bb -D 'without_efiuki 0' --without debuginfo --with baseonly --target=x86_64 kernel.spec 2>&1 | tee rpm-out`


===================
The Kernel dist-git
===================

The kernel is maintained in a `source tree`_ rather than directly in dist-git.
The specfile is maintained as a `template`_ in the source tree along with a set
of build scripts to generate configurations, (S)RPMs, and to populate the
dist-git repository.

The `documentation`_ for the source tree covers how to contribute and maintain
the tree.

If you're looking for the downstream patch set it's available in the source
tree with "git log master..ark-patches" or
`online`_.

Each release in dist-git is tagged in the source repository so you can easily
check out the source tree for a build. The tags are in the format
name-version-release, but note release doesn't contain the dist tag since the
source can be built in different build roots (Fedora, CentOS, etc.)

.. _source tree: https://gitlab.com/cki-project/kernel-ark.git
.. _template: https://gitlab.com/cki-project/kernel-ark/-/blob/os-build/redhat/kernel.spec.template
.. _documentation: https://gitlab.com/cki-project/kernel-ark/-/wikis/home
.. _online: https://gitlab.com/cki-project/kernel-ark/-/commits/ark-patches
