# GetDragDropHostCLSID(_GUID *)

- ea: `0x180048c00`
- end: `0x180048d10`
- name: `?GetDragDropHostCLSID@@YAJPEAU_GUID@@@Z`
- size: `272`
- prototype: `HRESULT __fastcall(_GUID *pclsid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008fdc0`

## callees

- `0x180048c00`
- `0x180052390`
- `0x180053014`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180048c64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180048c64`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180048ca8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180048ca8`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180048d06`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180048d06`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180048cd6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180048cd6`

## string_xrefs

- `0x180048c56`: `SOFTWARE\Microsoft\Ole\Extensions`

## pseudocode

```c

```
