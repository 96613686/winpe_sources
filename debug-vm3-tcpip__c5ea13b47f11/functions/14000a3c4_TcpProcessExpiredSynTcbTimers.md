# TcpProcessExpiredSynTcbTimers

- ea: `0x14000a3c4`
- end: `0x14000a589`
- name: `TcpProcessExpiredSynTcbTimers`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140008fd0`

## callees

- `0x14000a3c4`
- `0x14000ad00`
- `0x14007bef4`
- `0x1400b0398`
- `0x1400b18e8`
- `0x1401242ac`
- `0x1401620c4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000a487`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401c0e9b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000a487`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401c0e9b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000a52a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401c0e7f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000a52a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401c0e7f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000a3f2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000a3f2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a42b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a46b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a51b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a558`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a42b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a46b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a51b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a558`
- `NETIO!RtlIsTimerWheelSuspended` at `0x14000a412`
- `NETIO!RtlIsTimerWheelSuspended` at `0x14000a412`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x1401c0db0`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x1401c0db0`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1401c0dc3`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1401c0ece`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1401c0dc3`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1401c0ece`
- `NETIO!RtlReturnTimerWheelEntry` at `0x1401c0ebb`
- `NETIO!RtlReturnTimerWheelEntry` at `0x1401c0ebb`

## pseudocode

```c

```
