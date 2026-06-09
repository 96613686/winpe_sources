# CGPWMI::NoWMIFilterOrFilterAllowed(HKEY__ *,int *,_GPOINFO *)

- ea: `0x180005e4c`
- end: `0x18000620d`
- name: `?NoWMIFilterOrFilterAllowed@CGPWMI@@SAKPEAUHKEY__@@PEAHPEAU_GPOINFO@@@Z`
- size: `961`
- prototype: `unsigned int __fastcall(HKEY hKey, int *, struct _GPOINFO *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180003800`

## callees

- `0x180005e4c`
- `0x180016640`
- `0x1800183d4`
- `0x18001ae40`
- `0x18001ae60`
- `0x18001ee6c`
- `0x18005334c`
- `0x18006da50`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006076`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800061ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800061ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005eb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005f83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005eb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005f83`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005ff9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006196`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005ff9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006196`

## string_xrefs

- `0x180005ef3`: `CGPWMI::NoWMIFilterOrFilterAllowed: failed to get the size of registry value with error: %d`
- `0x180005f23`: `CGPWMI::NoWMIFilterOrFilterAllowed: failed to get the size of registry value with error: %d`
- `0x180005fa8`: `CGPWMI::NoWMIFilterOrFilterAllowed: failed to get registry value with error: %d`
- `0x180005fd3`: `CGPWMI::NoWMIFilterOrFilterAllowed: failed to get registry value with error: %d`
- `0x180006096`: `CGPWMI::NoWMIFilterOrFilterAllowed: Impersonate to User Token failed with error: %d.`
- `0x1800060bb`: `CGPWMI::NoWMIFilterOrFilterAllowed: Impersonate to User Token failed with error: %d.`

## pseudocode

```c

```
