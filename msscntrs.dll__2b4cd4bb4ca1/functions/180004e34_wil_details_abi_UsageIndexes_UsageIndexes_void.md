# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180004e34`
- end: `0x180004ec1`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800049c0`
- `0x180007cf0`
- `0x180008800`
- `0x180015944`

## callees

- `0x180004e34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ea2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ea2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004eb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004eb0`

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
0x180004e34  mov     [rsp+arg_0], rbx
0x180004e39  push    rdi
0x180004e3a  sub     rsp, 20h
0x180004e3e  mov     rdi, [rcx+0B0h]
0x180004e45  mov     rbx, rcx
0x180004e48  mov     qword ptr [rcx+0B0h], 0
0x180004e53  test    rdi, rdi
0x180004e56  jz      short loc_180004E6C
0x180004e58  call    cs:__imp_GetProcessHeap
0x180004e5e  mov     r8, rdi; lpMem
0x180004e61  xor     edx, edx; dwFlags
0x180004e63  mov     rcx, rax; hHeap
0x180004e66  call    cs:__imp_HeapFree
0x180004e6c  mov     rdi, [rbx+70h]
0x180004e70  mov     qword ptr [rbx+70h], 0
0x180004e78  test    rdi, rdi
0x180004e7b  jz      short loc_180004E91
0x180004e7d  call    cs:__imp_GetProcessHeap
0x180004e83  mov     r8, rdi; lpMem
0x180004e86  xor     edx, edx; dwFlags
0x180004e88  mov     rcx, rax; hHeap
0x180004e8b  call    cs:__imp_HeapFree
0x180004e91  mov     rdi, [rbx+30h]
0x180004e95  mov     qword ptr [rbx+30h], 0
0x180004e9d  test    rdi, rdi
0x180004ea0  jz      short loc_180004EB6
0x180004ea2  call    cs:__imp_GetProcessHeap
0x180004ea8  mov     r8, rdi; lpMem
0x180004eab  xor     edx, edx; dwFlags
0x180004ead  mov     rcx, rax; hHeap
0x180004eb0  call    cs:__imp_HeapFree
0x180004eb6  mov     rbx, [rsp+28h+arg_0]
0x180004ebb  add     rsp, 20h
0x180004ebf  pop     rdi
0x180004ec0  retn
```
