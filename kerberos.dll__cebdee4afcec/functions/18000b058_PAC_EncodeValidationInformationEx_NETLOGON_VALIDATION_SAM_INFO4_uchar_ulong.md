# PAC_EncodeValidationInformationEx(_NETLOGON_VALIDATION_SAM_INFO4 *,uchar * *,ulong *)

- ea: `0x18000b058`
- end: `0x18000b1ce`
- name: `?PAC_EncodeValidationInformationEx@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAPEAEPEAK@Z`
- size: `374`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO4 *, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000ad2c`
- `0x18000b288`
- `0x1800be880`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x18000b058`

## import_xrefs

- `RPCRT4!MesIncrementalHandleReset` at `0x18000b12a`
- `RPCRT4!MesIncrementalHandleReset` at `0x18000b12a`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18000b0e5`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18000b0e5`
- `RPCRT4!NdrMesTypeEncode3` at `0x18000b16f`
- `RPCRT4!NdrMesTypeEncode3` at `0x18000b16f`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18000b0a2`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18000b0a2`
- `RPCRT4!MesHandleFree` at `0x18000b1b0`
- `RPCRT4!MesHandleFree` at `0x18000b1b0`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000b136`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000b136`

## pseudocode

```c

```
