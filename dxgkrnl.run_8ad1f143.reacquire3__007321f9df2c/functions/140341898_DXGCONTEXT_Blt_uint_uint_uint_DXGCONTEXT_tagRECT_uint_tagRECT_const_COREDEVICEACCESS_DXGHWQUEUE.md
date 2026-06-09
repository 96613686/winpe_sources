# DXGCONTEXT::Blt(uint,uint,uint,DXGCONTEXT * *,tagRECT *,uint,tagRECT const *,COREDEVICEACCESS *,DXGHWQUEUE * *)

- ea: `0x140341898`
- end: `0x140342404`
- name: `?Blt@DXGCONTEXT@@QEAAJIIIPEAPEAV1@PEAUtagRECT@@IPEBU2@PEAVCOREDEVICEACCESS@@PEAPEAVDXGHWQUEUE@@@Z`
- size: `2924`
- prototype: `__int64 __usercall@<rax>(DXGCONTEXT *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, struct DXGCONTEXT **, struct tagRECT *, unsigned int, const struct tagRECT *, struct COREDEVICEACCESS *, struct DXGHWQUEUE **)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation`

## callers

- `0x140220b84`
- `0x1403e2f94`

## callees

- `0x14001b890`
- `0x14001d070`
- `0x14002d9f0`
- `0x14002da40`
- `0x14003cab0`
- `0x140049224`
- `0x1400a0100`
- `0x1400a0540`
- `0x14028bed8`
- `0x140313c5c`
- `0x140317868`
- `0x140323854`
- `0x140327c10`
- `0x140329000`
- `0x140340858`
- `0x140341898`
- `0x1403427f4`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140341a40`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140341c72`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140341a40`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140341c72`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140341a34`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140341c66`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140341a34`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140341c66`
- `watchdog!WdLogSingleEntry4` at `0x140341ea6`
- `watchdog!WdLogSingleEntry4` at `0x140341eff`
- `watchdog!WdLogSingleEntry4` at `0x140341ea6`
- `watchdog!WdLogSingleEntry4` at `0x140341eff`
- `watchdog!WdLogSingleEntry3` at `0x140342318`
- `watchdog!WdLogSingleEntry3` at `0x140342385`
- `watchdog!WdLogSingleEntry3` at `0x140342318`
- `watchdog!WdLogSingleEntry3` at `0x140342385`
- `watchdog!WdLogSingleEntry0` at `0x140341925`
- `watchdog!WdLogSingleEntry0` at `0x1403419d7`
- `watchdog!WdLogSingleEntry0` at `0x140341c09`
- `watchdog!WdLogSingleEntry0` at `0x1403422a2`
- `watchdog!WdLogSingleEntry0` at `0x140341925`
- `watchdog!WdLogSingleEntry0` at `0x1403419d7`
- `watchdog!WdLogSingleEntry0` at `0x140341c09`
- `watchdog!WdLogSingleEntry0` at `0x1403422a2`
- `watchdog!WdLogSingleEntry5` at `0x140341b3b`
- `watchdog!WdLogSingleEntry5` at `0x140341d7e`
- `watchdog!WdLogSingleEntry5` at `0x140341b3b`
- `watchdog!WdLogSingleEntry5` at `0x140341d7e`
- `watchdog!WdLogSingleEntry1` at `0x140341a5d`
- `watchdog!WdLogSingleEntry1` at `0x140341c8f`
- `watchdog!WdLogSingleEntry1` at `0x1403420de`
- `watchdog!WdLogSingleEntry1` at `0x140342233`
- `watchdog!WdLogSingleEntry1` at `0x140341a5d`
- `watchdog!WdLogSingleEntry1` at `0x140341c8f`
- `watchdog!WdLogSingleEntry1` at `0x1403420de`
- `watchdog!WdLogSingleEntry1` at `0x140342233`

## string_xrefs

- `0x140341ebb`: `The (right bottom) of blit sub rect (0x%I64x,0x%I64x) is outside of dst rectangle (0x%I64x,0x%I64x)`
- `0x140341f10`: `The (left, top) of blit sub rect (0x%I64x,0x%I64x) is outside of dst rectangle (0x%I64x,0x%I64x)`

## pseudocode

```c

```
