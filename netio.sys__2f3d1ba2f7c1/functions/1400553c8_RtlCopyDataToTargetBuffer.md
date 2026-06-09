# RtlCopyDataToTargetBuffer

- ea: `0x1400553c8`
- end: `0x14005553a`
- name: `RtlCopyDataToTargetBuffer`
- size: `370`
- prototype: `__int64 __usercall@<rax>(PMDL SourceMdl@<rcx>, __int64, PMDL TargetMdl, PVOID MappingAddress)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14004798c`
- `0x140055710`

## callees

- `0x1400553c8`
- `0x140077fd0`
- `0x1400a90a8`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x140055447`
- `ntoskrnl!IoBuildPartialMdl` at `0x140055447`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140055469`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140055469`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400554a7`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400554f6`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400554a7`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400554f6`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400554c0`
- `ntoskrnl!MmUnmapLockedPages` at `0x14005550f`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400554c0`
- `ntoskrnl!MmUnmapLockedPages` at `0x14005550f`

## pseudocode

```c

```
