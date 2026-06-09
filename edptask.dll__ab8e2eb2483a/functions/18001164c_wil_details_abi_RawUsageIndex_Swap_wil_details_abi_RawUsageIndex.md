# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x18001164c`
- end: `0x18001170e`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800077fc`
- `0x18000f7e0`
- `0x180010190`

## callees

- `0x18001164c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800116b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800116dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800116b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800116dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800116a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800116cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800116a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800116cf`

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
0x18001164c  push    rbx
0x18001164e  push    rbp
0x18001164f  push    rsi
0x180011650  push    rdi
0x180011651  sub     rsp, 48h
0x180011655  mov     rbp, [rcx+30h]
0x180011659  mov     rbx, rdx
0x18001165c  movaps  [rsp+68h+var_38], xmm6
0x180011661  mov     rdi, rcx
0x180011664  movups  xmm6, xmmword ptr [rcx+18h]
0x180011668  movaps  [rsp+68h+var_48], xmm7
0x18001166d  movsd   xmm7, qword ptr [rcx+28h]
0x180011672  mov     qword ptr [rcx+30h], 0
0x18001167a  movups  xmm0, xmmword ptr [rdx+18h]
0x18001167e  movups  xmmword ptr [rcx+18h], xmm0
0x180011682  movsd   xmm1, qword ptr [rdx+28h]
0x180011687  movsd   qword ptr [rcx+28h], xmm1
0x18001168c  mov     rax, [rdx+30h]
0x180011690  mov     qword ptr [rdx+30h], 0
0x180011698  mov     rsi, [rcx+30h]
0x18001169c  mov     [rcx+30h], rax
0x1800116a0  test    rsi, rsi
0x1800116a3  jz      short loc_1800116B9
0x1800116a5  call    cs:__imp_GetProcessHeap
0x1800116ab  mov     r8, rsi; lpMem
0x1800116ae  xor     edx, edx; dwFlags
0x1800116b0  mov     rcx, rax; hHeap
0x1800116b3  call    cs:__imp_HeapFree
0x1800116b9  movups  xmmword ptr [rbx+18h], xmm6
0x1800116bd  movsd   qword ptr [rbx+28h], xmm7
0x1800116c2  mov     rsi, [rbx+30h]
0x1800116c6  mov     [rbx+30h], rbp
0x1800116ca  test    rsi, rsi
0x1800116cd  jz      short loc_1800116E3
0x1800116cf  call    cs:__imp_GetProcessHeap
0x1800116d5  mov     r8, rsi; lpMem
0x1800116d8  xor     edx, edx; dwFlags
0x1800116da  mov     rcx, rax; hHeap
0x1800116dd  call    cs:__imp_HeapFree
0x1800116e3  mov     al, [rbx+38h]
0x1800116e6  mov     cl, [rdi+38h]
0x1800116e9  movaps  xmm6, [rsp+68h+var_38]
0x1800116ee  movaps  xmm7, [rsp+68h+var_48]
0x1800116f3  mov     [rdi+38h], al
0x1800116f6  mov     al, [rbx+39h]
0x1800116f9  mov     [rbx+38h], cl
0x1800116fc  mov     cl, [rdi+39h]
0x1800116ff  mov     [rdi+39h], al
0x180011702  mov     [rbx+39h], cl
0x180011705  add     rsp, 48h
0x180011709  pop     rdi
0x18001170a  pop     rsi
0x18001170b  pop     rbp
0x18001170c  pop     rbx
0x18001170d  retn
```
