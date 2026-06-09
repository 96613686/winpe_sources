# WaitForSynchronizationObjectFromGpu(uint,uint const *,unsigned __int64 const *,unsigned __int64,uint,DXGPROCESS *,bool,bool,bool,bool,bool)

- ea: `0x14034d6b4`
- end: `0x14034efec`
- name: `?WaitForSynchronizationObjectFromGpu@@YAJIPEBIPEB_K_KIPEAVDXGPROCESS@@_N4444@Z`
- size: `6456`
- prototype: `__int64 __fastcall(unsigned int, const unsigned int *, const unsigned __int64 *, unsigned __int64, unsigned int, struct DXGPROCESS *, bool, bool, bool, bool, bool)`
- caller_count: `4`
- callee_count: `38`
- tags: ``

## callers

- `0x14034cc0c`
- `0x14034d144`
- `0x14034eff4`
- `0x14034f270`

## callees

- `0x140012380`
- `0x1400144ec`
- `0x1400150d0`
- `0x140015970`
- `0x140015d70`
- `0x140016330`
- `0x140017fb8`
- `0x14001a2ec`
- `0x14001ab20`
- `0x14001b890`
- `0x14001bd70`
- `0x14001ccf0`
- `0x14001d070`
- `0x14001dad4`
- `0x14001e704`
- `0x14001f120`
- `0x140021b20`
- `0x14002dd20`
- `0x14002e000`
- `0x140030680`
- `0x140030860`
- `0x140033bd4`
- `0x140036cd8`
- `0x140037a84`
- `0x140037d20`
- `0x14003bcb0`
- `0x14004885c`
- `0x1400670a4`
- `0x14007b4e4`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1401990b0`
- `0x14032d748`
- `0x14032d860`
- `0x14032f5f0`
- `0x140330704`
- `0x14034d6b4`
- `0x14038dc24`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14034db10`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14034de71`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14034db10`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14034de71`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034d848`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034d88a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034d9cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034da0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e057`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e1a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e1ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e344`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e436`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e477`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e611`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e652`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e737`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e7b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e7fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e8a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e916`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e957`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e9f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034ea6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034edea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034ee5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034ef07`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034ef79`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034efba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034d848`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034d88a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034d9cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034da0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e057`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e1a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e1ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e344`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e436`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e477`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e611`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e652`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e737`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e7b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e7fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e8a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e916`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e957`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e9f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034ea6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034edea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034ee5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034ef07`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034ef79`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034efba`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14034db04`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14034de65`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14034db04`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14034de65`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14034d91f`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14034d91f`
- `watchdog!WdLogSingleEntry4` at `0x14034ed77`
- `watchdog!WdLogSingleEntry4` at `0x14034ee98`
- `watchdog!WdLogSingleEntry4` at `0x14034eed0`
- `watchdog!WdLogSingleEntry4` at `0x14034ed77`
- `watchdog!WdLogSingleEntry4` at `0x14034ee98`
- `watchdog!WdLogSingleEntry4` at `0x14034eed0`
- `watchdog!WdLogSingleEntry2` at `0x14034dfbb`
- `watchdog!WdLogSingleEntry2` at `0x14034e081`
- `watchdog!WdLogSingleEntry2` at `0x14034e490`
- `watchdog!WdLogSingleEntry2` at `0x14034dfbb`
- `watchdog!WdLogSingleEntry2` at `0x14034e081`
- `watchdog!WdLogSingleEntry2` at `0x14034e490`
- `watchdog!WdLogSingleEntry3` at `0x14034d790`
- `watchdog!WdLogSingleEntry3` at `0x14034e0f4`
- `watchdog!WdLogSingleEntry3` at `0x14034e217`
- `watchdog!WdLogSingleEntry3` at `0x14034e513`
- `watchdog!WdLogSingleEntry3` at `0x14034d790`
- `watchdog!WdLogSingleEntry3` at `0x14034e0f4`
- `watchdog!WdLogSingleEntry3` at `0x14034e217`
- `watchdog!WdLogSingleEntry3` at `0x14034e513`
- `watchdog!WdLogSingleEntry0` at `0x14034db48`
- `watchdog!WdLogSingleEntry0` at `0x14034db9e`
- `watchdog!WdLogSingleEntry0` at `0x14034dbf4`
- `watchdog!WdLogSingleEntry0` at `0x14034ddfb`
- `watchdog!WdLogSingleEntry0` at `0x14034df2f`
- `watchdog!WdLogSingleEntry0` at `0x14034db48`
- `watchdog!WdLogSingleEntry0` at `0x14034db9e`
- `watchdog!WdLogSingleEntry0` at `0x14034dbf4`
- `watchdog!WdLogSingleEntry0` at `0x14034ddfb`
- `watchdog!WdLogSingleEntry0` at `0x14034df2f`
- `watchdog!WdLogSingleEntry1` at `0x14034e258`
- `watchdog!WdLogSingleEntry1` at `0x14034e2a8`
- `watchdog!WdLogSingleEntry1` at `0x14034e367`
- `watchdog!WdLogSingleEntry1` at `0x14034e397`
- `watchdog!WdLogSingleEntry1` at `0x14034e4db`
- `watchdog!WdLogSingleEntry1` at `0x14034e6c5`
- `watchdog!WdLogSingleEntry1` at `0x14034e845`
- `watchdog!WdLogSingleEntry1` at `0x14034e258`
- `watchdog!WdLogSingleEntry1` at `0x14034e2a8`
- `watchdog!WdLogSingleEntry1` at `0x14034e367`
- `watchdog!WdLogSingleEntry1` at `0x14034e397`
- `watchdog!WdLogSingleEntry1` at `0x14034e4db`
- `watchdog!WdLogSingleEntry1` at `0x14034e6c5`
- `watchdog!WdLogSingleEntry1` at `0x14034e845`

## string_xrefs

- `0x14034e4c9`: `WaitForSynchronizationObjectFromGpu on device 0x%p attempts to use a sync object opened on a different device 0x%p.`
- `0x14034e3cb`: `0x%x object is opened as signal only and thus cannot be waited on.`
- `0x14034e131`: `0x%I64x failed, failed to create a sync object on logical adapter 0x%I64x returning 0x%I64x`
- `0x14034e704`: `0x%I64x encountered exception when copying monitored fence value array.`

## pseudocode

```c

```
