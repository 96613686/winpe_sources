# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x140002aa8`
- end: `0x140002ad3`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400025a4`
- `0x140004128`

## callees

- `0x140002aa8`
- `0x140002c14`

## import_xrefs

- `msvcrt!malloc` at `0x140002ab4`
- `msvcrt!malloc` at `0x140002ab4`

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
0x140002aa8  push    rbx
0x140002aaa  sub     rsp, 20h
0x140002aae  mov     rbx, rcx
0x140002ab1  mov     rcx, rdx; Size
0x140002ab4  call    cs:__imp_malloc
0x140002aba  test    rax, rax
0x140002abd  jz      short loc_140002AC8
0x140002abf  mov     [rbx], rax
0x140002ac2  add     rsp, 20h
0x140002ac6  pop     rbx
0x140002ac7  retn
0x140002ac8  mov     ecx, 8007000Eh; int
0x140002acd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
