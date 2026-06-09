# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x18000e698`
- end: `0x18000e6c3`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e0bc`
- `0x1800110a8`

## callees

- `0x18000e698`
- `0x18000f208`

## import_xrefs

- `msvcrt!malloc` at `0x18000e6a4`
- `msvcrt!malloc` at `0x18000e6a4`

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
0x18000e698  push    rbx
0x18000e69a  sub     rsp, 20h
0x18000e69e  mov     rbx, rcx
0x18000e6a1  mov     rcx, rdx; Size
0x18000e6a4  call    cs:__imp_malloc
0x18000e6aa  test    rax, rax
0x18000e6ad  jz      short loc_18000E6B8
0x18000e6af  mov     [rbx], rax
0x18000e6b2  add     rsp, 20h
0x18000e6b6  pop     rbx
0x18000e6b7  retn
0x18000e6b8  mov     ecx, 8007000Eh; int
0x18000e6bd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
