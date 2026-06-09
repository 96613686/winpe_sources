# MIDL_user_allocate

- ea: `0x1800036a0`
- end: `0x1800036d1`
- name: `MIDL_user_allocate`
- size: `49`
- prototype: `void *__stdcall(size_t size)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800069d0`
- `0x180006f40`
- `0x1800070d0`
- `0x1800072b0`
- `0x18000c530`
- `0x18000c7c0`
- `0x18000c930`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800036c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036a9`

## pseudocode

```c
void *__stdcall MIDL_user_allocate(size_t size)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 8u, size);
}

```

## disassembly

```asm
0x1800036a0  push    rbx
0x1800036a2  sub     rsp, 20h
0x1800036a6  mov     rbx, rcx
0x1800036a9  call    cs:__imp_GetProcessHeap
0x1800036b0  nop     dword ptr [rax+rax+00h]
0x1800036b5  mov     r8, rbx
0x1800036b8  mov     edx, 8
0x1800036bd  mov     rcx, rax
0x1800036c0  add     rsp, 20h
0x1800036c4  pop     rbx
0x1800036c5  jmp     cs:__imp_HeapAlloc
```
