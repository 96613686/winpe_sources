# DXGDXGIKEYEDMUTEX::OpenSharedSurfForDevice(DXGDEVICE *)

- ea: `0x14024d9cc`
- end: `0x14024e266`
- name: `?OpenSharedSurfForDevice@DXGDXGIKEYEDMUTEX@@AEAAJPEAVDXGDEVICE@@@Z`
- size: `2202`
- prototype: `int(DXGDXGIKEYEDMUTEX *__hidden this, struct DXGDEVICE *)`
- caller_count: `1`
- callee_count: `26`
- tags: ``

## callers

- `0x14038ae34`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x1400146ac`
- `0x140015290`
- `0x140016388`
- `0x14001b9c0`
- `0x14001d1a0`
- `0x14002dbc0`
- `0x14003bfbc`
- `0x14003bff4`
- `0x14003c448`
- `0x14004d064`
- `0x1400532c8`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x14024d9cc`
- `0x1402970b0`
- `0x140299968`
- `0x140320f8c`
- `0x14032a5c4`
- `0x14032e980`
- `0x14032fd70`
- `0x14035f174`
- `0x14036fa30`
- `0x14036fdd0`
- `0x1403c9c38`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14024de3d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14024de3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024dcc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024e22d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024dcc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024e22d`
- `ntoskrnl!ExAllocatePool2` at `0x14024dc00`
- `ntoskrnl!ExAllocatePool2` at `0x14024dc00`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14024de31`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14024de31`
- `watchdog!WdLogSingleEntry2` at `0x14024db5e`
- `watchdog!WdLogSingleEntry2` at `0x14024e18f`
- `watchdog!WdLogSingleEntry2` at `0x14024e1f4`
- `watchdog!WdLogSingleEntry2` at `0x14024db5e`
- `watchdog!WdLogSingleEntry2` at `0x14024e18f`
- `watchdog!WdLogSingleEntry2` at `0x14024e1f4`
- `watchdog!WdLogSingleEntry0` at `0x14024da1a`
- `watchdog!WdLogSingleEntry0` at `0x14024dabe`
- `watchdog!WdLogSingleEntry0` at `0x14024db20`
- `watchdog!WdLogSingleEntry0` at `0x14024dc5d`
- `watchdog!WdLogSingleEntry0` at `0x14024ddd3`
- `watchdog!WdLogSingleEntry0` at `0x14024da1a`
- `watchdog!WdLogSingleEntry0` at `0x14024dabe`
- `watchdog!WdLogSingleEntry0` at `0x14024db20`
- `watchdog!WdLogSingleEntry0` at `0x14024dc5d`
- `watchdog!WdLogSingleEntry0` at `0x14024ddd3`
- `watchdog!WdLogSingleEntry1` at `0x14024da8e`
- `watchdog!WdLogSingleEntry1` at `0x14024dfe4`
- `watchdog!WdLogSingleEntry1` at `0x14024e0d3`
- `watchdog!WdLogSingleEntry1` at `0x14024da8e`
- `watchdog!WdLogSingleEntry1` at `0x14024dfe4`
- `watchdog!WdLogSingleEntry1` at `0x14024e0d3`

## string_xrefs

- `0x14024dc6b`: `Failed to allocate memory for D3DDDI_OPENALLOCATIONINFO2`

## pseudocode

```c

```
