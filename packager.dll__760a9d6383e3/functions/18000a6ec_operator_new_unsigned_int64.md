# operator new(unsigned __int64)

- ea: `0x18000a6ec`
- end: `0x18000a712`
- name: `??2@YAPEAX_K@Z`
- size: `38`
- prototype: `LPVOID __fastcall(SIZE_T)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180001674`
- `0x180005470`
- `0x180005e30`
- `0x180006f48`
- `0x1800073b8`
- `0x1800074e0`
- `0x1800079ac`
- `0x180007b28`
- `0x180007cf8`
- `0x1800098ac`
- `0x180009bc8`
- `0x180009dd8`
- `0x18000a760`
- `0x18000a930`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a6f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a6f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a70b`

## pseudocode

```c
LPVOID __fastcall operator new(SIZE_T a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 8u, a1);
}

```

## disassembly

```asm
0x18000a6ec  push    rbx
0x18000a6ee  sub     rsp, 20h
0x18000a6f2  mov     rbx, rcx
0x18000a6f5  call    cs:__imp_GetProcessHeap
0x18000a6fb  mov     r8, rbx
0x18000a6fe  mov     edx, 8
0x18000a703  mov     rcx, rax
0x18000a706  add     rsp, 20h
0x18000a70a  pop     rbx
0x18000a70b  jmp     cs:__imp_HeapAlloc
```
