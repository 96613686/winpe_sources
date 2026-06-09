# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x18000ee48`
- end: `0x18000ee73`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ea4c`
- `0x180010e3c`

## callees

- `0x18000afe0`
- `0x18000ee48`

## import_xrefs

- `msvcrt!malloc` at `0x18000ee54`
- `msvcrt!malloc` at `0x18000ee54`

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
0x18000ee48  push    rbx
0x18000ee4a  sub     rsp, 20h
0x18000ee4e  mov     rbx, rcx
0x18000ee51  mov     rcx, rdx; Size
0x18000ee54  call    cs:__imp_malloc
0x18000ee5a  test    rax, rax
0x18000ee5d  jz      short loc_18000EE68
0x18000ee5f  mov     [rbx], rax
0x18000ee62  add     rsp, 20h
0x18000ee66  pop     rbx
0x18000ee67  retn
0x18000ee68  mov     ecx, 8007000Eh; int
0x18000ee6d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
