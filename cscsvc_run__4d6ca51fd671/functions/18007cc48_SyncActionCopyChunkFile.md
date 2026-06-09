# SyncActionCopyChunkFile

- ea: `0x18007cc48`
- end: `0x18007cf4b`
- name: `SyncActionCopyChunkFile`
- size: `771`
- prototype: `__int64 __usercall@<rax>(HANDLE hHandle@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18007d6d8`

## callees

- `0x180020f2c`
- `0x180030aec`
- `0x1800360c0`
- `0x180036394`
- `0x18006eb2c`
- `0x1800728c4`
- `0x180073a00`
- `0x18007cc48`
- `0x18007cf54`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x18007ceb6`
- `KERNEL32!VirtualFree` at `0x18007cecb`
- `KERNEL32!VirtualFree` at `0x18007ceb6`
- `KERNEL32!VirtualFree` at `0x18007cecb`

## string_xrefs

- `0x18007cee7`: `exit: CopyChunkFailed = %c, status = 0x%08x ( EE = %u )`
- `0x18007ce05`: `Should not copy entire file using copy chunk, failing with 0x%08x`

## pseudocode

```c

```
