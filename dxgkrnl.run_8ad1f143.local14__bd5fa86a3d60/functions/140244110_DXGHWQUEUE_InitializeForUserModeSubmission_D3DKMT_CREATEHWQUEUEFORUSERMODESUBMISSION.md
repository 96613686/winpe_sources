# DXGHWQUEUE::InitializeForUserModeSubmission(_D3DKMT_CREATEHWQUEUEFORUSERMODESUBMISSION *)

- ea: `0x140244110`
- end: `0x140244d8b`
- name: `?InitializeForUserModeSubmission@DXGHWQUEUE@@IEAAJPEAU_D3DKMT_CREATEHWQUEUEFORUSERMODESUBMISSION@@@Z`
- size: `3195`
- prototype: `__int64 __fastcall(DXGHWQUEUE *__hidden this, struct _D3DKMT_CREATEHWQUEUEFORUSERMODESUBMISSION *)`
- caller_count: `1`
- callee_count: `32`
- tags: ``

## callers

- `0x1402439e0`

## callees

- `0x140012540`
- `0x1400146ac`
- `0x140015290`
- `0x140015448`
- `0x140015618`
- `0x140016388`
- `0x14001a874`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001bea0`
- `0x14001d1a0`
- `0x140030a30`
- `0x140033da4`
- `0x140047188`
- `0x140048a5c`
- `0x14004c924`
- `0x14004d90c`
- `0x14005248c`
- `0x14007193c`
- `0x1400719e0`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x14019d080`
- `0x1402025c0`
- `0x1402438d4`
- `0x140244110`
- `0x14032a5c4`
- `0x14032e980`
- `0x14032fd70`
- `0x140334c88`
- `0x14035327c`
- `0x1403b806c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402443ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402444c0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402446a3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402443ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402444c0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402446a3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1402443ae`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1402443ae`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1402444b4`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140244697`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1402444b4`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140244697`
- `watchdog!WdLogSingleEntry4` at `0x14024455e`
- `watchdog!WdLogSingleEntry4` at `0x140244739`
- `watchdog!WdLogSingleEntry4` at `0x14024455e`
- `watchdog!WdLogSingleEntry4` at `0x140244739`
- `watchdog!WdLogSingleEntry2` at `0x140244171`
- `watchdog!WdLogSingleEntry2` at `0x140244297`
- `watchdog!WdLogSingleEntry2` at `0x140244a21`
- `watchdog!WdLogSingleEntry2` at `0x140244aeb`
- `watchdog!WdLogSingleEntry2` at `0x140244bd6`
- `watchdog!WdLogSingleEntry2` at `0x140244cee`
- `watchdog!WdLogSingleEntry2` at `0x140244171`
- `watchdog!WdLogSingleEntry2` at `0x140244297`
- `watchdog!WdLogSingleEntry2` at `0x140244a21`
- `watchdog!WdLogSingleEntry2` at `0x140244aeb`
- `watchdog!WdLogSingleEntry2` at `0x140244bd6`
- `watchdog!WdLogSingleEntry2` at `0x140244cee`
- `watchdog!WdLogSingleEntry3` at `0x1402444eb`
- `watchdog!WdLogSingleEntry3` at `0x1402446cd`
- `watchdog!WdLogSingleEntry3` at `0x1402444eb`
- `watchdog!WdLogSingleEntry3` at `0x1402446cd`
- `watchdog!WdLogSingleEntry0` at `0x14024434e`
- `watchdog!WdLogSingleEntry0` at `0x140244441`
- `watchdog!WdLogSingleEntry0` at `0x140244625`
- `watchdog!WdLogSingleEntry0` at `0x140244980`
- `watchdog!WdLogSingleEntry0` at `0x14024434e`
- `watchdog!WdLogSingleEntry0` at `0x140244441`
- `watchdog!WdLogSingleEntry0` at `0x140244625`
- `watchdog!WdLogSingleEntry0` at `0x140244980`
- `watchdog!WdLogSingleEntry1` at `0x140244927`
- `watchdog!WdLogSingleEntry1` at `0x140244c5d`
- `watchdog!WdLogSingleEntry1` at `0x140244927`
- `watchdog!WdLogSingleEntry1` at `0x140244c5d`

## string_xrefs

- `0x14024498e`: `The HW queue must not specify NoKmdAccess flag`
- `0x140244938`: `DdiCreateHwQueueForUserModeSubmission() failed with status 0x%I64d`
- `0x140244c78`: `DXGHWQUEUE 0x%I64x: Failed to open ProgressFenceLastQueuedValue fence storage`

## pseudocode

```c

```
