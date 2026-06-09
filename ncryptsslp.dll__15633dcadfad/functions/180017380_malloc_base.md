# _malloc_base

- ea: `0x180017380`
- end: `0x1800173de`
- name: `_malloc_base`
- size: `94`
- prototype: `void *__cdecl(size_t Size)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180016a3c`
- `0x1800173e4`
- `0x180017bf8`
- `0x180018910`
- `0x18001b0e0`

## callees

- `0x1800150d0`
- `0x180017380`
- `0x1800179a0`
- `0x180017aa0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800173be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800173be`

## pseudocode

```c
void *__cdecl malloc_base(size_t Size)
{
  SIZE_T v1; // rbx
  void *result; // rax

  v1 = Size;
  if ( Size > 0xFFFFFFFFFFFFFFE0uLL )
  {
LABEL_9:
    *errno() = 12;
    return 0;
  }
  else
  {
    if ( !Size )
      v1 = 1;
    while ( 1 )
    {
      result = HeapAlloc(_acrt_heap, 0, v1);
      if ( result )
        break;
      if ( !query_new_mode() || !callnewh(v1) )
        goto LABEL_9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180017380  push    rbx
0x180017382  sub     rsp, 20h
0x180017386  mov     rbx, rcx
0x180017389  cmp     rcx, 0FFFFFFFFFFFFFFE0h
0x18001738d  ja      short loc_1800173CB
0x18001738f  test    rcx, rcx
0x180017392  mov     eax, 1
0x180017397  cmovz   rbx, rax
0x18001739b  jmp     short loc_1800173B2
0x18001739d  call    _query_new_mode
0x1800173a2  test    eax, eax
0x1800173a4  jz      short loc_1800173CB
0x1800173a6  mov     rcx, rbx; Size
0x1800173a9  call    _callnewh
0x1800173ae  test    eax, eax
0x1800173b0  jz      short loc_1800173CB
0x1800173b2  mov     rcx, cs:__acrt_heap; hHeap
0x1800173b9  mov     r8, rbx; dwBytes
0x1800173bc  xor     edx, edx; dwFlags
0x1800173be  call    cs:__imp_HeapAlloc
0x1800173c4  test    rax, rax
0x1800173c7  jz      short loc_18001739D
0x1800173c9  jmp     short loc_1800173D8
0x1800173cb  call    _errno
0x1800173d0  mov     dword ptr [rax], 0Ch
0x1800173d6  xor     eax, eax
0x1800173d8  add     rsp, 20h
0x1800173dc  pop     rbx
0x1800173dd  retn
```
