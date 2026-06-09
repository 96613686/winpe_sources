# UnregisterV4Apps(_INIDRIVER *,bool)

- ea: `0x1800c22f4`
- end: `0x1800c263a`
- name: `?UnregisterV4Apps@@YAJPEAU_INIDRIVER@@_N@Z`
- size: `838`
- prototype: `__int64 __fastcall(struct _INIDRIVER *, bool)`
- caller_count: `3`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800685e4`
- `0x1800bdf84`
- `0x1800be85c`

## callees

- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x18001fb10`
- `0x180034308`
- `0x18003e984`
- `0x180046650`
- `0x18004eb80`
- `0x180054638`
- `0x1800c22f4`
- `0x1800ccbd8`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c23f8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c24ea`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c23f8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c24ea`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800c239f`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800c2429`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800c24c2`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800c239f`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800c2429`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800c24c2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c2381`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c2381`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c253b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c253b`

## string_xrefs

- `0x1800c2491`: `Unregistered printer extension: printer driver ID={%ws}, activation ID={%ws}, app ID={%ws}`
- `0x1800c24ad`: `Failed to unregister printer extension: printer driver ID={%ws}, activation ID={%ws}, app ID={%ws}, hr=0x%x`

## pseudocode

```c

```
