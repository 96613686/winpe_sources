# SxRegReadString(HKEY__ *,ushort const *,CBsString *)

- ea: `0x18001a6c0`
- end: `0x18001a889`
- name: `?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, struct CBsString *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800298ec`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800192b4`
- `0x18001a6c0`
- `0x180023220`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a7aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a7aa`

## string_xrefs

- `0x18001a6e2`: `SxRegReadString`

## pseudocode

```c

```
