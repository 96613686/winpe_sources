# AcquireWriteLock

- ea: `0x180089a58`
- end: `0x180089a95`
- name: `AcquireWriteLock`
- size: `61`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180089924`
- `0x180089a9c`
- `0x180089da8`
- `0x18008a084`

## callees

- `0x180089a58`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180089a73`
- `KERNEL32!WaitForSingleObject` at `0x180089a73`
- `KERNEL32!LeaveCriticalSection` at `0x180089a66`
- `KERNEL32!LeaveCriticalSection` at `0x180089a66`
- `KERNEL32!EnterCriticalSection` at `0x180089a7c`
- `KERNEL32!EnterCriticalSection` at `0x180089a7c`

## pseudocode

```c

```
