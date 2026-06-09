# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x18000cdf0`
- end: `0x18000ce7d`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cb24`
- `0x180010210`
- `0x180010bb0`

## callees

- `0x18000cdf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce6c`

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
0x18000cdf0  mov     [rsp+arg_0], rbx
0x18000cdf5  push    rdi
0x18000cdf6  sub     rsp, 20h
0x18000cdfa  mov     rdi, [rcx+0B0h]
0x18000ce01  mov     rbx, rcx
0x18000ce04  mov     qword ptr [rcx+0B0h], 0
0x18000ce0f  test    rdi, rdi
0x18000ce12  jz      short loc_18000CE28
0x18000ce14  call    cs:__imp_GetProcessHeap
0x18000ce1a  mov     r8, rdi; lpMem
0x18000ce1d  xor     edx, edx; dwFlags
0x18000ce1f  mov     rcx, rax; hHeap
0x18000ce22  call    cs:__imp_HeapFree
0x18000ce28  mov     rdi, [rbx+70h]
0x18000ce2c  mov     qword ptr [rbx+70h], 0
0x18000ce34  test    rdi, rdi
0x18000ce37  jz      short loc_18000CE4D
0x18000ce39  call    cs:__imp_GetProcessHeap
0x18000ce3f  mov     r8, rdi; lpMem
0x18000ce42  xor     edx, edx; dwFlags
0x18000ce44  mov     rcx, rax; hHeap
0x18000ce47  call    cs:__imp_HeapFree
0x18000ce4d  mov     rdi, [rbx+30h]
0x18000ce51  mov     qword ptr [rbx+30h], 0
0x18000ce59  test    rdi, rdi
0x18000ce5c  jz      short loc_18000CE72
0x18000ce5e  call    cs:__imp_GetProcessHeap
0x18000ce64  mov     r8, rdi; lpMem
0x18000ce67  xor     edx, edx; dwFlags
0x18000ce69  mov     rcx, rax; hHeap
0x18000ce6c  call    cs:__imp_HeapFree
0x18000ce72  mov     rbx, [rsp+28h+arg_0]
0x18000ce77  add     rsp, 20h
0x18000ce7b  pop     rdi
0x18000ce7c  retn
```
