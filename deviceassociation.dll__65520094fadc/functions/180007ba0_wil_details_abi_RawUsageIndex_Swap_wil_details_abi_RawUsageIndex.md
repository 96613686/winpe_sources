# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x180007ba0`
- end: `0x180007c62`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003c84`
- `0x18000681c`
- `0x1800072d0`

## callees

- `0x180007ba0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007bf9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007bf9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c31`

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
0x180007ba0  push    rbx
0x180007ba2  push    rbp
0x180007ba3  push    rsi
0x180007ba4  push    rdi
0x180007ba5  sub     rsp, 48h
0x180007ba9  mov     rbp, [rcx+30h]
0x180007bad  mov     rbx, rdx
0x180007bb0  movaps  [rsp+68h+var_38], xmm6
0x180007bb5  mov     rdi, rcx
0x180007bb8  movups  xmm6, xmmword ptr [rcx+18h]
0x180007bbc  movaps  [rsp+68h+var_48], xmm7
0x180007bc1  movsd   xmm7, qword ptr [rcx+28h]
0x180007bc6  mov     qword ptr [rcx+30h], 0
0x180007bce  movups  xmm0, xmmword ptr [rdx+18h]
0x180007bd2  movups  xmmword ptr [rcx+18h], xmm0
0x180007bd6  movsd   xmm1, qword ptr [rdx+28h]
0x180007bdb  movsd   qword ptr [rcx+28h], xmm1
0x180007be0  mov     rax, [rdx+30h]
0x180007be4  mov     qword ptr [rdx+30h], 0
0x180007bec  mov     rsi, [rcx+30h]
0x180007bf0  mov     [rcx+30h], rax
0x180007bf4  test    rsi, rsi
0x180007bf7  jz      short loc_180007C0D
0x180007bf9  call    cs:__imp_GetProcessHeap
0x180007bff  mov     r8, rsi; lpMem
0x180007c02  xor     edx, edx; dwFlags
0x180007c04  mov     rcx, rax; hHeap
0x180007c07  call    cs:__imp_HeapFree
0x180007c0d  movups  xmmword ptr [rbx+18h], xmm6
0x180007c11  movsd   qword ptr [rbx+28h], xmm7
0x180007c16  mov     rsi, [rbx+30h]
0x180007c1a  mov     [rbx+30h], rbp
0x180007c1e  test    rsi, rsi
0x180007c21  jz      short loc_180007C37
0x180007c23  call    cs:__imp_GetProcessHeap
0x180007c29  mov     r8, rsi; lpMem
0x180007c2c  xor     edx, edx; dwFlags
0x180007c2e  mov     rcx, rax; hHeap
0x180007c31  call    cs:__imp_HeapFree
0x180007c37  mov     al, [rbx+38h]
0x180007c3a  mov     cl, [rdi+38h]
0x180007c3d  movaps  xmm6, [rsp+68h+var_38]
0x180007c42  movaps  xmm7, [rsp+68h+var_48]
0x180007c47  mov     [rdi+38h], al
0x180007c4a  mov     al, [rbx+39h]
0x180007c4d  mov     [rbx+38h], cl
0x180007c50  mov     cl, [rdi+39h]
0x180007c53  mov     [rdi+39h], al
0x180007c56  mov     [rbx+39h], cl
0x180007c59  add     rsp, 48h
0x180007c5d  pop     rdi
0x180007c5e  pop     rsi
0x180007c5f  pop     rbp
0x180007c60  pop     rbx
0x180007c61  retn
```
