# WaitForSynchronizationObjectFromGpu(uint,uint const *,unsigned __int64 const *,unsigned __int64,uint,DXGPROCESS *,bool,bool,bool,bool,bool)

- ea: `0x1403434d4`
- end: `0x140344e0c`
- name: `?WaitForSynchronizationObjectFromGpu@@YAJIPEBIPEB_K_KIPEAVDXGPROCESS@@_N4444@Z`
- size: `6456`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *, unsigned __int64 *, unsigned int *, unsigned int, struct DXGPROCESS *, bool, bool, bool, bool, bool)`
- caller_count: `4`
- callee_count: `38`
- tags: ``

## callers

- `0x140342a2c`
- `0x140342f64`
- `0x140344e14`
- `0x140345090`

## callees

- `0x140012540`
- `0x1400146ac`
- `0x140015290`
- `0x140015b30`
- `0x140015f30`
- `0x1400164f0`
- `0x140018054`
- `0x14001a38c`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001bea0`
- `0x14001ce20`
- `0x14001d1a0`
- `0x14001dca4`
- `0x14001e8d4`
- `0x14001f2f0`
- `0x140021cf0`
- `0x14002def0`
- `0x14002e1d0`
- `0x140030850`
- `0x140030a30`
- `0x140033da4`
- `0x140036ea8`
- `0x140037c54`
- `0x140037ef0`
- `0x14003bf10`
- `0x140048a5c`
- `0x1400674c4`
- `0x14007bd50`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x14019d0b0`
- `0x1403344b8`
- `0x1403345d0`
- `0x140336360`
- `0x140337124`
- `0x1403434d4`
- `0x14038ccec`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140343930`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140343c91`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140343930`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140343c91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140343668`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403436aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403437ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034382f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140343e77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140343fc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034400a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344164`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344256`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344297`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344431`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344472`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344557`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403445d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034461a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403446c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344736`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344777`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344810`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034488a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344c0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344c7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344d27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344d99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344dda`
- `ntoskrnl!ExFreePoolWithTag` at `0x140343668`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403436aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403437ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034382f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140343e77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140343fc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034400a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344164`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344256`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344297`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344431`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344472`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344557`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403445d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034461a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403446c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344736`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344777`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344810`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034488a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344c0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344c7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344d27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344d99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344dda`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140343924`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140343c85`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140343924`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140343c85`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14034373f`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14034373f`
- `watchdog!WdLogSingleEntry4` at `0x140344b97`
- `watchdog!WdLogSingleEntry4` at `0x140344cb8`
- `watchdog!WdLogSingleEntry4` at `0x140344cf0`
- `watchdog!WdLogSingleEntry4` at `0x140344b97`
- `watchdog!WdLogSingleEntry4` at `0x140344cb8`
- `watchdog!WdLogSingleEntry4` at `0x140344cf0`
- `watchdog!WdLogSingleEntry2` at `0x140343ddb`
- `watchdog!WdLogSingleEntry2` at `0x140343ea1`
- `watchdog!WdLogSingleEntry2` at `0x1403442b0`
- `watchdog!WdLogSingleEntry2` at `0x140343ddb`
- `watchdog!WdLogSingleEntry2` at `0x140343ea1`
- `watchdog!WdLogSingleEntry2` at `0x1403442b0`
- `watchdog!WdLogSingleEntry3` at `0x1403435b0`
- `watchdog!WdLogSingleEntry3` at `0x140343f14`
- `watchdog!WdLogSingleEntry3` at `0x140344037`
- `watchdog!WdLogSingleEntry3` at `0x140344333`
- `watchdog!WdLogSingleEntry3` at `0x1403435b0`
- `watchdog!WdLogSingleEntry3` at `0x140343f14`
- `watchdog!WdLogSingleEntry3` at `0x140344037`
- `watchdog!WdLogSingleEntry3` at `0x140344333`
- `watchdog!WdLogSingleEntry0` at `0x140343968`
- `watchdog!WdLogSingleEntry0` at `0x1403439be`
- `watchdog!WdLogSingleEntry0` at `0x140343a14`
- `watchdog!WdLogSingleEntry0` at `0x140343c1b`
- `watchdog!WdLogSingleEntry0` at `0x140343d4f`
- `watchdog!WdLogSingleEntry0` at `0x140343968`
- `watchdog!WdLogSingleEntry0` at `0x1403439be`
- `watchdog!WdLogSingleEntry0` at `0x140343a14`
- `watchdog!WdLogSingleEntry0` at `0x140343c1b`
- `watchdog!WdLogSingleEntry0` at `0x140343d4f`
- `watchdog!WdLogSingleEntry1` at `0x140344078`
- `watchdog!WdLogSingleEntry1` at `0x1403440c8`
- `watchdog!WdLogSingleEntry1` at `0x140344187`
- `watchdog!WdLogSingleEntry1` at `0x1403441b7`
- `watchdog!WdLogSingleEntry1` at `0x1403442fb`
- `watchdog!WdLogSingleEntry1` at `0x1403444e5`
- `watchdog!WdLogSingleEntry1` at `0x140344665`
- `watchdog!WdLogSingleEntry1` at `0x140344078`
- `watchdog!WdLogSingleEntry1` at `0x1403440c8`
- `watchdog!WdLogSingleEntry1` at `0x140344187`
- `watchdog!WdLogSingleEntry1` at `0x1403441b7`
- `watchdog!WdLogSingleEntry1` at `0x1403442fb`
- `watchdog!WdLogSingleEntry1` at `0x1403444e5`
- `watchdog!WdLogSingleEntry1` at `0x140344665`

## string_xrefs

- `0x1403442e9`: `WaitForSynchronizationObjectFromGpu on device 0x%p attempts to use a sync object opened on a different device 0x%p.`
- `0x1403441eb`: `0x%x object is opened as signal only and thus cannot be waited on.`
- `0x140343f51`: `0x%I64x failed, failed to create a sync object on logical adapter 0x%I64x returning 0x%I64x`
- `0x140344524`: `0x%I64x encountered exception when copying monitored fence value array.`

## pseudocode

```c

```
