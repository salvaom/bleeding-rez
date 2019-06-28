
<img width=300 src=https://user-images.githubusercontent.com/2152766/59975170-e925e880-95ac-11e9-9751-c37ff554b5f1.png>

A [Rez](https://github.com/nerdvegas/rez) superset, with all [feature branches](https://github.com/mottosso/bleeding-rez/branches/all?utf8=%E2%9C%93&query=feature%2F) merged, editable [wiki](https://github.com/mottosso/bleeding-rez/wiki) and independent [roadmap](https://github.com/mottosso/bleeding-rez/wiki/Bleeding-Roadmap-2019).

<br>

#### Build Status

<table>
    <tr>
        <td><code>master</code></td>
        <td width=150px><a href=https://mottosso.visualstudio.com/bleeding-rez/_build?definitionId=1><img src=https://img.shields.io/azure-devops/build/mottosso/df4341a8-04df-420f-9aa6-91a53513dd14/1/master.svg?label=Windows></a></td>
        <td width=150px><a href=https://mottosso.visualstudio.com/bleeding-rez/_build?definitionId=1><img src=https://img.shields.io/azure-devops/build/mottosso/df4341a8-04df-420f-9aa6-91a53513dd14/1/master.svg?label=Linux></a></td>
        <td width=150px><a href=https://mottosso.visualstudio.com/bleeding-rez/_build?definitionId=1><img src=https://img.shields.io/azure-devops/build/mottosso/df4341a8-04df-420f-9aa6-91a53513dd14/1/master.svg?label=MacOS></a></td>
    </tr>
    <tr>
        <td><code>dev</code></td>
        <td width=150px><a href=https://mottosso.visualstudio.com/bleeding-rez/_build?definitionId=1><img src=https://img.shields.io/azure-devops/build/mottosso/df4341a8-04df-420f-9aa6-91a53513dd14/1/dev.svg?label=Windows></a></td>
        <td width=150px><a href=https://mottosso.visualstudio.com/bleeding-rez/_build?definitionId=1><img src=https://img.shields.io/azure-devops/build/mottosso/df4341a8-04df-420f-9aa6-91a53513dd14/1/dev.svg?label=Linux></a></td>
        <td width=150px><a href=https://mottosso.visualstudio.com/bleeding-rez/_build?definitionId=1><img src=https://img.shields.io/azure-devops/build/mottosso/df4341a8-04df-420f-9aa6-91a53513dd14/1/dev.svg?label=MacOS></a></td>
    </tr>
</table>

![](https://badge.fury.io/py/bleeding-rez.svg)

<br>

### Ecosystem

A small but growing number of companion projects for bleeding- and nerdvegas-rez.

- `rez-installz` - Native package manager for bleeding-rez
- [`rez-localz`](https://github.com/mottosso/rez-localz) - Package localisation from network or cloud storage
- [`rez-scoopz`](https://github.com/mottosso/rez-scoopz) - Install from [500+ system packages](https://github.com/ScoopInstaller/Main/tree/master/bucket) for Windows as a Rez package
- [`rez-pipz`](https://github.com/mottosso/rez-pipz) - Build and install any [PyPI](https://pypi.org) compatible project as a Rez package
- `rez-cmakez` - Build your projects using CMake
- `rez-yumz` - Install from a selection of [80,000+ RPM packages](https://centos.pkgs.org/7/centos-x86_64/) and counting
- `rez-vcpkgz` - Install any of the [1000+ C++ libraries](https://github.com/Microsoft/vcpkg/tree/master/ports) as a Rez package
- `rez-conanz` - Install any of the [200+ C++ libraries](https://conan.io/) as a Rez package
- `rez-allspark` - Visual application launcher and Rez debugging tool
- [`rez-for-projects`](https://github.com/mottosso/rez-for-projects) - A set of example packages for use of Rez (and Allspark) with project and application configurations
- `rez-performance` - Test the impact of x-number of packages with y-level of complexity in your network environment to make better integration and deployment decisions.
- `rez-releaz` - Secure package releases with Git integration
- `rez-guiz` - Old-school visual editor of Rez contexts
- `rez-flowchartz` - Visualise package dependencies as a flowchart, useful for debugging
- `rez-...` Your project here!

<br>

### Quickstart

Choose your installation method.

<details>
  <summary>Simple</summary>
<table>
<tr><td>
<br>

**Simple** The simple approach is well suited for beginners and those looking to learn more about Rez and whether it is suited to their problem and environment.

</td></tr>
<tr><td>

```bash
$ pip install bleeding-rez
$ rez --version
2.31.0
```
</td></tr>
<tr><td>

<br>

**Advantages**

- **User-friendly and familiar installation method** Everybody loves pip
- **Inception** Make `bleeding-rez` a Rez package with [pipz](https://github.com/mottosso/rez-pipz)

</td></tr>
</table>

</details>
<details>
  <summary>Recommended</summary>

<table>
<tr><td>
<br>

**Recommended** The recommended approach is better suited for live production, where you've committed to Rez and want precision and control.

</td></tr>
<tr><td>

```bash
$ python -m virtualenv rez
$ rez\Scripts\activate  # *
(rez) $ pip install bleeding-rez
```

> Use `source rez/bin/activate` on Linux and OSX

**Advanced**

You may alternatively install directly from the GitHub repository using one of the following commands.

```bash
$ pip install git+https://github.com/mottosso/bleeding-rez.git
$ pip install git+https://github.com/mottosso/bleeding-rez.git@dev
$ pip install git+https://github.com/mottosso/bleeding-rez.git@feature/windows-alias-additional-argument
```

</td></tr>
<tr><td>
<br>

**Optional**

Virtualenv exposes a `python` and `pip` binary on your `PATH` which make them available from within a Rez context despite no `python` or `pip` package having been included. For additional protection, you can create a separate directory with only Rez binaries and expose this on your `PATH` instead.

<details>
  <summary>Windows</summary>

```bash
(rez) $ mkdir rez\Scripts\rez
(rez) $ cp rez\Scripts\rez*.exe rez\Scripts\rez\
(rez) $ deactivate
$ set PATH=%cd%\rez\Scripts\rez
$ rez env
> $ python
'python' is not recognized as an internal or external command,
operable program or batch file.
```
</details>

<details>
  <summary>Linux and MacOS</summary>

```bash
(rez) $ mkdir rez\bin\rez
(rez) $ cp rez\bin\rez* rez\bin\rez\
(rez) $ deactivate
$ export PATH=$(pwd)\rez\bin\rez
$ rez env
> $ python
-bash: python: command not found
```

</details>
<br>

**Advantages**

- **Isolated PATH** No interference from external binaries in your `Scripts/` Python directory.
- **Isolated site-packages** No interference from system-wide Python packages

</td></tr>
</table>
</details>
<details>
  <summary>Developer</summary>

<table>
<tr><td>
<br>

**Developer** The developer approach maintains Git history and enables you to contribute back to this project (yay!)

</td></tr>
<tr><td>

```bash
$ python -m virtualenv rez-dev
$ rez-dev\Scripts\activate
(rez) $ git clone https://github.com/mottosso/bleeding-rez.git
(rez) $ cd rez
(rez) $ pip install . -e
```

> Use `. rez-dev\bin\activate` on Linux and MacOS

</td></tr>
<tr><td>
<br>

**Advantages**

- **Git history** History is maintained and you're all set to contribute back to the project

</td></tr>
</table>
</details>
<br>

This installs the Rez command line tools.

Next, you'll need to create some essential Rez packages.

```bash
$ rez bind platform
$ rez bind arch
$ rez bind os
```

Now try creating an empty environment.

```bash
$ rez env
> $ echo Hello World!
Hello World!
```

The `>` character denotes that you are in a resolved environment, great job!

<br>

### Changes

This project is fully compatible with the original Rez and contains, amongst others, these additional features.

<table>
    <tr>
        <th width="25%">Feature</th>
        <th>Description</th>
        <th></th>
    </tr>
    <tr></tr>
    <tr>
        <td>Python 2 and 3</td>
        <td>

Support has been updated from Python 2.7 to 2.7-3.7 and beyond.

</td>
        <td><a href=https://github.com/nerdvegas/rez/pull/629><i>PR</i></a></td>
    <tr></tr>
    </tr>
    <tr>
        <td>Continuous Integration</td>
        <td>

Every commit is run against each supported platform and version of Python.

**OS's**

- Windows 10
- Ubuntu 16 (Xenial)
- MacOS 10.13 (Mojave)

**Python's**

- Python 2.7
- Python 3.5
- Python 3.6
- Python 3.7

</td>
<td></td>
<tr></tr>
    </tr>
    <tr>
        <td>PowerShell</td>
        <td>

The native `cmd` integration of the original Rez supports environment variable length up-to 2,000 characters, which may cause issues in particular with `PATH` and `PYTHONPATH`. PowerShell supports lengths up-to 32,000 characters.

</td>
        <td><a href=https://github.com/nerdvegas/rez/pull/644><i>PR</i></a></td>
    <tr></tr>
    </tr>
    <tr>
        <td>Rez & PyPI</td>
        <td>

bleeding-rez is now a standard pip package and available on PyPI.

```bash
$ pip install bleeding-rez
```

`--target` is supported with one caveat on Windows; the destination must be available on your PYTHONPATH either globally or for the user. It cannot be added from within a console, as Rez is looking at your registry for where to find it.

```bash
$ pip install bleeding-rez --target ./some_dir
$ setx PYTHONPATH=some_dir
```
</td>
        <td><a href=https://github.com/mottosso/bleeding-rez/tree/feature/windows-appveyor><i>link</i></a></td>
    <tr></tr>
    </tr>
        <td>Preprocess function</td>
        <td>

`rezconfig.py` can take a `preprocess` function, rather than having to create and manage a separate module and `PYTHONPATH`</td>
        <td><a href=https://github.com/mottosso/bleeding-rez/tree/feature/windows-appveyor><i>link</i></a></td>
    </tr>
    <tr></tr>
    <tr>
        <td>Windows Tests</td>
        <td>Tests now run on both Windows and Linux</td>
        <td><a href=https://github.com/mottosso/bleeding-rez/tree/feature/windows-appveyor><i>link</i></a></td>
    </tr>
    <tr></tr>
    <tr>
        <td>OR-versions on Windows</td>
        <td>

Now you can use `rez-2.28|2.29` on Windows, like you can on Linux.

</td>
        <td><a href=https://github.com/nerdvegas/rez/pull/647><i>PR</i></a></td>
    </tr>
    <tr>
        <td>Preprocess function</td>
        <td>

`rezconfig.py` can take a `preprocess` function, rather than having to create and manage a separate module and `PYTHONPATH`</td>
        <td><a href=https://github.com/mottosso/bleeding-rez/tree/feature/windows-appveyor><i>link</i></a></td>
    </tr>
    <tr>
        <td>Aliases & Windows</td>
        <td>

The `package.py:commands()` function `alias` didn't let Windows-users pass additional arguments to their aliases (doskeys)</td>
        <td><a href=https://github.com/mottosso/bleeding-rez/tree/feature/windows-alias-additional-arguments><i>link</i></a></td>
    </tr>
    <tr></tr>
    <tr>
        <td>Pip & Usability</td>
        <td>

As it happens, no one is actually using the `rez pip` command. It has some severe flaws which makes it unusable on anything other than a testing environment on a local machine you don't update.</td>
        <td><a href=https://github.com/mottosso/bleeding-rez/tree/feature/useful-pip><i>link</i></a></td>
    </tr>
    <tr></tr>
    <tr>
        <td>`Request.__iter__`</td>
        <td>

You can now iterate over `request` and `resolve` from within your `package.py:commands()` section, e.g. `for req in request: print(req)`
<td><a href=https://github.com/mottosso/bleeding-rez/tree/feature/iterate-over-request><i>link</i></a></td>
    </tr>
    <tr></tr>
    <tr>
        <td>Pip & Wheels</td>
        <td>

`rez pip` now uses wheels when available, avoiding needless a build step</td>
        <td><a href=https://github.com/mottosso/bleeding-rez/tree/feature/pip-wheels-windows><i>link</i></a></td>
    </tr>
    <tr></tr>
    <tr>
        <td>Pip & Multi-install</td>
        <td>

`rez pip` can now take multiple packages, e.g. `rez pip --install six requests`</td>
        <td><a href=https://github.com/mottosso/bleeding-rez/tree/feature/pip-multipleinstall><i>link</i></a></td>
    </tr>
    <tr></tr>
    <tr>
        <td>Pip & `--prefix`</td>
        <td>

`rez pip` can now take a `--prefix` argument, letting you install packages wherever</td>
        <td><a href=https://github.com/mottosso/bleeding-rez/tree/feature/pip-prefix><i>link</i></a></td>
    </tr>
    <tr>
        <td>PyYAML and Python 3</td>
        <td>

Prior to this, you couldn't use PyYAML and Python 3 as Rez packages.</td>
        <td><a href=https://github.com/mottosso/bleeding-rez/tree/feature/pip-multipleinstall><i>link</i></a></td>
    </tr>
    <tr>
        <td>Auto-create missing repository dir</td>
        <td>

New users no longer have to worry about creating their default package repository directory at `~/packages`, which may seem minor but was the resulting traceback was the first thing any new user would experience with Rez.</td>
        <td><a href=https://github.com/nerdvegas/rez/pull/623><i>PR</i></a></td>
    </tr>
    <tr>
        <td>Cross-platform rez-bind python</td>
        <td>

rez-bind previously used features unsupported on Windows to create the default Python package, now it uses the cross-compatible `alias()` command instead.</td>
        <td><a href=https://github.com/nerdvegas/rez/pull/624><i>PR</i></a></td>
    </tr>
    <tr>
        <td>No more "Terminate Batch Job? (Y/N)"</td>
        <td>

Rez used to create a .bat file which was later used as the Rez context. Exiting a .bat file using CTRL+C prompts the user for a "Terminate Batch Job? (Y/N)", adding some extra annoyance to exiting a Rez context.</td>
        <td><a href=https://github.com/nerdvegas/rez/pull/626><i>PR</i></a></td>
    </tr>
</table>

<br>

### PRs

Along with these pull-requests from the original repository, as they can take a while to get through (some take years!)

<table>
    <tr>
        <th>

Change</th>
        <th>Description</th>
        <th></th>
    </tr>
    <tr></tr>
    <tr>
        <td>Support for inverse version range</td>
        <td>E.g. `requires = ["urllib3>=1.21.1,<1.23"]`</td>
        <td>[#618](https://github.com/nerdvegas/rez/pull/618)</td>
    </tr>
    <tr></tr>
    <tr>
        <td>Misc Improvements</td>
        <td>

> Make logging less destructive.

Previously, when configured in `rez.__init__` rez's logging (when used as
an api) would clobber anything set by the calling application.  Push log
configuration down into the cli only so it's more acceptale to api
usage.

> Allow for packages which have no versions.

> Fix typo.

> Catch exception raised on Windows.

On Windows it is likely the local packages path is on a different drive
to the release packages path.  This causes an exception to be raised in
this function.

> Add missing unimplmented methods.

> Reset to base configuration, some of our site specific configuration …

…slipped out on a recent merge.

> Clean up syntax.

> This helps external projects (that use FindPackage from CMake) locate…

… things installed by rez.

> Various improvements to git vcs repository.

* Handle the case where we might be both ahead of and behind the remote.
* Fix docstrings.
* Add a check for untracked files.  This was in rez 1 although does make
  things more strict
* Handle if the changelog is broken - if history is rewritten or the
  repository moves (in our case git to github) the changelog can fail
  ungracefully.
* Don't let the export function leave you in a different directory to
  which you started - that is bad for tests etc.            

</td>
<td>

[#204](https://github.com/nerdvegas/rez/pull/204)</td>
</tr>
</table>

<br>

### Backwards Compatibility

Some deprecated features have been disabled by default. If you encounter any issues, here is how can re-enable them.

**rezconfig.py**

```python
# bleeding-rez does not affect file permissions at all
# as it can cause issues on SMB/CIFS shares
make_package_temporarily_writable = True

# bleeding-rez does not support Rez 1 or below
disable_rez_1_compatibility = False
```

<br>

### FAQ

##### <blockquote>Should I use nerdvegas/rez or bleeding-rez?</blockquote>

Rez isn't for everyone, and neither is bleeding-rez.

- If you've already committed to nerdvegas/rez and have built your pipeline on it, stick with nerdvegas/rez
- If you've just gotten started using Rez, use bleeding-rez.

##### <blockquote>Why does bleeding-rez exist?</blockquote>

bleeding-rez started off as a fork from which to make PRs to nerdvegas/rez, but eventually started to diverge. Now it's meant as a fire up the butt of the project. Competition breeds innovation.

##### <blockquote>Are there any similar projects to bleeding-rez?</blockquote>

Yes, to some extent. Have a look at these.

| Project | Scope | Shared Packages | Commercial
|:--------|:------|:----------------|:-----------------
| [bleeding-rez]()                        | ESAP | x
| [rez]()                                 | ES | x
| [Stash]()                               | ESAP | x | x
| [be]()                                  | ESAP | x
| [Ecosystem]()                           | E | x
| [add]()                                 | E | x
| [avalon]()                              | EA | x
| [miniconda]()                           | S |
| [virtualenv]()                          | S | 
| [venv]()                                | S |
| [pipenv]()                              | S |
| [hatch](https://github.com/ofek/hatch)  | S |
| [nixpkgs](https://nixos.org/nixpkgs/)   | S | x
| [scoop]()                               | S | 

- **Project** Name of project
- **Shared** Whether packages are re-installed per environment, or shared amongst them
- **Scope** Usecases covered by project
    - **E** Environment management, per-package control over what is should look like when requested
    - **S** Software builds, e.g. via cmake
    - **A** Application versioning, along with associated dependencies
    - **P** Project versioning, with associated software and application dependencies

##### <blockquote>How can I get involved?</blockquote>

If you would like to contribute code you can do so through GitHub by forking the repository and sending a pull request. Please follow these guidelines:

1.  Always retain backwards compatibility, unless a breaking change is necessary. If it is necessary, the associated release notes must make this explicit and obvious
2.  Make every effort to follow existing conventions and style
3.  Follow [PEP8](https://www.python.org/dev/peps/pep-0008/)
4.  Follow the [Google Python Style Guide](https://google.github.io/styleguide/pyguide.html)
    for docstrings
5.  Use *spaces*, not *tabs*
6.  Update the [bleeding-rez version](https://github.com/mottosso/bleeding-rez/blob/master/src/bleeding-rez/utils/_version.py) appropriately, and follow [semantic versioning](https://semver.org/);
7.  Update [the changelog](https://github.com/mottosso/bleeding-rez/blob/master/CHANGELOG.md); see the section below for more details
8.  Use [this format](https://help.github.com/articles/closing-issues-using-keywords/) to mention the issue(s) your PR closes
9.  Add relevant tests to demonstrate that your changes work
10. Add relevant documentation (see [here](https://github.com/mottosso/bleeding-rez/blob/master/wiki/README.md)) to document your changes, if applicable.

##### <blockquote>How do I report a bug?</blockquote>

If you report a bug, please ensure to specify the following:

1.  Rez version (e.g. 2.18.0);
2.  Platform and operating system you were using;
3.  Contextual information (what were you trying to do using Rez);
4.  Simplest possible steps to reproduce.
