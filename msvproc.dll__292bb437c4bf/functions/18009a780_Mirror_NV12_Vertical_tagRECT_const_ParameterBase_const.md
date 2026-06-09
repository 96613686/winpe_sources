# Mirror_NV12_Vertical(tagRECT const &,ParameterBase const *)

- ea: `0x18009a780`
- end: `0x18009a958`
- name: `?Mirror_NV12_Vertical@@YAJAEBUtagRECT@@PEBUParameterBase@@@Z`
- size: `472`
- prototype: `__int64 __fastcall(const struct tagRECT *, const struct ParameterBase *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18009a780`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x18009a8c5`
- `MFPlat!MFCopyImage` at `0x18009a8e8`
- `MFPlat!MFCopyImage` at `0x18009a911`
- `MFPlat!MFCopyImage` at `0x18009a8c5`
- `MFPlat!MFCopyImage` at `0x18009a8e8`
- `MFPlat!MFCopyImage` at `0x18009a911`

## pseudocode

```c
__int64 __fastcall Mirror_NV12_Vertical(const struct tagRECT *a1, const struct ParameterBase *a2)
{
  __int64 v2; // rbp
  __int64 v4; // r14
  __int64 v5; // rdi
  __int64 v6; // r10
  signed int v7; // r11d
  unsigned int v8; // ebx
  int v9; // r9d
  DWORD dwWidthInBytes; // r13d
  int v11; // edx
  int v12; // r8d
  const BYTE *v13; // r15
  BYTE *v14; // r12
  int v15; // eax
  int v16; // esi
  int v18; // [rsp+88h] [rbp+10h]
  BYTE *pSrc; // [rsp+90h] [rbp+18h]
  BYTE *pDest; // [rsp+98h] [rbp+20h]

  v2 = *((int *)a2 + 6);
  v4 = *((int *)a2 + 2);
  v5 = *(_QWORD *)a2;
  v6 = *((_QWORD *)a2 + 2);
  v7 = a1->top & 0xFFFFFFFE;
  v8 = a1->left & 0xFFFFFFFE;
  v9 = (*((_DWORD *)a2 + 24) + *((_DWORD *)a2 + 26)) >> 1;
  dwWidthInBytes = (a1->right & 0xFFFFFFFE) - v8;
  v18 = (int)(a1->bottom & 0xFFFFFFFE) / 2;
  v11 = ((*((_DWORD *)a2 + 21) + *((_DWORD *)a2 + 23)) >> 1) + ((*((_DWORD *)a2 + 25) + *((_DWORD *)a2 + 27)) >> 1);
  v12 = (*((_DWORD *)a2 + 20) + *((_DWORD *)a2 + 22)) >> 1;
  v13 = (const BYTE *)(v6 + v12 + (int)v2 * (v11 - 1) - v9 - (__int64)(int)(v2 * v7 - v8));
  v14 = (BYTE *)(v5 + (int)(v8 + v4 * v7));
  pSrc = (BYTE *)(v6
                + v12
                + (int)v2 * ((v11 >> 1) - 1)
                - v9
                - (__int64)(int)(v2 * (v7 / 2) - v8)
                + *((_DWORD *)a2 + 7) * (int)v2);
  v15 = *((_DWORD *)a2 + 3) * v4;
  v16 = v7 / 2;
  for ( pDest = (BYTE *)(v5 + (int)(v8 + v4 * (v7 / 2)) + v15); v16 < v18; ++v16 )
  {
    MFCopyImage(v14, v4, v13, v2, dwWidthInBytes, 1u);
    MFCopyImage(&v14[v4], v4, &v13[-v2], v2, dwWidthInBytes, 1u);
    MFCopyImage(pDest, v4, pSrc, v2, dwWidthInBytes, 1u);
    pSrc -= v2;
    pDest += v4;
    v14 += 2 * v4;
    v13 -= 2 * v2;
  }
  return 0;
}

