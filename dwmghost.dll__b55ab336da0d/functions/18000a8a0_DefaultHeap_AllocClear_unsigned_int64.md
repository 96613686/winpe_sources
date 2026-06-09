# DefaultHeap::AllocClear(unsigned __int64)

- ea: `0x18000a8a0`
- end: `0x18000a8c6`
- name: `?AllocClear@DefaultHeap@@SAPEAX_K@Z`
- size: `38`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180007c2c`
- `0x180007d0c`
- `0x180007e64`
- `0x180008140`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a8a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a8a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a8bf`

## pseudocode

```c
LPVOID __fastcall DefaultHeap::AllocClear(SIZE_T a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 8u, a1);
}

```

## disassembly

```asm
0x18000a8a0  push    rbx
0x18000a8a2  sub     rsp, 20h
0x18000a8a6  mov     rbx, rcx
0x18000a8a9  call    cs:__imp_GetProcessHeap
0x18000a8af  mov     r8, rbx
0x18000a8b2  mov     edx, 8
0x18000a8b7  mov     rcx, rax
0x18000a8ba  add     rsp, 20h
0x18000a8be  pop     rbx
0x18000a8bf  jmp     cs:__imp_HeapAlloc
```
