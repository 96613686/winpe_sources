# FwpIOCompletionRoutine(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *)

- ea: `0x1800526d0`
- end: `0x180052a33`
- name: `?FwpIOCompletionRoutine@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z`
- size: `867`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PVOID Overlapped, ULONG IoResult, ULONG_PTR NumberOfBytesTransferred, PTP_IO Io)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800093b0`
- `0x18000af3c`
- `0x1800520a4`
- `0x1800526d0`
- `0x180052a3c`
- `0x18005398c`
- `0x18006bbe0`
- `0x18006fb90`
- `0x180079750`
- `0x180094290`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800528eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052927`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052a22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800528eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052927`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052a22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800526ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800527b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800526ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800527b2`
- `fwbase!FwFree` at `0x180052827`
- `fwbase!FwFree` at `0x1800528b6`
- `fwbase!FwFree` at `0x1800529e6`
- `fwbase!FwFree` at `0x180052827`
- `fwbase!FwFree` at `0x1800528b6`
- `fwbase!FwFree` at `0x1800529e6`

## string_xrefs

- `0x180052709`: `FwpIOCompletionRoutine`

## pseudocode

```c

```
