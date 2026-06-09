# DxgkCreateLightweightDeviceAndContext

- ea: `0x1401a9f7c`
- end: `0x1401aa7dc`
- name: `DxgkCreateLightweightDeviceAndContext`
- size: `2144`
- prototype: `__int64 __fastcall(struct _LUID *)`
- caller_count: `1`
- callee_count: `20`
- tags: ``

## callers

- `0x1403157a0`

## callees

- `0x140015940`
- `0x140015ad0`
- `0x140015f30`
- `0x14001683c`
- `0x14001b9c0`
- `0x14001f630`
- `0x14002ddf0`
- `0x14002ee60`
- `0x140045c44`
- `0x14004acd8`
- `0x14004c888`
- `0x1400552b4`
- `0x1400a0bd0`
- `0x1401a9f7c`
- `0x14032a5c4`
- `0x14032aaa8`
- `0x140353aa0`
- `0x14035a180`
- `0x14035fa08`
- `0x1403ac284`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401aa085`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401aa15e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401aa085`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401aa15e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401aa074`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401aa14d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401aa074`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401aa14d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa218`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa245`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa2df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa30f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa622`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa65a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa70d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa218`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa245`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa2df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa30f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa622`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa65a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa70d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401aa20c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401aa239`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401aa2d3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401aa303`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401aa616`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401aa64e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401aa701`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401aa20c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401aa239`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401aa2d3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401aa303`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401aa616`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401aa64e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401aa701`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401aa3d7`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401aa409`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401aa3d7`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401aa409`
- `watchdog!WdLogSingleEntry2` at `0x1401aa5a1`
- `watchdog!WdLogSingleEntry2` at `0x1401aa730`
- `watchdog!WdLogSingleEntry2` at `0x1401aa5a1`
- `watchdog!WdLogSingleEntry2` at `0x1401aa730`
- `watchdog!WdLogSingleEntry3` at `0x1401aa298`
- `watchdog!WdLogSingleEntry3` at `0x1401aa3f3`
- `watchdog!WdLogSingleEntry3` at `0x1401aa5db`
- `watchdog!WdLogSingleEntry3` at `0x1401aa69f`
- `watchdog!WdLogSingleEntry3` at `0x1401aa78b`
- `watchdog!WdLogSingleEntry3` at `0x1401aa298`
- `watchdog!WdLogSingleEntry3` at `0x1401aa3f3`
- `watchdog!WdLogSingleEntry3` at `0x1401aa5db`
- `watchdog!WdLogSingleEntry3` at `0x1401aa69f`
- `watchdog!WdLogSingleEntry3` at `0x1401aa78b`
- `watchdog!WdLogSingleEntry0` at `0x1401aa0e7`
- `watchdog!WdLogSingleEntry0` at `0x1401aa4ec`
- `watchdog!WdLogSingleEntry0` at `0x1401aa0e7`
- `watchdog!WdLogSingleEntry0` at `0x1401aa4ec`
- `watchdog!WdLogSingleEntry1` at `0x1401a9fe5`
- `watchdog!WdLogSingleEntry1` at `0x1401aa1da`
- `watchdog!WdLogSingleEntry1` at `0x1401a9fe5`
- `watchdog!WdLogSingleEntry1` at `0x1401aa1da`

## string_xrefs

- `0x1401aa41e`: `Failed to create CDD DXGDEVICE for adapter 0x%I64x in process 0x%I64x (Status = 0x%I64x).`

## pseudocode

```c

```
