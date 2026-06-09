# ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x18000c308`
- end: `0x18000c333`
- name: `?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bd2c`
- `0x18000edc8`

## callees

- `0x18000c308`
- `0x18000c434`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c314`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c314`

## pseudocode

```c
void *__fastcall ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(_QWORD *a1, size_t a2)
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
0x18000c308  push    rbx
0x18000c30a  sub     rsp, 20h
0x18000c30e  mov     rbx, rcx
0x18000c311  mov     rcx, rdx; Size
0x18000c314  call    cs:__imp_malloc
0x18000c31a  test    rax, rax
0x18000c31d  jz      short loc_18000C328
0x18000c31f  mov     [rbx], rax
0x18000c322  add     rsp, 20h
0x18000c326  pop     rbx
0x18000c327  retn
0x18000c328  mov     ecx, 8007000Eh; int
0x18000c32d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
