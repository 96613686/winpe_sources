# KpsFreeMem(void *)

- ea: `0x18003012c`
- end: `0x180030160`
- name: `?KpsFreeMem@@YAXPEAX@Z`
- size: `52`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x1800195d8`
- `0x180019a20`
- `0x18001a0c0`
- `0x18001a1e0`
- `0x1800203ac`
- `0x180027af8`
- `0x1800289f8`
- `0x180028e78`
- `0x180029038`
- `0x18002a42c`
- `0x18002a5a8`
- `0x18002aae8`
- `0x18002b24c`
- `0x18002dc4c`
- `0x18002dd00`
- `0x18002e1f0`
- `0x18002ed24`
- `0x18002f194`

## callees

- `0x18003012c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030139`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030139`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003014d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003014d`

## pseudocode

```c
void __fastcall KpsFreeMem(void *lpMem)
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
0x18003012c  test    rcx, rcx
0x18003012f  jz      short locret_18003015E
0x180030131  push    rbx
0x180030132  sub     rsp, 20h
0x180030136  mov     rbx, rcx
0x180030139  call    cs:__imp_GetProcessHeap
0x180030140  nop     dword ptr [rax+rax+00h]
0x180030145  mov     r8, rbx; lpMem
0x180030148  xor     edx, edx; dwFlags
0x18003014a  mov     rcx, rax; hHeap
0x18003014d  call    cs:__imp_HeapFree
0x180030154  nop     dword ptr [rax+rax+00h]
0x180030159  add     rsp, 20h
0x18003015d  pop     rbx
0x18003015e  retn
```
