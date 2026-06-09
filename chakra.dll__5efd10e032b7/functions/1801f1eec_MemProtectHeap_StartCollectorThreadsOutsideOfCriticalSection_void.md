# MemProtectHeap::StartCollectorThreadsOutsideOfCriticalSection(void)

- ea: `0x1801f1eec`
- end: `0x1801f1f6c`
- name: `?StartCollectorThreadsOutsideOfCriticalSection@MemProtectHeap@@AEAAXXZ`
- size: `128`
- prototype: `void __fastcall(MemProtectHeap *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1801f1d58`
- `0x1804945c4`

## callees

- `0x1801f1eec`
- `0x1801f1f74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801f1f16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801f1f16`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801f1f4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801f1f4f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f1f3f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f1f3f`

## pseudocode

```c

```
