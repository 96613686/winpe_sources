# CQueryContext::MakeResult(_DEV_QUERY_RESULT_ACTION,_LIST_ENTRY *,DafDynamicArray<_DEVPROPCOMPKEY> &)

- ea: `0x18000aad0`
- end: `0x18000c120`
- name: `?MakeResult@CQueryContext@@IEAAJW4_DEV_QUERY_RESULT_ACTION@@PEAU_LIST_ENTRY@@AEAV?$DafDynamicArray@U_DEVPROPCOMPKEY@@@@@Z`
- size: `5712`
- prototype: `__int64 __fastcall(char, char)`
- caller_count: `4`
- callee_count: `25`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000759c`
- `0x180009800`
- `0x18001efb0`
- `0x1800359c0`

## callees

- `0x180007500`
- `0x1800089e0`
- `0x180008a50`
- `0x180009434`
- `0x1800095bc`
- `0x180009690`
- `0x180009d50`
- `0x18000aad0`
- `0x18000c128`
- `0x18000cbe0`
- `0x18000cd88`
- `0x18000d100`
- `0x1800152c0`
- `0x1800153e0`
- `0x180017760`
- `0x18001cd30`
- `0x18001fc28`
- `0x180023f34`
- `0x180036e34`
- `0x18003bc80`
- `0x18003c79c`
- `0x180053b70`
- `0x18005e308`
- `0x18007e9d8`
- `0x180082010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000bcda`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000bcda`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000b183`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000bb16`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000b183`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000bb16`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000bbd7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000bbd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bb46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bb46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bb05`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bb05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bbaa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bbaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bbe9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bbe9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b172`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000bb99`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b172`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000bb99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b18f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000bbf2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b18f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000bbf2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b057`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b074`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b0a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b833`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c107`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b057`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b074`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b0a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b833`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c107`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000af14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000af3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b065`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b082`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b0af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c115`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000af14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000af3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b065`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b082`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b0af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c115`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b7bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b841`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b7bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0fc`

## pseudocode

```c

```
