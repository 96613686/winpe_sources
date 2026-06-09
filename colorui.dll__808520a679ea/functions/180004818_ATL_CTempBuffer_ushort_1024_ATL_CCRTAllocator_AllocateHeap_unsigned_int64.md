# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180004818`
- end: `0x180004843`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004314`
- `0x180008c0c`

## callees

- `0x180004818`
- `0x180004a90`

## import_xrefs

- `msvcrt!malloc` at `0x180004824`
- `msvcrt!malloc` at `0x180004824`

## pseudocode

```c
void *__fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(_QWORD *a1, size_t a2)
{
  void *result; // rax

  result = malloc(a2);
  if ( !result )
    ATL::AtlThrowImpl(-2147024882);
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x180004818  push    rbx
0x18000481a  sub     rsp, 20h
0x18000481e  mov     rbx, rcx
0x180004821  mov     rcx, rdx; Size
0x180004824  call    cs:__imp_malloc
0x18000482a  test    rax, rax
0x18000482d  jz      short loc_180004838
0x18000482f  mov     [rbx], rax
0x180004832  add     rsp, 20h
0x180004836  pop     rbx
0x180004837  retn
0x180004838  mov     ecx, 8007000Eh; int
0x18000483d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
