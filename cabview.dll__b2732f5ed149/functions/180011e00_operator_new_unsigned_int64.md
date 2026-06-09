# operator new(unsigned __int64)

- ea: `0x180011e00`
- end: `0x180011e26`
- name: `??2@YAPEAX_K@Z`
- size: `38`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180004a70`
- `0x180004e50`
- `0x18000b074`
- `0x18000b2e0`
- `0x18000ba40`
- `0x18000d478`
- `0x18000dfa0`
- `0x18000e910`
- `0x180010440`
- `0x180011e5c`
- `0x180012150`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011e1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011e09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011e09`

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
0x180011e00  push    rbx
0x180011e02  sub     rsp, 20h
0x180011e06  mov     rbx, rcx
0x180011e09  call    cs:__imp_GetProcessHeap
0x180011e0f  mov     r8, rbx
0x180011e12  mov     edx, 8
0x180011e17  mov     rcx, rax
0x180011e1a  add     rsp, 20h
0x180011e1e  pop     rbx
0x180011e1f  jmp     cs:__imp_HeapAlloc
```
