# operator delete(void *)

- ea: `0x18000a718`
- end: `0x18000a73f`
- name: `??3@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `17`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004f10`
- `0x180004f40`
- `0x180005470`
- `0x180005b40`
- `0x180005e30`
- `0x180005f5c`
- `0x180006f48`
- `0x18000710c`
- `0x1800074e0`
- `0x180007cf8`
- `0x1800092d0`
- `0x1800098ac`
- `0x180009bc8`
- `0x180009dd8`
- `0x18000a300`
- `0x18000a760`
- `0x18000a8d0`

## callees

- `0x18000a718`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a733`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a733`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a725`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a725`

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
0x18000a718  test    rcx, rcx
0x18000a71b  jz      short locret_18000A73E
0x18000a71d  push    rbx
0x18000a71e  sub     rsp, 20h
0x18000a722  mov     rbx, rcx
0x18000a725  call    cs:__imp_GetProcessHeap
0x18000a72b  mov     r8, rbx; lpMem
0x18000a72e  xor     edx, edx; dwFlags
0x18000a730  mov     rcx, rax; hHeap
0x18000a733  call    cs:__imp_HeapFree
0x18000a739  add     rsp, 20h
0x18000a73d  pop     rbx
0x18000a73e  retn
```
