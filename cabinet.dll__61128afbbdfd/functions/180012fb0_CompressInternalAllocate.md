# CompressInternalAllocate

- ea: `0x180012fb0`
- end: `0x180012fd3`
- name: `CompressInternalAllocate`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012fb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012fb9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012fcc`

## pseudocode

```c
LPVOID __fastcall CompressInternalAllocate(__int64 a1, SIZE_T a2)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 0, a2);
}

```

## disassembly

```asm
0x180012fb0  push    rbx
0x180012fb2  sub     rsp, 20h
0x180012fb6  mov     rbx, rdx
0x180012fb9  call    cs:__imp_GetProcessHeap
0x180012fbf  mov     r8, rbx
0x180012fc2  xor     edx, edx
0x180012fc4  mov     rcx, rax
0x180012fc7  add     rsp, 20h
0x180012fcb  pop     rbx
0x180012fcc  jmp     cs:__imp_HeapAlloc
```
