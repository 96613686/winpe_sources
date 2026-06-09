# CAARpcClientTunnel::Create(IAAAsyncCreateTunnel *)

- ea: `0x1805317d0`
- end: `0x180531ebe`
- name: `?Create@CAARpcClientTunnel@@IEAAJPEAVIAAAsyncCreateTunnel@@@Z`
- size: `1774`
- prototype: `__int64 __fastcall(CAARpcClientTunnel *__hidden this, struct IAAAsyncCreateTunnel *)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180533ad8`

## callees

- `0x18001cdc0`
- `0x1800204e8`
- `0x18002a334`
- `0x180039ce4`
- `0x1800ec8e8`
- `0x18011a690`
- `0x18011a6d0`
- `0x1801351f0`
- `0x1802279a0`
- `0x1805317d0`
- `0x1805330e0`
- `0x1805385f8`
- `0x180538808`
- `0x1805393e8`
- `0x180539754`
- `0x18053997c`
- `0x180539c38`
- `0x180688f3e`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180531ac1`
- `KERNEL32!GetLastError` at `0x180531ac1`
- `KERNEL32!LocalAlloc` at `0x180531830`
- `KERNEL32!LocalAlloc` at `0x180531932`
- `KERNEL32!LocalAlloc` at `0x1805319c9`
- `KERNEL32!LocalAlloc` at `0x180531830`
- `KERNEL32!LocalAlloc` at `0x180531932`
- `KERNEL32!LocalAlloc` at `0x1805319c9`
- `KERNEL32!LocalFree` at `0x180531e3f`
- `KERNEL32!LocalFree` at `0x180531e73`
- `KERNEL32!LocalFree` at `0x180531e3f`
- `KERNEL32!LocalFree` at `0x180531e73`
- `CRYPT32!CryptUnprotectData` at `0x180531ab7`
- `CRYPT32!CryptUnprotectData` at `0x180531ab7`
- `RPCRT4!I_RpcExceptionFilter` at `0x180689296`
- `RPCRT4!I_RpcExceptionFilter` at `0x180689296`

## string_xrefs

- `0x180531dad`: `TsProxyCreateTunnel failed. RpcExceptionCode is %d`
- `0x18053190a`: `InitAsyncStateForIoCompletionNotification`
- `0x180531971`: `tunnelIoContext->u.createComplete.pTsgCaps`

## pseudocode

```c

```
