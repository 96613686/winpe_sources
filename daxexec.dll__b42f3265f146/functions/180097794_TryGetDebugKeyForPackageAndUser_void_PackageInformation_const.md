# TryGetDebugKeyForPackageAndUser(void *,PackageInformation const &)

- ea: `0x180097794`
- end: `0x18009796a`
- name: `?TryGetDebugKeyForPackageAndUser@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAXAEBVPackageInformation@@@Z`
- size: `470`
- prototype: `HKEY __fastcall(HKEY, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180017b10`

## callees

- `0x180004f70`
- `0x180012ddc`
- `0x180012f3c`
- `0x180013510`
- `0x18004abe8`
- `0x180097794`
- `0x180098008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009790f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009790f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800978f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800978f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800978cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800978cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180097901`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180097901`

## pseudocode

```c

```
