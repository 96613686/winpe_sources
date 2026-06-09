# DpiRequestDevicePowerState

- ea: `0x1400224b0`
- end: `0x1400228ee`
- name: `DpiRequestDevicePowerState`
- size: `1086`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: ``

## callers

- `0x140022264`
- `0x140022370`
- `0x1400223ec`
- `0x140057770`
- `0x140321790`

## callees

- `0x14001b890`
- `0x14001becc`
- `0x1400224b0`
- `0x140022998`
- `0x140022a70`
- `0x140022cc0`
- `0x14004ab24`
- `0x140052dbc`
- `0x14007f3c8`
- `0x14007f4f4`
- `0x14037b2b0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400228a6`
- `ntoskrnl!KeSetEvent` at `0x1400228a6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400228d5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400228d5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140022552`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002277c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140022552`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002277c`
- `watchdog!WdLogSingleEntry3` at `0x1400224d8`
- `watchdog!WdLogSingleEntry3` at `0x140022572`
- `watchdog!WdLogSingleEntry3` at `0x14002266f`
- `watchdog!WdLogSingleEntry3` at `0x1400226a3`
- `watchdog!WdLogSingleEntry3` at `0x1400226d9`
- `watchdog!WdLogSingleEntry3` at `0x14002273a`
- `watchdog!WdLogSingleEntry3` at `0x14002279c`
- `watchdog!WdLogSingleEntry3` at `0x1400227f9`
- `watchdog!WdLogSingleEntry3` at `0x140022840`
- `watchdog!WdLogSingleEntry3` at `0x1400224d8`
- `watchdog!WdLogSingleEntry3` at `0x140022572`
- `watchdog!WdLogSingleEntry3` at `0x14002266f`
- `watchdog!WdLogSingleEntry3` at `0x1400226a3`
- `watchdog!WdLogSingleEntry3` at `0x1400226d9`
- `watchdog!WdLogSingleEntry3` at `0x14002273a`
- `watchdog!WdLogSingleEntry3` at `0x14002279c`
- `watchdog!WdLogSingleEntry3` at `0x1400227f9`
- `watchdog!WdLogSingleEntry3` at `0x140022840`
- `watchdog!WdLogSingleEntry0` at `0x1400225a6`
- `watchdog!WdLogSingleEntry0` at `0x1400225a6`

## string_xrefs

- `0x1400225bb`: `FdoContext->DeviceThreadState != StateSuspended || FdoContext->DevicePnpState == SurpriseRemoved || FdoContext->DevicePowerTransitionState != DevicePoweredOn`

## pseudocode

```c

```
