# KernelBitmap32DumpTargetInfo::Write(void *,DUMP_WRITE_ARGS *)

- ea: `0x18021a580`
- end: `0x18021a96b`
- name: `?Write@KernelBitmap32DumpTargetInfo@@UEAAJPEAXPEAUDUMP_WRITE_ARGS@@@Z`
- size: `1003`
- prototype: `__int64 __fastcall(KernelBitmap32DumpTargetInfo *__hidden this, void *, struct DUMP_WRITE_ARGS *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting`

## callees

- `0x1800727b8`
- `0x1800793cc`
- `0x1800797ec`
- `0x180096068`
- `0x180096320`
- `0x180099a10`
- `0x18009cad8`
- `0x1800cef30`
- `0x1800e770c`
- `0x1800e8b30`
- `0x1800f0f40`
- `0x180218c18`
- `0x18021a580`
- `0x18026b6f4`
- `0x18038605c`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18021a65b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18021a70a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18021a65b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18021a70a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18021a8d9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18021a8ed`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18021a8d9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18021a8ed`
- `ntdll!RtlInitializeBitMap` at `0x18021a74f`
- `ntdll!RtlInitializeBitMap` at `0x18021a74f`

## string_xrefs

- `0x18021a928`: `\nKernel bitmap dumps can only be written when all of physical memory is accessible - aborting now\n`
- `0x18021a75b`: `Collecting pages to write to the dump. This may take a while.\n`
- `0x18021a917`: `Failed to write kernel dump, %s.\n`

## pseudocode

```c

```
