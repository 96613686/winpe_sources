# KsiDefaultClockAddMarkEvent

- ea: `0x180011d50`
- end: `0x180011ebe`
- name: `KsiDefaultClockAddMarkEvent`
- size: `366`
- prototype: `NTSTATUS __stdcall(PIRP Irp, PKSEVENT_TIME_INTERVAL EventTime, PKSEVENT_ENTRY EventEntry)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18000b704`
- `0x18001028c`
- `0x180011d50`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180011da1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180011da1`
- `ntoskrnl!KeReleaseSpinLock` at `0x180011e9f`
- `ntoskrnl!KeReleaseSpinLock` at `0x180011e9f`
- `HAL!KeQueryPerformanceCounter` at `0x180011e0b`
- `HAL!KeQueryPerformanceCounter` at `0x180011e0b`

## pseudocode

```c

```
