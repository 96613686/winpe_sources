# FatToggleMediaEjectDisable

- ea: `0x140002b30`
- end: `0x140002ca7`
- name: `FatToggleMediaEjectDisable`
- size: `375`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1400019b8`
- `0x140006918`
- `0x1400268c0`
- `0x14002c234`
- `0x14003dba0`
- `0x14003e94c`
- `0x14003f1bc`
- `0x140040674`
- `0x140048848`
- `0x1400498f0`

## callees

- `0x140002b30`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140002bc5`
- `ntoskrnl!KeInitializeEvent` at `0x140002bc5`
- `ntoskrnl!IofCallDriver` at `0x140002c55`
- `ntoskrnl!IofCallDriver` at `0x140002c55`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002c7e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002c7e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b63`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b63`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002b89`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002ba7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002b89`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002ba7`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140002c13`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140002c13`

## pseudocode

```c

```
