# operator delete(void *)

- ea: `0x180001b58`
- end: `0x180001b7c`
- name: `??3@YAXPEAX@Z`
- size: `36`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180012b30`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180001b6f`
- `KERNEL32!HeapFree` at `0x180001b6f`
- `KERNEL32!GetProcessHeap` at `0x180001b61`
- `KERNEL32!GetProcessHeap` at `0x180001b61`

## pseudocode

```c
void __fastcall operator delete(void *lpMem)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, lpMem);
}

```

## disassembly

```asm
0x180001b58  push    rbx
0x180001b5a  sub     rsp, 20h
0x180001b5e  mov     rbx, rcx
0x180001b61  call    cs:__imp_GetProcessHeap
0x180001b67  mov     rcx, rax; hHeap
0x180001b6a  mov     r8, rbx; lpMem
0x180001b6d  xor     edx, edx; dwFlags
0x180001b6f  call    cs:__imp_HeapFree
0x180001b75  nop
0x180001b76  add     rsp, 20h
0x180001b7a  pop     rbx
0x180001b7b  retn
```
