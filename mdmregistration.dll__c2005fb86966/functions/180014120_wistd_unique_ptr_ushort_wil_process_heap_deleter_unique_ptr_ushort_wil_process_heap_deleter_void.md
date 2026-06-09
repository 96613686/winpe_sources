# wistd::unique_ptr<ushort,wil::process_heap_deleter>::~unique_ptr<ushort,wil::process_heap_deleter>(void)

- ea: `0x180014120`
- end: `0x18001415c`
- name: `??1?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `60`
- prototype: ``
- caller_count: `25`
- callee_count: `1`
- tags: ``

## callers

- `0x180022e74`
- `0x18004c089`
- `0x18004c0e3`
- `0x18004c107`
- `0x18004c119`
- `0x18004c173`
- `0x18004c185`
- `0x18004c1f6`
- `0x18004c286`
- `0x18004c2bc`
- `0x18004c666`
- `0x18004c678`
- `0x18004c6d2`
- `0x18004c7f2`
- `0x18004c882`
- `0x18004c990`
- `0x18004c9c6`
- `0x18004cac2`
- `0x18004cad4`
- `0x18004cae6`
- `0x18004caf8`
- `0x18004cb0a`
- `0x18004cb1c`
- `0x18004cb2e`
- `0x18004cd38`

## callees

- `0x180014120`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014149`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014149`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014135`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014135`

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
0x180014120  push    rbx
0x180014122  sub     rsp, 20h
0x180014126  mov     rbx, [rcx]
0x180014129  mov     qword ptr [rcx], 0
0x180014130  test    rbx, rbx
0x180014133  jz      short loc_180014155
0x180014135  call    cs:__imp_GetProcessHeap
0x18001413c  nop     dword ptr [rax+rax+00h]
0x180014141  mov     r8, rbx; lpMem
0x180014144  xor     edx, edx; dwFlags
0x180014146  mov     rcx, rax; hHeap
0x180014149  call    cs:__imp_HeapFree
0x180014150  nop     dword ptr [rax+rax+00h]
0x180014155  add     rsp, 20h
0x180014159  pop     rbx
0x18001415a  retn
```
