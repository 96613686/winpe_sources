# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180003688`
- end: `0x1800036b3`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030ac`
- `0x180004a88`

## callees

- `0x180003688`
- `0x180004048`

## import_xrefs

- `msvcrt!malloc` at `0x180003694`
- `msvcrt!malloc` at `0x180003694`

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
0x180003688  push    rbx
0x18000368a  sub     rsp, 20h
0x18000368e  mov     rbx, rcx
0x180003691  mov     rcx, rdx; Size
0x180003694  call    cs:__imp_malloc
0x18000369a  test    rax, rax
0x18000369d  jz      short loc_1800036A8
0x18000369f  mov     [rbx], rax
0x1800036a2  add     rsp, 20h
0x1800036a6  pop     rbx
0x1800036a7  retn
0x1800036a8  mov     ecx, 8007000Eh; int
0x1800036ad  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
