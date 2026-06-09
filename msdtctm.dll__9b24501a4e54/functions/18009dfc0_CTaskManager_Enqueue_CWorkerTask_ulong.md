# CTaskManager::Enqueue(CWorkerTask *,ulong)

- ea: `0x18009dfc0`
- end: `0x18009e07a`
- name: `?Enqueue@CTaskManager@@SAXPEAVCWorkerTask@@K@Z`
- size: `186`
- prototype: `void __fastcall(struct CWorkerTask *, unsigned int)`
- caller_count: `10`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001b8f0`
- `0x18001c790`
- `0x1800a1548`
- `0x1800a18d0`
- `0x1800a2090`
- `0x1800a2280`
- `0x1800a2740`
- `0x1800a2b00`
- `0x1800a43d0`
- `0x1800a4690`

## callees

- `0x180073ca0`
- `0x18009df64`
- `0x18009dfc0`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18009e068`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e013`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e056`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e013`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e056`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009dff2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e035`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009dff2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e035`

## pseudocode

```c

```
