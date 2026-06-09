# ndisReleaseStackTrace(ulong)

- ea: `0x1400688e0`
- end: `0x1400689d0`
- name: `?ndisReleaseStackTrace@@YAXK@Z`
- size: `240`
- prototype: `void __fastcall(ULONG_PTR Signature)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140014a00`
- `0x140017780`
- `0x140025c70`
- `0x140032aa0`
- `0x140168bd0`

## callees

- `0x1400688e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400689ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400689ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x140068969`
- `ntoskrnl!KeReleaseSpinLock` at `0x140068969`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140068904`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140068904`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400689a9`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400689a9`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14006893d`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14006893d`

## pseudocode

```c

```
