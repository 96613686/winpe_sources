# PlaiRegSaveValue(HKEY__ *,ushort const *,_PLA_REGISTRY_CONTEXT *)

- ea: `0x18001e8e4`
- end: `0x18001ef8b`
- name: `?PlaiRegSaveValue@@YAJPEAUHKEY__@@PEBGPEAU_PLA_REGISTRY_CONTEXT@@@Z`
- size: `1703`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, struct _PLA_REGISTRY_CONTEXT *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001e000`
- `0x1800f4804`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x18001d848`
- `0x18001e8e4`
- `0x18001ef94`
- `0x18002b3a0`
- `0x180088b5c`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e982`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001eaa3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001eb6a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ebaf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ecf9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e982`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001eaa3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001eb6a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ebaf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ecf9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001ebd8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001ebd8`
- `OLEAUT32!__imp_VariantInit` at `0x18001e958`
- `OLEAUT32!__imp_VariantInit` at `0x18001e958`
- `OLEAUT32!__imp_VariantClear` at `0x18001ef43`
- `OLEAUT32!__imp_VariantClear` at `0x18001ef43`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001ed82`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001ed82`

## pseudocode

```c

```
