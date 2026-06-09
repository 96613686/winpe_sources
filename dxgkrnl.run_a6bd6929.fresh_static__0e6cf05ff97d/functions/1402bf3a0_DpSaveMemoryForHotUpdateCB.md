# DpSaveMemoryForHotUpdateCB

- ea: `0x1402bf3a0`
- end: `0x1402bf6f6`
- name: `DpSaveMemoryForHotUpdateCB`
- size: `854`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1402bf7f8`

## callees

- `0x1400a0bd0`
- `0x1400a0d00`
- `0x1402bf3a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1402bf692`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bf6c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bf692`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bf6c1`
- `ntoskrnl!ExAllocatePool2` at `0x1402bf572`
- `ntoskrnl!ExAllocatePool2` at `0x1402bf572`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1402bf470`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1402bf470`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402bf4c6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402bf4c6`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402bf6b0`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402bf6b0`
- `watchdog!WdLogSingleEntry1` at `0x1402bf423`
- `watchdog!WdLogSingleEntry1` at `0x1402bf493`
- `watchdog!WdLogSingleEntry1` at `0x1402bf4e6`
- `watchdog!WdLogSingleEntry1` at `0x1402bf546`
- `watchdog!WdLogSingleEntry1` at `0x1402bf593`
- `watchdog!WdLogSingleEntry1` at `0x1402bf5d7`
- `watchdog!WdLogSingleEntry1` at `0x1402bf672`
- `watchdog!WdLogSingleEntry1` at `0x1402bf423`
- `watchdog!WdLogSingleEntry1` at `0x1402bf493`
- `watchdog!WdLogSingleEntry1` at `0x1402bf4e6`
- `watchdog!WdLogSingleEntry1` at `0x1402bf546`
- `watchdog!WdLogSingleEntry1` at `0x1402bf593`
- `watchdog!WdLogSingleEntry1` at `0x1402bf5d7`
- `watchdog!WdLogSingleEntry1` at `0x1402bf672`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrPersistMemoryWithMetadata` at `0x1402bf657`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrPersistMemoryWithMetadata` at `0x1402bf657`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x1402bf5bc`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x1402bf5bc`

## pseudocode

```c

```
