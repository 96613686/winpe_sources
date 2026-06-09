# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x1400067c8`
- end: `0x1400067fa`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400061bc`
- `0x140007880`

## callees

- `0x1400067c8`
- `0x140006940`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400067d4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400067d4`

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
0x1400067c8  push    rbx
0x1400067ca  sub     rsp, 20h
0x1400067ce  mov     rbx, rcx
0x1400067d1  mov     rcx, rdx; Size
0x1400067d4  call    cs:__imp_malloc
0x1400067db  nop     dword ptr [rax+rax+00h]
0x1400067e0  test    rax, rax
0x1400067e3  jz      short loc_1400067EF
0x1400067e5  mov     [rbx], rax
0x1400067e8  add     rsp, 20h
0x1400067ec  pop     rbx
0x1400067ed  retn
0x1400067ef  mov     ecx, 8007000Eh; int
0x1400067f4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
