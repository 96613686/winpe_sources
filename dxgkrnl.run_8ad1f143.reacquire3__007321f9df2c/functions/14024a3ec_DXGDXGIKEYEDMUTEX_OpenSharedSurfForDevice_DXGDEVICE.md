# DXGDXGIKEYEDMUTEX::OpenSharedSurfForDevice(DXGDEVICE *)

- ea: `0x14024a3ec`
- end: `0x14024ac86`
- name: `?OpenSharedSurfForDevice@DXGDXGIKEYEDMUTEX@@AEAAJPEAVDXGDEVICE@@@Z`
- size: `2202`
- prototype: `int(DXGDXGIKEYEDMUTEX *__hidden this, struct DXGDEVICE *)`
- caller_count: `1`
- callee_count: `26`
- tags: ``

## callers

- `0x140348634`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x1400144ec`
- `0x1400150d0`
- `0x1400161c8`
- `0x14001b890`
- `0x14001d070`
- `0x14002d9f0`
- `0x14003bd5c`
- `0x14003bd94`
- `0x14003c1e8`
- `0x14004ce64`
- `0x1400530e8`
- `0x1400a0100`
- `0x1400a0540`
- `0x14024a3ec`
- `0x140290750`
- `0x140293008`
- `0x14031a21c`
- `0x140323854`
- `0x140327c10`
- `0x140329000`
- `0x14035ecc4`
- `0x14036f9f0`
- `0x14036fd90`
- `0x1403ca888`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14024a85d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14024a85d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024a6e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024ac4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024a6e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024ac4d`
- `ntoskrnl!ExAllocatePool2` at `0x14024a620`
- `ntoskrnl!ExAllocatePool2` at `0x14024a620`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14024a851`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14024a851`
- `watchdog!WdLogSingleEntry2` at `0x14024a57e`
- `watchdog!WdLogSingleEntry2` at `0x14024abaf`
- `watchdog!WdLogSingleEntry2` at `0x14024ac14`
- `watchdog!WdLogSingleEntry2` at `0x14024a57e`
- `watchdog!WdLogSingleEntry2` at `0x14024abaf`
- `watchdog!WdLogSingleEntry2` at `0x14024ac14`
- `watchdog!WdLogSingleEntry0` at `0x14024a43a`
- `watchdog!WdLogSingleEntry0` at `0x14024a4de`
- `watchdog!WdLogSingleEntry0` at `0x14024a540`
- `watchdog!WdLogSingleEntry0` at `0x14024a67d`
- `watchdog!WdLogSingleEntry0` at `0x14024a7f3`
- `watchdog!WdLogSingleEntry0` at `0x14024a43a`
- `watchdog!WdLogSingleEntry0` at `0x14024a4de`
- `watchdog!WdLogSingleEntry0` at `0x14024a540`
- `watchdog!WdLogSingleEntry0` at `0x14024a67d`
- `watchdog!WdLogSingleEntry0` at `0x14024a7f3`
- `watchdog!WdLogSingleEntry1` at `0x14024a4ae`
- `watchdog!WdLogSingleEntry1` at `0x14024aa04`
- `watchdog!WdLogSingleEntry1` at `0x14024aaf3`
- `watchdog!WdLogSingleEntry1` at `0x14024a4ae`
- `watchdog!WdLogSingleEntry1` at `0x14024aa04`
- `watchdog!WdLogSingleEntry1` at `0x14024aaf3`

## string_xrefs

- `0x14024a68b`: `Failed to allocate memory for D3DDDI_OPENALLOCATIONINFO2`

## pseudocode

```c

```
