# MemProtectHeap::ProtectCurrentThread(void (*)(void *),void *)

- ea: `0x1801f1c80`
- end: `0x1801f1d4f`
- name: `?ProtectCurrentThread@MemProtectHeap@@QEAAXP6AXPEAX@Z0@Z`
- size: `207`
- prototype: `void __fastcall(MemProtectHeap *__hidden this, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1801f1c40`

## callees

- `0x180072650`
- `0x1801f1c80`
- `0x1801f1d58`
- `0x1801f1dcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801f1d39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801f1d39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801f1cd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801f1cd3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801f1ca3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801f1ca3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f1cbb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f1d1e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f1cbb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f1d1e`

## pseudocode

```c

```
