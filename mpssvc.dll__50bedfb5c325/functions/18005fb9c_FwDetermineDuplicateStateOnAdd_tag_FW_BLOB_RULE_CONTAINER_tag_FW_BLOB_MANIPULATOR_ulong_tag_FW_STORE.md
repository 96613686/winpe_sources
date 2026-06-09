# FwDetermineDuplicateStateOnAdd(_tag_FW_BLOB_RULE_CONTAINER *,_tag_FW_BLOB_MANIPULATOR *,ulong,_tag_FW_STORE *)

- ea: `0x18005fb9c`
- end: `0x18005fddb`
- name: `?FwDetermineDuplicateStateOnAdd@@YAXPEAU_tag_FW_BLOB_RULE_CONTAINER@@PEAU_tag_FW_BLOB_MANIPULATOR@@KPEAU_tag_FW_STORE@@@Z`
- size: `575`
- prototype: `void __fastcall(struct _tag_FW_BLOB_RULE_CONTAINER *, struct _tag_FW_BLOB_MANIPULATOR *, unsigned int, struct _tag_FW_STORE *)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x18002892c`
- `0x180029484`
- `0x180062790`

## callees

- `0x18002d208`
- `0x18002dcc0`
- `0x18005fb9c`
- `0x18006a710`
- `0x1800729c0`
- `0x18008f3d0`
- `0x1800ec010`

## import_xrefs

- `fwbase!FwHashtableFind` at `0x18005fc7b`
- `fwbase!FwHashtableFind` at `0x18005fc7b`
- `fwbase!FwHashtableGetNext` at `0x18005fd70`
- `fwbase!FwHashtableGetNext` at `0x18005fd70`
- `fwbase!FwUpdateHash` at `0x18005fc16`
- `fwbase!FwUpdateHash` at `0x18005fc16`
- `fwbase!FwInitializeHashContext` at `0x18005fbfc`
- `fwbase!FwInitializeHashContext` at `0x18005fbfc`
- `fwbase!FwFinalHash` at `0x18005fc27`
- `fwbase!FwFinalHash` at `0x18005fc27`

## string_xrefs

- `0x18005fd50`: `mpssvc.dll`

## pseudocode

```c

```
