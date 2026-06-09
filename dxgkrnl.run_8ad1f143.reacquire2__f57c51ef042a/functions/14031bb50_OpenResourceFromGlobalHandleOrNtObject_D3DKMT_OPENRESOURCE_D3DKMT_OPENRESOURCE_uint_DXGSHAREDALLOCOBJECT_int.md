# OpenResourceFromGlobalHandleOrNtObject<_D3DKMT_OPENRESOURCE>(_D3DKMT_OPENRESOURCE *,uint,_DXGSHAREDALLOCOBJECT *,int)

- ea: `0x14031bb50`
- end: `0x14031cc7d`
- name: `??$OpenResourceFromGlobalHandleOrNtObject@U_D3DKMT_OPENRESOURCE@@@@YAJPEAU_D3DKMT_OPENRESOURCE@@IPEAU_DXGSHAREDALLOCOBJECT@@H@Z`
- size: `4397`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `41`
- tags: ``

## callers

- `0x14020e720`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140012380`
- `0x1400144ec`
- `0x1400150d0`
- `0x1400158b0`
- `0x140015970`
- `0x1400160e4`
- `0x140016830`
- `0x140017fb8`
- `0x14001a7d4`
- `0x14001ab20`
- `0x14001b890`
- `0x14001c660`
- `0x14001cec0`
- `0x14001d070`
- `0x14001e15c`
- `0x14001f120`
- `0x14002ed70`
- `0x140030820`
- `0x140034740`
- `0x14003bab8`
- `0x14003fb68`
- `0x140042498`
- `0x1400425f4`
- `0x14004d73c`
- `0x140055d4c`
- `0x1400670a4`
- `0x1400a0100`
- `0x1400a0240`
- `0x1400a0540`
- `0x1401e5360`
- `0x1401e54cc`
- `0x14031acbc`
- `0x14031bb50`
- `0x14031de8c`
- `0x140323854`
- `0x140323d38`
- `0x14036f9f0`
- `0x1403c36ac`
- `0x1403d9f70`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14031bf58`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14031bf58`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14031bf4c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14031bf4c`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14031bb8e`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14031bb8e`
- `watchdog!WdLogSingleEntry4` at `0x14031c393`
- `watchdog!WdLogSingleEntry4` at `0x14031c3d9`
- `watchdog!WdLogSingleEntry4` at `0x14031c393`
- `watchdog!WdLogSingleEntry4` at `0x14031c3d9`
- `watchdog!WdLogSingleEntry2` at `0x14031bced`
- `watchdog!WdLogSingleEntry2` at `0x14031bd58`
- `watchdog!WdLogSingleEntry2` at `0x14031bde3`
- `watchdog!WdLogSingleEntry2` at `0x14031bffb`
- `watchdog!WdLogSingleEntry2` at `0x14031c10c`
- `watchdog!WdLogSingleEntry2` at `0x14031c41d`
- `watchdog!WdLogSingleEntry2` at `0x14031cb4e`
- `watchdog!WdLogSingleEntry2` at `0x14031cbd1`
- `watchdog!WdLogSingleEntry2` at `0x14031bced`
- `watchdog!WdLogSingleEntry2` at `0x14031bd58`
- `watchdog!WdLogSingleEntry2` at `0x14031bde3`
- `watchdog!WdLogSingleEntry2` at `0x14031bffb`
- `watchdog!WdLogSingleEntry2` at `0x14031c10c`
- `watchdog!WdLogSingleEntry2` at `0x14031c41d`
- `watchdog!WdLogSingleEntry2` at `0x14031cb4e`
- `watchdog!WdLogSingleEntry2` at `0x14031cbd1`
- `watchdog!WdLogSingleEntry3` at `0x14031bf88`
- `watchdog!WdLogSingleEntry3` at `0x14031c1c6`
- `watchdog!WdLogSingleEntry3` at `0x14031c238`
- `watchdog!WdLogSingleEntry3` at `0x14031c292`
- `watchdog!WdLogSingleEntry3` at `0x14031c2ea`
- `watchdog!WdLogSingleEntry3` at `0x14031c69a`
- `watchdog!WdLogSingleEntry3` at `0x14031cb9a`
- `watchdog!WdLogSingleEntry3` at `0x14031bf88`
- `watchdog!WdLogSingleEntry3` at `0x14031c1c6`
- `watchdog!WdLogSingleEntry3` at `0x14031c238`
- `watchdog!WdLogSingleEntry3` at `0x14031c292`
- `watchdog!WdLogSingleEntry3` at `0x14031c2ea`
- `watchdog!WdLogSingleEntry3` at `0x14031c69a`
- `watchdog!WdLogSingleEntry3` at `0x14031cb9a`
- `watchdog!WdLogSingleEntry0` at `0x14031bedd`
- `watchdog!WdLogSingleEntry0` at `0x14031c94a`
- `watchdog!WdLogSingleEntry0` at `0x14031ca08`
- `watchdog!WdLogSingleEntry0` at `0x14031bedd`
- `watchdog!WdLogSingleEntry0` at `0x14031c94a`
- `watchdog!WdLogSingleEntry0` at `0x14031ca08`
- `watchdog!WdLogSingleEntry1` at `0x14031bbc5`
- `watchdog!WdLogSingleEntry1` at `0x14031bc5f`
- `watchdog!WdLogSingleEntry1` at `0x14031c7a4`
- `watchdog!WdLogSingleEntry1` at `0x14031c808`
- `watchdog!WdLogSingleEntry1` at `0x14031c869`
- `watchdog!WdLogSingleEntry1` at `0x14031c8d1`
- `watchdog!WdLogSingleEntry1` at `0x14031c911`
- `watchdog!WdLogSingleEntry1` at `0x14031bbc5`
- `watchdog!WdLogSingleEntry1` at `0x14031bc5f`
- `watchdog!WdLogSingleEntry1` at `0x14031c7a4`
- `watchdog!WdLogSingleEntry1` at `0x14031c808`
- `watchdog!WdLogSingleEntry1` at `0x14031c869`
- `watchdog!WdLogSingleEntry1` at `0x14031c8d1`
- `watchdog!WdLogSingleEntry1` at `0x14031c911`

## pseudocode

```c

```
