# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180004cc8`
- end: `0x180004cf3`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800046ec`
- `0x1800060c8`

## callees

- `0x180004cc8`
- `0x180005688`

## import_xrefs

- `msvcrt!malloc` at `0x180004cd4`
- `msvcrt!malloc` at `0x180004cd4`

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
0x180004cc8  push    rbx
0x180004cca  sub     rsp, 20h
0x180004cce  mov     rbx, rcx
0x180004cd1  mov     rcx, rdx; Size
0x180004cd4  call    cs:__imp_malloc
0x180004cda  test    rax, rax
0x180004cdd  jz      short loc_180004CE8
0x180004cdf  mov     [rbx], rax
0x180004ce2  add     rsp, 20h
0x180004ce6  pop     rbx
0x180004ce7  retn
0x180004ce8  mov     ecx, 8007000Eh; int
0x180004ced  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
