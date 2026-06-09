# CACMWrapper::StopStreaming(void)

- ea: `0x1801207f0`
- end: `0x1801208bf`
- name: `?StopStreaming@CACMWrapper@@UEAAJXZ`
- size: `207`
- prototype: `__int64 __fastcall(CACMWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800233b0`

## callees

- `0x1801207f0`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180120891`
- `KERNEL32!LeaveCriticalSection` at `0x1801208a0`
- `KERNEL32!LeaveCriticalSection` at `0x180120891`
- `KERNEL32!LeaveCriticalSection` at `0x1801208a0`
- `KERNEL32!EnterCriticalSection` at `0x18012080c`
- `KERNEL32!EnterCriticalSection` at `0x180120855`
- `KERNEL32!EnterCriticalSection` at `0x18012080c`
- `KERNEL32!EnterCriticalSection` at `0x180120855`
- `ole32!CoTaskMemFree` at `0x18012086d`
- `ole32!CoTaskMemFree` at `0x18012086d`

## pseudocode

```c

```
