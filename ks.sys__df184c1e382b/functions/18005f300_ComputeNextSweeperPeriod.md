# ComputeNextSweeperPeriod

- ea: `0x18005f300`
- end: `0x18005f405`
- name: `ComputeNextSweeperPeriod`
- size: `261`
- prototype: `__int64 __fastcall(__int64 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180034d30`
- `0x18005a890`

## callees

- `0x18005f300`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18005f329`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18005f329`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005f319`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005f319`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18005f34f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18005f34f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005f35b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005f35b`

## pseudocode

```c

```
