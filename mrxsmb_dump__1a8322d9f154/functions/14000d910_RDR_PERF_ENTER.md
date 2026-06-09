# RDR_PERF_ENTER

- ea: `0x14000d910`
- end: `0x14000d9f2`
- name: `RDR_PERF_ENTER`
- size: `226`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140006150`
- `0x140006680`
- `0x140006ec0`
- `0x14000b4b0`
- `0x14000c270`
- `0x14000e530`
- `0x140012190`
- `0x140013cb0`
- `0x140016e60`
- `0x14008d190`

## callees

- `0x140004938`
- `0x14000d910`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d95c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d95c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d9b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d9b5`
- `HAL!KeQueryPerformanceCounter` at `0x14000d946`
- `HAL!KeQueryPerformanceCounter` at `0x14000d946`

## pseudocode

```c

```
