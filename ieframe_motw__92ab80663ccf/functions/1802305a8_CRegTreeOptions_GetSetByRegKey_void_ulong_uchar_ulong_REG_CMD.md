# CRegTreeOptions::_GetSetByRegKey(void *,ulong *,uchar *,ulong *,REG_CMD)

- ea: `0x1802305a8`
- end: `0x180230d07`
- name: `?_GetSetByRegKey@CRegTreeOptions@@IEAAKPEAXPEAKPEAE1W4REG_CMD@@@Z`
- size: `1887`
- prototype: `unsigned int __high(void *, unsigned int *, unsigned __int8 *, unsigned int *, enum REG_CMD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180231528`

## callees

- `0x180009610`
- `0x180230280`
- `0x1802305a8`
- `0x180591f80`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1802307c3`
- `msvcrt!_wcsicmp` at `0x180230a55`
- `msvcrt!_wcsicmp` at `0x180230a76`
- `msvcrt!_wcsicmp` at `0x1802307c3`
- `msvcrt!_wcsicmp` at `0x180230a55`
- `msvcrt!_wcsicmp` at `0x180230a76`
- `KERNEL32!LocalAlloc` at `0x1802308fb`
- `KERNEL32!LocalAlloc` at `0x180230bc6`
- `KERNEL32!LocalAlloc` at `0x1802308fb`
- `KERNEL32!LocalAlloc` at `0x180230bc6`
- `KERNEL32!LocalFree` at `0x180230979`
- `KERNEL32!LocalFree` at `0x180230c5e`
- `KERNEL32!LocalFree` at `0x180230979`
- `KERNEL32!LocalFree` at `0x180230c5e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180230a14`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180230a29`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180230a14`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180230a29`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCreateKeyExW` at `0x180230824`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCreateKeyExW` at `0x180230824`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x18023062c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x180230674`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x1802306be`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x180230713`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x1802307a2`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x180230b65`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x180230c98`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x180230cd7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x18023062c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x180230674`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x1802306be`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x180230713`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x1802307a2`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x180230b65`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x180230c98`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegQueryUSValueW` at `0x180230cd7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x180230ad9`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x180230b9d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x180230c4d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x180230ad9`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x180230b9d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHSetValueW` at `0x180230c4d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x180230884`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x1802308d7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x180230946`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x1802309a2`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x180230a01`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x180230b0f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x180230bfc`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x180230884`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x1802308d7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x180230946`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x1802309a2`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x180230a01`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x180230b0f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHQueryValueExW` at `0x180230bfc`

## string_xrefs

- `0x1802306f9`: `RegPath`

## pseudocode

```c

```
