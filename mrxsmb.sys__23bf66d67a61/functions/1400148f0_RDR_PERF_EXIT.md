# RDR_PERF_EXIT

- ea: `0x1400148f0`
- end: `0x1400149be`
- name: `RDR_PERF_EXIT`
- size: `206`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140006150`
- `0x140006ec0`
- `0x14000b4b0`
- `0x14000c270`
- `0x140013cb0`
- `0x1400147e0`
- `0x140014830`
- `0x140016e60`

## callees

- `0x1400148f0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014937`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014937`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400149a1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400149a1`
- `HAL!KeQueryPerformanceCounter` at `0x14001491e`
- `HAL!KeQueryPerformanceCounter` at `0x14001491e`

## pseudocode

```c

```
