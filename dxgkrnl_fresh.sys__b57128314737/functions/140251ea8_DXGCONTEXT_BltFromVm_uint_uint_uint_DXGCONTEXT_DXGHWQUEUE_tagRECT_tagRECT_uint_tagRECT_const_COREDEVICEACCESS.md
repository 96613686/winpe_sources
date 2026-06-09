# DXGCONTEXT::BltFromVm(uint,uint,uint,DXGCONTEXT * *,DXGHWQUEUE *,tagRECT,tagRECT,uint,tagRECT const *,COREDEVICEACCESS *)

- ea: `0x140251ea8`
- end: `0x140252a26`
- name: `?BltFromVm@DXGCONTEXT@@QEAAJIIIPEAPEAV1@PEAVDXGHWQUEUE@@UtagRECT@@2IPEBU3@PEAVCOREDEVICEACCESS@@@Z`
- size: `2942`
- prototype: `__int64 __fastcall(DXGCONTEXT *this, unsigned int, unsigned int, __int64, struct DXGCONTEXT **, struct DXGHWQUEUE *, struct tagRECT *, struct tagRECT *, UINT, const struct tagRECT *, struct COREDEVICEACCESS *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x140288e20`

## callees

- `0x14001b9c0`
- `0x14001d1a0`
- `0x14002dc10`
- `0x14003cd10`
- `0x140049424`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x140251ea8`
- `0x14031a9cc`
- `0x14031e5d8`
- `0x14032e980`
- `0x14032fd70`
- `0x140393f58`
- `0x1403942d8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140251ff9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14025222f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140251ff9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14025222f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140251fed`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140252223`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140251fed`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140252223`
- `watchdog!WdLogSingleEntry3` at `0x140252933`
- `watchdog!WdLogSingleEntry3` at `0x1402529a0`
- `watchdog!WdLogSingleEntry3` at `0x140252933`
- `watchdog!WdLogSingleEntry3` at `0x1402529a0`
- `watchdog!WdLogSingleEntry0` at `0x140251f85`
- `watchdog!WdLogSingleEntry0` at `0x1402521b8`
- `watchdog!WdLogSingleEntry0` at `0x140252524`
- `watchdog!WdLogSingleEntry0` at `0x140252810`
- `watchdog!WdLogSingleEntry0` at `0x140252879`
- `watchdog!WdLogSingleEntry0` at `0x1402528ba`
- `watchdog!WdLogSingleEntry0` at `0x140251f85`
- `watchdog!WdLogSingleEntry0` at `0x1402521b8`
- `watchdog!WdLogSingleEntry0` at `0x140252524`
- `watchdog!WdLogSingleEntry0` at `0x140252810`
- `watchdog!WdLogSingleEntry0` at `0x140252879`
- `watchdog!WdLogSingleEntry0` at `0x1402528ba`
- `watchdog!WdLogSingleEntry5` at `0x1402520ee`
- `watchdog!WdLogSingleEntry5` at `0x140252330`
- `watchdog!WdLogSingleEntry5` at `0x1402520ee`
- `watchdog!WdLogSingleEntry5` at `0x140252330`
- `watchdog!WdLogSingleEntry1` at `0x14025201b`
- `watchdog!WdLogSingleEntry1` at `0x14025224c`
- `watchdog!WdLogSingleEntry1` at `0x1402525c0`
- `watchdog!WdLogSingleEntry1` at `0x1402526da`
- `watchdog!WdLogSingleEntry1` at `0x1402527a1`
- `watchdog!WdLogSingleEntry1` at `0x14025201b`
- `watchdog!WdLogSingleEntry1` at `0x14025224c`
- `watchdog!WdLogSingleEntry1` at `0x1402525c0`
- `watchdog!WdLogSingleEntry1` at `0x1402526da`
- `watchdog!WdLogSingleEntry1` at `0x1402527a1`

## string_xrefs

- `0x1402526eb`: `Attempting to Blt on a HardwareContext:0x%I64x with no HwQueues`

## pseudocode

```c

```
