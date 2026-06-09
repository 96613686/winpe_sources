# NdisTryAcquireRWLockWrite

- ea: `0x1400c1d20`
- end: `0x1400c1de1`
- name: `NdisTryAcquireRWLockWrite`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400c19b0`

## callees

- `0x1400c1d20`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400c1d51`
- `ntoskrnl!KfRaiseIrql` at `0x1400c1d51`
- `ntoskrnl!KeLowerIrql` at `0x1400c1d7d`
- `ntoskrnl!KeLowerIrql` at `0x1400c1d7d`
- `ntoskrnl!KeTestSpinLock` at `0x1400c1d39`
- `ntoskrnl!KeTestSpinLock` at `0x1400c1d39`
- `ntoskrnl!KeTryToAcquireSpinLockAtDpcLevel` at `0x1400c1d66`
- `ntoskrnl!KeTryToAcquireSpinLockAtDpcLevel` at `0x1400c1d66`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400c1dbe`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400c1dbe`

## pseudocode

```c

```
