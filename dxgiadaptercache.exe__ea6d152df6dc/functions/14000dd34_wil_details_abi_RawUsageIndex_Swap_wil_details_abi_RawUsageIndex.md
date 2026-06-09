# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x14000dd34`
- end: `0x14000ddf6`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140006850`
- `0x14000b4c0`
- `0x14000c2bc`

## callees

- `0x14000dd34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000dd8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ddb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000dd8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ddb7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000dd9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ddc5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000dd9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ddc5`

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
0x14000dd34  push    rbx
0x14000dd36  push    rbp
0x14000dd37  push    rsi
0x14000dd38  push    rdi
0x14000dd39  sub     rsp, 48h
0x14000dd3d  mov     rbp, [rcx+30h]
0x14000dd41  mov     rbx, rdx
0x14000dd44  movaps  [rsp+68h+var_38], xmm6
0x14000dd49  mov     rdi, rcx
0x14000dd4c  movups  xmm6, xmmword ptr [rcx+18h]
0x14000dd50  movaps  [rsp+68h+var_48], xmm7
0x14000dd55  movsd   xmm7, qword ptr [rcx+28h]
0x14000dd5a  mov     qword ptr [rcx+30h], 0
0x14000dd62  movups  xmm0, xmmword ptr [rdx+18h]
0x14000dd66  movups  xmmword ptr [rcx+18h], xmm0
0x14000dd6a  movsd   xmm1, qword ptr [rdx+28h]
0x14000dd6f  movsd   qword ptr [rcx+28h], xmm1
0x14000dd74  mov     rax, [rdx+30h]
0x14000dd78  mov     qword ptr [rdx+30h], 0
0x14000dd80  mov     rsi, [rcx+30h]
0x14000dd84  mov     [rcx+30h], rax
0x14000dd88  test    rsi, rsi
0x14000dd8b  jz      short loc_14000DDA1
0x14000dd8d  call    cs:__imp_GetProcessHeap
0x14000dd93  mov     r8, rsi; lpMem
0x14000dd96  xor     edx, edx; dwFlags
0x14000dd98  mov     rcx, rax; hHeap
0x14000dd9b  call    cs:__imp_HeapFree
0x14000dda1  movups  xmmword ptr [rbx+18h], xmm6
0x14000dda5  movsd   qword ptr [rbx+28h], xmm7
0x14000ddaa  mov     rsi, [rbx+30h]
0x14000ddae  mov     [rbx+30h], rbp
0x14000ddb2  test    rsi, rsi
0x14000ddb5  jz      short loc_14000DDCB
0x14000ddb7  call    cs:__imp_GetProcessHeap
0x14000ddbd  mov     r8, rsi; lpMem
0x14000ddc0  xor     edx, edx; dwFlags
0x14000ddc2  mov     rcx, rax; hHeap
0x14000ddc5  call    cs:__imp_HeapFree
0x14000ddcb  mov     al, [rbx+38h]
0x14000ddce  mov     cl, [rdi+38h]
0x14000ddd1  movaps  xmm6, [rsp+68h+var_38]
0x14000ddd6  movaps  xmm7, [rsp+68h+var_48]
0x14000dddb  mov     [rdi+38h], al
0x14000ddde  mov     al, [rbx+39h]
0x14000dde1  mov     [rbx+38h], cl
0x14000dde4  mov     cl, [rdi+39h]
0x14000dde7  mov     [rdi+39h], al
0x14000ddea  mov     [rbx+39h], cl
0x14000dded  add     rsp, 48h
0x14000ddf1  pop     rdi
0x14000ddf2  pop     rsi
0x14000ddf3  pop     rbp
0x14000ddf4  pop     rbx
0x14000ddf5  retn
```
