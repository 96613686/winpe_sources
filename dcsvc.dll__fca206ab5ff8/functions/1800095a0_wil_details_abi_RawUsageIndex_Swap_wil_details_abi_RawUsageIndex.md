# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x1800095a0`
- end: `0x180009662`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003d98`
- `0x1800071a0`
- `0x180007fec`

## callees

- `0x1800095a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009623`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009623`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009607`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009631`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009607`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009631`

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
0x1800095a0  push    rbx
0x1800095a2  push    rbp
0x1800095a3  push    rsi
0x1800095a4  push    rdi
0x1800095a5  sub     rsp, 48h
0x1800095a9  mov     rbp, [rcx+30h]
0x1800095ad  mov     rbx, rdx
0x1800095b0  movaps  [rsp+68h+var_38], xmm6
0x1800095b5  mov     rdi, rcx
0x1800095b8  movups  xmm6, xmmword ptr [rcx+18h]
0x1800095bc  movaps  [rsp+68h+var_48], xmm7
0x1800095c1  movsd   xmm7, qword ptr [rcx+28h]
0x1800095c6  mov     qword ptr [rcx+30h], 0
0x1800095ce  movups  xmm0, xmmword ptr [rdx+18h]
0x1800095d2  movups  xmmword ptr [rcx+18h], xmm0
0x1800095d6  movsd   xmm1, qword ptr [rdx+28h]
0x1800095db  movsd   qword ptr [rcx+28h], xmm1
0x1800095e0  mov     rax, [rdx+30h]
0x1800095e4  mov     qword ptr [rdx+30h], 0
0x1800095ec  mov     rsi, [rcx+30h]
0x1800095f0  mov     [rcx+30h], rax
0x1800095f4  test    rsi, rsi
0x1800095f7  jz      short loc_18000960D
0x1800095f9  call    cs:__imp_GetProcessHeap
0x1800095ff  mov     r8, rsi; lpMem
0x180009602  xor     edx, edx; dwFlags
0x180009604  mov     rcx, rax; hHeap
0x180009607  call    cs:__imp_HeapFree
0x18000960d  movups  xmmword ptr [rbx+18h], xmm6
0x180009611  movsd   qword ptr [rbx+28h], xmm7
0x180009616  mov     rsi, [rbx+30h]
0x18000961a  mov     [rbx+30h], rbp
0x18000961e  test    rsi, rsi
0x180009621  jz      short loc_180009637
0x180009623  call    cs:__imp_GetProcessHeap
0x180009629  mov     r8, rsi; lpMem
0x18000962c  xor     edx, edx; dwFlags
0x18000962e  mov     rcx, rax; hHeap
0x180009631  call    cs:__imp_HeapFree
0x180009637  mov     al, [rbx+38h]
0x18000963a  mov     cl, [rdi+38h]
0x18000963d  movaps  xmm6, [rsp+68h+var_38]
0x180009642  movaps  xmm7, [rsp+68h+var_48]
0x180009647  mov     [rdi+38h], al
0x18000964a  mov     al, [rbx+39h]
0x18000964d  mov     [rbx+38h], cl
0x180009650  mov     cl, [rdi+39h]
0x180009653  mov     [rdi+39h], al
0x180009656  mov     [rbx+39h], cl
0x180009659  add     rsp, 48h
0x18000965d  pop     rdi
0x18000965e  pop     rsi
0x18000965f  pop     rbp
0x180009660  pop     rbx
0x180009661  retn
```
