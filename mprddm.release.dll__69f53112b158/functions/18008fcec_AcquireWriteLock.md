# AcquireWriteLock

- ea: `0x18008fcec`
- end: `0x18008fd3c`
- name: `AcquireWriteLock`
- size: `80`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18008fb8c`
- `0x18008fd44`
- `0x180090048`
- `0x180090344`

## callees

- `0x18008fcec`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18008fd0d`
- `KERNEL32!WaitForSingleObject` at `0x18008fd0d`
- `KERNEL32!LeaveCriticalSection` at `0x18008fcfa`
- `KERNEL32!LeaveCriticalSection` at `0x18008fcfa`
- `KERNEL32!EnterCriticalSection` at `0x18008fd1c`
- `KERNEL32!EnterCriticalSection` at `0x18008fd1c`

## pseudocode

```c

```
