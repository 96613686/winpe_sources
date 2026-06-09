# CRemoteReadCtx::CancelPendingRemoteRead(ulong)

- ea: `0x180087234`
- end: `0x1800873d3`
- name: `?CancelPendingRemoteRead@CRemoteReadCtx@@QEAAJK@Z`
- size: `415`
- prototype: `__int64 __fastcall(CRemoteReadCtx *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18008a270`

## callees

- `0x180009924`
- `0x18000f35c`
- `0x1800129cc`
- `0x18002c61c`
- `0x180085c90`
- `0x1800867ac`
- `0x1800871a8`
- `0x180087234`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800872d4`
- `KERNEL32!LeaveCriticalSection` at `0x1800872fe`
- `KERNEL32!LeaveCriticalSection` at `0x1800873ba`
- `KERNEL32!LeaveCriticalSection` at `0x1800872d4`
- `KERNEL32!LeaveCriticalSection` at `0x1800872fe`
- `KERNEL32!LeaveCriticalSection` at `0x1800873ba`
- `ntdll!NtDeviceIoControlFile` at `0x18008734d`
- `ntdll!NtDeviceIoControlFile` at `0x18008734d`

## string_xrefs

- `0x1800872bf`: `qm\RemoteReadSrv`
- `0x1800873a8`: `qm\RemoteReadSrv`

## pseudocode

```c

```
