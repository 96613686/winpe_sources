# LogETWPolicyOptionEvent

- ea: `0x180081180`
- end: `0x1800813aa`
- name: `LogETWPolicyOptionEvent`
- size: `554`
- prototype: `__int64 __fastcall(int, int, int, int, u_long netlong, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003ef9c`

## callees

- `0x18007e6b0`
- `0x18007e8a8`
- `0x18007e968`
- `0x180081180`
- `0x180083358`
- `0x1800836c8`
- `0x180093220`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180081278`
- `RPCRT4!RpcImpersonateClient` at `0x180081278`
- `RPCRT4!RpcRevertToSelf` at `0x180081329`
- `RPCRT4!RpcRevertToSelf` at `0x180081329`
- `WS2_32!__imp_ntohl` at `0x18008125a`
- `WS2_32!__imp_ntohl` at `0x18008125a`
- `KERNEL32!HeapFree` at `0x180081346`
- `KERNEL32!HeapFree` at `0x180081363`
- `KERNEL32!HeapFree` at `0x180081380`
- `KERNEL32!HeapFree` at `0x180081346`
- `KERNEL32!HeapFree` at `0x180081363`
- `KERNEL32!HeapFree` at `0x180081380`

## pseudocode

```c

```
