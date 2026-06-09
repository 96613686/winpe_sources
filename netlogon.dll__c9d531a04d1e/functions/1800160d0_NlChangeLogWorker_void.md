# NlChangeLogWorker(void *)

- ea: `0x1800160d0`
- end: `0x1800161b6`
- name: `?NlChangeLogWorker@@YAXPEAX@Z`
- size: `230`
- prototype: `NTSTATUS __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x180007278`
- `0x1800160d0`
- `0x18003a488`
- `0x1800847f4`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180016101`
- `ntdll!RtlLeaveCriticalSection` at `0x1800161ab`
- `ntdll!RtlLeaveCriticalSection` at `0x180016101`
- `ntdll!RtlLeaveCriticalSection` at `0x1800161ab`
- `ntdll!RtlEnterCriticalSection` at `0x180016176`
- `ntdll!RtlEnterCriticalSection` at `0x180016176`
- `netutils!NetApiBufferFree` at `0x180016153`
- `netutils!NetApiBufferFree` at `0x180016153`

## string_xrefs

- `0x1800160d4`: `ChangeLogWorker Thread is starting \n`
- `0x18001613d`: `ChangeLogWorker: Browser won't rename domain: %lx\n`
- `0x180016189`: `ChangeLogWorker Thread is exiting \n`

## pseudocode

```c

```
