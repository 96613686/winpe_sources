# DpiRequestDevicePowerState

- ea: `0x140022680`
- end: `0x140022abe`
- name: `DpiRequestDevicePowerState`
- size: `1086`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: ``

## callers

- `0x140022434`
- `0x140022540`
- `0x1400225bc`
- `0x1400579e0`
- `0x140328500`

## callees

- `0x14001b9c0`
- `0x14001bffc`
- `0x140022680`
- `0x140022b68`
- `0x140022c40`
- `0x140022e90`
- `0x14004ad24`
- `0x140052f9c`
- `0x14007fccc`
- `0x14007fdf8`
- `0x140382c30`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140022a76`
- `ntoskrnl!KeSetEvent` at `0x140022a76`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140022aa5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140022aa5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140022722`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002294c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140022722`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002294c`
- `watchdog!WdLogSingleEntry3` at `0x1400226a8`
- `watchdog!WdLogSingleEntry3` at `0x140022742`
- `watchdog!WdLogSingleEntry3` at `0x14002283f`
- `watchdog!WdLogSingleEntry3` at `0x140022873`
- `watchdog!WdLogSingleEntry3` at `0x1400228a9`
- `watchdog!WdLogSingleEntry3` at `0x14002290a`
- `watchdog!WdLogSingleEntry3` at `0x14002296c`
- `watchdog!WdLogSingleEntry3` at `0x1400229c9`
- `watchdog!WdLogSingleEntry3` at `0x140022a10`
- `watchdog!WdLogSingleEntry3` at `0x1400226a8`
- `watchdog!WdLogSingleEntry3` at `0x140022742`
- `watchdog!WdLogSingleEntry3` at `0x14002283f`
- `watchdog!WdLogSingleEntry3` at `0x140022873`
- `watchdog!WdLogSingleEntry3` at `0x1400228a9`
- `watchdog!WdLogSingleEntry3` at `0x14002290a`
- `watchdog!WdLogSingleEntry3` at `0x14002296c`
- `watchdog!WdLogSingleEntry3` at `0x1400229c9`
- `watchdog!WdLogSingleEntry3` at `0x140022a10`
- `watchdog!WdLogSingleEntry0` at `0x140022776`
- `watchdog!WdLogSingleEntry0` at `0x140022776`

## string_xrefs

- `0x14002278b`: `FdoContext->DeviceThreadState != StateSuspended || FdoContext->DevicePnpState == SurpriseRemoved || FdoContext->DevicePowerTransitionState != DevicePoweredOn`

## pseudocode

```c

```
