# DXGCONTEXT::BltFromVm(uint,uint,uint,DXGCONTEXT * *,DXGHWQUEUE *,tagRECT,tagRECT,uint,tagRECT const *,COREDEVICEACCESS *)

- ea: `0x14024e8c8`
- end: `0x14024f446`
- name: `?BltFromVm@DXGCONTEXT@@QEAAJIIIPEAPEAV1@PEAVDXGHWQUEUE@@UtagRECT@@2IPEBU3@PEAVCOREDEVICEACCESS@@@Z`
- size: `2942`
- prototype: `__int64 __usercall@<rax>(DXGCONTEXT *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, struct DXGCONTEXT **, struct DXGHWQUEUE *, struct tagRECT *, struct tagRECT *, unsigned int, const struct tagRECT *, struct COREDEVICEACCESS *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x140282210`

## callees

- `0x14001b890`
- `0x14001d070`
- `0x14002da40`
- `0x14003cab0`
- `0x140049224`
- `0x1400a0100`
- `0x1400a0540`
- `0x14024e8c8`
- `0x140313c5c`
- `0x140317868`
- `0x140327c10`
- `0x140329000`
- `0x140340858`
- `0x1403427f4`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14024ea19`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14024ec4f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14024ea19`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14024ec4f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14024ea0d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14024ec43`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14024ea0d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14024ec43`
- `watchdog!WdLogSingleEntry3` at `0x14024f353`
- `watchdog!WdLogSingleEntry3` at `0x14024f3c0`
- `watchdog!WdLogSingleEntry3` at `0x14024f353`
- `watchdog!WdLogSingleEntry3` at `0x14024f3c0`
- `watchdog!WdLogSingleEntry0` at `0x14024e9a5`
- `watchdog!WdLogSingleEntry0` at `0x14024ebd8`
- `watchdog!WdLogSingleEntry0` at `0x14024ef44`
- `watchdog!WdLogSingleEntry0` at `0x14024f230`
- `watchdog!WdLogSingleEntry0` at `0x14024f299`
- `watchdog!WdLogSingleEntry0` at `0x14024f2da`
- `watchdog!WdLogSingleEntry0` at `0x14024e9a5`
- `watchdog!WdLogSingleEntry0` at `0x14024ebd8`
- `watchdog!WdLogSingleEntry0` at `0x14024ef44`
- `watchdog!WdLogSingleEntry0` at `0x14024f230`
- `watchdog!WdLogSingleEntry0` at `0x14024f299`
- `watchdog!WdLogSingleEntry0` at `0x14024f2da`
- `watchdog!WdLogSingleEntry5` at `0x14024eb0e`
- `watchdog!WdLogSingleEntry5` at `0x14024ed50`
- `watchdog!WdLogSingleEntry5` at `0x14024eb0e`
- `watchdog!WdLogSingleEntry5` at `0x14024ed50`
- `watchdog!WdLogSingleEntry1` at `0x14024ea3b`
- `watchdog!WdLogSingleEntry1` at `0x14024ec6c`
- `watchdog!WdLogSingleEntry1` at `0x14024efe0`
- `watchdog!WdLogSingleEntry1` at `0x14024f0fa`
- `watchdog!WdLogSingleEntry1` at `0x14024f1c1`
- `watchdog!WdLogSingleEntry1` at `0x14024ea3b`
- `watchdog!WdLogSingleEntry1` at `0x14024ec6c`
- `watchdog!WdLogSingleEntry1` at `0x14024efe0`
- `watchdog!WdLogSingleEntry1` at `0x14024f0fa`
- `watchdog!WdLogSingleEntry1` at `0x14024f1c1`

## string_xrefs

- `0x14024f10b`: `Attempting to Blt on a HardwareContext:0x%I64x with no HwQueues`

## pseudocode

```c

```
