# CfpOplockCompletionKeyTableAllocate

- ea: `0x180004940`
- end: `0x18000496d`
- name: `CfpOplockCompletionKeyTableAllocate`
- size: `45`
- prototype: `RTL_AVL_ALLOCATE_ROUTINE`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004948`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004948`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004961`

## pseudocode

```c
PVOID __fastcall CfpOplockCompletionKeyTableAllocate(struct _RTL_AVL_TABLE *Table, CLONG ByteSize)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 0, ByteSize);
}

```

## disassembly

```asm
0x180004940  push    rbx
0x180004942  sub     rsp, 20h
0x180004946  mov     ebx, edx
0x180004948  call    cs:__imp_GetProcessHeap
0x18000494f  nop     dword ptr [rax+rax+00h]
0x180004954  mov     r8d, ebx
0x180004957  xor     edx, edx
0x180004959  mov     rcx, rax
0x18000495c  add     rsp, 20h
0x180004960  pop     rbx
0x180004961  jmp     cs:__imp_HeapAlloc
```
