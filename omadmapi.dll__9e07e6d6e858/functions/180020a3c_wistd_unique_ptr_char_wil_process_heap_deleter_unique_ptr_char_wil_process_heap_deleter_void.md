# wistd::unique_ptr<char,wil::process_heap_deleter>::~unique_ptr<char,wil::process_heap_deleter>(void)

- ea: `0x180020a3c`
- end: `0x180020a78`
- name: `??1?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180023408`

## callees

- `0x180020a3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020a65`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020a65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020a51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020a51`

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
0x180020a3c  push    rbx
0x180020a3e  sub     rsp, 20h
0x180020a42  mov     rbx, [rcx]
0x180020a45  mov     qword ptr [rcx], 0
0x180020a4c  test    rbx, rbx
0x180020a4f  jz      short loc_180020A71
0x180020a51  call    cs:__imp_GetProcessHeap
0x180020a58  nop     dword ptr [rax+rax+00h]
0x180020a5d  mov     r8, rbx; lpMem
0x180020a60  xor     edx, edx; dwFlags
0x180020a62  mov     rcx, rax; hHeap
0x180020a65  call    cs:__imp_HeapFree
0x180020a6c  nop     dword ptr [rax+rax+00h]
0x180020a71  add     rsp, 20h
0x180020a75  pop     rbx
0x180020a76  retn
```
