# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180003d88`
- end: `0x180003db3`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800037ac`
- `0x180005488`

## callees

- `0x18000278c`
- `0x180003d88`

## import_xrefs

- `msvcrt!malloc` at `0x180003d94`
- `msvcrt!malloc` at `0x180003d94`

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
0x180003d88  push    rbx
0x180003d8a  sub     rsp, 20h
0x180003d8e  mov     rbx, rcx
0x180003d91  mov     rcx, rdx; Size
0x180003d94  call    cs:__imp_malloc
0x180003d9a  test    rax, rax
0x180003d9d  jz      short loc_180003DA8
0x180003d9f  mov     [rbx], rax
0x180003da2  add     rsp, 20h
0x180003da6  pop     rbx
0x180003da7  retn
0x180003da8  mov     ecx, 8007000Eh; int
0x180003dad  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
