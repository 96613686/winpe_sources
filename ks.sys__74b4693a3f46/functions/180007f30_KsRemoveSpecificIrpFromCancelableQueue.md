# KsRemoveSpecificIrpFromCancelableQueue

- ea: `0x180007f30`
- end: `0x180007f8f`
- name: `KsRemoveSpecificIrpFromCancelableQueue`
- size: `95`
- prototype: `void __stdcall(PIRP Irp)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180010a04`
- `0x1800182c4`

## callees

- `0x180007f30`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180007f40`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180007f40`
- `ntoskrnl!KeReleaseSpinLock` at `0x180007f75`
- `ntoskrnl!KeReleaseSpinLock` at `0x180007f75`

## pseudocode

```c

```
