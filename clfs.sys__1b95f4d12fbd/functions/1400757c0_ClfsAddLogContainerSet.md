# ClfsAddLogContainerSet

- ea: `0x1400757c0`
- end: `0x140075bbe`
- name: `ClfsAddLogContainerSet`
- size: `1022`
- prototype: `NTSTATUS __stdcall(PLOG_FILE_OBJECT plfoLog, USHORT cContainers, PULONGLONG pcbContainer, PUNICODE_STRING rguszContainerPath)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140032294`
- `0x140033250`

## callees

- `0x14000c2f0`
- `0x14000e6f4`
- `0x14000ed64`
- `0x140011d90`
- `0x140016e9c`
- `0x140017f20`
- `0x140017f80`
- `0x140018280`
- `0x140059e80`
- `0x1400757c0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140075913`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140075913`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140075b6e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007c5c4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140075b6e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007c5c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075af1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075af1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140075a88`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140075a88`

## pseudocode

```c

```
