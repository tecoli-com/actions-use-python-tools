# actions-use-python-tools

![actions-use-python-tools](https://github.com/office-tecoli/actions-use-python-tools/actions/workflows/test.yml/badge.svg)

This GitHub action isntall python-based packages and cache them for
later use.  When executed next time with same package list, and any
other environment are not changed, installed files are extracted from
the cached archive.

When valid cached archive is not found, all packages are installed by
`pip3` command.

Output is same as [`@actions/cache`](https://github.com/actions/cache).

## Usage

```yaml
# inputs:
#   tools:   { required: true,  type: string }
#   version: { required: false, type: string, default: 3 }
#   cache:   { required: false, type: string, default: yes }
#   key:     { required: false, type: string }

- uses: office-tecoli/actions-use-python-tools@v0
  with:

    # python packages
    tools: ''

    # python version
    # Default: 3
    version: '3'

    # Cache strategey
    #
    # yes:      activate cache
    # no:       no cache
    # workflow: effective within same workflow (mainly for test)
    #
    cache: yes

    # Additional cache key
    key: ''
```

## Example

```yaml
- uses: office-tecoli/actions-use-python-tools@v0
  with:
    tools: legit
```

## Issues

- Always install as a root.  I could't find a good way to install
  under user directory across ubuntu and macos.

## See Also

### [office-tecoli/actions](https://github.com/office-tecoli/actions)
