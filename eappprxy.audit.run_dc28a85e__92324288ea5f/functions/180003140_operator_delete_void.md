# operator delete(void *)

- ea: `0x180003140`
- end: `0x180003190`
- name: `??3@YAXPEAX@Z`
- size: `80`
- prototype: `void __fastcall(LPCVOID lpMem)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800017a4`
- `0x1800017b0`

## callees

- `0x180003140`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000315a`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000315a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003184`

## pseudocode

```c
void __fastcall operator delete(void *lpMem)
{
  int v2; // eax

  if ( lpMem )
    v2 = HeapSize(HeapAllocator::heap, 0, lpMem);
  else
    v2 = 0;
  _InterlockedAdd(&dword_180015488, -v2);
  HeapFree(HeapAllocator::heap, 0, lpMem);
}

```

## disassembly

```asm
0x180003140  push    rbx
0x180003142  sub     rsp, 20h
0x180003146  mov     rbx, rcx
0x180003149  test    rcx, rcx
0x18000314c  jz      short loc_180003168
0x18000314e  mov     r8, rcx; lpMem
0x180003151  xor     edx, edx; dwFlags
0x180003153  mov     rcx, cs:?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; hHeap
0x18000315a  call    cs:__imp_HeapSize
0x180003161  nop     dword ptr [rax+rax+00h]
0x180003166  jmp     short loc_18000316A
0x180003168  xor     eax, eax
0x18000316a  neg     eax
0x18000316c  lock add cs:dword_180015488, eax
0x180003173  mov     rcx, cs:?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; StaticObject<Heap> HeapAllocator::heap
0x18000317a  mov     r8, rbx
0x18000317d  xor     edx, edx
0x18000317f  add     rsp, 20h
0x180003183  pop     rbx
0x180003184  jmp     cs:__imp_HeapFree
```
