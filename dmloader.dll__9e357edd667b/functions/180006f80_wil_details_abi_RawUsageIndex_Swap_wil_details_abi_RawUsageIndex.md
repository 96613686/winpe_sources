# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x180006f80`
- end: `0x180007042`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c44`
- `0x180005a9c`
- `0x1800065a0`

## callees

- `0x180006f80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006fe7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007011`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006fe7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007011`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006fd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007003`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006fd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007003`

## pseudocode

```c
void __fastcall wil::details_abi::RawUsageIndex::Swap(
        wil::details_abi::RawUsageIndex *this,
        struct wil::details_abi::RawUsageIndex *a2)
{
  __int64 v2; // rbp
  __int128 v5; // xmm6
  __int64 v6; // xmm7_8
  __int64 v7; // rax
  void *v8; // rsi
  HANDLE ProcessHeap; // rax
  void *v10; // rsi
  HANDLE v11; // rax
  char v12; // cl
  char v13; // al
  char v14; // cl

  v2 = *((_QWORD *)this + 6);
  v5 = *(_OWORD *)((char *)this + 24);
  v6 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 6) = 0;
  *(_OWORD *)((char *)this + 24) = *(_OWORD *)((char *)a2 + 24);
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 5);
  v7 = *((_QWORD *)a2 + 6);
  *((_QWORD *)a2 + 6) = 0;
  v8 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = v7;
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  *(_OWORD *)((char *)a2 + 24) = v5;
  *((_QWORD *)a2 + 5) = v6;
  v10 = (void *)*((_QWORD *)a2 + 6);
  *((_QWORD *)a2 + 6) = v2;
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  v12 = *((_BYTE *)this + 56);
  *((_BYTE *)this + 56) = *((_BYTE *)a2 + 56);
  v13 = *((_BYTE *)a2 + 57);
  *((_BYTE *)a2 + 56) = v12;
  v14 = *((_BYTE *)this + 57);
  *((_BYTE *)this + 57) = v13;
  *((_BYTE *)a2 + 57) = v14;
}

```

## disassembly

```asm
0x180006f80  push    rbx
0x180006f82  push    rbp
0x180006f83  push    rsi
0x180006f84  push    rdi
0x180006f85  sub     rsp, 48h
0x180006f89  mov     rbp, [rcx+30h]
0x180006f8d  mov     rbx, rdx
0x180006f90  movaps  [rsp+68h+var_38], xmm6
0x180006f95  mov     rdi, rcx
0x180006f98  movups  xmm6, xmmword ptr [rcx+18h]
0x180006f9c  movaps  [rsp+68h+var_48], xmm7
0x180006fa1  movsd   xmm7, qword ptr [rcx+28h]
0x180006fa6  mov     qword ptr [rcx+30h], 0
0x180006fae  movups  xmm0, xmmword ptr [rdx+18h]
0x180006fb2  movups  xmmword ptr [rcx+18h], xmm0
0x180006fb6  movsd   xmm1, qword ptr [rdx+28h]
0x180006fbb  movsd   qword ptr [rcx+28h], xmm1
0x180006fc0  mov     rax, [rdx+30h]
0x180006fc4  mov     qword ptr [rdx+30h], 0
0x180006fcc  mov     rsi, [rcx+30h]
0x180006fd0  mov     [rcx+30h], rax
0x180006fd4  test    rsi, rsi
0x180006fd7  jz      short loc_180006FED
0x180006fd9  call    cs:__imp_GetProcessHeap
0x180006fdf  mov     r8, rsi; lpMem
0x180006fe2  xor     edx, edx; dwFlags
0x180006fe4  mov     rcx, rax; hHeap
0x180006fe7  call    cs:__imp_HeapFree
0x180006fed  movups  xmmword ptr [rbx+18h], xmm6
0x180006ff1  movsd   qword ptr [rbx+28h], xmm7
0x180006ff6  mov     rsi, [rbx+30h]
0x180006ffa  mov     [rbx+30h], rbp
0x180006ffe  test    rsi, rsi
0x180007001  jz      short loc_180007017
0x180007003  call    cs:__imp_GetProcessHeap
0x180007009  mov     r8, rsi; lpMem
0x18000700c  xor     edx, edx; dwFlags
0x18000700e  mov     rcx, rax; hHeap
0x180007011  call    cs:__imp_HeapFree
0x180007017  mov     al, [rbx+38h]
0x18000701a  mov     cl, [rdi+38h]
0x18000701d  movaps  xmm6, [rsp+68h+var_38]
0x180007022  movaps  xmm7, [rsp+68h+var_48]
0x180007027  mov     [rdi+38h], al
0x18000702a  mov     al, [rbx+39h]
0x18000702d  mov     [rbx+38h], cl
0x180007030  mov     cl, [rdi+39h]
0x180007033  mov     [rdi+39h], al
0x180007036  mov     [rbx+39h], cl
0x180007039  add     rsp, 48h
0x18000703d  pop     rdi
0x18000703e  pop     rsi
0x18000703f  pop     rbp
0x180007040  pop     rbx
0x180007041  retn
```
