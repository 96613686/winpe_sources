# operator delete(void *)

- ea: `0x18000ab70`
- end: `0x18000abb5`
- name: `??3@YAXPEAX@Z`
- size: `69`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `27`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002330`
- `0x180002340`
- `0x18000a914`
- `0x18000a978`
- `0x18000c880`
- `0x18000cbec`
- `0x18000cc0c`
- `0x18000cc1c`
- `0x18000ccd8`
- `0x18000cee8`
- `0x18000cf50`
- `0x18000d0f8`
- `0x18000d3b8`
- `0x18000de8c`
- `0x18000dfb0`
- `0x18000e4c4`
- `0x18000e530`
- `0x18000eafc`
- `0x18000ecfc`
- `0x18000ee60`
- `0x18000f77c`
- `0x180011524`
- `0x18001159c`
- `0x180011698`
- `0x180011cb0`
- `0x1800122b8`
- `0x180012cf8`

## callees

- `0x18000ab70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000abae`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000ab8a`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000ab8a`

## pseudocode

```c
void __fastcall operator delete(void *lpMem)
{
  int v2; // eax

  if ( lpMem )
    v2 = HeapSize(HeapAllocator::heap, 0, lpMem);
  else
    v2 = 0;
  _InterlockedAdd(&dword_180020B58, -v2);
  HeapFree(HeapAllocator::heap, 0, lpMem);
}

```

## disassembly

```asm
0x18000ab70  push    rbx
0x18000ab72  sub     rsp, 20h
0x18000ab76  mov     rbx, rcx
0x18000ab79  test    rcx, rcx
0x18000ab7c  jz      short loc_18000AB92
0x18000ab7e  mov     r8, rcx; lpMem
0x18000ab81  xor     edx, edx; dwFlags
0x18000ab83  mov     rcx, cs:?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; hHeap
0x18000ab8a  call    cs:__imp_HeapSize
0x18000ab90  jmp     short loc_18000AB94
0x18000ab92  xor     eax, eax
0x18000ab94  neg     eax
0x18000ab96  lock add cs:dword_180020B58, eax
0x18000ab9d  mov     rcx, cs:?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; StaticObject<Heap> HeapAllocator::heap
0x18000aba4  mov     r8, rbx
0x18000aba7  xor     edx, edx
0x18000aba9  add     rsp, 20h
0x18000abad  pop     rbx
0x18000abae  jmp     cs:__imp_HeapFree
```
