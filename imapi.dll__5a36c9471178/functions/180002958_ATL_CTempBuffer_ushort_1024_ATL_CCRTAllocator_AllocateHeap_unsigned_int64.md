# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180002958`
- end: `0x180002983`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002454`
- `0x180003878`

## callees

- `0x180002958`
- `0x180002ac4`

## import_xrefs

- `msvcrt!malloc` at `0x180002964`
- `msvcrt!malloc` at `0x180002964`

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
0x180002958  push    rbx
0x18000295a  sub     rsp, 20h
0x18000295e  mov     rbx, rcx
0x180002961  mov     rcx, rdx; Size
0x180002964  call    cs:__imp_malloc
0x18000296a  test    rax, rax
0x18000296d  jz      short loc_180002978
0x18000296f  mov     [rbx], rax
0x180002972  add     rsp, 20h
0x180002976  pop     rbx
0x180002977  retn
0x180002978  mov     ecx, 8007000Eh; int
0x18000297d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
