# ClfsReserveAndAppendLogAligned

- ea: `0x140055aa0`
- end: `0x140055ee8`
- name: `ClfsReserveAndAppendLogAligned`
- size: `1096`
- prototype: `NTSTATUS __stdcall(PVOID pvMarshalContext, PCLFS_WRITE_ENTRY rgWriteEntries, ULONG cWriteEntries, ULONG cbEntryAlignment, PCLFS_LSN plsnUndoNext, PCLFS_LSN plsnPrevious, ULONG cReserveRecords, PLONGLONG rgcbReservation, ULONG fFlags, PCLFS_LSN plsn)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140055a40`

## callees

- `0x14000ed64`
- `0x140011d90`
- `0x140055aa0`
- `0x140055ef0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140055baf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140055baf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140055c65`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079839`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140055c65`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079839`

## pseudocode

```c

```
