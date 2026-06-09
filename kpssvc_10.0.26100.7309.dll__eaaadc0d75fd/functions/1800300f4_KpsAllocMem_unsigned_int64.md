# KpsAllocMem(unsigned __int64)

- ea: `0x1800300f4`
- end: `0x180030125`
- name: `?KpsAllocMem@@YAPEAX_K@Z`
- size: `49`
- prototype: `LPVOID __fastcall(SIZE_T)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x1800195d8`
- `0x18001a0c0`
- `0x18001aa80`
- `0x18001e520`
- `0x18001e8e8`
- `0x18001eb40`
- `0x18001edec`
- `0x180020038`
- `0x180027530`
- `0x1800276c8`
- `0x1800289f8`
- `0x18002a5a8`
- `0x18002b24c`
- `0x18002dd00`
- `0x18002e1f0`
- `0x18002e330`
- `0x18002e7f8`
- `0x18002ed24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030119`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800300fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800300fd`

## pseudocode

```c
LPVOID __fastcall KpsAllocMem(SIZE_T a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 8u, a1);
}

```

## disassembly

```asm
0x1800300f4  push    rbx
0x1800300f6  sub     rsp, 20h
0x1800300fa  mov     rbx, rcx
0x1800300fd  call    cs:__imp_GetProcessHeap
0x180030104  nop     dword ptr [rax+rax+00h]
0x180030109  mov     r8, rbx
0x18003010c  mov     edx, 8
0x180030111  mov     rcx, rax
0x180030114  add     rsp, 20h
0x180030118  pop     rbx
0x180030119  jmp     cs:__imp_HeapAlloc
```
