# DefaultHeap::Free(void *)

- ea: `0x18000a8cc`
- end: `0x18000a8f3`
- name: `?Free@DefaultHeap@@SAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800058a0`
- `0x180006070`
- `0x180007a80`
- `0x1800083a0`
- `0x180008da0`
- `0x180009fd0`
- `0x18000a868`

## callees

- `0x18000a8cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a8d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a8d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a8e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a8e7`

## pseudocode

```c
void __fastcall DefaultHeap::Free(void *lpMem)
{
  HANDLE ProcessHeap; // rax

  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x18000a8cc  test    rcx, rcx
0x18000a8cf  jz      short locret_18000A8F2
0x18000a8d1  push    rbx
0x18000a8d2  sub     rsp, 20h
0x18000a8d6  mov     rbx, rcx
0x18000a8d9  call    cs:__imp_GetProcessHeap
0x18000a8df  mov     r8, rbx; lpMem
0x18000a8e2  xor     edx, edx; dwFlags
0x18000a8e4  mov     rcx, rax; hHeap
0x18000a8e7  call    cs:__imp_HeapFree
0x18000a8ed  add     rsp, 20h
0x18000a8f1  pop     rbx
0x18000a8f2  retn
```
