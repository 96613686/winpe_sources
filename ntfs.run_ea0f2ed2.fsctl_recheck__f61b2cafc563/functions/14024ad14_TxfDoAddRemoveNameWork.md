# TxfDoAddRemoveNameWork

- ea: `0x14024ad14`
- end: `0x14024c5e5`
- name: `TxfDoAddRemoveNameWork`
- size: `6353`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, BOOLEAN Wait, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `35`
- tags: `authz_impersonation`

## callers

- `0x140249d88`
- `0x14026d0c4`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000ea70`
- `0x14001e810`
- `0x1400211b0`
- `0x1400331f8`
- `0x1400410a8`
- `0x140041a88`
- `0x14005410c`
- `0x140059250`
- `0x1400593c0`
- `0x1400596c0`
- `0x140105e78`
- `0x14010c31c`
- `0x14010c42c`
- `0x1401250b0`
- `0x1401261d0`
- `0x140129fb0`
- `0x14012ba70`
- `0x140140380`
- `0x14014bae0`
- `0x140154d10`
- `0x1401620c0`
- `0x14018cb48`
- `0x14018e5d4`
- `0x1401913d4`
- `0x140195138`
- `0x14019b330`
- `0x1401e0660`
- `0x1401e3230`
- `0x14022c774`
- `0x14024ad14`
- `0x14024c5ec`
- `0x140294b1c`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14024b823`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14024ba5f`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14024b823`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14024ba5f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14024b372`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14024b372`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14024b3ea`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14024b3ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024c586`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024c599`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024c5bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b861d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8638`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b871c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024c586`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024c599`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024c5bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b861d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8638`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b871c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024b10d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024bbf8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024b10d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024bbf8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14024b3c0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14024b3c0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b2c0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b769`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b7af`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b9a3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b9e8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024bda1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b2c0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b769`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b7af`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b9a3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b9e8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024bda1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024b322`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024b78e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024b91c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024b9c7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024bae7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024bdd8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024c456`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024c5d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b873c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024b322`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024b78e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024b91c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024b9c7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024bae7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024bdd8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024c456`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024c5d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b873c`

## pseudocode

```c

```
