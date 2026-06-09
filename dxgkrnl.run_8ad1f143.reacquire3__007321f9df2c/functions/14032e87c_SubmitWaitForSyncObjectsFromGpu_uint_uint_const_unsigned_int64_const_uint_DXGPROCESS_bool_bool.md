# SubmitWaitForSyncObjectsFromGpu(uint,uint const *,unsigned __int64 const *,uint,DXGPROCESS *,bool,bool)

- ea: `0x14032e87c`
- end: `0x14032f5e9`
- name: `?SubmitWaitForSyncObjectsFromGpu@@YAJIPEBIPEB_KIPEAVDXGPROCESS@@_N3@Z`
- size: `3437`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, const unsigned int *@<rdx>, const unsigned __int64 *@<r8>, unsigned int@<r9d>, struct DXGPROCESS *, bool, bool)`
- caller_count: `2`
- callee_count: `27`
- tags: ``

## callers

- `0x140330258`
- `0x14034f270`

## callees

- `0x140012380`
- `0x1400144ec`
- `0x140014790`
- `0x1400150d0`
- `0x140015970`
- `0x140015d70`
- `0x140017fb8`
- `0x14001b890`
- `0x14001c490`
- `0x14001d070`
- `0x14001dad4`
- `0x14001f120`
- `0x14002dd20`
- `0x14002e000`
- `0x140030860`
- `0x140033bd4`
- `0x14003bcb0`
- `0x140047790`
- `0x14004885c`
- `0x1400670a4`
- `0x1400a0100`
- `0x140194d48`
- `0x14032d860`
- `0x14032e87c`
- `0x14032f5f0`
- `0x140330704`
- `0x14034cb40`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14032ea88`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14032f085`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14032ea88`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14032f085`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032ec32`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032eeca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032ef29`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032ef65`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032ef88`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032efdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032eff8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f14e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f17f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f1b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f248`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f27a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f2af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f33d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f36f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f3ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f457`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f489`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f4be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032ec32`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032eeca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032ef29`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032ef65`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032ef88`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032efdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032eff8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f14e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f17f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f1b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f248`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f27a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f2af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f33d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f36f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f3ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f457`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f489`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f4be`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14032ea7c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14032f079`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14032ea7c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14032f079`
- `watchdog!WdLogSingleEntry4` at `0x14032f3d4`
- `watchdog!WdLogSingleEntry4` at `0x14032f3d4`
- `watchdog!WdLogSingleEntry2` at `0x14032eaf5`
- `watchdog!WdLogSingleEntry2` at `0x14032eaf5`
- `watchdog!WdLogSingleEntry3` at `0x14032f4ea`
- `watchdog!WdLogSingleEntry3` at `0x14032f584`
- `watchdog!WdLogSingleEntry3` at `0x14032f4ea`
- `watchdog!WdLogSingleEntry3` at `0x14032f584`
- `watchdog!WdLogSingleEntry1` at `0x14032ee58`
- `watchdog!WdLogSingleEntry1` at `0x14032f0d8`
- `watchdog!WdLogSingleEntry1` at `0x14032f1d2`
- `watchdog!WdLogSingleEntry1` at `0x14032ee58`
- `watchdog!WdLogSingleEntry1` at `0x14032f0d8`
- `watchdog!WdLogSingleEntry1` at `0x14032f1d2`

## string_xrefs

- `0x14032eb32`: `WaitForSynchronizationObjectFromGpu on device 0x%p attempts to use a sync object opened on a different device 0x%p.`
- `0x14032f208`: `0x%x object is opened as signal only and thus cannot be waited on.`
- `0x14032ee97`: `0x%I64x encountered exception when copying monitored fence value array.`

## pseudocode

```c

```
