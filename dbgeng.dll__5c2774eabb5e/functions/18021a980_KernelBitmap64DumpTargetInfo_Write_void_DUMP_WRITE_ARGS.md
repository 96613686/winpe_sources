# KernelBitmap64DumpTargetInfo::Write(void *,DUMP_WRITE_ARGS *)

- ea: `0x18021a980`
- end: `0x18021ada9`
- name: `?Write@KernelBitmap64DumpTargetInfo@@UEAAJPEAXPEAUDUMP_WRITE_ARGS@@@Z`
- size: `1065`
- prototype: `__int64 __fastcall(KernelBitmap64DumpTargetInfo *__hidden this, void *, struct DUMP_WRITE_ARGS *)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting`

## callees

- `0x1800727b8`
- `0x1800793cc`
- `0x1800797ec`
- `0x180096068`
- `0x180096320`
- `0x180099a10`
- `0x18009bfc0`
- `0x18009cad8`
- `0x1800cef30`
- `0x1800e770c`
- `0x1800e8b30`
- `0x1800f0f40`
- `0x180215c70`
- `0x18021a980`
- `0x18026b6f4`
- `0x18038605c`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18021aa5b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18021ab38`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18021aa5b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18021ab38`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18021ad16`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18021ad2a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18021ad16`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18021ad2a`
- `ntdll!RtlInitializeBitMap` at `0x18021ab7d`
- `ntdll!RtlInitializeBitMap` at `0x18021ab7d`

## string_xrefs

- `0x18021ad66`: `\nKernel bitmap dumps can only be written when all of physical memory is accessible - aborting now\n`
- `0x18021ab89`: `Collecting pages to write to the dump. This may take a while.\n`
- `0x18021ad4c`: `Failed to write kernel dump, %s.\n`

## pseudocode

```c

```
