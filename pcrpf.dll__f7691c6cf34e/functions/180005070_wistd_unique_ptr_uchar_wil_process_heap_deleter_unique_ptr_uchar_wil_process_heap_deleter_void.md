# wistd::unique_ptr<uchar,wil::process_heap_deleter>::~unique_ptr<uchar,wil::process_heap_deleter>(void)

- ea: `0x180005070`
- end: `0x1800050ac`
- name: `??1?$unique_ptr@EUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(void **)`
- caller_count: `25`
- callee_count: `1`
- tags: ``

## callers

- `0x1800107e8`
- `0x180047b20`
- `0x18005762c`
- `0x180057787`
- `0x1800577bd`
- `0x1800577e1`
- `0x180057805`
- `0x180057817`
- `0x1800578e9`
- `0x180057923`
- `0x18005794f`
- `0x180057a65`
- `0x180057a89`
- `0x180057be5`
- `0x180057c3f`
- `0x180057c75`
- `0x180057d56`
- `0x180057d9e`
- `0x180058408`
- `0x180058462`
- `0x180058687`
- `0x1800586ab`
- `0x180058720`
- `0x180058744`
- `0x18005897b`

## callees

- `0x180005070`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005085`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005085`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005099`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005099`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned char,wil::process_heap_deleter>::~unique_ptr<unsigned char,wil::process_heap_deleter>(
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
0x180005070  push    rbx
0x180005072  sub     rsp, 20h
0x180005076  mov     rbx, [rcx]
0x180005079  mov     qword ptr [rcx], 0
0x180005080  test    rbx, rbx
0x180005083  jz      short loc_1800050A5
0x180005085  call    cs:__imp_GetProcessHeap
0x18000508c  nop     dword ptr [rax+rax+00h]
0x180005091  mov     r8, rbx; lpMem
0x180005094  xor     edx, edx; dwFlags
0x180005096  mov     rcx, rax; hHeap
0x180005099  call    cs:__imp_HeapFree
0x1800050a0  nop     dword ptr [rax+rax+00h]
0x1800050a5  add     rsp, 20h
0x1800050a9  pop     rbx
0x1800050aa  retn
```
