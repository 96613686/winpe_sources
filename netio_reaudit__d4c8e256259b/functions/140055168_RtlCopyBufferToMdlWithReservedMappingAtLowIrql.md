# RtlCopyBufferToMdlWithReservedMappingAtLowIrql

- ea: `0x140055168`
- end: `0x140055249`
- name: `RtlCopyBufferToMdlWithReservedMappingAtLowIrql`
- size: `225`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, PMDL SourceMdl@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140054f60`

## callees

- `0x140055250`
- `0x140077fa0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400551ae`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400551ae`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400551c3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400551c3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005520e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005520e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005521a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005521a`

## pseudocode

```c

```
