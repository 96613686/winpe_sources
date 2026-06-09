# ClfsQueryLogFileInformation

- ea: `0x140059b80`
- end: `0x140059e76`
- name: `ClfsQueryLogFileInformation`
- size: `758`
- prototype: `NTSTATUS __stdcall(PLOG_FILE_OBJECT plfoLog, CLFS_LOG_INFORMATION_CLASS eInformationClass, PVOID pinfoInputBuffer, ULONG cbinfoInputBuffer, PVOID pinfoBuffer, PULONG pcbInfoBuffer)`
- caller_count: `8`
- callee_count: `6`
- tags: ``

## callers

- `0x1400518b0`
- `0x140051968`
- `0x140059a48`
- `0x14005e910`
- `0x14006fe80`
- `0x1400705e8`
- `0x140071928`
- `0x14007487c`

## callees

- `0x14000c2f0`
- `0x14000ed64`
- `0x140011d90`
- `0x140017f20`
- `0x140059b80`
- `0x140059e80`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140059bf7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140059bf7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140059d3a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079d3c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140059d3a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079d3c`

## pseudocode

```c

```
