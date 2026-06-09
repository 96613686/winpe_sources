# MemFree(void *)

- ea: `0x180007d80`
- end: `0x180007da5`
- name: `?MemFree@@YAXPEAX@Z`
- size: `37`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180003088`
- `0x18000331c`
- `0x180003ed8`
- `0x180006d30`
- `0x180007c94`
- `0x18000831c`
- `0x1800099f0`
- `0x18000af5c`
- `0x18000b584`
- `0x180010a00`
- `0x180010f54`

## callees

- `0x180007d80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007d9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007d9a`

## pseudocode

```c
void __fastcall MemFree(void *lpMem)
{
  if ( lpMem )
  {
    if ( g_hLocalHeap )
      HeapFree(g_hLocalHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x180007d80  sub     rsp, 28h
0x180007d84  mov     r8, rcx; lpMem
0x180007d87  test    rcx, rcx
0x180007d8a  jz      short loc_180007DA0
0x180007d8c  mov     rcx, cs:?g_hLocalHeap@@3PEAXEA; hHeap
0x180007d93  test    rcx, rcx
0x180007d96  jz      short loc_180007DA0
0x180007d98  xor     edx, edx; dwFlags
0x180007d9a  call    cs:__imp_HeapFree
0x180007da0  add     rsp, 28h
0x180007da4  retn
```
