# ClfsMgmtSetLogFileSizeAsClient

- ea: `0x140071880`
- end: `0x140071921`
- name: `ClfsMgmtSetLogFileSizeAsClient`
- size: `161`
- prototype: `NTSTATUS __stdcall(PLOG_FILE_OBJECT LogFile, PCLFS_MGMT_CLIENT ClientCookie, PULONGLONG NewSizeInContainers, PULONGLONG ResultingSizeInContainers, PCLFS_SET_LOG_SIZE_COMPLETE_CALLBACK CompletionRoutine, PVOID CompletionRoutineData)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140050434`
- `0x140071850`

## callees

- `0x140017f20`
- `0x1400595fc`
- `0x140071880`
- `0x140071928`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400718a9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400718a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400718fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007bea1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400718fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007bea1`

## pseudocode

```c

```
