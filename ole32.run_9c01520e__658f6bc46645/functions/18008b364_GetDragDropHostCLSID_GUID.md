# GetDragDropHostCLSID(_GUID *)

- ea: `0x18008b364`
- end: `0x18008b48d`
- name: `?GetDragDropHostCLSID@@YAJPEAU_GUID@@@Z`
- size: `297`
- prototype: `HRESULT __fastcall(_GUID *pclsid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008be98`

## callees

- `0x180046460`
- `0x180047484`
- `0x18008b364`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008b3ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008b3ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008b410`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008b410`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18008b47d`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18008b47d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18008b442`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18008b442`

## string_xrefs

- `0x18008b3bc`: `SOFTWARE\Microsoft\Ole\Extensions`

## pseudocode

```c

```
