# ndisReleaseStackTrace(ulong)

- ea: `0x14006df40`
- end: `0x14006e030`
- name: `?ndisReleaseStackTrace@@YAXK@Z`
- size: `240`
- prototype: `void __fastcall(ULONG_PTR Signature)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b820`
- `0x140019dd0`
- `0x1400260b0`
- `0x14003e070`
- `0x14016fac0`

## callees

- `0x14006df40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006e01a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e01a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006dfc9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006dfc9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006df64`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006df64`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14006e009`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14006e009`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14006df9d`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14006df9d`

## pseudocode

```c

```
