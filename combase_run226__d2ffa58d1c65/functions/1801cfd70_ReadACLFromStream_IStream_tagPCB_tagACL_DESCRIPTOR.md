# ReadACLFromStream(IStream *,tagPCB *,tagACL_DESCRIPTOR *)

- ea: `0x1801cfd70`
- end: `0x1801cff94`
- name: `?ReadACLFromStream@@YAJPEAUIStream@@PEAUtagPCB@@PEAUtagACL_DESCRIPTOR@@@Z`
- size: `548`
- prototype: `HRESULT __fastcall(IStream *pStm, tagPCB *ppcb, tagACL_DESCRIPTOR *pACLDesc)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1801955e0`

## callees

- `0x1801cfd70`
- `0x1801cffe0`
- `0x1801d074c`
- `0x180255010`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x1802447a1`
- `RPCRT4!I_RpcExceptionFilter` at `0x1802447bd`
- `RPCRT4!I_RpcExceptionFilter` at `0x1802447a1`
- `RPCRT4!I_RpcExceptionFilter` at `0x1802447bd`
- `RPCRT4!MesHandleFree` at `0x1801cfee1`
- `RPCRT4!MesHandleFree` at `0x1801cfee1`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x1801cfdc5`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x1801cfdc5`
- `RPCRT4!MesBufferHandleReset` at `0x1801cfe9d`
- `RPCRT4!MesBufferHandleReset` at `0x1801cfe9d`
- `RPCRT4!NdrMesTypeDecode3` at `0x1801cfe21`
- `RPCRT4!NdrMesTypeDecode3` at `0x1801cfed4`
- `RPCRT4!NdrMesTypeDecode3` at `0x1801cfe21`
- `RPCRT4!NdrMesTypeDecode3` at `0x1801cfed4`

## pseudocode

```c

```
