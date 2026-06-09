# APP_POOL_ISOLATION::CalculateAppPoolChangedList(CONFIG_CHANGES *,SITEAPP_HASH *,SITEAPP_HASH *,SITE_DATA_OBJECT_TABLE *,SITE_DATA_OBJECT_TABLE *,APPLICATION_DATA_OBJECT_TABLE *,APPLICATION_DATA_OBJECT_TABLE *,APP_POOL_CHANGED_LIST * *)

- ea: `0x18000a58c`
- end: `0x18000a8d3`
- name: `?CalculateAppPoolChangedList@APP_POOL_ISOLATION@@AEAAJPEAUCONFIG_CHANGES@@PEAVSITEAPP_HASH@@1PEAVSITE_DATA_OBJECT_TABLE@@2PEAVAPPLICATION_DATA_OBJECT_TABLE@@3PEAPEAVAPP_POOL_CHANGED_LIST@@@Z`
- size: `839`
- prototype: `__int64 __fastcall(APP_POOL_ISOLATION *__hidden this, struct CONFIG_CHANGES *, struct SITEAPP_HASH *, struct SITEAPP_HASH *, struct SITE_DATA_OBJECT_TABLE *, struct SITE_DATA_OBJECT_TABLE *, struct APPLICATION_DATA_OBJECT_TABLE *, struct APPLICATION_DATA_OBJECT_TABLE *, struct APP_POOL_CHANGED_LIST **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000d8a4`

## callees

- `0x180001234`
- `0x180001274`
- `0x180007d98`
- `0x18000a494`
- `0x18000a58c`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000a6dd`
- `msvcrt!_wcsnicmp` at `0x18000a6dd`
- `msvcrt!wcschr` at `0x18000a72d`
- `msvcrt!wcschr` at `0x18000a72d`
- `msvcrt!_wcsicmp` at `0x18000a6bd`
- `msvcrt!_wcsicmp` at `0x18000a6bd`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000a753`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000a786`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000a753`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000a786`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a8a8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a8a8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a5e9`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a5e9`

## pseudocode

```c

```
