# CompressInternalFree

- ea: `0x180013120`
- end: `0x180013143`
- name: `CompressInternalFree`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013129`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013129`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001313c`

## pseudocode

```c
BOOL __fastcall CompressInternalFree(__int64 a1, void *a2)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapFree(ProcessHeap, 0, a2);
}

```

## disassembly

```asm
0x180013120  push    rbx
0x180013122  sub     rsp, 20h
0x180013126  mov     rbx, rdx
0x180013129  call    cs:__imp_GetProcessHeap
0x18001312f  mov     r8, rbx
0x180013132  xor     edx, edx
0x180013134  mov     rcx, rax
0x180013137  add     rsp, 20h
0x18001313b  pop     rbx
0x18001313c  jmp     cs:__imp_HeapFree
```
