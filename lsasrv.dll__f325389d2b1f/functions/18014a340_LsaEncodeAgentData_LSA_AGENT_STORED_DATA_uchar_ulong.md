# LsaEncodeAgentData(_LSA_AGENT_STORED_DATA *,uchar * *,ulong *)

- ea: `0x18014a340`
- end: `0x18014a574`
- name: `?LsaEncodeAgentData@@YAJPEAU_LSA_AGENT_STORED_DATA@@PEAPEAEPEAK@Z`
- size: `564`
- prototype: `__int64 __fastcall(struct _LSA_AGENT_STORED_DATA *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180132c80`

## callees

- `0x1801382a4`
- `0x18014a224`
- `0x18014a238`
- `0x18014a340`
- `0x18014a57c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18014a42c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18014a42c`
- `RPCRT4!MesBufferHandleReset` at `0x18014a487`
- `RPCRT4!MesBufferHandleReset` at `0x18014a487`
- `RPCRT4!I_RpcMapWin32Status` at `0x18014a3b7`
- `RPCRT4!I_RpcMapWin32Status` at `0x18014a495`
- `RPCRT4!I_RpcMapWin32Status` at `0x18014a515`
- `RPCRT4!I_RpcMapWin32Status` at `0x18014a53f`
- `RPCRT4!I_RpcMapWin32Status` at `0x18014a3b7`
- `RPCRT4!I_RpcMapWin32Status` at `0x18014a495`
- `RPCRT4!I_RpcMapWin32Status` at `0x18014a515`
- `RPCRT4!I_RpcMapWin32Status` at `0x18014a53f`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18014a3a9`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18014a3a9`
- `RPCRT4!NdrMesTypeEncode3` at `0x18014a4d7`
- `RPCRT4!NdrMesTypeEncode3` at `0x18014a4d7`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18014a412`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18014a412`

## pseudocode

```c

```
