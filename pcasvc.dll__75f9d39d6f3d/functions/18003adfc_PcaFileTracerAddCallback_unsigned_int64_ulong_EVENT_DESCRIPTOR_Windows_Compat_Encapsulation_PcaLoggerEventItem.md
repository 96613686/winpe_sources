# PcaFileTracerAddCallback(unsigned __int64,ulong (*)(_EVENT_DESCRIPTOR *,Windows::Compat::Encapsulation::PcaLoggerEventItem const &,void *),bool (*)(ulong))

- ea: `0x18003adfc`
- end: `0x18003b020`
- name: `?PcaFileTracerAddCallback@@YAK_KP6AKPEAU_EVENT_DESCRIPTOR@@AEBVPcaLoggerEventItem@Encapsulation@Compat@Windows@@PEAX@ZP6A_NK@Z@Z`
- size: `548`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned int (*)(struct _EVENT_DESCRIPTOR *, const struct Windows::Compat::Encapsulation::PcaLoggerEventItem *, void *), bool (*)(unsigned int))`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a7c0`
- `0x1800b8c58`

## callees

- `0x18003adfc`
- `0x18007a9cf`
- `0x1800b8b38`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x18003aee5`
- `ntdll!RtlReAllocateHeap` at `0x18003afbb`
- `ntdll!RtlReAllocateHeap` at `0x18003aee5`
- `ntdll!RtlReAllocateHeap` at `0x18003afbb`
- `ntdll!RtlAllocateHeap` at `0x18003aec5`
- `ntdll!RtlAllocateHeap` at `0x18003af9b`
- `ntdll!RtlAllocateHeap` at `0x18003aec5`
- `ntdll!RtlAllocateHeap` at `0x18003af9b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003ae3c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003ae3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b001`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b001`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ae4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ae4c`

## pseudocode

```c

```
