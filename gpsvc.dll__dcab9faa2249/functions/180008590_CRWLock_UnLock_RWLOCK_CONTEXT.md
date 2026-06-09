# CRWLock::UnLock(_RWLOCK_CONTEXT * *)

- ea: `0x180008590`
- end: `0x180008831`
- name: `?UnLock@CRWLock@@QEAAKPEAPEAU_RWLOCK_CONTEXT@@@Z`
- size: `673`
- prototype: `unsigned int __fastcall(CRWLock *__hidden this, struct _RWLOCK_CONTEXT **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000fa40`
- `0x1800925f0`

## callees

- `0x18000844c`
- `0x180008590`
- `0x18000a4b0`
- `0x18005ce24`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800085c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000864c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800085c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000864c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008728`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008809`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008728`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008809`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000862a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800086a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000862a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800086a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008796`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008825`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008796`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008825`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008619`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008695`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008619`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008695`

## string_xrefs

- `0x1800086eb`: `Signalling first writer with ID [%d]`
- `0x180008713`: `Signalling first writer with ID [%d]`
- `0x1800087cc`: `Waking up writer with ID [%d].`
- `0x1800087f4`: `Waking up writer with ID [%d].`

## pseudocode

```c

```
