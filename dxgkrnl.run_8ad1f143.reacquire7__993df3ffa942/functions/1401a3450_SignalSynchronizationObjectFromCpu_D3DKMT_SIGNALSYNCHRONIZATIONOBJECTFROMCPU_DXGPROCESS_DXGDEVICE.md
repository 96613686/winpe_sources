# SignalSynchronizationObjectFromCpu(_D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU *,DXGPROCESS *,DXGDEVICE *)

- ea: `0x1401a3450`
- end: `0x1401a3f7e`
- name: `?SignalSynchronizationObjectFromCpu@@YAJPEAU_D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU@@PEAVDXGPROCESS@@PEAVDXGDEVICE@@@Z`
- size: `2862`
- prototype: `__int64 __fastcall(struct _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU *, struct DXGPROCESS *, struct ADAPTER_RENDER **)`
- caller_count: `2`
- callee_count: `17`
- tags: ``

## callers

- `0x1401a2c40`
- `0x1403def20`

## callees

- `0x140012540`
- `0x140012cd4`
- `0x140013a20`
- `0x14001b9c0`
- `0x14001d1a0`
- `0x14001d214`
- `0x14001dca4`
- `0x14001fa40`
- `0x1400203d0`
- `0x1400221b0`
- `0x140033eb0`
- `0x140047ad4`
- `0x1400a1000`
- `0x1401a3450`
- `0x1401a3f84`
- `0x1403345d0`
- `0x140336360`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a3822`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a3822`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a364b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3673`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3950`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3978`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3a6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3a92`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3bc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3bea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3cb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3cd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3dc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3dec`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3efa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3f22`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a364b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3673`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3950`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3978`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3a6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3a92`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3bc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3bea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3cb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3cd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3dc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3dec`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3efa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a3f22`
- `ntoskrnl!ExAllocatePool2` at `0x1401a36d1`
- `ntoskrnl!ExAllocatePool2` at `0x1401a36d1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401a3816`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401a3816`
- `watchdog!WdLogSingleEntry4` at `0x1401a3afa`
- `watchdog!WdLogSingleEntry4` at `0x1401a3afa`
- `watchdog!WdLogSingleEntry0` at `0x1401a34eb`
- `watchdog!WdLogSingleEntry0` at `0x1401a3536`
- `watchdog!WdLogSingleEntry0` at `0x1401a3582`
- `watchdog!WdLogSingleEntry0` at `0x1401a35ce`
- `watchdog!WdLogSingleEntry0` at `0x1401a37ac`
- `watchdog!WdLogSingleEntry0` at `0x1401a3879`
- `watchdog!WdLogSingleEntry0` at `0x1401a3b69`
- `watchdog!WdLogSingleEntry0` at `0x1401a34eb`
- `watchdog!WdLogSingleEntry0` at `0x1401a3536`
- `watchdog!WdLogSingleEntry0` at `0x1401a3582`
- `watchdog!WdLogSingleEntry0` at `0x1401a35ce`
- `watchdog!WdLogSingleEntry0` at `0x1401a37ac`
- `watchdog!WdLogSingleEntry0` at `0x1401a3879`
- `watchdog!WdLogSingleEntry0` at `0x1401a3b69`
- `watchdog!WdLogSingleEntry5` at `0x1401a39b8`
- `watchdog!WdLogSingleEntry5` at `0x1401a39b8`
- `watchdog!WdLogSingleEntry1` at `0x1401a38f6`
- `watchdog!WdLogSingleEntry1` at `0x1401a3a08`
- `watchdog!WdLogSingleEntry1` at `0x1401a3d5a`
- `watchdog!WdLogSingleEntry1` at `0x1401a3e97`
- `watchdog!WdLogSingleEntry1` at `0x1401a38f6`
- `watchdog!WdLogSingleEntry1` at `0x1401a3a08`
- `watchdog!WdLogSingleEntry1` at `0x1401a3d5a`
- `watchdog!WdLogSingleEntry1` at `0x1401a3e97`

## string_xrefs

- `0x1401a3a19`: `0x%I64x object is opened as wait only and thus cannot be signaled.`

## pseudocode

```c

```
