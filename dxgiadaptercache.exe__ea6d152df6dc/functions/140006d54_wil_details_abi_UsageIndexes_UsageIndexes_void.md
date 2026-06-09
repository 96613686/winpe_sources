# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140006d54`
- end: `0x140006de1`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140006850`
- `0x14000b4c0`
- `0x14000c2bc`
- `0x140011737`

## callees

- `0x140006d54`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006d78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006d9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006dc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006d78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006d9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006dc2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006d86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006dab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006dd0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006d86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006dab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006dd0`

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
0x140006d54  mov     [rsp+arg_0], rbx
0x140006d59  push    rdi
0x140006d5a  sub     rsp, 20h
0x140006d5e  mov     rdi, [rcx+0B0h]
0x140006d65  mov     rbx, rcx
0x140006d68  mov     qword ptr [rcx+0B0h], 0
0x140006d73  test    rdi, rdi
0x140006d76  jz      short loc_140006D8C
0x140006d78  call    cs:__imp_GetProcessHeap
0x140006d7e  mov     r8, rdi; lpMem
0x140006d81  xor     edx, edx; dwFlags
0x140006d83  mov     rcx, rax; hHeap
0x140006d86  call    cs:__imp_HeapFree
0x140006d8c  mov     rdi, [rbx+70h]
0x140006d90  mov     qword ptr [rbx+70h], 0
0x140006d98  test    rdi, rdi
0x140006d9b  jz      short loc_140006DB1
0x140006d9d  call    cs:__imp_GetProcessHeap
0x140006da3  mov     r8, rdi; lpMem
0x140006da6  xor     edx, edx; dwFlags
0x140006da8  mov     rcx, rax; hHeap
0x140006dab  call    cs:__imp_HeapFree
0x140006db1  mov     rdi, [rbx+30h]
0x140006db5  mov     qword ptr [rbx+30h], 0
0x140006dbd  test    rdi, rdi
0x140006dc0  jz      short loc_140006DD6
0x140006dc2  call    cs:__imp_GetProcessHeap
0x140006dc8  mov     r8, rdi; lpMem
0x140006dcb  xor     edx, edx; dwFlags
0x140006dcd  mov     rcx, rax; hHeap
0x140006dd0  call    cs:__imp_HeapFree
0x140006dd6  mov     rbx, [rsp+28h+arg_0]
0x140006ddb  add     rsp, 20h
0x140006ddf  pop     rdi
0x140006de0  retn
```
