# CSettingAccessor::_ReadMultipleValues(HKEY__ *,tagVARIANT *)

- ea: `0x180032bd8`
- end: `0x180032e5f`
- name: `?_ReadMultipleValues@CSettingAccessor@@AEAAJPEAUHKEY__@@PEAUtagVARIANT@@@Z`
- size: `647`
- prototype: `__int64 __fastcall(CSettingAccessor *__hidden this, HKEY hKey, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002594c`

## callees

- `0x18000d640`
- `0x180025ff4`
- `0x18002edf8`
- `0x180032bd8`
- `0x180033250`
- `0x18007f774`
- `0x18008053c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032e2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032e2a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180032d0d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180032d0d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180032c45`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180032c45`
- `OLEAUT32!__imp_SysAllocString` at `0x180032de1`
- `OLEAUT32!__imp_SysAllocString` at `0x180032de1`
- `OLEAUT32!__imp_VariantInit` at `0x180032d32`
- `OLEAUT32!__imp_VariantInit` at `0x180032d89`
- `OLEAUT32!__imp_VariantInit` at `0x180032d32`
- `OLEAUT32!__imp_VariantInit` at `0x180032d89`
- `OLEAUT32!__imp_VariantClear` at `0x180032dc6`
- `OLEAUT32!__imp_VariantClear` at `0x180032dd0`
- `OLEAUT32!__imp_VariantClear` at `0x180032e3b`
- `OLEAUT32!__imp_VariantClear` at `0x180032dc6`
- `OLEAUT32!__imp_VariantClear` at `0x180032dd0`
- `OLEAUT32!__imp_VariantClear` at `0x180032e3b`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180032d6c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180032dba`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180032d6c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180032dba`

## pseudocode

```c

```
