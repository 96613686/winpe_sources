# CRegTreeOptions::_GetSetByRegKey(void *,ulong *,uchar *,ulong *,REG_CMD)

- ea: `0x180214fe4`
- end: `0x18021568f`
- name: `?_GetSetByRegKey@CRegTreeOptions@@IEAAKPEAXPEAKPEAE1W4REG_CMD@@@Z`
- size: `1707`
- prototype: `unsigned int __high(void *, unsigned int *, unsigned __int8 *, unsigned int *, enum REG_CMD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180215de8`

## callees

- `0x18000c530`
- `0x180214ce0`
- `0x180214fe4`
- `0x18054e310`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1802151e1`
- `msvcrt!_wcsicmp` at `0x18021542d`
- `msvcrt!_wcsicmp` at `0x180215448`
- `msvcrt!_wcsicmp` at `0x1802151e1`
- `msvcrt!_wcsicmp` at `0x18021542d`
- `msvcrt!_wcsicmp` at `0x180215448`
- `KERNEL32!LocalAlloc` at `0x180215301`
- `KERNEL32!LocalAlloc` at `0x180215577`
- `KERNEL32!LocalAlloc` at `0x180215301`
- `KERNEL32!LocalAlloc` at `0x180215577`
- `KERNEL32!LocalFree` at `0x180215373`
- `KERNEL32!LocalFree` at `0x1802155f9`
- `KERNEL32!LocalFree` at `0x180215373`
- `KERNEL32!LocalFree` at `0x1802155f9`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1802153f8`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180215407`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1802153f8`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180215407`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCreateKeyExW` at `0x18021523c`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCreateKeyExW` at `0x18021523c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x180215068`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x1802150aa`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x1802150ee`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x18021513d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x1802151c6`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x180215522`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x18021562d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x180215666`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x180215068`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x1802150aa`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x1802150ee`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x18021513d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x1802151c6`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x180215522`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x18021562d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x180215666`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x1802154a2`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x180215554`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x1802155ee`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x1802154a2`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x180215554`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x1802155ee`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x180215296`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x1802152e3`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x180215346`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x180215392`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x1802153eb`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x1802154d2`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x1802155a3`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x180215296`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x1802152e3`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x180215346`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x180215392`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x1802153eb`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x1802154d2`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x1802155a3`

## string_xrefs

- `0x180215123`: `RegPath`

## pseudocode

```c

```
