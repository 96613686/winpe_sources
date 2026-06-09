# operator delete(void *)

- ea: `0x180011e2c`
- end: `0x180011e53`
- name: `??3@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002644`

## callees

- `0x180011e2c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011e47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011e47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011e39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011e39`

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
0x180011e2c  test    rcx, rcx
0x180011e2f  jz      short locret_180011E52
0x180011e31  push    rbx
0x180011e32  sub     rsp, 20h
0x180011e36  mov     rbx, rcx
0x180011e39  call    cs:__imp_GetProcessHeap
0x180011e3f  mov     r8, rbx; lpMem
0x180011e42  xor     edx, edx; dwFlags
0x180011e44  mov     rcx, rax; hHeap
0x180011e47  call    cs:__imp_HeapFree
0x180011e4d  add     rsp, 20h
0x180011e51  pop     rbx
0x180011e52  retn
```
