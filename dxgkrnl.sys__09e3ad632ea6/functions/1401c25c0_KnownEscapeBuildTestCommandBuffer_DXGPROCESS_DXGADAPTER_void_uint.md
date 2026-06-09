# KnownEscapeBuildTestCommandBuffer(DXGPROCESS *,DXGADAPTER *,void *,uint)

- ea: `0x1401c25c0`
- end: `0x1401c2fe8`
- name: `?KnownEscapeBuildTestCommandBuffer@@YAJPEAVDXGPROCESS@@PEAVDXGADAPTER@@PEAXI@Z`
- size: `2600`
- prototype: `__int64 __fastcall(struct DXGPROCESS *, struct DXGADAPTER *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14023d6cc`

## callees

- `0x14001a874`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001bea0`
- `0x1400a1000`
- `0x1401c25c0`
- `0x1401e76e0`
- `0x1402002e8`
- `0x140295184`
- `0x14036d1f4`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401c2ef6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401c2ef6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401c2eea`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401c2eea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c2b0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c2dff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c2e15`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c2b0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c2dff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c2e15`
- `ntoskrnl!ExAllocatePool2` at `0x1401c2a25`
- `ntoskrnl!ExAllocatePool2` at `0x1401c2bcf`
- `ntoskrnl!ExAllocatePool2` at `0x1401c2bfd`
- `ntoskrnl!ExAllocatePool2` at `0x1401c2a25`
- `ntoskrnl!ExAllocatePool2` at `0x1401c2bcf`
- `ntoskrnl!ExAllocatePool2` at `0x1401c2bfd`
- `watchdog!WdLogSingleEntry0` at `0x1401c25f4`
- `watchdog!WdLogSingleEntry0` at `0x1401c261e`
- `watchdog!WdLogSingleEntry0` at `0x1401c2799`
- `watchdog!WdLogSingleEntry0` at `0x1401c28b0`
- `watchdog!WdLogSingleEntry0` at `0x1401c2981`
- `watchdog!WdLogSingleEntry0` at `0x1401c29db`
- `watchdog!WdLogSingleEntry0` at `0x1401c2af3`
- `watchdog!WdLogSingleEntry0` at `0x1401c2b8d`
- `watchdog!WdLogSingleEntry0` at `0x1401c2d53`
- `watchdog!WdLogSingleEntry0` at `0x1401c2d93`
- `watchdog!WdLogSingleEntry0` at `0x1401c2e91`
- `watchdog!WdLogSingleEntry0` at `0x1401c2f0e`
- `watchdog!WdLogSingleEntry0` at `0x1401c2f69`
- `watchdog!WdLogSingleEntry0` at `0x1401c2f88`
- `watchdog!WdLogSingleEntry0` at `0x1401c25f4`
- `watchdog!WdLogSingleEntry0` at `0x1401c261e`
- `watchdog!WdLogSingleEntry0` at `0x1401c2799`
- `watchdog!WdLogSingleEntry0` at `0x1401c28b0`
- `watchdog!WdLogSingleEntry0` at `0x1401c2981`
- `watchdog!WdLogSingleEntry0` at `0x1401c29db`
- `watchdog!WdLogSingleEntry0` at `0x1401c2af3`
- `watchdog!WdLogSingleEntry0` at `0x1401c2b8d`
- `watchdog!WdLogSingleEntry0` at `0x1401c2d53`
- `watchdog!WdLogSingleEntry0` at `0x1401c2d93`
- `watchdog!WdLogSingleEntry0` at `0x1401c2e91`
- `watchdog!WdLogSingleEntry0` at `0x1401c2f0e`
- `watchdog!WdLogSingleEntry0` at `0x1401c2f69`
- `watchdog!WdLogSingleEntry0` at `0x1401c2f88`

## string_xrefs

- `0x1401c2f99`: `Invalid command`

## pseudocode

```c

```
