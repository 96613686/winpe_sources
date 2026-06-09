# MIDL_user_free

- ea: `0x180003540`
- end: `0x180003563`
- name: `MIDL_user_free`
- size: `35`
- prototype: `void __stdcall(void *)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180005ef0`
- `0x1800063c0`
- `0x1800068a0`
- `0x180006a00`
- `0x180006bb0`
- `0x18000b880`
- `0x18000bad0`
- `0x18000bc20`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000355c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003549`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003549`

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
0x180003540  push    rbx
0x180003542  sub     rsp, 20h
0x180003546  mov     rbx, rcx
0x180003549  call    cs:__imp_GetProcessHeap
0x18000354f  mov     r8, rbx
0x180003552  xor     edx, edx
0x180003554  mov     rcx, rax
0x180003557  add     rsp, 20h
0x18000355b  pop     rbx
0x18000355c  jmp     cs:__imp_HeapFree
```
