# SubmitWaitForSyncObjectsFromGpu(uint,uint const *,unsigned __int64 const *,uint,DXGPROCESS *,bool,bool)

- ea: `0x1403355ec`
- end: `0x140336359`
- name: `?SubmitWaitForSyncObjectsFromGpu@@YAJIPEBIPEB_KIPEAVDXGPROCESS@@_N3@Z`
- size: `3437`
- prototype: `__int64 __fastcall(unsigned int, const unsigned int *, unsigned __int64 *, unsigned int, struct DXGPROCESS *, bool, bool)`
- caller_count: `2`
- callee_count: `27`
- tags: ``

## callers

- `0x140336418`
- `0x140345090`

## callees

- `0x140012540`
- `0x1400146ac`
- `0x140014950`
- `0x140015290`
- `0x140015b30`
- `0x140015f30`
- `0x140018054`
- `0x14001b9c0`
- `0x14001c5c0`
- `0x14001d1a0`
- `0x14001dca4`
- `0x14001f2f0`
- `0x14002def0`
- `0x14002e1d0`
- `0x140030a30`
- `0x140033da4`
- `0x14003bf10`
- `0x140047990`
- `0x140048a5c`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x140198d48`
- `0x1403345d0`
- `0x1403355ec`
- `0x140336360`
- `0x140337124`
- `0x140342960`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403357f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140335df5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403357f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140335df5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403359a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335c3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335c99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335cd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335cf8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335d4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335d68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335ebe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335eef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335f23`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335fb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335fea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033601f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403360ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403360df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033611c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403361c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403361f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033622e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403359a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335c3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335c99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335cd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335cf8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335d4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335d68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335ebe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335eef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335f23`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335fb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140335fea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033601f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403360ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403360df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033611c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403361c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403361f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033622e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403357ec`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140335de9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403357ec`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140335de9`
- `watchdog!WdLogSingleEntry4` at `0x140336144`
- `watchdog!WdLogSingleEntry4` at `0x140336144`
- `watchdog!WdLogSingleEntry2` at `0x140335865`
- `watchdog!WdLogSingleEntry2` at `0x140335865`
- `watchdog!WdLogSingleEntry3` at `0x14033625a`
- `watchdog!WdLogSingleEntry3` at `0x1403362f4`
- `watchdog!WdLogSingleEntry3` at `0x14033625a`
- `watchdog!WdLogSingleEntry3` at `0x1403362f4`
- `watchdog!WdLogSingleEntry1` at `0x140335bc8`
- `watchdog!WdLogSingleEntry1` at `0x140335e48`
- `watchdog!WdLogSingleEntry1` at `0x140335f42`
- `watchdog!WdLogSingleEntry1` at `0x140335bc8`
- `watchdog!WdLogSingleEntry1` at `0x140335e48`
- `watchdog!WdLogSingleEntry1` at `0x140335f42`

## string_xrefs

- `0x1403358a2`: `WaitForSynchronizationObjectFromGpu on device 0x%p attempts to use a sync object opened on a different device 0x%p.`
- `0x140335f78`: `0x%x object is opened as signal only and thus cannot be waited on.`
- `0x140335c07`: `0x%I64x encountered exception when copying monitored fence value array.`

## pseudocode

```c

```
