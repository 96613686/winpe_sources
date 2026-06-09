# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180002ed8`
- end: `0x180002f03`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800028fc`
- `0x180004d18`

## callees

- `0x180002ed8`
- `0x1800039a4`

## import_xrefs

- `msvcrt!malloc` at `0x180002ee4`
- `msvcrt!malloc` at `0x180002ee4`

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
0x180002ed8  push    rbx
0x180002eda  sub     rsp, 20h
0x180002ede  mov     rbx, rcx
0x180002ee1  mov     rcx, rdx; Size
0x180002ee4  call    cs:__imp_malloc
0x180002eea  test    rax, rax
0x180002eed  jz      short loc_180002EF8
0x180002eef  mov     [rbx], rax
0x180002ef2  add     rsp, 20h
0x180002ef6  pop     rbx
0x180002ef7  retn
0x180002ef8  mov     ecx, 8007000Eh; int
0x180002efd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
