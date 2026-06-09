# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x18000bbd0`
- end: `0x18000bc92`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004220`
- `0x180008920`
- `0x180009440`

## callees

- `0x18000bbd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bc37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bc61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bc37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bc61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc53`

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
0x18000bbd0  push    rbx
0x18000bbd2  push    rbp
0x18000bbd3  push    rsi
0x18000bbd4  push    rdi
0x18000bbd5  sub     rsp, 48h
0x18000bbd9  mov     rbp, [rcx+30h]
0x18000bbdd  mov     rbx, rdx
0x18000bbe0  movaps  [rsp+68h+var_38], xmm6
0x18000bbe5  mov     rdi, rcx
0x18000bbe8  movups  xmm6, xmmword ptr [rcx+18h]
0x18000bbec  movaps  [rsp+68h+var_48], xmm7
0x18000bbf1  movsd   xmm7, qword ptr [rcx+28h]
0x18000bbf6  mov     qword ptr [rcx+30h], 0
0x18000bbfe  movups  xmm0, xmmword ptr [rdx+18h]
0x18000bc02  movups  xmmword ptr [rcx+18h], xmm0
0x18000bc06  movsd   xmm1, qword ptr [rdx+28h]
0x18000bc0b  movsd   qword ptr [rcx+28h], xmm1
0x18000bc10  mov     rax, [rdx+30h]
0x18000bc14  mov     qword ptr [rdx+30h], 0
0x18000bc1c  mov     rsi, [rcx+30h]
0x18000bc20  mov     [rcx+30h], rax
0x18000bc24  test    rsi, rsi
0x18000bc27  jz      short loc_18000BC3D
0x18000bc29  call    cs:__imp_GetProcessHeap
0x18000bc2f  mov     r8, rsi; lpMem
0x18000bc32  xor     edx, edx; dwFlags
0x18000bc34  mov     rcx, rax; hHeap
0x18000bc37  call    cs:__imp_HeapFree
0x18000bc3d  movups  xmmword ptr [rbx+18h], xmm6
0x18000bc41  movsd   qword ptr [rbx+28h], xmm7
0x18000bc46  mov     rsi, [rbx+30h]
0x18000bc4a  mov     [rbx+30h], rbp
0x18000bc4e  test    rsi, rsi
0x18000bc51  jz      short loc_18000BC67
0x18000bc53  call    cs:__imp_GetProcessHeap
0x18000bc59  mov     r8, rsi; lpMem
0x18000bc5c  xor     edx, edx; dwFlags
0x18000bc5e  mov     rcx, rax; hHeap
0x18000bc61  call    cs:__imp_HeapFree
0x18000bc67  mov     al, [rbx+38h]
0x18000bc6a  mov     cl, [rdi+38h]
0x18000bc6d  movaps  xmm6, [rsp+68h+var_38]
0x18000bc72  movaps  xmm7, [rsp+68h+var_48]
0x18000bc77  mov     [rdi+38h], al
0x18000bc7a  mov     al, [rbx+39h]
0x18000bc7d  mov     [rbx+38h], cl
0x18000bc80  mov     cl, [rdi+39h]
0x18000bc83  mov     [rdi+39h], al
0x18000bc86  mov     [rbx+39h], cl
0x18000bc89  add     rsp, 48h
0x18000bc8d  pop     rdi
0x18000bc8e  pop     rsi
0x18000bc8f  pop     rbp
0x18000bc90  pop     rbx
0x18000bc91  retn
```
