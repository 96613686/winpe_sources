# KnownEscapeBuildTestCommandBuffer(DXGPROCESS *,DXGADAPTER *,void *,uint)

- ea: `0x1401bf9c0`
- end: `0x1401c03e8`
- name: `?KnownEscapeBuildTestCommandBuffer@@YAJPEAVDXGPROCESS@@PEAVDXGADAPTER@@PEAXI@Z`
- size: `2600`
- prototype: `__int64 __fastcall(struct DXGPROCESS *, struct DXGADAPTER *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14023ab6c`

## callees

- `0x14001a7d4`
- `0x14001ab20`
- `0x14001b890`
- `0x14001bd70`
- `0x1400a0540`
- `0x1401bf9c0`
- `0x1401e5360`
- `0x1401fdf08`
- `0x14028e824`
- `0x14036d1b4`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401c02f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401c02f6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401c02ea`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401c02ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401bff0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c01ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c0215`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401bff0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c01ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c0215`
- `ntoskrnl!ExAllocatePool2` at `0x1401bfe25`
- `ntoskrnl!ExAllocatePool2` at `0x1401bffcf`
- `ntoskrnl!ExAllocatePool2` at `0x1401bfffd`
- `ntoskrnl!ExAllocatePool2` at `0x1401bfe25`
- `ntoskrnl!ExAllocatePool2` at `0x1401bffcf`
- `ntoskrnl!ExAllocatePool2` at `0x1401bfffd`
- `watchdog!WdLogSingleEntry0` at `0x1401bf9f4`
- `watchdog!WdLogSingleEntry0` at `0x1401bfa1e`
- `watchdog!WdLogSingleEntry0` at `0x1401bfb99`
- `watchdog!WdLogSingleEntry0` at `0x1401bfcb0`
- `watchdog!WdLogSingleEntry0` at `0x1401bfd81`
- `watchdog!WdLogSingleEntry0` at `0x1401bfddb`
- `watchdog!WdLogSingleEntry0` at `0x1401bfef3`
- `watchdog!WdLogSingleEntry0` at `0x1401bff8d`
- `watchdog!WdLogSingleEntry0` at `0x1401c0153`
- `watchdog!WdLogSingleEntry0` at `0x1401c0193`
- `watchdog!WdLogSingleEntry0` at `0x1401c0291`
- `watchdog!WdLogSingleEntry0` at `0x1401c030e`
- `watchdog!WdLogSingleEntry0` at `0x1401c0369`
- `watchdog!WdLogSingleEntry0` at `0x1401c0388`
- `watchdog!WdLogSingleEntry0` at `0x1401bf9f4`
- `watchdog!WdLogSingleEntry0` at `0x1401bfa1e`
- `watchdog!WdLogSingleEntry0` at `0x1401bfb99`
- `watchdog!WdLogSingleEntry0` at `0x1401bfcb0`
- `watchdog!WdLogSingleEntry0` at `0x1401bfd81`
- `watchdog!WdLogSingleEntry0` at `0x1401bfddb`
- `watchdog!WdLogSingleEntry0` at `0x1401bfef3`
- `watchdog!WdLogSingleEntry0` at `0x1401bff8d`
- `watchdog!WdLogSingleEntry0` at `0x1401c0153`
- `watchdog!WdLogSingleEntry0` at `0x1401c0193`
- `watchdog!WdLogSingleEntry0` at `0x1401c0291`
- `watchdog!WdLogSingleEntry0` at `0x1401c030e`
- `watchdog!WdLogSingleEntry0` at `0x1401c0369`
- `watchdog!WdLogSingleEntry0` at `0x1401c0388`

## string_xrefs

- `0x1401c0399`: `Invalid command`

## pseudocode

```c

```
