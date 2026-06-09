# operator delete(void *)

- ea: `0x180004038`
- end: `0x18000405f`
- name: `??3@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002294`
- `0x180002680`
- `0x180016e7c`
- `0x18001b9a0`
- `0x18001c600`
- `0x18001c6c0`
- `0x18001c700`
- `0x18001cf70`
- `0x18001d760`
- `0x18001d7a0`

## callees

- `0x180004038`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004053`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004053`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004045`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004045`

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
0x180004038  test    rcx, rcx
0x18000403b  jz      short locret_18000405E
0x18000403d  push    rbx
0x18000403e  sub     rsp, 20h
0x180004042  mov     rbx, rcx
0x180004045  call    cs:__imp_GetProcessHeap
0x18000404b  mov     r8, rbx; lpMem
0x18000404e  xor     edx, edx; dwFlags
0x180004050  mov     rcx, rax; hHeap
0x180004053  call    cs:__imp_HeapFree
0x180004059  add     rsp, 20h
0x18000405d  pop     rbx
0x18000405e  retn
```
