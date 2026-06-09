# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x180007524`
- end: `0x1800075ff`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `219`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800032d8`
- `0x180005f78`
- `0x180006a90`

## callees

- `0x180007524`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000757d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000757d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007591`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800075c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007591`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800075c7`

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
0x180007524  push    rbx
0x180007526  push    rbp
0x180007527  push    rsi
0x180007528  push    rdi
0x180007529  sub     rsp, 48h
0x18000752d  mov     rbp, [rcx+30h]
0x180007531  mov     rbx, rdx
0x180007534  movaps  [rsp+68h+var_38], xmm6
0x180007539  mov     rdi, rcx
0x18000753c  movups  xmm6, xmmword ptr [rcx+18h]
0x180007540  movaps  [rsp+68h+var_48], xmm7
0x180007545  movsd   xmm7, qword ptr [rcx+28h]
0x18000754a  mov     qword ptr [rcx+30h], 0
0x180007552  movups  xmm0, xmmword ptr [rdx+18h]
0x180007556  movups  xmmword ptr [rcx+18h], xmm0
0x18000755a  movsd   xmm1, qword ptr [rdx+28h]
0x18000755f  movsd   qword ptr [rcx+28h], xmm1
0x180007564  mov     rax, [rdx+30h]
0x180007568  mov     qword ptr [rdx+30h], 0
0x180007570  mov     rsi, [rcx+30h]
0x180007574  mov     [rcx+30h], rax
0x180007578  test    rsi, rsi
0x18000757b  jz      short loc_18000759D
0x18000757d  call    cs:__imp_GetProcessHeap
0x180007584  nop     dword ptr [rax+rax+00h]
0x180007589  mov     r8, rsi; lpMem
0x18000758c  xor     edx, edx; dwFlags
0x18000758e  mov     rcx, rax; hHeap
0x180007591  call    cs:__imp_HeapFree
0x180007598  nop     dword ptr [rax+rax+00h]
0x18000759d  movups  xmmword ptr [rbx+18h], xmm6
0x1800075a1  movsd   qword ptr [rbx+28h], xmm7
0x1800075a6  mov     rsi, [rbx+30h]
0x1800075aa  mov     [rbx+30h], rbp
0x1800075ae  test    rsi, rsi
0x1800075b1  jz      short loc_1800075D3
0x1800075b3  call    cs:__imp_GetProcessHeap
0x1800075ba  nop     dword ptr [rax+rax+00h]
0x1800075bf  mov     r8, rsi; lpMem
0x1800075c2  xor     edx, edx; dwFlags
0x1800075c4  mov     rcx, rax; hHeap
0x1800075c7  call    cs:__imp_HeapFree
0x1800075ce  nop     dword ptr [rax+rax+00h]
0x1800075d3  mov     al, [rbx+38h]
0x1800075d6  mov     cl, [rdi+38h]
0x1800075d9  movaps  xmm6, [rsp+68h+var_38]
0x1800075de  movaps  xmm7, [rsp+68h+var_48]
0x1800075e3  mov     [rdi+38h], al
0x1800075e6  mov     al, [rbx+39h]
0x1800075e9  mov     [rbx+38h], cl
0x1800075ec  mov     cl, [rdi+39h]
0x1800075ef  mov     [rdi+39h], al
0x1800075f2  mov     [rbx+39h], cl
0x1800075f5  add     rsp, 48h
0x1800075f9  pop     rdi
0x1800075fa  pop     rsi
0x1800075fb  pop     rbp
0x1800075fc  pop     rbx
0x1800075fd  retn
```
