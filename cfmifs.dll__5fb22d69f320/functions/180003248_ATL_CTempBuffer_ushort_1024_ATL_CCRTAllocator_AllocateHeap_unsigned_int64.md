# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180003248`
- end: `0x180003273`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d44`
- `0x180004818`

## callees

- `0x180003248`
- `0x18000397c`

## import_xrefs

- `msvcrt!malloc` at `0x180003254`
- `msvcrt!malloc` at `0x180003254`

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
0x180003248  push    rbx
0x18000324a  sub     rsp, 20h
0x18000324e  mov     rbx, rcx
0x180003251  mov     rcx, rdx; Size
0x180003254  call    cs:__imp_malloc
0x18000325a  test    rax, rax
0x18000325d  jz      short loc_180003268
0x18000325f  mov     [rbx], rax
0x180003262  add     rsp, 20h
0x180003266  pop     rbx
0x180003267  retn
0x180003268  mov     ecx, 8007000Eh; int
0x18000326d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
