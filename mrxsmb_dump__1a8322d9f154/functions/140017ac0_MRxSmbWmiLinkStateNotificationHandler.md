# MRxSmbWmiLinkStateNotificationHandler

- ea: `0x140017ac0`
- end: `0x140017cb8`
- name: `MRxSmbWmiLinkStateNotificationHandler`
- size: `504`
- prototype: `FWMI_NOTIFICATION_CALLBACK`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x140017ac0`
- `0x140039fa8`
- `0x1400420b8`
- `0x14008ff20`
- `0x140090350`
- `0x140092670`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017b1d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017b1d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140017ae0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140017ae0`
- `ntoskrnl!RtlGetCallersAddress` at `0x140017ba8`
- `ntoskrnl!RtlGetCallersAddress` at `0x140017ba8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017b43`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017c21`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017b43`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017c21`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017c03`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017c03`

## pseudocode

```c

```
