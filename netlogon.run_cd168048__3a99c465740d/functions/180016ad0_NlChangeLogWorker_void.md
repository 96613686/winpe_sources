# NlChangeLogWorker(void *)

- ea: `0x180016ad0`
- end: `0x180016bd2`
- name: `?NlChangeLogWorker@@YAXPEAX@Z`
- size: `258`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x180007518`
- `0x180016ad0`
- `0x18003c86c`
- `0x18008a93c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180016b04`
- `ntdll!RtlLeaveCriticalSection` at `0x180016bc0`
- `ntdll!RtlLeaveCriticalSection` at `0x180016b04`
- `ntdll!RtlLeaveCriticalSection` at `0x180016bc0`
- `ntdll!RtlEnterCriticalSection` at `0x180016b85`
- `ntdll!RtlEnterCriticalSection` at `0x180016b85`
- `netutils!NetApiBufferFree` at `0x180016b5c`
- `netutils!NetApiBufferFree` at `0x180016b5c`

## string_xrefs

- `0x180016ad4`: `ChangeLogWorker Thread is starting \n`
- `0x180016b46`: `ChangeLogWorker: Browser won't rename domain: %lx\n`
- `0x180016b9e`: `ChangeLogWorker Thread is exiting \n`

## pseudocode

```c

```
