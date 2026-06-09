# wistd::unique_ptr<ushort,wil::process_heap_deleter>::~unique_ptr<ushort,wil::process_heap_deleter>(void)

- ea: `0x14000da18`
- end: `0x14000da54`
- name: `??1?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140015c5b`
- `0x140015ca3`

## callees

- `0x14000da18`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000da2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000da2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000da41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000da41`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned short,wil::process_heap_deleter>::~unique_ptr<unsigned short,wil::process_heap_deleter>(
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
0x14000da18  push    rbx
0x14000da1a  sub     rsp, 20h
0x14000da1e  mov     rbx, [rcx]
0x14000da21  mov     qword ptr [rcx], 0
0x14000da28  test    rbx, rbx
0x14000da2b  jz      short loc_14000DA4D
0x14000da2d  call    cs:__imp_GetProcessHeap
0x14000da34  nop     dword ptr [rax+rax+00h]
0x14000da39  mov     r8, rbx; lpMem
0x14000da3c  xor     edx, edx; dwFlags
0x14000da3e  mov     rcx, rax; hHeap
0x14000da41  call    cs:__imp_HeapFree
0x14000da48  nop     dword ptr [rax+rax+00h]
0x14000da4d  add     rsp, 20h
0x14000da51  pop     rbx
0x14000da52  retn
```
