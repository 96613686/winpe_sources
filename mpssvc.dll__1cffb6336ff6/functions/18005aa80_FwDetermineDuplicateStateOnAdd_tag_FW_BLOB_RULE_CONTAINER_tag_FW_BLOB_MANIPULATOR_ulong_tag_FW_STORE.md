# FwDetermineDuplicateStateOnAdd(_tag_FW_BLOB_RULE_CONTAINER *,_tag_FW_BLOB_MANIPULATOR *,ulong,_tag_FW_STORE *)

- ea: `0x18005aa80`
- end: `0x18005aca0`
- name: `?FwDetermineDuplicateStateOnAdd@@YAXPEAU_tag_FW_BLOB_RULE_CONTAINER@@PEAU_tag_FW_BLOB_MANIPULATOR@@KPEAU_tag_FW_STORE@@@Z`
- size: `544`
- prototype: `void __fastcall(struct _tag_FW_BLOB_RULE_CONTAINER *, struct _tag_FW_BLOB_MANIPULATOR *, unsigned int, struct _tag_FW_STORE *)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180026384`
- `0x180026e70`
- `0x18005e450`

## callees

- `0x180029a24`
- `0x18002a470`
- `0x18005aa80`
- `0x1800670c0`
- `0x18006f520`
- `0x18008abb0`
- `0x1800e6010`

## import_xrefs

- `fwbase!FwHashtableFind` at `0x18005ab4d`
- `fwbase!FwHashtableFind` at `0x18005ab4d`
- `fwbase!FwHashtableGetNext` at `0x18005ac3c`
- `fwbase!FwHashtableGetNext` at `0x18005ac3c`
- `fwbase!FwUpdateHash` at `0x18005aaf4`
- `fwbase!FwUpdateHash` at `0x18005aaf4`
- `fwbase!FwInitializeHashContext` at `0x18005aae0`
- `fwbase!FwInitializeHashContext` at `0x18005aae0`
- `fwbase!FwFinalHash` at `0x18005aaff`
- `fwbase!FwFinalHash` at `0x18005aaff`

## string_xrefs

- `0x18005ac1c`: `mpssvc.dll`

## pseudocode

```c

```
