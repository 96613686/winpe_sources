# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x18000c1a0`
- end: `0x18000c262`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008284`
- `0x18000ae1c`
- `0x18000b8d0`

## callees

- `0x18000c1a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c207`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c231`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c207`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c231`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c223`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c223`

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
0x18000c1a0  push    rbx
0x18000c1a2  push    rbp
0x18000c1a3  push    rsi
0x18000c1a4  push    rdi
0x18000c1a5  sub     rsp, 48h
0x18000c1a9  mov     rbp, [rcx+30h]
0x18000c1ad  mov     rbx, rdx
0x18000c1b0  movaps  [rsp+68h+var_38], xmm6
0x18000c1b5  mov     rdi, rcx
0x18000c1b8  movups  xmm6, xmmword ptr [rcx+18h]
0x18000c1bc  movaps  [rsp+68h+var_48], xmm7
0x18000c1c1  movsd   xmm7, qword ptr [rcx+28h]
0x18000c1c6  mov     qword ptr [rcx+30h], 0
0x18000c1ce  movups  xmm0, xmmword ptr [rdx+18h]
0x18000c1d2  movups  xmmword ptr [rcx+18h], xmm0
0x18000c1d6  movsd   xmm1, qword ptr [rdx+28h]
0x18000c1db  movsd   qword ptr [rcx+28h], xmm1
0x18000c1e0  mov     rax, [rdx+30h]
0x18000c1e4  mov     qword ptr [rdx+30h], 0
0x18000c1ec  mov     rsi, [rcx+30h]
0x18000c1f0  mov     [rcx+30h], rax
0x18000c1f4  test    rsi, rsi
0x18000c1f7  jz      short loc_18000C20D
0x18000c1f9  call    cs:__imp_GetProcessHeap
0x18000c1ff  mov     r8, rsi; lpMem
0x18000c202  xor     edx, edx; dwFlags
0x18000c204  mov     rcx, rax; hHeap
0x18000c207  call    cs:__imp_HeapFree
0x18000c20d  movups  xmmword ptr [rbx+18h], xmm6
0x18000c211  movsd   qword ptr [rbx+28h], xmm7
0x18000c216  mov     rsi, [rbx+30h]
0x18000c21a  mov     [rbx+30h], rbp
0x18000c21e  test    rsi, rsi
0x18000c221  jz      short loc_18000C237
0x18000c223  call    cs:__imp_GetProcessHeap
0x18000c229  mov     r8, rsi; lpMem
0x18000c22c  xor     edx, edx; dwFlags
0x18000c22e  mov     rcx, rax; hHeap
0x18000c231  call    cs:__imp_HeapFree
0x18000c237  mov     al, [rbx+38h]
0x18000c23a  mov     cl, [rdi+38h]
0x18000c23d  movaps  xmm6, [rsp+68h+var_38]
0x18000c242  movaps  xmm7, [rsp+68h+var_48]
0x18000c247  mov     [rdi+38h], al
0x18000c24a  mov     al, [rbx+39h]
0x18000c24d  mov     [rbx+38h], cl
0x18000c250  mov     cl, [rdi+39h]
0x18000c253  mov     [rdi+39h], al
0x18000c256  mov     [rbx+39h], cl
0x18000c259  add     rsp, 48h
0x18000c25d  pop     rdi
0x18000c25e  pop     rsi
0x18000c25f  pop     rbp
0x18000c260  pop     rbx
0x18000c261  retn
```
