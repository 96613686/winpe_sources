# DpiClaimPersistedMemoryBlock(_FDO_CONTEXT *,unsigned __int64,_GUID const *)

- ea: `0x1402be8d0`
- end: `0x1402bedc8`
- name: `?DpiClaimPersistedMemoryBlock@@YAJPEAU_FDO_CONTEXT@@_KPEBU_GUID@@@Z`
- size: `1272`
- prototype: `__int64 __fastcall(struct _FDO_CONTEXT *, __int64, const struct _GUID *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1402bfb5c`
- `0x1402bfd5c`

## callees

- `0x1402be8d0`
- `0x1402bedd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1402bed26`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bed7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bed90`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bed26`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bed7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bed90`
- `ntoskrnl!ExAllocatePool2` at `0x1402be944`
- `ntoskrnl!ExAllocatePool2` at `0x1402bea4e`
- `ntoskrnl!ExAllocatePool2` at `0x1402beb24`
- `ntoskrnl!ExAllocatePool2` at `0x1402be944`
- `ntoskrnl!ExAllocatePool2` at `0x1402bea4e`
- `ntoskrnl!ExAllocatePool2` at `0x1402beb24`
- `ntoskrnl!MmFreePagesFromMdl` at `0x1402bed15`
- `ntoskrnl!MmFreePagesFromMdl` at `0x1402bed15`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402bec48`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402bec48`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402bec96`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402bec96`
- `watchdog!WdLogSingleEntry1` at `0x1402be965`
- `watchdog!WdLogSingleEntry1` at `0x1402be9d4`
- `watchdog!WdLogSingleEntry1` at `0x1402bea23`
- `watchdog!WdLogSingleEntry1` at `0x1402bea70`
- `watchdog!WdLogSingleEntry1` at `0x1402beb46`
- `watchdog!WdLogSingleEntry1` at `0x1402bec6f`
- `watchdog!WdLogSingleEntry1` at `0x1402becfc`
- `watchdog!WdLogSingleEntry1` at `0x1402bed42`
- `watchdog!WdLogSingleEntry1` at `0x1402bed5f`
- `watchdog!WdLogSingleEntry1` at `0x1402be965`
- `watchdog!WdLogSingleEntry1` at `0x1402be9d4`
- `watchdog!WdLogSingleEntry1` at `0x1402bea23`
- `watchdog!WdLogSingleEntry1` at `0x1402bea70`
- `watchdog!WdLogSingleEntry1` at `0x1402beb46`
- `watchdog!WdLogSingleEntry1` at `0x1402bec6f`
- `watchdog!WdLogSingleEntry1` at `0x1402becfc`
- `watchdog!WdLogSingleEntry1` at `0x1402bed42`
- `watchdog!WdLogSingleEntry1` at `0x1402bed5f`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrQueryMetadata` at `0x1402be91b`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrQueryMetadata` at `0x1402bea07`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrQueryMetadata` at `0x1402be91b`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrQueryMetadata` at `0x1402bea07`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1402be99c`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1402beaae`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1402be99c`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1402beaae`

## pseudocode

```c

```
