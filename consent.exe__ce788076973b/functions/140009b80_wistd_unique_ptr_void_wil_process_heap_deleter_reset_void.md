# wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)

- ea: `0x140009b80`
- end: `0x140009bad`
- name: `?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z`
- size: `45`
- prototype: `void __fastcall(void **, void *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140008c20`
- `0x14000e088`
- `0x14000ec00`
- `0x14000fa30`
- `0x140012700`
- `0x140013f54`
- `0x140016968`
- `0x140016e24`
- `0x140017bc8`

## callees

- `0x140009b80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009b97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009b97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009ba5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009ba5`

## pseudocode

```c
void __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void **a1, void *a2)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
}

```

## disassembly

```asm
0x140009b80  push    rbx
0x140009b82  sub     rsp, 20h
0x140009b86  mov     rbx, [rcx]
0x140009b89  mov     [rcx], rdx
0x140009b8c  test    rbx, rbx
0x140009b8f  jnz     short loc_140009B97
0x140009b91  add     rsp, 20h
0x140009b95  pop     rbx
0x140009b96  retn
0x140009b97  call    cs:__imp_GetProcessHeap
0x140009b9d  mov     r8, rbx; lpMem
0x140009ba0  xor     edx, edx; dwFlags
0x140009ba2  mov     rcx, rax; hHeap
0x140009ba5  call    cs:__imp_HeapFree
0x140009bab  jmp     short loc_140009B91
```
