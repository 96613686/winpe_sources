# DpiClaimPersistedMemoryBlock(_FDO_CONTEXT *,unsigned __int64,_GUID const *)

- ea: `0x1402b7e80`
- end: `0x1402b8378`
- name: `?DpiClaimPersistedMemoryBlock@@YAJPEAU_FDO_CONTEXT@@_KPEBU_GUID@@@Z`
- size: `1272`
- prototype: `__int64 __fastcall(struct _FDO_CONTEXT *, unsigned __int64, const struct _GUID *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1402b910c`
- `0x1402b930c`

## callees

- `0x1402b7e80`
- `0x1402b8380`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1402b82d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b832a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8340`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b82d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b832a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8340`
- `ntoskrnl!ExAllocatePool2` at `0x1402b7ef4`
- `ntoskrnl!ExAllocatePool2` at `0x1402b7ffe`
- `ntoskrnl!ExAllocatePool2` at `0x1402b80d4`
- `ntoskrnl!ExAllocatePool2` at `0x1402b7ef4`
- `ntoskrnl!ExAllocatePool2` at `0x1402b7ffe`
- `ntoskrnl!ExAllocatePool2` at `0x1402b80d4`
- `ntoskrnl!MmFreePagesFromMdl` at `0x1402b82c5`
- `ntoskrnl!MmFreePagesFromMdl` at `0x1402b82c5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402b81f8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402b81f8`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402b8246`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402b8246`
- `watchdog!WdLogSingleEntry1` at `0x1402b7f15`
- `watchdog!WdLogSingleEntry1` at `0x1402b7f84`
- `watchdog!WdLogSingleEntry1` at `0x1402b7fd3`
- `watchdog!WdLogSingleEntry1` at `0x1402b8020`
- `watchdog!WdLogSingleEntry1` at `0x1402b80f6`
- `watchdog!WdLogSingleEntry1` at `0x1402b821f`
- `watchdog!WdLogSingleEntry1` at `0x1402b82ac`
- `watchdog!WdLogSingleEntry1` at `0x1402b82f2`
- `watchdog!WdLogSingleEntry1` at `0x1402b830f`
- `watchdog!WdLogSingleEntry1` at `0x1402b7f15`
- `watchdog!WdLogSingleEntry1` at `0x1402b7f84`
- `watchdog!WdLogSingleEntry1` at `0x1402b7fd3`
- `watchdog!WdLogSingleEntry1` at `0x1402b8020`
- `watchdog!WdLogSingleEntry1` at `0x1402b80f6`
- `watchdog!WdLogSingleEntry1` at `0x1402b821f`
- `watchdog!WdLogSingleEntry1` at `0x1402b82ac`
- `watchdog!WdLogSingleEntry1` at `0x1402b82f2`
- `watchdog!WdLogSingleEntry1` at `0x1402b830f`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrQueryMetadata` at `0x1402b7ecb`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrQueryMetadata` at `0x1402b7fb7`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrQueryMetadata` at `0x1402b7ecb`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrQueryMetadata` at `0x1402b7fb7`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1402b7f4c`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1402b805e`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1402b7f4c`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1402b805e`

## pseudocode

```c

```
