# CMstscAdvSettings::CreateExplicitPathList(ushort const *)

- ea: `0x1803e5c34`
- end: `0x1803e5ef7`
- name: `?CreateExplicitPathList@CMstscAdvSettings@@AEAAPEAGPEBG@Z`
- size: `707`
- prototype: `unsigned __int16 *(CMstscAdvSettings *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1803e8830`

## callees

- `0x18008a2c0`
- `0x18022312c`
- `0x1803e5c34`
- `0x180688f3e`
- `0x180688fc0`

## import_xrefs

- `msvcrt!wcsstr` at `0x1803e5d08`
- `msvcrt!wcsstr` at `0x1803e5d08`
- `KERNEL32!LocalAlloc` at `0x1803e5d5e`
- `KERNEL32!LocalAlloc` at `0x1803e5e16`
- `KERNEL32!LocalAlloc` at `0x1803e5d5e`
- `KERNEL32!LocalAlloc` at `0x1803e5e16`
- `KERNEL32!LocalFree` at `0x1803e5d81`
- `KERNEL32!LocalFree` at `0x1803e5edb`
- `KERNEL32!LocalFree` at `0x1803e5ee9`
- `KERNEL32!LocalFree` at `0x1803e5d81`
- `KERNEL32!LocalFree` at `0x1803e5edb`
- `KERNEL32!LocalFree` at `0x1803e5ee9`
- `KERNEL32!GetSystemDirectoryW` at `0x1803e5d2e`
- `KERNEL32!GetSystemDirectoryW` at `0x1803e5d2e`
- `ADVAPI32!RegOpenKeyExW` at `0x1803e5ca0`
- `ADVAPI32!RegOpenKeyExW` at `0x1803e5ca0`
- `ADVAPI32!RegQueryValueExW` at `0x1803e5ce5`
- `ADVAPI32!RegQueryValueExW` at `0x1803e5ce5`
- `ADVAPI32!RegCloseKey` at `0x1803e5d1b`
- `ADVAPI32!RegCloseKey` at `0x1803e5d1b`

## string_xrefs

- `0x1803e5cd6`: `vdllpath`

## pseudocode

```c

```
