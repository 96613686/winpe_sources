# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x18000c57c`
- end: `0x18000c5a7`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c0c8`
- `0x18000d5d0`

## callees

- `0x18000c57c`
- `0x18000c814`

## import_xrefs

- `msvcrt!malloc` at `0x18000c588`
- `msvcrt!malloc` at `0x18000c588`

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
0x18000c57c  push    rbx
0x18000c57e  sub     rsp, 20h
0x18000c582  mov     rbx, rcx
0x18000c585  mov     rcx, rdx; Size
0x18000c588  call    cs:__imp_malloc
0x18000c58e  test    rax, rax
0x18000c591  jnz     short loc_18000C59E
0x18000c593  mov     ecx, 8007000Eh; int
0x18000c598  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000c59e  mov     [rbx], rax
0x18000c5a1  add     rsp, 20h
0x18000c5a5  pop     rbx
0x18000c5a6  retn
```
