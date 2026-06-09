# Mirror_IYUV_Vertical(tagRECT const &,ParameterBase const *)

- ea: `0x18009a2c0`
- end: `0x18009a594`
- name: `?Mirror_IYUV_Vertical@@YAJAEBUtagRECT@@PEBUParameterBase@@@Z`
- size: `724`
- prototype: `__int64 __fastcall(const struct tagRECT *, const struct ParameterBase *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18009a2c0`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x18009a4bc`
- `MFPlat!MFCopyImage` at `0x18009a4eb`
- `MFPlat!MFCopyImage` at `0x18009a50f`
- `MFPlat!MFCopyImage` at `0x18009a533`
- `MFPlat!MFCopyImage` at `0x18009a4bc`
- `MFPlat!MFCopyImage` at `0x18009a4eb`
- `MFPlat!MFCopyImage` at `0x18009a50f`
- `MFPlat!MFCopyImage` at `0x18009a533`

## pseudocode

```c
__int64 __fastcall Mirror_IYUV_Vertical(const struct tagRECT *a1, const struct ParameterBase *a2)
{
  __int64 v3; // rdi
  signed int v4; // r12d
  signed int v5; // r15d
  __int64 v6; // r13
  int v7; // esi
  int v8; // r9d
  int v9; // ebp
  __int64 v10; // r14
  int v11; // r11d
  int v12; // r8d
  int v13; // edx
  __int64 v14; // rbx
  __int64 v15; // r10
  int v16; // eax
  LONG v17; // r9d
  __int64 v18; // r8
  int v19; // eax
  int v20; // r11d
  int v21; // ecx
  const BYTE *v22; // rax
  LONG v23; // r10d
  int v24; // r15d
  __int64 v25; // r12
  BYTE *v26; // rdi
  __int64 v27; // r8
  const BYTE *v28; // rbx
  const BYTE *v29; // r15
  const BYTE *v30; // r13
  int dwWidthInBytes; // [rsp+30h] [rbp-88h]
  int v33; // [rsp+34h] [rbp-84h]
  int v34; // [rsp+38h] [rbp-80h]
  BYTE *pDest; // [rsp+40h] [rbp-78h]
  BYTE *v36; // [rsp+48h] [rbp-70h]
  BYTE *pSrc; // [rsp+50h] [rbp-68h]
  BYTE *v38; // [rsp+60h] [rbp-58h]
  int v39; // [rsp+C0h] [rbp+8h]
  LONG lSrcStride; // [rsp+C8h] [rbp+10h]
  LONG v41; // [rsp+D0h] [rbp+18h]
  LONG lDestStride; // [rsp+D8h] [rbp+20h]

  v3 = *((_QWORD *)a2 + 2);
  v4 = a1->left & 0xFFFFFFFE;
  v41 = *((_DWORD *)a2 + 6) / 2;
  v5 = a1->top & 0xFFFFFFFE;
  v6 = *(_QWORD *)a2;
  lSrcStride = *((_DWORD *)a2 + 6);
  lDestStride = *((_DWORD *)a2 + 2);
  v7 = *((_DWORD *)a2 + 3) * lDestStride;
  v8 = (*((_DWORD *)a2 + 24) + *((_DWORD *)a2 + 26)) >> 1;
  v9 = v4 / 2;
  v10 = *(_QWORD *)a2 + v7;
  v39 = v5 / 2;
  v11 = *((_DWORD *)a2 + 7) * lSrcStride;
  v34 = (int)(a1->bottom & 0xFFFFFFFE) / 2;
  v12 = (*((_DWORD *)a2 + 20) + *((_DWORD *)a2 + 22)) >> 1;
  dwWidthInBytes = (a1->right & 0xFFFFFFFE) - v4;
  v33 = dwWidthInBytes >> 1;
  v13 = ((*((_DWORD *)a2 + 21) + *((_DWORD *)a2 + 23)) >> 1) + ((*((_DWORD *)a2 + 25) + *((_DWORD *)a2 + 27)) >> 1);
  v14 = v3 + v11;
  v15 = ((v12 - v8) >> 1) + v41 * ((v13 >> 1) - 1);
  v16 = lSrcStride * (v13 - 1) - v8;
  v17 = lSrcStride;
  pSrc = (BYTE *)(v3 + v12 + v16 - (__int64)(lSrcStride * v5 - v4));
  v18 = v41 * (v5 / 2) - v4 / 2;
  v38 = (BYTE *)(v15 + v14 - v18);
  v19 = v11;
  v20 = v5 / 2;
  v21 = v5 / 2;
  v22 = (const BYTE *)(v15 + v14 + v19 / 4 - v18);
  v23 = lDestStride;
  v24 = v4 + lDestStride * v5;
  v25 = lDestStride / 2;
  v26 = (BYTE *)(v6 + v24);
  v27 = v9 + lDestStride / 2 * v21;
  pDest = (BYTE *)(v10 + v27);
  v36 = (BYTE *)(v27 + v10 + v7 / 4);
  if ( v20 < v34 )
  {
    v28 = pSrc;
    v29 = v22;
    v30 = v38;
    do
    {
      MFCopyImage(v26, v23, v28, v17, dwWidthInBytes, 1u);
      MFCopyImage(&v26[lDestStride], lDestStride, &v28[-lSrcStride], lSrcStride, dwWidthInBytes, 1u);
      MFCopyImage(pDest, v25, v30, v41, v33, 1u);
      MFCopyImage(v36, v25, v29, v41, v33, 1u);
      v17 = lSrcStride;
      v23 = lDestStride;
      v26 += 2 * lDestStride;
      v28 -= 2 * lSrcStride;
      v30 -= v41;
      v29 -= v41;
      pDest += v25;
      v36 += v25;
      ++v39;
    }
    while ( v39 < v34 );
  }
  return 0;
}

