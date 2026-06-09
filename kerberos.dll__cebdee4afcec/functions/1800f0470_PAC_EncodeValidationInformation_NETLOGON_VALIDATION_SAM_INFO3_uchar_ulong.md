# PAC_EncodeValidationInformation(_NETLOGON_VALIDATION_SAM_INFO3 *,uchar * *,ulong *)

- ea: `0x1800f0470`
- end: `0x1800f05ee`
- name: `?PAC_EncodeValidationInformation@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAPEAEPEAK@Z`
- size: `382`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO3 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18006ef20`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x1800f0470`

## import_xrefs

- `RPCRT4!MesIncrementalHandleReset` at `0x1800f054b`
- `RPCRT4!MesIncrementalHandleReset` at `0x1800f054b`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x1800f0503`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x1800f0503`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800f0593`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800f0593`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x1800f04bd`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x1800f04bd`
- `RPCRT4!MesHandleFree` at `0x1800f05da`
- `RPCRT4!MesHandleFree` at `0x1800f05da`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800f0557`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800f0557`

## pseudocode

```c

```
