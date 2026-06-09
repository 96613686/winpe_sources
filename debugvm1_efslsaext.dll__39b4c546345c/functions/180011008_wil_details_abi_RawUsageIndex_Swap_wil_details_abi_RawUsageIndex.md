# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x180011008`
- end: `0x1800110ca`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cb24`
- `0x180010210`
- `0x180010bb0`

## callees

- `0x180011008`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011061`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001108b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011061`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001108b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001106f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011099`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001106f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011099`

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
0x180011008  push    rbx
0x18001100a  push    rbp
0x18001100b  push    rsi
0x18001100c  push    rdi
0x18001100d  sub     rsp, 48h
0x180011011  mov     rbp, [rcx+30h]
0x180011015  mov     rbx, rdx
0x180011018  movaps  [rsp+68h+var_38], xmm6
0x18001101d  mov     rdi, rcx
0x180011020  movups  xmm6, xmmword ptr [rcx+18h]
0x180011024  movaps  [rsp+68h+var_48], xmm7
0x180011029  movsd   xmm7, qword ptr [rcx+28h]
0x18001102e  mov     qword ptr [rcx+30h], 0
0x180011036  movups  xmm0, xmmword ptr [rdx+18h]
0x18001103a  movups  xmmword ptr [rcx+18h], xmm0
0x18001103e  movsd   xmm1, qword ptr [rdx+28h]
0x180011043  movsd   qword ptr [rcx+28h], xmm1
0x180011048  mov     rax, [rdx+30h]
0x18001104c  mov     qword ptr [rdx+30h], 0
0x180011054  mov     rsi, [rcx+30h]
0x180011058  mov     [rcx+30h], rax
0x18001105c  test    rsi, rsi
0x18001105f  jz      short loc_180011075
0x180011061  call    cs:__imp_GetProcessHeap
0x180011067  mov     r8, rsi; lpMem
0x18001106a  xor     edx, edx; dwFlags
0x18001106c  mov     rcx, rax; hHeap
0x18001106f  call    cs:__imp_HeapFree
0x180011075  movups  xmmword ptr [rbx+18h], xmm6
0x180011079  movsd   qword ptr [rbx+28h], xmm7
0x18001107e  mov     rsi, [rbx+30h]
0x180011082  mov     [rbx+30h], rbp
0x180011086  test    rsi, rsi
0x180011089  jz      short loc_18001109F
0x18001108b  call    cs:__imp_GetProcessHeap
0x180011091  mov     r8, rsi; lpMem
0x180011094  xor     edx, edx; dwFlags
0x180011096  mov     rcx, rax; hHeap
0x180011099  call    cs:__imp_HeapFree
0x18001109f  mov     al, [rbx+38h]
0x1800110a2  mov     cl, [rdi+38h]
0x1800110a5  movaps  xmm6, [rsp+68h+var_38]
0x1800110aa  movaps  xmm7, [rsp+68h+var_48]
0x1800110af  mov     [rdi+38h], al
0x1800110b2  mov     al, [rbx+39h]
0x1800110b5  mov     [rbx+38h], cl
0x1800110b8  mov     cl, [rdi+39h]
0x1800110bb  mov     [rdi+39h], al
0x1800110be  mov     [rbx+39h], cl
0x1800110c1  add     rsp, 48h
0x1800110c5  pop     rdi
0x1800110c6  pop     rsi
0x1800110c7  pop     rbp
0x1800110c8  pop     rbx
0x1800110c9  retn
```
