# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180009724`
- end: `0x18000974f`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000919c`
- `0x18000ac80`

## callees

- `0x180002338`
- `0x180009724`

## import_xrefs

- `msvcrt!malloc` at `0x180009730`
- `msvcrt!malloc` at `0x180009730`

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
0x180009724  push    rbx
0x180009726  sub     rsp, 20h
0x18000972a  mov     rbx, rcx
0x18000972d  mov     rcx, rdx; Size
0x180009730  call    cs:__imp_malloc
0x180009736  test    rax, rax
0x180009739  jnz     short loc_180009746
0x18000973b  mov     ecx, 8007000Eh; int
0x180009740  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009746  mov     [rbx], rax
0x180009749  add     rsp, 20h
0x18000974d  pop     rbx
0x18000974e  retn
```
