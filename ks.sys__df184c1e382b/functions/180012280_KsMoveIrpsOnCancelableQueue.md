# KsMoveIrpsOnCancelableQueue

- ea: `0x180012280`
- end: `0x180012432`
- name: `KsMoveIrpsOnCancelableQueue`
- size: `434`
- prototype: `NTSTATUS __stdcall(PLIST_ENTRY SourceList, PKSPIN_LOCK SourceLock, PLIST_ENTRY DestinationList, PKSPIN_LOCK DestinationLock, KSLIST_ENTRY_LOCATION ListLocation, PFNKSIRPLISTCALLBACK ListCallback, PVOID Context)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180012280`
- `0x180019cb0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800122e9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800122e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001240b`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001240b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1800122c9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1800122d8`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1800122c9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1800122d8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1800123d7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1800123e6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1800123d7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1800123e6`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1800122ba`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1800122ba`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1800123f6`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1800123f6`

## pseudocode

```c

```
