# FwAddDuplicateEntryToMap(_tag_FW_BLOB_CONTAINER *,_tag_FW_BLOB_MANIPULATOR *,_RTL_DYNAMIC_HASH_TABLE *)

- ea: `0x180062080`
- end: `0x1800621e9`
- name: `?FwAddDuplicateEntryToMap@@YAHPEAU_tag_FW_BLOB_CONTAINER@@PEAU_tag_FW_BLOB_MANIPULATOR@@PEAU_RTL_DYNAMIC_HASH_TABLE@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(struct _tag_FW_BLOB_CONTAINER *, struct _tag_FW_BLOB_MANIPULATOR *, struct _RTL_DYNAMIC_HASH_TABLE *)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002892c`
- `0x180029484`
- `0x180062790`

## callees

- `0x180001b44`
- `0x18000a710`
- `0x180062080`
- `0x1800729c0`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800620d0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800620d0`
- `fwbase!FwUpdateHash` at `0x1800620ff`
- `fwbase!FwUpdateHash` at `0x1800620ff`
- `fwbase!FwRestructureHashtable` at `0x1800621bc`
- `fwbase!FwRestructureHashtable` at `0x1800621bc`
- `fwbase!FwInitializeHashContext` at `0x1800620e4`
- `fwbase!FwInitializeHashContext` at `0x1800620e4`
- `fwbase!FwFinalHash` at `0x180062117`
- `fwbase!FwFinalHash` at `0x180062117`
- `fwbase!FwHashtableInsert` at `0x18006212d`
- `fwbase!FwHashtableInsert` at `0x18006212d`

## pseudocode

```c

```
