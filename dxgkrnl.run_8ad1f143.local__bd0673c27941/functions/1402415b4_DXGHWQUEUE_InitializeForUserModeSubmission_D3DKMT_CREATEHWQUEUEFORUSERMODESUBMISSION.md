# DXGHWQUEUE::InitializeForUserModeSubmission(_D3DKMT_CREATEHWQUEUEFORUSERMODESUBMISSION *)

- ea: `0x1402415b4`
- end: `0x1402421b5`
- name: `?InitializeForUserModeSubmission@DXGHWQUEUE@@IEAAJPEAU_D3DKMT_CREATEHWQUEUEFORUSERMODESUBMISSION@@@Z`
- size: `3073`
- prototype: `__int64 __fastcall(DXGHWQUEUE *__hidden this, struct _D3DKMT_CREATEHWQUEUEFORUSERMODESUBMISSION *)`
- caller_count: `1`
- callee_count: `32`
- tags: ``

## callers

- `0x140240e80`

## callees

- `0x140012380`
- `0x1400144ec`
- `0x1400150d0`
- `0x140015288`
- `0x140015458`
- `0x1400161c8`
- `0x14001a7d4`
- `0x14001ab20`
- `0x14001b890`
- `0x14001bd70`
- `0x14001d070`
- `0x140030860`
- `0x140033bd4`
- `0x140046f28`
- `0x140047564`
- `0x14004885c`
- `0x14004c724`
- `0x14004d70c`
- `0x1400522ac`
- `0x1400713a0`
- `0x1400a0100`
- `0x1400a0540`
- `0x140199080`
- `0x1402001e0`
- `0x140240d74`
- `0x1402415b4`
- `0x140323854`
- `0x140327c10`
- `0x140329000`
- `0x14032df18`
- `0x140352dcc`
- `0x1403af310`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140241858`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14024195e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140241b41`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140241858`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14024195e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140241b41`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14024184c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14024184c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140241952`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140241b35`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140241952`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140241b35`
- `watchdog!WdLogSingleEntry4` at `0x1402419fc`
- `watchdog!WdLogSingleEntry4` at `0x140241bd7`
- `watchdog!WdLogSingleEntry4` at `0x1402419fc`
- `watchdog!WdLogSingleEntry4` at `0x140241bd7`
- `watchdog!WdLogSingleEntry2` at `0x14024160f`
- `watchdog!WdLogSingleEntry2` at `0x140241735`
- `watchdog!WdLogSingleEntry2` at `0x140241e53`
- `watchdog!WdLogSingleEntry2` at `0x140241f1d`
- `watchdog!WdLogSingleEntry2` at `0x140242003`
- `watchdog!WdLogSingleEntry2` at `0x14024211b`
- `watchdog!WdLogSingleEntry2` at `0x14024160f`
- `watchdog!WdLogSingleEntry2` at `0x140241735`
- `watchdog!WdLogSingleEntry2` at `0x140241e53`
- `watchdog!WdLogSingleEntry2` at `0x140241f1d`
- `watchdog!WdLogSingleEntry2` at `0x140242003`
- `watchdog!WdLogSingleEntry2` at `0x14024211b`
- `watchdog!WdLogSingleEntry3` at `0x140241989`
- `watchdog!WdLogSingleEntry3` at `0x140241b6b`
- `watchdog!WdLogSingleEntry3` at `0x140241989`
- `watchdog!WdLogSingleEntry3` at `0x140241b6b`
- `watchdog!WdLogSingleEntry0` at `0x1402417ec`
- `watchdog!WdLogSingleEntry0` at `0x1402418df`
- `watchdog!WdLogSingleEntry0` at `0x140241ac3`
- `watchdog!WdLogSingleEntry0` at `0x140241db2`
- `watchdog!WdLogSingleEntry0` at `0x1402417ec`
- `watchdog!WdLogSingleEntry0` at `0x1402418df`
- `watchdog!WdLogSingleEntry0` at `0x140241ac3`
- `watchdog!WdLogSingleEntry0` at `0x140241db2`
- `watchdog!WdLogSingleEntry1` at `0x140241d59`
- `watchdog!WdLogSingleEntry1` at `0x14024208a`
- `watchdog!WdLogSingleEntry1` at `0x140241d59`
- `watchdog!WdLogSingleEntry1` at `0x14024208a`

## string_xrefs

- `0x140241dc0`: `The HW queue must not specify NoKmdAccess flag`
- `0x140241d6a`: `DdiCreateHwQueueForUserModeSubmission() failed with status 0x%I64d`
- `0x1402420a5`: `DXGHWQUEUE 0x%I64x: Failed to open ProgressFenceLastQueuedValue fence storage`

## pseudocode

```c

```