```

## disassembly

```asm
0x18009a2c0  push    rbx
0x18009a2c2  push    rbp
0x18009a2c3  push    rsi
0x18009a2c4  push    rdi
0x18009a2c5  push    r12
0x18009a2c7  push    r13
0x18009a2c9  push    r14
0x18009a2cb  push    r15
0x18009a2cd  sub     rsp, 78h
0x18009a2d1  mov     r9d, [rdx+8]
0x18009a2d5  mov     r10, rdx
0x18009a2d8  mov     r8d, [rdx+18h]
0x18009a2dc  mov     r11d, 2
0x18009a2e2  mov     r12d, [rcx]
0x18009a2e5  mov     eax, r8d
0x18009a2e8  mov     r15d, [rcx+4]
0x18009a2ec  cdq
0x18009a2ed  idiv    r11d
0x18009a2f0  mov     rdi, [r10+10h]
0x18009a2f4  and     r12d, 0FFFFFFFEh
0x18009a2f8  mov     [rsp+0B8h+arg_10], eax
0x18009a2ff  and     r15d, 0FFFFFFFEh
0x18009a303  mov     r13, [r10]
0x18009a306  mov     eax, r9d
0x18009a309  cdq
0x18009a30a  mov     [rsp+0B8h+lSrcStride], r8d
0x18009a312  idiv    r11d
0x18009a315  mov     esi, r9d
0x18009a318  mov     [rsp+0B8h+lDestStride], r9d
0x18009a320  mov     r9d, [r10+68h]
0x18009a324  add     r9d, [r10+60h]
0x18009a328  imul    esi, [r10+0Ch]
0x18009a32d  mov     dword ptr [rsp+0B8h+pDest], eax
0x18009a331  mov     eax, r12d
0x18009a334  cdq
0x18009a335  sar     r9d, 1
0x18009a338  idiv    r11d
0x18009a33b  movsxd  r14, esi
0x18009a33e  mov     ebp, eax
0x18009a340  add     r14, r13
0x18009a343  mov     eax, r15d
0x18009a346  cdq
0x18009a347  idiv    r11d
0x18009a34a  mov     [rsp+0B8h+arg_0], eax
0x18009a351  mov     eax, [rcx+0Ch]
0x18009a354  and     eax, 0FFFFFFFEh
0x18009a357  cdq
0x18009a358  idiv    r11d
0x18009a35b  mov     edx, [r10+6Ch]
0x18009a35f  mov     r11d, r8d
0x18009a362  add     edx, [r10+64h]
0x18009a366  imul    r11d, [r10+1Ch]
0x18009a36b  mov     r8d, [r10+58h]
0x18009a36f  add     r8d, [r10+50h]
0x18009a373  mov     [rsp+0B8h+var_80], eax
0x18009a377  mov     eax, [rcx+8]
0x18009a37a  and     eax, 0FFFFFFFEh
0x18009a37d  sar     edx, 1
0x18009a37f  sub     eax, r12d
0x18009a382  sar     r8d, 1
0x18009a385  mov     [rsp+0B8h+var_88], eax
0x18009a389  sar     eax, 1
0x18009a38b  mov     [rsp+0B8h+var_84], eax
0x18009a38f  mov     eax, [r10+5Ch]
0x18009a393  add     eax, [r10+54h]
0x18009a397  sar     eax, 1
0x18009a399  add     edx, eax
0x18009a39b  movsxd  rbx, r11d
0x18009a39e  mov     ecx, edx
0x18009a3a0  mov     eax, r8d
0x18009a3a3  sub     eax, r9d
0x18009a3a6  sar     ecx, 1
0x18009a3a8  sar     eax, 1
0x18009a3aa  dec     ecx
0x18009a3ac  imul    ecx, [rsp+0B8h+arg_10]
0x18009a3b4  add     rbx, rdi
0x18009a3b7  add     ecx, eax
0x18009a3b9  lea     eax, [rdx-1]
0x18009a3bc  imul    eax, [rsp+0B8h+lSrcStride]
0x18009a3c4  movsxd  r10, ecx
0x18009a3c7  sub     eax, r9d
0x18009a3ca  movsxd  r9, [rsp+0B8h+lSrcStride]; lSrcStride
0x18009a3d2  add     eax, r8d
0x18009a3d5  movsxd  rdx, eax
0x18009a3d8  mov     eax, r15d
0x18009a3db  imul    eax, r9d
0x18009a3df  sub     eax, r12d
0x18009a3e2  movsxd  rcx, eax
0x18009a3e5  sub     rdx, rcx
0x18009a3e8  add     rdx, rdi
0x18009a3eb  mov     ecx, [rsp+0B8h+arg_0]
0x18009a3f2  mov     rax, rbx
0x18009a3f5  imul    ecx, [rsp+0B8h+arg_10]
0x18009a3fd  mov     [rsp+0B8h+pSrc], rdx
0x18009a402  sub     ecx, ebp
0x18009a404  movsxd  r8, ecx
0x18009a407  mov     ecx, 4
0x18009a40c  sub     rax, r8
0x18009a40f  add     rax, r10
0x18009a412  mov     [rsp+0B8h+var_58], rax
0x18009a417  mov     eax, r11d
0x18009a41a  mov     r11d, [rsp+0B8h+arg_0]
0x18009a422  cdq
0x18009a423  idiv    ecx
0x18009a425  mov     ecx, r11d
0x18009a428  cdqe
0x18009a42a  sub     rax, r8
0x18009a42d  add     rax, rbx
0x18009a430  add     rax, r10
0x18009a433  movsxd  r10, [rsp+0B8h+lDestStride]
0x18009a43b  mov     [rsp+0B8h+var_60], rax
0x18009a440  imul    r15d, r10d
0x18009a444  add     r15d, r12d
0x18009a447  movsxd  r12, dword ptr [rsp+0B8h+pDest]
0x18009a44c  imul    ecx, r12d
0x18009a450  movsxd  rdi, r15d
0x18009a453  add     rdi, r13
0x18009a456  add     ecx, ebp
0x18009a458  movsxd  r8, ecx
0x18009a45b  mov     ecx, 4
0x18009a460  lea     rax, [r14+r8]
0x18009a464  mov     [rsp+0B8h+pDest], rax
0x18009a469  mov     eax, esi
0x18009a46b  cdq
0x18009a46c  idiv    ecx
0x18009a46e  cdqe
0x18009a470  add     rax, r14
0x18009a473  add     rax, r8
0x18009a476  mov     [rsp+0B8h+var_70], rax
0x18009a47b  cmp     r11d, [rsp+0B8h+var_80]
0x18009a480  jge     loc_18009A581
0x18009a486  movsxd  rbp, [rsp+0B8h+arg_10]
0x18009a48e  mov     rsi, r9
0x18009a491  mov     rbx, [rsp+0B8h+pSrc]
0x18009a496  mov     r14, r10
0x18009a499  mov     r15, [rsp+0B8h+var_60]
0x18009a49e  mov     r13, [rsp+0B8h+var_58]
0x18009a4a3  mov     eax, [rsp+0B8h+var_88]
0x18009a4a7  mov     r8, rbx; pSrc
0x18009a4aa  mov     [rsp+0B8h+dwLines], 1; dwLines
0x18009a4b2  mov     edx, r10d; lDestStride
0x18009a4b5  mov     rcx, rdi; pDest
0x18009a4b8  mov     [rsp+0B8h+dwWidthInBytes], eax; dwWidthInBytes
0x18009a4bc  call    cs:__imp_MFCopyImage
0x18009a4c2  mov     eax, [rsp+0B8h+var_88]
0x18009a4c6  lea     rcx, [r14+rdi]; pDest
0x18009a4ca  mov     r9d, [rsp+0B8h+lSrcStride]; lSrcStride
0x18009a4d2  mov     r8, rbx
0x18009a4d5  mov     edx, [rsp+0B8h+lDestStride]; lDestStride
0x18009a4dc  sub     r8, rsi; pSrc
0x18009a4df  mov     [rsp+0B8h+dwLines], 1; dwLines
0x18009a4e7  mov     [rsp+0B8h+dwWidthInBytes], eax; dwWidthInBytes
0x18009a4eb  call    cs:__imp_MFCopyImage
0x18009a4f1  mov     eax, [rsp+0B8h+var_84]
0x18009a4f5  mov     r9d, ebp; lSrcStride
0x18009a4f8  mov     rcx, [rsp+0B8h+pDest]; pDest
0x18009a4fd  mov     r8, r13; pSrc
0x18009a500  mov     edx, r12d; lDestStride
0x18009a503  mov     [rsp+0B8h+dwLines], 1; dwLines
0x18009a50b  mov     [rsp+0B8h+dwWidthInBytes], eax; dwWidthInBytes
0x18009a50f  call    cs:__imp_MFCopyImage
0x18009a515  mov     eax, [rsp+0B8h+var_84]
0x18009a519  mov     r9d, ebp; lSrcStride
0x18009a51c  mov     rcx, [rsp+0B8h+var_70]; pDest
0x18009a521  mov     r8, r15; pSrc
0x18009a524  mov     edx, r12d; lDestStride
0x18009a527  mov     [rsp+0B8h+dwLines], 1; dwLines
0x18009a52f  mov     [rsp+0B8h+dwWidthInBytes], eax; dwWidthInBytes
0x18009a533  call    cs:__imp_MFCopyImage
0x18009a539  mov     r9d, [rsp+0B8h+lSrcStride]
0x18009a541  lea     rax, [rsi+rsi]
0x18009a545  mov     r10d, [rsp+0B8h+lDestStride]
0x18009a54d  lea     rdi, [rdi+r14*2]
0x18009a551  sub     rbx, rax
0x18009a554  sub     r13, rbp
0x18009a557  mov     rax, r12
0x18009a55a  sub     r15, rbp
0x18009a55d  add     [rsp+0B8h+pDest], rax
0x18009a562  add     [rsp+0B8h+var_70], rax
0x18009a567  mov     eax, [rsp+0B8h+arg_0]
0x18009a56e  inc     eax
0x18009a570  mov     [rsp+0B8h+arg_0], eax
0x18009a577  cmp     eax, [rsp+0B8h+var_80]
0x18009a57b  jl      loc_18009A4A3
0x18009a581  xor     eax, eax
0x18009a583  add     rsp, 78h
0x18009a587  pop     r15
0x18009a589  pop     r14
0x18009a58b  pop     r13
0x18009a58d  pop     r12
0x18009a58f  pop     rdi
0x18009a590  pop     rsi
0x18009a591  pop     rbp
0x18009a592  pop     rbx
0x18009a593  retn
```
