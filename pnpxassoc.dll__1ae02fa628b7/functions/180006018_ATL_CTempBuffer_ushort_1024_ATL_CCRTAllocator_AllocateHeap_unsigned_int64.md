# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180006018`
- end: `0x180006043`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005b14`
- `0x180007a88`

## callees

- `0x180006018`
- `0x180006764`

## import_xrefs

- `msvcrt!malloc` at `0x180006024`
- `msvcrt!malloc` at `0x180006024`

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
0x180006018  push    rbx
0x18000601a  sub     rsp, 20h
0x18000601e  mov     rbx, rcx
0x180006021  mov     rcx, rdx; Size
0x180006024  call    cs:__imp_malloc
0x18000602a  test    rax, rax
0x18000602d  jz      short loc_180006038
0x18000602f  mov     [rbx], rax
0x180006032  add     rsp, 20h
0x180006036  pop     rbx
0x180006037  retn
0x180006038  mov     ecx, 8007000Eh; int
0x18000603d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
