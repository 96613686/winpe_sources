# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180003118`
- end: `0x180003143`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002b3c`
- `0x1800042a8`

## callees

- `0x180003118`
- `0x18000374c`

## import_xrefs

- `msvcrt!malloc` at `0x180003124`
- `msvcrt!malloc` at `0x180003124`

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
0x180003118  push    rbx
0x18000311a  sub     rsp, 20h
0x18000311e  mov     rbx, rcx
0x180003121  mov     rcx, rdx; Size
0x180003124  call    cs:__imp_malloc
0x18000312a  test    rax, rax
0x18000312d  jz      short loc_180003138
0x18000312f  mov     [rbx], rax
0x180003132  add     rsp, 20h
0x180003136  pop     rbx
0x180003137  retn
0x180003138  mov     ecx, 8007000Eh; int
0x18000313d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
