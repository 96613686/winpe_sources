# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180009484`
- end: `0x1800094af`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008efc`
- `0x18000b1f4`

## callees

- `0x180009484`
- `0x180009e80`

## import_xrefs

- `msvcrt!malloc` at `0x180009490`
- `msvcrt!malloc` at `0x180009490`

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
0x180009484  push    rbx
0x180009486  sub     rsp, 20h
0x18000948a  mov     rbx, rcx
0x18000948d  mov     rcx, rdx; Size
0x180009490  call    cs:__imp_malloc
0x180009496  test    rax, rax
0x180009499  jnz     short loc_1800094A6
0x18000949b  mov     ecx, 8007000Eh; int
0x1800094a0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800094a6  mov     [rbx], rax
0x1800094a9  add     rsp, 20h
0x1800094ad  pop     rbx
0x1800094ae  retn
```
