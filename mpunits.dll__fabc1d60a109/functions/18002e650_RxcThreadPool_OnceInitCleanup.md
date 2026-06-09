# RxcThreadPool_OnceInitCleanup

- ea: `0x18002e650`
- end: `0x18002e67d`
- name: `RxcThreadPool_OnceInitCleanup`
- size: `45`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008cf0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002e65b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002e65b`

## pseudocode

```c
void __fastcall RxcThreadPool_OnceInitCleanup()
{
  CloseThreadpool(ptpp);
  Cache_Destruct(&stru_18008E6B0);
  Cache_Destruct(&stru_18008E6F0);
}

```

## disassembly

```asm
0x18002e650  sub     rsp, 28h
0x18002e654  mov     rcx, cs:ptpp; ptpp
0x18002e65b  call    cs:__imp_CloseThreadpool
0x18002e661  lea     rcx, stru_18008E6B0; ListHead
0x18002e668  call    Cache_Destruct
0x18002e66d  lea     rcx, stru_18008E6F0; ListHead
0x18002e674  add     rsp, 28h
0x18002e678  jmp     Cache_Destruct
```
