# MIDL_user_allocate

- ea: `0x180003510`
- end: `0x180003536`
- name: `MIDL_user_allocate`
- size: `38`
- prototype: `void *__stdcall(size_t size)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800063c0`
- `0x1800068a0`
- `0x180006a00`
- `0x180006bb0`
- `0x18000b880`
- `0x18000bad0`
- `0x18000bc20`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000352f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003519`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003519`

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
0x180003510  push    rbx
0x180003512  sub     rsp, 20h
0x180003516  mov     rbx, rcx
0x180003519  call    cs:__imp_GetProcessHeap
0x18000351f  mov     r8, rbx
0x180003522  mov     edx, 8
0x180003527  mov     rcx, rax
0x18000352a  add     rsp, 20h
0x18000352e  pop     rbx
0x18000352f  jmp     cs:__imp_HeapAlloc
```
