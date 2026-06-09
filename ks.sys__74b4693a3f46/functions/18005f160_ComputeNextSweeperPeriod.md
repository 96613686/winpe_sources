# ComputeNextSweeperPeriod

- ea: `0x18005f160`
- end: `0x18005f265`
- name: `ComputeNextSweeperPeriod`
- size: `261`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180034c20`
- `0x18005a6f0`

## callees

- `0x18005f160`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18005f189`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18005f189`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005f179`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005f179`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18005f1af`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18005f1af`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005f1bb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005f1bb`

## pseudocode

```c

```
