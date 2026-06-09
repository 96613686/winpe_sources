# DXGCONTEXT::Blt(uint,uint,uint,DXGCONTEXT * *,tagRECT *,uint,tagRECT const *,COREDEVICEACCESS *,DXGHWQUEUE * *)

- ea: `0x1403930a8`
- end: `0x140393c14`
- name: `?Blt@DXGCONTEXT@@QEAAJIIIPEAPEAV1@PEAUtagRECT@@IPEBU2@PEAVCOREDEVICEACCESS@@PEAPEAVDXGHWQUEUE@@@Z`
- size: `2924`
- prototype: `__int64 __usercall@<rax>(DXGCONTEXT *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, struct DXGCONTEXT **, struct tagRECT *, unsigned int, const struct tagRECT *, struct COREDEVICEACCESS *, struct DXGHWQUEUE **)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation`

## callers

- `0x1402231d8`
- `0x140392ad0`

## callees

- `0x14001b9c0`
- `0x14001d1a0`
- `0x14002dbc0`
- `0x14002dc10`
- `0x14003cd10`
- `0x140049424`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x140292838`
- `0x14031a9cc`
- `0x14031e5d8`
- `0x14032a5c4`
- `0x14032e980`
- `0x14032fd70`
- `0x1403930a8`
- `0x140393f58`
- `0x1403942d8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140393250`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140393482`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140393250`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140393482`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140393244`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140393476`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140393244`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140393476`
- `watchdog!WdLogSingleEntry4` at `0x1403936b6`
- `watchdog!WdLogSingleEntry4` at `0x14039370f`
- `watchdog!WdLogSingleEntry4` at `0x1403936b6`
- `watchdog!WdLogSingleEntry4` at `0x14039370f`
- `watchdog!WdLogSingleEntry3` at `0x140393b28`
- `watchdog!WdLogSingleEntry3` at `0x140393b95`
- `watchdog!WdLogSingleEntry3` at `0x140393b28`
- `watchdog!WdLogSingleEntry3` at `0x140393b95`
- `watchdog!WdLogSingleEntry0` at `0x140393135`
- `watchdog!WdLogSingleEntry0` at `0x1403931e7`
- `watchdog!WdLogSingleEntry0` at `0x140393419`
- `watchdog!WdLogSingleEntry0` at `0x140393ab2`
- `watchdog!WdLogSingleEntry0` at `0x140393135`
- `watchdog!WdLogSingleEntry0` at `0x1403931e7`
- `watchdog!WdLogSingleEntry0` at `0x140393419`
- `watchdog!WdLogSingleEntry0` at `0x140393ab2`
- `watchdog!WdLogSingleEntry5` at `0x14039334b`
- `watchdog!WdLogSingleEntry5` at `0x14039358e`
- `watchdog!WdLogSingleEntry5` at `0x14039334b`
- `watchdog!WdLogSingleEntry5` at `0x14039358e`
- `watchdog!WdLogSingleEntry1` at `0x14039326d`
- `watchdog!WdLogSingleEntry1` at `0x14039349f`
- `watchdog!WdLogSingleEntry1` at `0x1403938ee`
- `watchdog!WdLogSingleEntry1` at `0x140393a43`
- `watchdog!WdLogSingleEntry1` at `0x14039326d`
- `watchdog!WdLogSingleEntry1` at `0x14039349f`
- `watchdog!WdLogSingleEntry1` at `0x1403938ee`
- `watchdog!WdLogSingleEntry1` at `0x140393a43`

## string_xrefs

- `0x1403936cb`: `The (right bottom) of blit sub rect (0x%I64x,0x%I64x) is outside of dst rectangle (0x%I64x,0x%I64x)`
- `0x140393720`: `The (left, top) of blit sub rect (0x%I64x,0x%I64x) is outside of dst rectangle (0x%I64x,0x%I64x)`

## pseudocode

```c

```
