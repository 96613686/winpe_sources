# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x180009bf8`
- end: `0x180009cba`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004894`
- `0x1800088e0`
- `0x180009394`

## callees

- `0x180009bf8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c89`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c89`

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
0x180009bf8  push    rbx
0x180009bfa  push    rbp
0x180009bfb  push    rsi
0x180009bfc  push    rdi
0x180009bfd  sub     rsp, 48h
0x180009c01  mov     rbp, [rcx+30h]
0x180009c05  mov     rbx, rdx
0x180009c08  movaps  [rsp+68h+var_38], xmm6
0x180009c0d  mov     rdi, rcx
0x180009c10  movups  xmm6, xmmword ptr [rcx+18h]
0x180009c14  movaps  [rsp+68h+var_48], xmm7
0x180009c19  movsd   xmm7, qword ptr [rcx+28h]
0x180009c1e  mov     qword ptr [rcx+30h], 0
0x180009c26  movups  xmm0, xmmword ptr [rdx+18h]
0x180009c2a  movups  xmmword ptr [rcx+18h], xmm0
0x180009c2e  movsd   xmm1, qword ptr [rdx+28h]
0x180009c33  movsd   qword ptr [rcx+28h], xmm1
0x180009c38  mov     rax, [rdx+30h]
0x180009c3c  mov     qword ptr [rdx+30h], 0
0x180009c44  mov     rsi, [rcx+30h]
0x180009c48  mov     [rcx+30h], rax
0x180009c4c  test    rsi, rsi
0x180009c4f  jz      short loc_180009C65
0x180009c51  call    cs:__imp_GetProcessHeap
0x180009c57  mov     r8, rsi; lpMem
0x180009c5a  xor     edx, edx; dwFlags
0x180009c5c  mov     rcx, rax; hHeap
0x180009c5f  call    cs:__imp_HeapFree
0x180009c65  movups  xmmword ptr [rbx+18h], xmm6
0x180009c69  movsd   qword ptr [rbx+28h], xmm7
0x180009c6e  mov     rsi, [rbx+30h]
0x180009c72  mov     [rbx+30h], rbp
0x180009c76  test    rsi, rsi
0x180009c79  jz      short loc_180009C8F
0x180009c7b  call    cs:__imp_GetProcessHeap
0x180009c81  mov     r8, rsi; lpMem
0x180009c84  xor     edx, edx; dwFlags
0x180009c86  mov     rcx, rax; hHeap
0x180009c89  call    cs:__imp_HeapFree
0x180009c8f  mov     al, [rbx+38h]
0x180009c92  mov     cl, [rdi+38h]
0x180009c95  movaps  xmm6, [rsp+68h+var_38]
0x180009c9a  movaps  xmm7, [rsp+68h+var_48]
0x180009c9f  mov     [rdi+38h], al
0x180009ca2  mov     al, [rbx+39h]
0x180009ca5  mov     [rbx+38h], cl
0x180009ca8  mov     cl, [rdi+39h]
0x180009cab  mov     [rdi+39h], al
0x180009cae  mov     [rbx+39h], cl
0x180009cb1  add     rsp, 48h
0x180009cb5  pop     rdi
0x180009cb6  pop     rsi
0x180009cb7  pop     rbp
0x180009cb8  pop     rbx
0x180009cb9  retn
```
