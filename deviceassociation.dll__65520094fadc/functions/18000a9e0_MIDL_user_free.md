# MIDL_user_free

- ea: `0x18000a9e0`
- end: `0x18000aa03`
- name: `MIDL_user_free`
- size: `35`
- prototype: `void __stdcall(void *)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002284`
- `0x180002a54`
- `0x180002dd0`
- `0x18000aa10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a9e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a9e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a9fc`

## pseudocode

```c
void __stdcall MIDL_user_free(void *a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x18000a9e0  push    rbx
0x18000a9e2  sub     rsp, 20h
0x18000a9e6  mov     rbx, rcx
0x18000a9e9  call    cs:__imp_GetProcessHeap
0x18000a9ef  mov     r8, rbx
0x18000a9f2  xor     edx, edx
0x18000a9f4  mov     rcx, rax
0x18000a9f7  add     rsp, 20h
0x18000a9fb  pop     rbx
0x18000a9fc  jmp     cs:__imp_HeapFree
```
