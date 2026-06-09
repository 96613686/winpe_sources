# CContextHandler::AddContext(CRemoteReadCtx *,unsigned __int64 *)

- ea: `0x18008680c`
- end: `0x180086a22`
- name: `?AddContext@CContextHandler@@QEAAJPEAVCRemoteReadCtx@@PEA_K@Z`
- size: `534`
- prototype: `__int64 __fastcall(CContextHandler *__hidden this, struct CRemoteReadCtx *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18008ac30`

## callees

- `0x180009924`
- `0x18000d1f0`
- `0x18000f35c`
- `0x180086620`
- `0x18008680c`
- `0x180089c4c`
- `0x18008b5e4`
- `0x18008b8a0`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x180086872`
- `bcrypt!BCryptGenRandom` at `0x180086872`
- `KERNEL32!LeaveCriticalSection` at `0x18008693c`
- `KERNEL32!LeaveCriticalSection` at `0x18008694f`
- `KERNEL32!LeaveCriticalSection` at `0x1800869c9`
- `KERNEL32!LeaveCriticalSection` at `0x180086a06`
- `KERNEL32!LeaveCriticalSection` at `0x18008693c`
- `KERNEL32!LeaveCriticalSection` at `0x18008694f`
- `KERNEL32!LeaveCriticalSection` at `0x1800869c9`
- `KERNEL32!LeaveCriticalSection` at `0x180086a06`

## pseudocode

```c

```
