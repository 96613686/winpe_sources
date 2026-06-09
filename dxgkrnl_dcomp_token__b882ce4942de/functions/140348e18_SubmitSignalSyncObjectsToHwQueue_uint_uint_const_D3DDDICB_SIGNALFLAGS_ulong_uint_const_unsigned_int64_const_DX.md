# SubmitSignalSyncObjectsToHwQueue(uint,uint const *,_D3DDDICB_SIGNALFLAGS,ulong,uint const *,unsigned __int64 const *,DXGPROCESS *,bool,bool)

- ea: `0x140348e18`
- end: `0x14034a8ad`
- name: `?SubmitSignalSyncObjectsToHwQueue@@YAJIPEBIU_D3DDDICB_SIGNALFLAGS@@K0PEB_KPEAVDXGPROCESS@@_N4@Z`
- size: `6805`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, const unsigned int *@<rdx>, struct _D3DDDICB_SIGNALFLAGS@<r8d>, unsigned int@<r9d>, const unsigned int *, const unsigned __int64 *, struct DXGPROCESS *, bool, bool)`
- caller_count: `3`
- callee_count: `38`
- tags: ``

## callers

- `0x14034aa08`
- `0x14034f270`
- `0x1403deb00`

## callees

- `0x140012380`
- `0x140014790`
- `0x140015780`
- `0x140015970`
- `0x140015d70`
- `0x140017fb8`
- `0x14001ab20`
- `0x14001b890`
- `0x14001c490`
- `0x14001cbe0`
- `0x14001d070`
- `0x14001d144`
- `0x14001f120`
- `0x14001f460`
- `0x14001f870`
- `0x140020200`
- `0x140021b20`
- `0x14002d9f0`
- `0x14002db80`
- `0x14002dd20`
- `0x14002ec90`
- `0x140030860`
- `0x140033bd4`
- `0x14003bc2c`
- `0x14004255c`
- `0x140047790`
- `0x14004885c`
- `0x1400670a4`
- `0x1400a0100`
- `0x1400a0240`
- `0x1400a0540`
- `0x14019fcc4`
- `0x14032d748`
- `0x14032d860`
- `0x140348dd0`
- `0x140348e18`
- `0x14034a8b4`
- `0x14034a930`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14034918d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140349df3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14034918d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140349df3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403496f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034972c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034978f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034988d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349906`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349922`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034993e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034995a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349976`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349b01`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349b24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349b40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349b5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349b78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349c1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349c59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349c90`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349d50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349e99`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a0ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a16c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a1f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a2a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a2e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a315`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a407`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a44b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a47c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a4df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a67e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a691`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a7dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a853`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a866`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a879`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403496f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034972c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034978f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034988d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349906`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349922`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034993e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034995a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349976`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349b01`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349b24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349b40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349b5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349b78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349c1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349c59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349c90`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349d50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140349e99`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a0ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a16c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a1f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a2a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a2e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a315`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a407`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a44b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a47c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a4df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a67e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a691`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a7dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a853`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a866`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034a879`
- `ntoskrnl!ExAllocatePool2` at `0x14034a660`
- `ntoskrnl!ExAllocatePool2` at `0x14034a660`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140349181`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140349de7`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140349181`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140349de7`
- `watchdog!WdLogSingleEntry4` at `0x140349e31`
- `watchdog!WdLogSingleEntry4` at `0x140349f16`
- `watchdog!WdLogSingleEntry4` at `0x14034a3a2`
- `watchdog!WdLogSingleEntry4` at `0x140349e31`
- `watchdog!WdLogSingleEntry4` at `0x140349f16`
- `watchdog!WdLogSingleEntry4` at `0x14034a3a2`
- `watchdog!WdLogSingleEntry2` at `0x14034a7ef`
- `watchdog!WdLogSingleEntry2` at `0x14034a7ef`
- `watchdog!WdLogSingleEntry3` at `0x14034a224`
- `watchdog!WdLogSingleEntry3` at `0x14034a510`
- `watchdog!WdLogSingleEntry3` at `0x14034a713`
- `watchdog!WdLogSingleEntry3` at `0x14034a224`
- `watchdog!WdLogSingleEntry3` at `0x14034a510`
- `watchdog!WdLogSingleEntry3` at `0x14034a713`
- `watchdog!WdLogSingleEntry0` at `0x140349a09`
- `watchdog!WdLogSingleEntry0` at `0x140349d80`
- `watchdog!WdLogSingleEntry0` at `0x14034a17f`
- `watchdog!WdLogSingleEntry0` at `0x14034a6a7`
- `watchdog!WdLogSingleEntry0` at `0x14034a766`
- `watchdog!WdLogSingleEntry0` at `0x14034a78a`
- `watchdog!WdLogSingleEntry0` at `0x140349a09`
- `watchdog!WdLogSingleEntry0` at `0x140349d80`
- `watchdog!WdLogSingleEntry0` at `0x14034a17f`
- `watchdog!WdLogSingleEntry0` at `0x14034a6a7`
- `watchdog!WdLogSingleEntry0` at `0x14034a766`
- `watchdog!WdLogSingleEntry0` at `0x14034a78a`
- `watchdog!WdLogSingleEntry1` at `0x140349501`
- `watchdog!WdLogSingleEntry1` at `0x140349681`
- `watchdog!WdLogSingleEntry1` at `0x140349ab8`
- `watchdog!WdLogSingleEntry1` at `0x14034a04c`
- `watchdog!WdLogSingleEntry1` at `0x140349501`
- `watchdog!WdLogSingleEntry1` at `0x140349681`
- `watchdog!WdLogSingleEntry1` at `0x140349ab8`
- `watchdog!WdLogSingleEntry1` at `0x14034a04c`

## string_xrefs

- `0x14034a838`: `SignalSynchronizationObjectFromGpu on device 0x%p attempts to use a sync object opened on a different device 0x%p.`
- `0x14034a081`: `0x%I64x object is opened with NoSignal flag and thus cannot be signaled.`
- `0x14034a270`: `0x%I64x failed, failed to create a sync object on logical adapter 0x%I64x returning 0x%I64x`
- `0x1403496c0`: `0x%I64x encountered exception when copying monitored fence value array.`

## pseudocode

```c

```
