# RpcConnect

- ea: `0x180144314`
- end: `0x180144581`
- name: `RpcConnect`
- size: `621`
- prototype: `__int64 __fastcall(RPC_WSTR ProtSeq, RPC_WSTR Endpoint)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180144588`

## callees

- `0x180011278`
- `0x180144074`
- `0x18014409c`
- `0x180144314`
- `0x180144754`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180144345`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180144345`
- `ntdll!RtlAllocateHeap` at `0x18014436e`
- `ntdll!RtlAllocateHeap` at `0x18014436e`
- `RPCRT4!NdrClientCall3` at `0x180144491`
- `RPCRT4!NdrClientCall3` at `0x180144491`
- `RPCRT4!I_RpcMapWin32Status` at `0x180144402`
- `RPCRT4!I_RpcMapWin32Status` at `0x1801444af`
- `RPCRT4!I_RpcMapWin32Status` at `0x180144402`
- `RPCRT4!I_RpcMapWin32Status` at `0x1801444af`
- `RPCRT4!RpcStringBindingComposeW` at `0x1801443bd`
- `RPCRT4!RpcStringBindingComposeW` at `0x1801443bd`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18014441d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18014441d`
- `RPCRT4!RpcStringFreeW` at `0x180144430`
- `RPCRT4!RpcStringFreeW` at `0x180144430`

## pseudocode

```c

```
