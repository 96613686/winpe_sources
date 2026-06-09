# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180002f48`
- end: `0x180002f73`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000296c`
- `0x180004428`

## callees

- `0x180002f48`
- `0x1800030b4`

## import_xrefs

- `msvcrt!malloc` at `0x180002f54`
- `msvcrt!malloc` at `0x180002f54`

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
0x180002f48  push    rbx
0x180002f4a  sub     rsp, 20h
0x180002f4e  mov     rbx, rcx
0x180002f51  mov     rcx, rdx; Size
0x180002f54  call    cs:__imp_malloc
0x180002f5a  test    rax, rax
0x180002f5d  jz      short loc_180002F68
0x180002f5f  mov     [rbx], rax
0x180002f62  add     rsp, 20h
0x180002f66  pop     rbx
0x180002f67  retn
0x180002f68  mov     ecx, 8007000Eh; int
0x180002f6d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
