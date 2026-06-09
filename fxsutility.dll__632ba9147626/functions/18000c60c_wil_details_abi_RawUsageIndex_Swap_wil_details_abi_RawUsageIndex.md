# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x18000c60c`
- end: `0x18000c6ce`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000824c`
- `0x18000af30`
- `0x18000b9f4`

## callees

- `0x18000c60c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000c673`
- `KERNEL32!HeapFree` at `0x18000c69d`
- `KERNEL32!HeapFree` at `0x18000c673`
- `KERNEL32!HeapFree` at `0x18000c69d`
- `KERNEL32!GetProcessHeap` at `0x18000c665`
- `KERNEL32!GetProcessHeap` at `0x18000c68f`
- `KERNEL32!GetProcessHeap` at `0x18000c665`
- `KERNEL32!GetProcessHeap` at `0x18000c68f`

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
0x18000c60c  push    rbx
0x18000c60e  push    rbp
0x18000c60f  push    rsi
0x18000c610  push    rdi
0x18000c611  sub     rsp, 48h
0x18000c615  mov     rbp, [rcx+30h]
0x18000c619  mov     rbx, rdx
0x18000c61c  movaps  [rsp+68h+var_38], xmm6
0x18000c621  mov     rdi, rcx
0x18000c624  movups  xmm6, xmmword ptr [rcx+18h]
0x18000c628  movaps  [rsp+68h+var_48], xmm7
0x18000c62d  movsd   xmm7, qword ptr [rcx+28h]
0x18000c632  mov     qword ptr [rcx+30h], 0
0x18000c63a  movups  xmm0, xmmword ptr [rdx+18h]
0x18000c63e  movups  xmmword ptr [rcx+18h], xmm0
0x18000c642  movsd   xmm1, qword ptr [rdx+28h]
0x18000c647  movsd   qword ptr [rcx+28h], xmm1
0x18000c64c  mov     rax, [rdx+30h]
0x18000c650  mov     qword ptr [rdx+30h], 0
0x18000c658  mov     rsi, [rcx+30h]
0x18000c65c  mov     [rcx+30h], rax
0x18000c660  test    rsi, rsi
0x18000c663  jz      short loc_18000C679
0x18000c665  call    cs:__imp_GetProcessHeap
0x18000c66b  mov     r8, rsi; lpMem
0x18000c66e  xor     edx, edx; dwFlags
0x18000c670  mov     rcx, rax; hHeap
0x18000c673  call    cs:__imp_HeapFree
0x18000c679  movups  xmmword ptr [rbx+18h], xmm6
0x18000c67d  movsd   qword ptr [rbx+28h], xmm7
0x18000c682  mov     rsi, [rbx+30h]
0x18000c686  mov     [rbx+30h], rbp
0x18000c68a  test    rsi, rsi
0x18000c68d  jz      short loc_18000C6A3
0x18000c68f  call    cs:__imp_GetProcessHeap
0x18000c695  mov     r8, rsi; lpMem
0x18000c698  xor     edx, edx; dwFlags
0x18000c69a  mov     rcx, rax; hHeap
0x18000c69d  call    cs:__imp_HeapFree
0x18000c6a3  mov     al, [rbx+38h]
0x18000c6a6  mov     cl, [rdi+38h]
0x18000c6a9  movaps  xmm6, [rsp+68h+var_38]
0x18000c6ae  movaps  xmm7, [rsp+68h+var_48]
0x18000c6b3  mov     [rdi+38h], al
0x18000c6b6  mov     al, [rbx+39h]
0x18000c6b9  mov     [rbx+38h], cl
0x18000c6bc  mov     cl, [rdi+39h]
0x18000c6bf  mov     [rdi+39h], al
0x18000c6c2  mov     [rbx+39h], cl
0x18000c6c5  add     rsp, 48h
0x18000c6c9  pop     rdi
0x18000c6ca  pop     rsi
0x18000c6cb  pop     rbp
0x18000c6cc  pop     rbx
0x18000c6cd  retn
```