```

## disassembly

```asm
0x18009a780  push    rbx
0x18009a782  push    rbp
0x18009a783  push    rsi
0x18009a784  push    rdi
0x18009a785  push    r12
0x18009a787  push    r13
0x18009a789  push    r14
0x18009a78b  push    r15
0x18009a78d  sub     rsp, 38h
0x18009a791  movsxd  rbp, dword ptr [rdx+18h]
0x18009a795  mov     rsi, rdx
0x18009a798  movsxd  r14, dword ptr [rdx+8]
0x18009a79c  mov     r8d, 2
0x18009a7a2  mov     rdi, [rdx]
0x18009a7a5  mov     r10, [rdx+10h]
0x18009a7a9  mov     r11d, [rcx+4]
0x18009a7ad  mov     ebx, [rcx]
0x18009a7af  and     r11d, 0FFFFFFFEh
0x18009a7b3  mov     r13d, [rcx+8]
0x18009a7b7  mov     eax, r11d
0x18009a7ba  cdq
0x18009a7bb  mov     r9d, [rsi+68h]
0x18009a7bf  idiv    r8d
0x18009a7c2  add     r9d, [rsi+60h]
0x18009a7c6  and     ebx, 0FFFFFFFEh
0x18009a7c9  mov     r12d, eax
0x18009a7cc  mov     [rsp+78h+arg_0], eax
0x18009a7d3  mov     eax, [rcx+0Ch]
0x18009a7d6  and     r13d, 0FFFFFFFEh
0x18009a7da  and     eax, 0FFFFFFFEh
0x18009a7dd  sar     r9d, 1
0x18009a7e0  cdq
0x18009a7e1  sub     r13d, ebx
0x18009a7e4  idiv    r8d
0x18009a7e7  mov     edx, [rsi+6Ch]
0x18009a7ea  add     edx, [rsi+64h]
0x18009a7ed  mov     r8d, [rsi+58h]
0x18009a7f1  add     r8d, [rsi+50h]
0x18009a7f5  mov     [rsp+78h+arg_8], eax
0x18009a7fc  mov     eax, [rsi+5Ch]
0x18009a7ff  add     eax, [rsi+54h]
0x18009a802  sar     eax, 1
0x18009a804  sar     edx, 1
0x18009a806  add     edx, eax
0x18009a808  sar     r8d, 1
0x18009a80b  lea     eax, [rdx-1]
0x18009a80e  sar     edx, 1
0x18009a810  imul    eax, ebp
0x18009a813  dec     edx
0x18009a815  imul    edx, ebp
0x18009a818  sub     eax, r9d
0x18009a81b  add     eax, r8d
0x18009a81e  sub     edx, r9d
0x18009a821  movsxd  r15, eax
0x18009a824  add     edx, r8d
0x18009a827  movsxd  rcx, edx
0x18009a82a  mov     eax, r11d
0x18009a82d  imul    eax, ebp
0x18009a830  imul    r11d, r14d
0x18009a834  sub     eax, ebx
0x18009a836  cdqe
0x18009a838  add     r11d, ebx
0x18009a83b  sub     r15, rax
0x18009a83e  mov     eax, r12d
0x18009a841  imul    eax, ebp
0x18009a844  add     r15, r10
0x18009a847  movsxd  r12, r11d
0x18009a84a  add     r12, rdi
0x18009a84d  sub     eax, ebx
0x18009a84f  cdqe
0x18009a851  sub     rcx, rax
0x18009a854  mov     eax, ebp
0x18009a856  imul    eax, [rsi+1Ch]
0x18009a85a  movsxd  rdx, eax
0x18009a85d  lea     rax, [r10+rcx]
0x18009a861  add     rdx, rax
0x18009a864  mov     eax, [rsp+78h+arg_0]
0x18009a86b  imul    eax, r14d
0x18009a86f  mov     [rsp+78h+pSrc], rdx
0x18009a877  add     eax, ebx
0x18009a879  movsxd  rcx, eax
0x18009a87c  mov     eax, r14d
0x18009a87f  imul    eax, [rsi+0Ch]
0x18009a883  mov     esi, [rsp+78h+arg_0]
0x18009a88a  movsxd  rdx, eax
0x18009a88d  lea     rax, [rdi+rcx]
0x18009a891  add     rdx, rax
0x18009a894  mov     [rsp+78h+pDest], rdx
0x18009a89c  cmp     esi, [rsp+78h+arg_8]
0x18009a8a3  jge     loc_18009A945
0x18009a8a9  mov     rbx, rbp
0x18009a8ac  mov     [rsp+78h+dwLines], 1; dwLines
0x18009a8b4  mov     r9d, ebp; lSrcStride
0x18009a8b7  mov     r8, r15; pSrc
0x18009a8ba  mov     [rsp+78h+dwWidthInBytes], r13d; dwWidthInBytes
0x18009a8bf  mov     edx, r14d; lDestStride
0x18009a8c2  mov     rcx, r12; pDest
0x18009a8c5  call    cs:__imp_MFCopyImage
0x18009a8cb  mov     r8, r15
0x18009a8ce  mov     [rsp+78h+dwLines], 1; dwLines
0x18009a8d6  sub     r8, rbx; pSrc
0x18009a8d9  mov     [rsp+78h+dwWidthInBytes], r13d; dwWidthInBytes
0x18009a8de  lea     rcx, [r14+r12]; pDest
0x18009a8e2  mov     r9d, ebp; lSrcStride
0x18009a8e5  mov     edx, r14d; lDestStride
0x18009a8e8  call    cs:__imp_MFCopyImage
0x18009a8ee  mov     r8, [rsp+78h+pSrc]; pSrc
0x18009a8f6  mov     r9d, ebp; lSrcStride
0x18009a8f9  mov     rcx, [rsp+78h+pDest]; pDest
0x18009a901  mov     edx, r14d; lDestStride
0x18009a904  mov     [rsp+78h+dwLines], 1; dwLines
0x18009a90c  mov     [rsp+78h+dwWidthInBytes], r13d; dwWidthInBytes
0x18009a911  call    cs:__imp_MFCopyImage
0x18009a917  sub     [rsp+78h+pSrc], rbx
0x18009a91f  lea     rax, ds:0[rbp*2]
0x18009a927  add     [rsp+78h+pDest], r14
0x18009a92f  lea     r12, [r12+r14*2]
0x18009a933  sub     r15, rax
0x18009a936  inc     esi
0x18009a938  cmp     esi, [rsp+78h+arg_8]
0x18009a93f  jl      loc_18009A8AC
0x18009a945  xor     eax, eax
0x18009a947  add     rsp, 38h
0x18009a94b  pop     r15
0x18009a94d  pop     r14
0x18009a94f  pop     r13
0x18009a951  pop     r12
0x18009a953  pop     rdi
0x18009a954  pop     rsi
0x18009a955  pop     rbp
0x18009a956  pop     rbx
0x18009a957  retn
```
