# RtlCopyMdlToBufferWithReservedMappingAtLowIrql

- ea: `0x140055710`
- end: `0x1400557f1`
- name: `RtlCopyMdlToBufferWithReservedMappingAtLowIrql`
- size: `225`
- prototype: `__int64 __usercall@<rax>(PMDL SourceMdl@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140055570`

## callees

- `0x1400553c8`
- `0x140077fa0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140055756`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140055756`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005576b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005576b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400557b6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400557b6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400557c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400557c2`

## pseudocode

```c

```
