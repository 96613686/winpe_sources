# DxgkCreateLightweightDeviceAndContext

- ea: `0x1401a5cbc`
- end: `0x1401a651c`
- name: `DxgkCreateLightweightDeviceAndContext`
- size: `2144`
- prototype: `__int64 __fastcall(struct _LUID *)`
- caller_count: `1`
- callee_count: `20`
- tags: ``

## callers

- `0x14030ea30`

## callees

- `0x140015780`
- `0x140015910`
- `0x140015d70`
- `0x14001667c`
- `0x14001b890`
- `0x14001f460`
- `0x14002dc20`
- `0x14002ec90`
- `0x1400459e4`
- `0x14004aad8`
- `0x14004c688`
- `0x140055044`
- `0x1400a0100`
- `0x1401a5cbc`
- `0x140323854`
- `0x140323d38`
- `0x1403535f0`
- `0x140359cd0`
- `0x14035f558`
- `0x1403ab4a4`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401a5dc5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401a5e9e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401a5dc5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401a5e9e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a5db4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a5e8d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a5db4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a5e8d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a5f58`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a5f85`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a601f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a604f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a6362`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a639a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a644d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a5f58`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a5f85`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a601f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a604f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a6362`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a639a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a644d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a5f4c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a5f79`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a6013`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a6043`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a6356`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a638e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a6441`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a5f4c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a5f79`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a6013`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a6043`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a6356`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a638e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a6441`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401a6117`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401a6149`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401a6117`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401a6149`
- `watchdog!WdLogSingleEntry2` at `0x1401a62e1`
- `watchdog!WdLogSingleEntry2` at `0x1401a6470`
- `watchdog!WdLogSingleEntry2` at `0x1401a62e1`
- `watchdog!WdLogSingleEntry2` at `0x1401a6470`
- `watchdog!WdLogSingleEntry3` at `0x1401a5fd8`
- `watchdog!WdLogSingleEntry3` at `0x1401a6133`
- `watchdog!WdLogSingleEntry3` at `0x1401a631b`
- `watchdog!WdLogSingleEntry3` at `0x1401a63df`
- `watchdog!WdLogSingleEntry3` at `0x1401a64cb`
- `watchdog!WdLogSingleEntry3` at `0x1401a5fd8`
- `watchdog!WdLogSingleEntry3` at `0x1401a6133`
- `watchdog!WdLogSingleEntry3` at `0x1401a631b`
- `watchdog!WdLogSingleEntry3` at `0x1401a63df`
- `watchdog!WdLogSingleEntry3` at `0x1401a64cb`
- `watchdog!WdLogSingleEntry0` at `0x1401a5e27`
- `watchdog!WdLogSingleEntry0` at `0x1401a622c`
- `watchdog!WdLogSingleEntry0` at `0x1401a5e27`
- `watchdog!WdLogSingleEntry0` at `0x1401a622c`
- `watchdog!WdLogSingleEntry1` at `0x1401a5d25`
- `watchdog!WdLogSingleEntry1` at `0x1401a5f1a`
- `watchdog!WdLogSingleEntry1` at `0x1401a5d25`
- `watchdog!WdLogSingleEntry1` at `0x1401a5f1a`

## string_xrefs

- `0x1401a615e`: `Failed to create CDD DXGDEVICE for adapter 0x%I64x in process 0x%I64x (Status = 0x%I64x).`

## pseudocode

```c

```
