# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180004be4`
- end: `0x180004c71`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004894`
- `0x1800088e0`
- `0x180009394`

## callees

- `0x180004be4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004c16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004c3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004c60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004c16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004c3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004c60`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexes::~UsageIndexes(wil::details_abi::UsageIndexes *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax

  v1 = (void *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = 0;
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
  v4 = (void *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
  v6 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
}

```

## disassembly

```asm
0x180004be4  mov     [rsp+arg_0], rbx
0x180004be9  push    rdi
0x180004bea  sub     rsp, 20h
0x180004bee  mov     rdi, [rcx+0B0h]
0x180004bf5  mov     rbx, rcx
0x180004bf8  mov     qword ptr [rcx+0B0h], 0
0x180004c03  test    rdi, rdi
0x180004c06  jz      short loc_180004C1C
0x180004c08  call    cs:__imp_GetProcessHeap
0x180004c0e  mov     r8, rdi; lpMem
0x180004c11  xor     edx, edx; dwFlags
0x180004c13  mov     rcx, rax; hHeap
0x180004c16  call    cs:__imp_HeapFree
0x180004c1c  mov     rdi, [rbx+70h]
0x180004c20  mov     qword ptr [rbx+70h], 0
0x180004c28  test    rdi, rdi
0x180004c2b  jz      short loc_180004C41
0x180004c2d  call    cs:__imp_GetProcessHeap
0x180004c33  mov     r8, rdi; lpMem
0x180004c36  xor     edx, edx; dwFlags
0x180004c38  mov     rcx, rax; hHeap
0x180004c3b  call    cs:__imp_HeapFree
0x180004c41  mov     rdi, [rbx+30h]
0x180004c45  mov     qword ptr [rbx+30h], 0
0x180004c4d  test    rdi, rdi
0x180004c50  jz      short loc_180004C66
0x180004c52  call    cs:__imp_GetProcessHeap
0x180004c58  mov     r8, rdi; lpMem
0x180004c5b  xor     edx, edx; dwFlags
0x180004c5d  mov     rcx, rax; hHeap
0x180004c60  call    cs:__imp_HeapFree
0x180004c66  mov     rbx, [rsp+28h+arg_0]
0x180004c6b  add     rsp, 20h
0x180004c6f  pop     rdi
0x180004c70  retn
```
