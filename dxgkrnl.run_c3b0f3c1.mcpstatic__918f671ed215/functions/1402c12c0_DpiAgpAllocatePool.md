# DpiAgpAllocatePool

- ea: `0x1402c12c0`
- end: `0x1402c171d`
- name: `DpiAgpAllocatePool`
- size: `1117`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, _QWORD *, _QWORD *BaseAddress)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400a0cb0`
- `0x1402c12c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1402c154d`
- `ntoskrnl!ExAllocatePool2` at `0x1402c154d`
- `ntoskrnl!IoAllocateMdl` at `0x1402c13c4`
- `ntoskrnl!IoAllocateMdl` at `0x1402c13c4`
- `ntoskrnl!IoFreeMdl` at `0x1402c15d9`
- `ntoskrnl!IoFreeMdl` at `0x1402c15d9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402c1505`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402c1505`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402c15a9`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402c15a9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402c1675`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402c1675`
- `ntoskrnl!KeReleaseMutex` at `0x1402c16ab`
- `ntoskrnl!KeReleaseMutex` at `0x1402c16ab`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1402c14cb`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1402c14cb`
- `ntoskrnl!MmUnmapIoSpace` at `0x1402c1598`
- `ntoskrnl!MmUnmapIoSpace` at `0x1402c1598`
- `watchdog!WdLogSingleEntry2` at `0x1402c1399`
- `watchdog!WdLogSingleEntry2` at `0x1402c144c`
- `watchdog!WdLogSingleEntry2` at `0x1402c1494`
- `watchdog!WdLogSingleEntry2` at `0x1402c1399`
- `watchdog!WdLogSingleEntry2` at `0x1402c144c`
- `watchdog!WdLogSingleEntry2` at `0x1402c1494`
- `watchdog!WdLogSingleEntry1` at `0x1402c13e4`
- `watchdog!WdLogSingleEntry1` at `0x1402c1525`
- `watchdog!WdLogSingleEntry1` at `0x1402c1572`
- `watchdog!WdLogSingleEntry1` at `0x1402c16bf`
- `watchdog!WdLogSingleEntry1` at `0x1402c16e5`
- `watchdog!WdLogSingleEntry1` at `0x1402c13e4`
- `watchdog!WdLogSingleEntry1` at `0x1402c1525`
- `watchdog!WdLogSingleEntry1` at `0x1402c1572`
- `watchdog!WdLogSingleEntry1` at `0x1402c16bf`
- `watchdog!WdLogSingleEntry1` at `0x1402c16e5`

## pseudocode

```c

```
