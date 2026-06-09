# KsMoveIrpsOnCancelableQueue

- ea: `0x1800119e0`
- end: `0x180011b92`
- name: `KsMoveIrpsOnCancelableQueue`
- size: `434`
- prototype: `NTSTATUS __stdcall(PLIST_ENTRY SourceList, PKSPIN_LOCK SourceLock, PLIST_ENTRY DestinationList, PKSPIN_LOCK DestinationLock, KSLIST_ENTRY_LOCATION ListLocation, PFNKSIRPLISTCALLBACK ListCallback, PVOID Context)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800119e0`
- `0x180019c60`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180011a49`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180011a49`
- `ntoskrnl!KeReleaseSpinLock` at `0x180011b6b`
- `ntoskrnl!KeReleaseSpinLock` at `0x180011b6b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x180011a29`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x180011a38`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x180011a29`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x180011a38`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x180011b37`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x180011b46`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x180011b37`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x180011b46`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x180011a1a`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x180011a1a`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180011b56`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180011b56`

## pseudocode

```c

```
