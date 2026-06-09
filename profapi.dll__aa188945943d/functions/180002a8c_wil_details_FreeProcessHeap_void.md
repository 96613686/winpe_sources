# wil::details::FreeProcessHeap(void *)

- ea: `0x180002a8c`
- end: `0x180002aaf`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x180002650`
- `0x18000bf10`
- `0x18000c288`
- `0x18000c964`
- `0x18000ca24`
- `0x18000ccc4`
- `0x18000d410`
- `0x18000da48`
- `0x18000ee5c`
- `0x18000f1f0`
- `0x18000f508`
- `0x18000f5ac`
- `0x180012844`
- `0x18001286c`
- `0x180014d54`
- `0x180015150`
- `0x1800166c4`
- `0x180016d14`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002aa8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a95`

## pseudocode

```c
void __fastcall wil::details::FreeProcessHeap(wil::details *this, void *a2)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, this);
}

```

## disassembly

```asm
0x180002a8c  push    rbx
0x180002a8e  sub     rsp, 20h
0x180002a92  mov     rbx, rcx
0x180002a95  call    cs:__imp_GetProcessHeap
0x180002a9b  mov     r8, rbx
0x180002a9e  xor     edx, edx
0x180002aa0  mov     rcx, rax
0x180002aa3  add     rsp, 20h
0x180002aa7  pop     rbx
0x180002aa8  jmp     cs:__imp_HeapFree
```
