# operator delete(void *)

- ea: `0x1400039bc`
- end: `0x1400039f0`
- name: `??3@YAXPEAX@Z`
- size: `52`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400038cc`
- `0x140004240`
- `0x140005e98`
- `0x140007bcc`
- `0x140007e20`
- `0x140007ed0`
- `0x140008230`
- `0x14000bfe0`

## callees

- `0x1400039bc`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1400039c9`
- `KERNEL32!GetProcessHeap` at `0x1400039c9`
- `KERNEL32!HeapFree` at `0x1400039dd`
- `KERNEL32!HeapFree` at `0x1400039dd`

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
0x1400039bc  test    rcx, rcx
0x1400039bf  jz      short locret_1400039EE
0x1400039c1  push    rbx
0x1400039c2  sub     rsp, 20h
0x1400039c6  mov     rbx, rcx
0x1400039c9  call    cs:__imp_GetProcessHeap
0x1400039d0  nop     dword ptr [rax+rax+00h]
0x1400039d5  mov     r8, rbx; lpMem
0x1400039d8  xor     edx, edx; dwFlags
0x1400039da  mov     rcx, rax; hHeap
0x1400039dd  call    cs:__imp_HeapFree
0x1400039e4  nop     dword ptr [rax+rax+00h]
0x1400039e9  add     rsp, 20h
0x1400039ed  pop     rbx
0x1400039ee  retn
```
