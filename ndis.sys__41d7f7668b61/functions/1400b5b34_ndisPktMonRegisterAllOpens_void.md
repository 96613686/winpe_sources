# ndisPktMonRegisterAllOpens(void)

- ea: `0x1400b5b34`
- end: `0x1400b5cd5`
- name: `?ndisPktMonRegisterAllOpens@@YAXXZ`
- size: `417`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400b5ce0`

## callees

- `0x140005140`
- `0x14009d0cc`
- `0x1400b5b34`
- `0x1400eb7c0`
- `0x14016ac50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400b5c7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b5c7a`
- `ntoskrnl!ExAllocatePool2` at `0x1400b5bcf`
- `ntoskrnl!ExAllocatePool2` at `0x1400b5bcf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b5c3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b5c3c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b5b57`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b5b57`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400b5b8e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400b5b8e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400b5bb5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400b5c0c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400b5bb5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400b5c0c`

## pseudocode

```c

```
