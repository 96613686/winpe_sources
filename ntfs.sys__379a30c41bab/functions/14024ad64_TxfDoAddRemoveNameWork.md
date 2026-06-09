# TxfDoAddRemoveNameWork

- ea: `0x14024ad64`
- end: `0x14024c635`
- name: `TxfDoAddRemoveNameWork`
- size: `6353`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, BOOLEAN Wait, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `35`
- tags: `authz_impersonation`

## callers

- `0x140249dd8`
- `0x14026d114`

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
- `0x14005417c`
- `0x1400592c0`
- `0x140059440`
- `0x140059740`
- `0x140105ec8`
- `0x14010c36c`
- `0x14010c47c`
- `0x140125100`
- `0x140126220`
- `0x14012a000`
- `0x14012bac0`
- `0x1401403d0`
- `0x14014bb30`
- `0x140154d60`
- `0x140162110`
- `0x14018cb98`
- `0x14018e624`
- `0x140191424`
- `0x140195188`
- `0x14019b380`
- `0x1401e06b0`
- `0x1401e3280`
- `0x14022c7c4`
- `0x14024ad64`
- `0x14024c63c`
- `0x140294b6c`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14024b873`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14024baaf`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14024b873`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14024baaf`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14024b3c2`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14024b3c2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14024b43a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14024b43a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024c5d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024c5e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024c60c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b866d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8688`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b876c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024c5d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024c5e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024c60c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b866d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8688`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b876c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024b15d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024bc48`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024b15d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024bc48`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14024b410`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14024b410`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b310`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b7b9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b7ff`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b9f3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024ba38`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024bdf1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b310`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b7b9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b7ff`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024b9f3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024ba38`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024bdf1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024b372`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024b7de`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024b96c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024ba17`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024bb37`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024be28`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024c4a6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024c624`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b878c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024b372`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024b7de`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024b96c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024ba17`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024bb37`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024be28`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024c4a6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024c624`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b878c`

## pseudocode

```c

```
