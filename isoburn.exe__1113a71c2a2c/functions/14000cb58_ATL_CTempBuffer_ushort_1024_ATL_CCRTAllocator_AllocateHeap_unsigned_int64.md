# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x14000cb58`
- end: `0x14000cb83`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c654`
- `0x14000d708`

## callees

- `0x1400045e4`
- `0x14000cb58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000cb64`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000cb64`

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
0x14000cb58  push    rbx
0x14000cb5a  sub     rsp, 20h
0x14000cb5e  mov     rbx, rcx
0x14000cb61  mov     rcx, rdx; Size
0x14000cb64  call    cs:__imp_malloc
0x14000cb6a  test    rax, rax
0x14000cb6d  jz      short loc_14000CB78
0x14000cb6f  mov     [rbx], rax
0x14000cb72  add     rsp, 20h
0x14000cb76  pop     rbx
0x14000cb77  retn
0x14000cb78  mov     ecx, 8007000Eh; int
0x14000cb7d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
