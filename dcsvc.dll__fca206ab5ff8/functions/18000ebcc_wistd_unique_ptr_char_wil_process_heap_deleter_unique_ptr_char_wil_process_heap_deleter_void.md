# wistd::unique_ptr<char,wil::process_heap_deleter>::~unique_ptr<char,wil::process_heap_deleter>(void)

- ea: `0x18000ebcc`
- end: `0x18000ebfb`
- name: `??1?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011e35`

## callees

- `0x18000ebcc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ebe1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ebe1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ebef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ebef`

## pseudocode

```c
void __fastcall wistd::unique_ptr<char,wil::process_heap_deleter>::~unique_ptr<char,wil::process_heap_deleter>(
        void **a1)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
}

```

## disassembly

```asm
0x18000ebcc  push    rbx
0x18000ebce  sub     rsp, 20h
0x18000ebd2  mov     rbx, [rcx]
0x18000ebd5  mov     qword ptr [rcx], 0
0x18000ebdc  test    rbx, rbx
0x18000ebdf  jz      short loc_18000EBF5
0x18000ebe1  call    cs:__imp_GetProcessHeap
0x18000ebe7  mov     r8, rbx; lpMem
0x18000ebea  xor     edx, edx; dwFlags
0x18000ebec  mov     rcx, rax; hHeap
0x18000ebef  call    cs:__imp_HeapFree
0x18000ebf5  add     rsp, 20h
0x18000ebf9  pop     rbx
0x18000ebfa  retn
```
