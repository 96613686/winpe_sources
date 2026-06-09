# FwpIOCompletionRoutine(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *)

- ea: `0x180056b40`
- end: `0x180056ed4`
- name: `?FwpIOCompletionRoutine@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z`
- size: `916`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PVOID Overlapped, ULONG IoResult, ULONG_PTR NumberOfBytesTransferred, PTP_IO Io)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800089bc`
- `0x18000a710`
- `0x180056574`
- `0x180056b40`
- `0x180056edc`
- `0x180058ba0`
- `0x18006ed38`
- `0x180073030`
- `0x18007d3c8`
- `0x1800990a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056d74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056db6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056ebd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056d74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056db6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056ebd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056b5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056c28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056b5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056c28`
- `fwbase!FwFree` at `0x180056ca3`
- `fwbase!FwFree` at `0x180056d39`
- `fwbase!FwFree` at `0x180056e7b`
- `fwbase!FwFree` at `0x180056ca3`
- `fwbase!FwFree` at `0x180056d39`
- `fwbase!FwFree` at `0x180056e7b`

## string_xrefs

- `0x180056b7f`: `FwpIOCompletionRoutine`

## pseudocode

```c

```
