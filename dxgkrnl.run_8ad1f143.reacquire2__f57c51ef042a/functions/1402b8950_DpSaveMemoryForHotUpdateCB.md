# DpSaveMemoryForHotUpdateCB

- ea: `0x1402b8950`
- end: `0x1402b8ca6`
- name: `DpSaveMemoryForHotUpdateCB`
- size: `854`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1402b8da8`

## callees

- `0x1400a0100`
- `0x1400a0240`
- `0x1402b8950`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8c42`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8c71`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8c42`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8c71`
- `ntoskrnl!ExAllocatePool2` at `0x1402b8b22`
- `ntoskrnl!ExAllocatePool2` at `0x1402b8b22`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1402b8a20`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1402b8a20`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402b8a76`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402b8a76`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402b8c60`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402b8c60`
- `watchdog!WdLogSingleEntry1` at `0x1402b89d3`
- `watchdog!WdLogSingleEntry1` at `0x1402b8a43`
- `watchdog!WdLogSingleEntry1` at `0x1402b8a96`
- `watchdog!WdLogSingleEntry1` at `0x1402b8af6`
- `watchdog!WdLogSingleEntry1` at `0x1402b8b43`
- `watchdog!WdLogSingleEntry1` at `0x1402b8b87`
- `watchdog!WdLogSingleEntry1` at `0x1402b8c22`
- `watchdog!WdLogSingleEntry1` at `0x1402b89d3`
- `watchdog!WdLogSingleEntry1` at `0x1402b8a43`
- `watchdog!WdLogSingleEntry1` at `0x1402b8a96`
- `watchdog!WdLogSingleEntry1` at `0x1402b8af6`
- `watchdog!WdLogSingleEntry1` at `0x1402b8b43`
- `watchdog!WdLogSingleEntry1` at `0x1402b8b87`
- `watchdog!WdLogSingleEntry1` at `0x1402b8c22`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrPersistMemoryWithMetadata` at `0x1402b8c07`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrPersistMemoryWithMetadata` at `0x1402b8c07`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x1402b8b6c`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x1402b8b6c`

## pseudocode

```c

```
