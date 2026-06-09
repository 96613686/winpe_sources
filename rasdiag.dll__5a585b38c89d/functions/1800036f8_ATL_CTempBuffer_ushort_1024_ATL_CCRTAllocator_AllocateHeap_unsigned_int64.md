# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x1800036f8`
- end: `0x18000372a`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `50`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030ec`
- `0x180004cf0`

## callees

- `0x1800036f8`
- `0x18000418c`

## import_xrefs

- `msvcrt!malloc` at `0x180003704`
- `msvcrt!malloc` at `0x180003704`

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
0x1800036f8  push    rbx
0x1800036fa  sub     rsp, 20h
0x1800036fe  mov     rbx, rcx
0x180003701  mov     rcx, rdx; Size
0x180003704  call    cs:__imp_malloc
0x18000370b  nop     dword ptr [rax+rax+00h]
0x180003710  test    rax, rax
0x180003713  jz      short loc_18000371F
0x180003715  mov     [rbx], rax
0x180003718  add     rsp, 20h
0x18000371c  pop     rbx
0x18000371d  retn
0x18000371f  mov     ecx, 8007000Eh; int
0x180003724  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
