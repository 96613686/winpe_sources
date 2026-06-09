# CContextHandler::GetContext(unsigned __int64)

- ea: `0x180088244`
- end: `0x180088397`
- name: `?GetContext@CContextHandler@@QEAAPEAVCRemoteReadCtx@@_K@Z`
- size: `339`
- prototype: `struct CRemoteReadCtx *__fastcall(CContextHandler *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18008a740`

## callees

- `0x180009924`
- `0x180011698`
- `0x1800116d8`
- `0x180086620`
- `0x180088244`
- `0x180089c4c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800882cc`
- `KERNEL32!LeaveCriticalSection` at `0x18008833a`
- `KERNEL32!LeaveCriticalSection` at `0x180088381`
- `KERNEL32!LeaveCriticalSection` at `0x1800882cc`
- `KERNEL32!LeaveCriticalSection` at `0x18008833a`
- `KERNEL32!LeaveCriticalSection` at `0x180088381`

## pseudocode

```c

```
