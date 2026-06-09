# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180006768`
- end: `0x18000679a`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000615c`
- `0x180008f00`

## callees

- `0x180006768`
- `0x1800068ec`

## import_xrefs

- `msvcrt!malloc` at `0x180006774`
- `msvcrt!malloc` at `0x180006774`

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
0x180006768  push    rbx
0x18000676a  sub     rsp, 20h
0x18000676e  mov     rbx, rcx
0x180006771  mov     rcx, rdx; Size
0x180006774  call    cs:__imp_malloc
0x18000677b  nop     dword ptr [rax+rax+00h]
0x180006780  test    rax, rax
0x180006783  jz      short loc_18000678F
0x180006785  mov     [rbx], rax
0x180006788  add     rsp, 20h
0x18000678c  pop     rbx
0x18000678d  retn
0x18000678f  mov     ecx, 8007000Eh; int
0x180006794  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
