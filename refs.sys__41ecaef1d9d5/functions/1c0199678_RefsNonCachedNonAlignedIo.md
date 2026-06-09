# RefsNonCachedNonAlignedIo

- ea: `0x1c0199678`
- end: `0x1c0199df6`
- name: `RefsNonCachedNonAlignedIo`
- size: `1918`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, PIRP Irp@<rdx>, int)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1c000dc80`

## callees

- `0x1c0004a30`
- `0x1c000f770`
- `0x1c000f980`
- `0x1c000fa60`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c006acc0`
- `0x1c006af80`
- `0x1c009166c`
- `0x1c00925e8`
- `0x1c00a29c4`
- `0x1c01639a0`
- `0x1c0199678`
- `0x1c019a770`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0199785`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0199785`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0199d19`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0199db1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0199d19`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0199db1`
- `ntoskrnl!IoBuildPartialMdl` at `0x1c0199ccd`
- `ntoskrnl!IoBuildPartialMdl` at `0x1c0199ccd`
- `ntoskrnl!IoAllocateMdl` at `0x1c0199c3c`
- `ntoskrnl!IoAllocateMdl` at `0x1c0199c3c`
- `ntoskrnl!IoFreeMdl` at `0x1c0199cfb`
- `ntoskrnl!IoFreeMdl` at `0x1c0199d75`
- `ntoskrnl!IoFreeMdl` at `0x1c0199cfb`
- `ntoskrnl!IoFreeMdl` at `0x1c0199d75`
- `ntoskrnl!KeFlushIoBuffers` at `0x1c0199d40`
- `ntoskrnl!KeFlushIoBuffers` at `0x1c0199de1`
- `ntoskrnl!KeFlushIoBuffers` at `0x1c0199d40`
- `ntoskrnl!KeFlushIoBuffers` at `0x1c0199de1`

## pseudocode

```c

```
