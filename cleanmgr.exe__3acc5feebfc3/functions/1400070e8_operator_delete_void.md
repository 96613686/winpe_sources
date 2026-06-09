# operator delete(void *)

- ea: `0x1400070e8`
- end: `0x14000710f`
- name: `??3@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400029c4`
- `0x1400029d0`

## callees

- `0x1400070e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400070f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400070f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007103`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007103`

## pseudocode

```c
void __fastcall operator delete(void *lpMem)
{
  HANDLE ProcessHeap; // rax

  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x1400070e8  test    rcx, rcx
0x1400070eb  jz      short locret_14000710E
0x1400070ed  push    rbx
0x1400070ee  sub     rsp, 20h
0x1400070f2  mov     rbx, rcx
0x1400070f5  call    cs:__imp_GetProcessHeap
0x1400070fb  mov     r8, rbx; lpMem
0x1400070fe  xor     edx, edx; dwFlags
0x140007100  mov     rcx, rax; hHeap
0x140007103  call    cs:__imp_HeapFree
0x140007109  add     rsp, 20h
0x14000710d  pop     rbx
0x14000710e  retn
```
