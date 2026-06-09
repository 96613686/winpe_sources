# MIDL_user_free

- ea: `0x1800036e0`
- end: `0x18000370e`
- name: `MIDL_user_free`
- size: `46`
- prototype: `void __stdcall(void *)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180006460`
- `0x1800069d0`
- `0x180006f40`
- `0x1800070d0`
- `0x1800072b0`
- `0x18000c530`
- `0x18000c7c0`
- `0x18000c930`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003702`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036e9`

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
0x1800036e0  push    rbx
0x1800036e2  sub     rsp, 20h
0x1800036e6  mov     rbx, rcx
0x1800036e9  call    cs:__imp_GetProcessHeap
0x1800036f0  nop     dword ptr [rax+rax+00h]
0x1800036f5  mov     r8, rbx
0x1800036f8  xor     edx, edx
0x1800036fa  mov     rcx, rax
0x1800036fd  add     rsp, 20h
0x180003701  pop     rbx
0x180003702  jmp     cs:__imp_HeapFree
```
