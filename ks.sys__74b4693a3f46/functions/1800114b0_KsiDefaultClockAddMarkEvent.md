# KsiDefaultClockAddMarkEvent

- ea: `0x1800114b0`
- end: `0x18001161e`
- name: `KsiDefaultClockAddMarkEvent`
- size: `366`
- prototype: `NTSTATUS __stdcall(PIRP Irp, PKSEVENT_TIME_INTERVAL EventTime, PKSEVENT_ENTRY EventEntry)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18000b704`
- `0x18001017c`
- `0x1800114b0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180011501`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180011501`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800115ff`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800115ff`
- `HAL!KeQueryPerformanceCounter` at `0x18001156b`
- `HAL!KeQueryPerformanceCounter` at `0x18001156b`

## pseudocode

```c

```
