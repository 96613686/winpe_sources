# CscNotifyIrpCompletionRoutine

- ea: `0x1400154f0`
- end: `0x14001562b`
- name: `CscNotifyIrpCompletionRoutine`
- size: `315`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400154f0`
- `0x140018930`
- `0x14002f0f0`
- `0x14006f058`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400155ca`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400155ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400155de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400155de`
- `ntoskrnl!KeSetEvent` at `0x140015580`
- `ntoskrnl!KeSetEvent` at `0x140015580`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001555e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001555e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400155be`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400155be`

## pseudocode

```c

```
