# ReadTableIntoStructure

- ea: `0x1800168d0`
- end: `0x180016dd0`
- name: `ReadTableIntoStructure`
- size: `1280`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800154a4`

## callees

- `0x1800168d0`
- `0x18001a3bc`
- `0x18001a680`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall ReadTableIntoStructure(__int16 *a1, __int64 a2, _WORD *a3)
{
  unsigned int v4; // r15d
  __int16 v6; // r13
  __int16 v8; // si
  __int64 v9; // r14
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  __int64 result; // rax
  unsigned int v15; // r10d
  unsigned __int16 i; // r15
  int v17; // r10d
  unsigned int v18; // esi
  unsigned __int16 v19; // r15
  unsigned __int16 v20; // r13
  unsigned int v21; // esi
  int v22; // r8d
  int v23; // r10d
  __int16 v24; // si
  unsigned int v25; // r15d
  unsigned __int16 v26; // r13
  unsigned __int16 v27; // si
  unsigned __int16 j; // r10
  __int16 v29; // r10
  int v30; // r8d
  int v31; // r9d
  unsigned __int16 v32; // r8
  unsigned __int16 v33; // si
  _WORD v34[2]; // [rsp+30h] [rbp-40h] BYREF
  _WORD v35[2]; // [rsp+34h] [rbp-3Ch] BYREF
  int v36; // [rsp+38h] [rbp-38h] BYREF
  _OWORD v37[2]; // [rsp+40h] [rbp-30h] BYREF

  v4 = *((_DWORD *)a1 + 1) + *((_DWORD *)a1 + 9);
  v6 = *a1;
  v8 = a1[1];
  v9 = *((_QWORD *)a1 + 6);
  v34[0] = 0;
  v35[0] = 0;
  LOWORD(v36) = 0;
  if ( !*a3 )
  {
    *(_WORD *)a2 = a1[4];
    *(_WORD *)(a2 + 2) = a1[5];
  }
  v10 = (unsigned __int16)a1[4] - 1;
  if ( !v10 )
    return 0;
  v11 = v10 - 1;
  if ( !v11 )
  {
    memset(v37, 0, 20);
    result = ReadGeneric(v9, (__int64)v37, 0x14u, (unsigned __int8 *)INDEXSUBTABLE2_CONTROL, v4, v34);
    if ( (_WORD)result )
      return result;
    v31 = DWORD2(v37[0]);
    if ( !*a3 )
    {
      *(_QWORD *)(a2 + 24) = *(_QWORD *)((char *)v37 + 12);
      *(_DWORD *)(a2 + 4) = v31;
    }
    v32 = 0;
    v33 = v8 - v6 + 1;
    while ( v32 < v33 )
    {
      if ( *a3 >= *(_WORD *)(a2 + 8) )
        return 1086;
      *(_WORD *)(32LL * (unsigned __int16)*a3 + *(_QWORD *)(a2 + 16) + 16) = v32 + v6;
      *(_DWORD *)(32LL * (unsigned __int16)*a3 + *(_QWORD *)(a2 + 16) + 12) = v31;
      *(_DWORD *)(32LL * (unsigned __int16)*a3 + *(_QWORD *)(a2 + 16) + 8) = *((_DWORD *)a1 + 3)
                                                                           + *((_DWORD *)a1 + 7)
                                                                           + v31 * v32;
      *(_QWORD *)(32LL * (unsigned __int16)*a3 + *(_QWORD *)(a2 + 16)) = v9;
      *(_QWORD *)(32LL * (unsigned __int16)(*a3)++ + *(_QWORD *)(a2 + 16) + 24) = *((_QWORD *)a1 + 7);
      ++v32;
    }
    return 0;
  }
  v12 = v11 - 1;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      if ( v13 != 1 )
        return 1086;
      v35[0] = 0;
      memset(v37, 0, 28);
      result = ReadGeneric(v9, (__int64)v37, 0x18u, (unsigned __int8 *)INDEXSUBTABLE5_CONTROL, v4, v34);
      if ( (_WORD)result )
        return result;
      v15 = v4 + v34[0];
      if ( !*a3 )
      {
        *(_DWORD *)(a2 + 4) = DWORD2(v37[0]);
        *(_QWORD *)(a2 + 24) = *(_QWORD *)((char *)v37 + 12);
      }
      for ( i = 0; (unsigned int)i < DWORD1(v37[1]); ++i )
      {
        result = ReadWord(v9, (__int64)v35, v15);
        if ( (_WORD)result )
          return result;
        if ( *a3 >= *(_WORD *)(a2 + 8) )
          return 1086;
        v15 = v17 + 2;
        *(_WORD *)(32LL * (unsigned __int16)*a3 + *(_QWORD *)(a2 + 16) + 16) = v35[0];
        *(_DWORD *)(32LL * (unsigned __int16)*a3 + *(_QWORD *)(a2 + 16) + 12) = *(_DWORD *)(a2 + 4);
        *(_DWORD *)(32LL * (unsigned __int16)*a3 + *(_QWORD *)(a2 + 16) + 8) = *((_DWORD *)a1 + 3)
                                                                             + *((_DWORD *)a1 + 7)
                                                                             + *(_DWORD *)(a2 + 4) * i;
        *(_QWORD *)(32LL * (unsigned __int16)*a3 + *(_QWORD *)(a2 + 16)) = v9;
        *(_QWORD *)(32LL * (unsigned __int16)(*a3)++ + *(_QWORD *)(a2 + 16) + 24) = *((_QWORD *)a1 + 7);
      }
      return 0;
    }
    v36 = 0;
    v37[0] = 0;
    result = ReadGeneric(v9, (__int64)v37, 0xCu, (unsigned __int8 *)&INDEXSUBTABLE4_CONTROL, v4, v34);
    if ( !(_WORD)result )
    {
      v18 = v4 + v34[0];
      result = ReadGeneric(v9, (__int64)&v36, 4u, (unsigned __int8 *)&CODEOFFSETPAIR_CONTROL, v18, v34);
      if ( !(_WORD)result )
      {
        v19 = 0;
        v20 = HIWORD(v36);
        v21 = v34[0] + v18;
        while ( (unsigned int)v19 < DWORD2(v37[0]) )
        {
          if ( *a3 >= *(_WORD *)(a2 + 8) )
            return 1086;
          *(_WORD *)(32LL * (unsigned __int16)*a3 + *(_QWORD *)(a2 + 16) + 16) = v36;
          result = ReadGeneric(v9, (__int64)&v36, 4u, (unsigned __int8 *)&CODEOFFSETPAIR_CONTROL, v21, v34);
          if ( (_WORD)result )
            return result;
          v21 += v34[0];
          v22 = v20;
          v20 = HIWORD(v36);
          *(_DWORD *)(32LL * (unsigned __int16)*a3 + *(_QWORD *)(a2 + 16) + 12) = HIWORD(v36) - v22;
          *(_DWORD *)(32LL * (unsigned __int16)*a3 + *(_QWORD *)(a2 + 16) + 8) = v22
                                                                               + *((_DWORD *)a1 + 3)
                                                                               + *((_DWORD *)a1 + 7);
          *(_QWORD *)(32LL * (unsigned __int16)*a3 + *(_QWORD *)(a2 + 16)) = v9;
          *(_QWORD *)(32LL * (unsigned __int16)(*a3)++ + *(_QWORD *)(a2 + 16) + 24) = *((_QWORD *)a1 + 7);
          ++v19;
        }
        return 0;
      }
    }
  }
  else
  {
    *(_QWORD *)&v37[0] = 0;
    DWORD2(v37[0]) = 0;
    result = ReadGeneric(v9, (__int64)v37, 8u, (unsigned __int8 *)INDEXSUBTABLE3_CONTROL, v4, v34);
    if ( !(_WORD)result )
    {
      result = ReadWord(v9, (__int64)v35, v4 + v34[0]);
      if ( !(_WORD)result )
      {
        v24 = v8 - v6;
        v25 = v23 + 2;
        v26 = v35[0];
        v27 = v24 + 1;
        for ( j = 0; j < v27; j = v29 + 1 )
        {
          result = ReadWord(v9, (__int64)&v36, v25);
          if ( (_WORD)result )
            return result;
          if ( *a3 >= *(_WORD *)(a2 + 8) )
            return 1086;
          v30 = v26;
          v25 += 2;
          v26 = v36;
          *(_DWORD *)(32LL * (unsigned __int16)*a3 + *(_QWORD *)(a2 + 16) + 12) = (unsigned __int16)v36 - v30;
          *(_DWORD *)(32LL * (unsigned __int16)*a3 + *(_QWORD *)(a2 + 16) + 8) = v30
                                                                               + *((_DWORD *)a1 + 3)
                                                                               + *((_DWORD *)a1 + 7);
          *(_QWORD *)(32LL * (unsigned __int16)*a3 + *(_QWORD *)(a2 + 16)) = v9;
          *(_QWORD *)(32LL * (unsigned __int16)(*a3)++ + *(_QWORD *)(a2 + 16) + 24) = *((_QWORD *)a1 + 7);
        }
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800168d0  mov     [rsp-38h+arg_18], rbx
0x1800168d5  push    rbp
0x1800168d6  push    rsi
0x1800168d7  push    rdi
0x1800168d8  push    r12
0x1800168da  push    r13
0x1800168dc  push    r14
0x1800168de  push    r15
0x1800168e0  mov     rbp, rsp
0x1800168e3  sub     rsp, 70h
0x1800168e7  mov     rax, cs:__security_cookie
0x1800168ee  xor     rax, rsp
0x1800168f1  mov     [rbp+var_10], rax
0x1800168f5  mov     r15d, [rcx+24h]
0x1800168f9  mov     rbx, rdx
0x1800168fc  add     r15d, [rcx+4]
0x180016900  xor     edx, edx
0x180016902  mov     rdi, r8
0x180016905  movzx   r13d, word ptr [rcx]
0x180016909  mov     r12, rcx
0x18001690c  movzx   esi, word ptr [rcx+2]
0x180016910  mov     r14, [rcx+30h]
0x180016914  mov     [rbp+var_40], dx
0x180016918  mov     [rbp+var_3C], dx
0x18001691c  mov     word ptr [rbp+var_38], dx
0x180016920  cmp     [r8], dx
0x180016924  jnz     short loc_180016935
0x180016926  movzx   eax, word ptr [rcx+8]
0x18001692a  mov     [rbx], ax
0x18001692d  movzx   eax, word ptr [rcx+0Ah]
0x180016931  mov     [rbx+2], ax
0x180016935  movzx   ecx, word ptr [rcx+8]
0x180016939  sub     ecx, 1
0x18001693c  jz      loc_180016DAA
0x180016942  sub     ecx, 1
0x180016945  jz      loc_180016CBF
0x18001694b  sub     ecx, 1
0x18001694e  jz      loc_180016BB7
0x180016954  sub     ecx, 1
0x180016957  jz      loc_180016A6B
0x18001695d  cmp     ecx, 1
0x180016960  jnz     loc_180016DA1
0x180016966  xorps   xmm0, xmm0
0x180016969  mov     [rbp+var_3C], dx
0x18001696d  lea     rax, [rbp+var_40]
0x180016971  lea     r8d, [rcx+17h]
0x180016975  mov     [rsp+70h+var_48], rax
0x18001697a  movups  [rbp+var_30], xmm0
0x18001697e  lea     r9, INDEXSUBTABLE5_CONTROL
0x180016985  mov     [rsp+70h+var_50], r15d
0x18001698a  lea     rdx, [rbp+var_30]
0x18001698e  mov     rcx, r14
0x180016991  movups  [rbp+var_30+0Ch], xmm0
0x180016995  call    ReadGeneric
0x18001699a  xor     edx, edx
0x18001699c  test    ax, ax
0x18001699f  jnz     loc_180016DAC
0x1800169a5  movzx   r10d, [rbp+var_40]
0x1800169aa  add     r10d, r15d
0x1800169ad  cmp     [rdi], dx
0x1800169b0  jnz     short loc_1800169C0
0x1800169b2  mov     eax, dword ptr [rbp+var_30+8]
0x1800169b5  mov     [rbx+4], eax
0x1800169b8  mov     rax, qword ptr [rbp+var_30+0Ch]
0x1800169bc  mov     [rbx+18h], rax
0x1800169c0  mov     r15d, edx
0x1800169c3  movzx   esi, r15w
0x1800169c7  cmp     esi, [rbp+var_1C]
0x1800169ca  jnb     loc_180016DA8
0x1800169d0  mov     r8d, r10d
0x1800169d3  lea     rdx, [rbp+var_3C]
0x1800169d7  mov     rcx, r14
0x1800169da  call    ReadWord
0x1800169df  test    ax, ax
0x1800169e2  jnz     loc_180016DAC
0x1800169e8  movzx   eax, word ptr [rdi]
0x1800169eb  cmp     ax, [rbx+8]
0x1800169ef  jnb     loc_180016DA1
0x1800169f5  mov     rcx, [rbx+10h]
0x1800169f9  mov     edx, eax
0x1800169fb  movzx   eax, [rbp+var_3C]
0x1800169ff  add     r10d, 2
0x180016a03  shl     rdx, 5
0x180016a07  mov     [rdx+rcx+10h], ax
0x180016a0c  movzx   edx, word ptr [rdi]
0x180016a0f  mov     rcx, [rbx+10h]
0x180016a13  mov     eax, [rbx+4]
0x180016a16  shl     rdx, 5
0x180016a1a  mov     [rdx+rcx+0Ch], eax
0x180016a1e  imul    esi, [rbx+4]
0x180016a22  movzx   ecx, word ptr [rdi]
0x180016a25  mov     rax, [rbx+10h]
0x180016a29  shl     rcx, 5
0x180016a2d  add     esi, [r12+1Ch]
0x180016a32  add     esi, [r12+0Ch]
0x180016a37  mov     [rcx+rax+8], esi
0x180016a3b  movzx   ecx, word ptr [rdi]
0x180016a3e  mov     rax, [rbx+10h]
0x180016a42  shl     rcx, 5
0x180016a46  mov     [rcx+rax], r14
0x180016a4a  movzx   edx, word ptr [rdi]
0x180016a4d  mov     rcx, [rbx+10h]
0x180016a51  mov     rax, [r12+38h]
0x180016a56  shl     rdx, 5
0x180016a5a  mov     [rdx+rcx+18h], rax
0x180016a5f  inc     word ptr [rdi]
0x180016a62  inc     r15w
0x180016a66  jmp     loc_1800169C3
0x180016a6b  lea     rax, [rbp+var_40]
0x180016a6f  mov     [rbp+var_38], edx
0x180016a72  xorps   xmm0, xmm0
0x180016a75  mov     [rsp+70h+var_48], rax
0x180016a7a  mov     r8d, 0Ch
0x180016a80  mov     [rsp+70h+var_50], r15d
0x180016a85  lea     r9, INDEXSUBTABLE4_CONTROL
0x180016a8c  mov     rcx, r14
0x180016a8f  lea     rdx, [rbp+var_30]
0x180016a93  movups  [rbp+var_30], xmm0
0x180016a97  call    ReadGeneric
0x180016a9c  test    ax, ax
0x180016a9f  jnz     loc_180016DAC
0x180016aa5  movzx   esi, [rbp+var_40]
0x180016aa9  lea     rax, [rbp+var_40]
0x180016aad  mov     [rsp+70h+var_48], rax
0x180016ab2  lea     r9, CODEOFFSETPAIR_CONTROL
0x180016ab9  add     esi, r15d
0x180016abc  lea     rdx, [rbp+var_38]
0x180016ac0  mov     r8d, 4
0x180016ac6  mov     [rsp+70h+var_50], esi
0x180016aca  mov     rcx, r14
0x180016acd  call    ReadGeneric
0x180016ad2  xor     edx, edx
0x180016ad4  test    ax, ax
0x180016ad7  jnz     loc_180016DAC
0x180016add  movzx   eax, [rbp+var_40]
0x180016ae1  mov     r15d, edx
0x180016ae4  movzx   r13d, word ptr [rbp+var_38+2]
0x180016ae9  add     esi, eax
0x180016aeb  movzx   eax, r15w
0x180016aef  cmp     eax, dword ptr [rbp+var_30+8]
0x180016af2  jnb     loc_180016DA8
0x180016af8  movzx   eax, word ptr [rdi]
0x180016afb  cmp     ax, [rbx+8]
0x180016aff  jnb     loc_180016DA1
0x180016b05  mov     rcx, [rbx+10h]
0x180016b09  lea     r9, CODEOFFSETPAIR_CONTROL
0x180016b10  mov     edx, eax
0x180016b12  mov     r8d, 4
0x180016b18  movzx   eax, word ptr [rbp+var_38]
0x180016b1c  shl     rdx, 5
0x180016b20  mov     [rdx+rcx+10h], ax
0x180016b25  lea     rax, [rbp+var_40]
0x180016b29  mov     [rsp+70h+var_48], rax
0x180016b2e  lea     rdx, [rbp+var_38]
0x180016b32  mov     rcx, r14
0x180016b35  mov     [rsp+70h+var_50], esi
0x180016b39  call    ReadGeneric
0x180016b3e  test    ax, ax
0x180016b41  jnz     loc_180016DAC
0x180016b47  movzx   ecx, word ptr [rdi]
0x180016b4a  movzx   eax, [rbp+var_40]
0x180016b4e  shl     rcx, 5
0x180016b52  add     esi, eax
0x180016b54  mov     rax, [rbx+10h]
0x180016b58  movzx   r8d, r13w
0x180016b5c  movzx   r13d, word ptr [rbp+var_38+2]
0x180016b61  mov     edx, r13d
0x180016b64  sub     edx, r8d
0x180016b67  mov     [rcx+rax+0Ch], edx
0x180016b6b  mov     edx, [r12+1Ch]
0x180016b70  add     edx, [r12+0Ch]
0x180016b75  movzx   ecx, word ptr [rdi]
0x180016b78  add     edx, r8d
0x180016b7b  mov     rax, [rbx+10h]
0x180016b7f  shl     rcx, 5
0x180016b83  mov     [rcx+rax+8], edx
0x180016b87  movzx   ecx, word ptr [rdi]
0x180016b8a  mov     rax, [rbx+10h]
0x180016b8e  shl     rcx, 5
0x180016b92  mov     [rcx+rax], r14
0x180016b96  movzx   edx, word ptr [rdi]
0x180016b99  mov     rcx, [rbx+10h]
0x180016b9d  mov     rax, [r12+38h]
0x180016ba2  shl     rdx, 5
0x180016ba6  mov     [rdx+rcx+18h], rax
0x180016bab  inc     word ptr [rdi]
0x180016bae  inc     r15w
0x180016bb2  jmp     loc_180016AEB
0x180016bb7  xor     eax, eax
0x180016bb9  lea     r9, INDEXSUBTABLE3_CONTROL
0x180016bc0  mov     qword ptr [rbp+var_30], rax
0x180016bc4  lea     rdx, [rbp+var_30]
0x180016bc8  mov     dword ptr [rbp+var_30+8], eax
0x180016bcb  mov     rcx, r14
0x180016bce  lea     r8d, [rax+8]
0x180016bd2  lea     rax, [rbp+var_40]
0x180016bd6  mov     [rsp+70h+var_48], rax
0x180016bdb  mov     [rsp+70h+var_50], r15d
0x180016be0  call    ReadGeneric
0x180016be5  test    ax, ax
0x180016be8  jnz     loc_180016DAC
0x180016bee  movzx   r10d, [rbp+var_40]
0x180016bf3  lea     rdx, [rbp+var_3C]
0x180016bf7  add     r10d, r15d
0x180016bfa  mov     rcx, r14
0x180016bfd  mov     r8d, r10d
0x180016c00  call    ReadWord
0x180016c05  xor     edx, edx
0x180016c07  test    ax, ax
0x180016c0a  jnz     loc_180016DAC
0x180016c10  sub     si, r13w
0x180016c14  lea     r15d, [r10+2]
0x180016c18  movzx   r13d, [rbp+var_3C]
0x180016c1d  inc     si
0x180016c20  mov     r10d, edx
0x180016c23  cmp     r10w, si
0x180016c27  jnb     loc_180016DA8
0x180016c2d  mov     r8d, r15d
0x180016c30  lea     rdx, [rbp+var_38]
0x180016c34  mov     rcx, r14
0x180016c37  call    ReadWord
0x180016c3c  test    ax, ax
0x180016c3f  jnz     loc_180016DAC
0x180016c45  movzx   eax, word ptr [rdi]
0x180016c48  cmp     ax, [rbx+8]
0x180016c4c  jnb     loc_180016DA1
0x180016c52  mov     ecx, eax
0x180016c54  movzx   r8d, r13w
0x180016c58  mov     rax, [rbx+10h]
0x180016c5c  add     r15d, 2
0x180016c60  movzx   r13d, word ptr [rbp+var_38]
0x180016c65  shl     rcx, 5
0x180016c69  mov     edx, r13d
0x180016c6c  sub     edx, r8d
0x180016c6f  mov     [rcx+rax+0Ch], edx
0x180016c73  mov     edx, [r12+1Ch]
0x180016c78  add     edx, [r12+0Ch]
0x180016c7d  movzx   ecx, word ptr [rdi]
0x180016c80  add     edx, r8d
0x180016c83  mov     rax, [rbx+10h]
0x180016c87  shl     rcx, 5
0x180016c8b  mov     [rcx+rax+8], edx
0x180016c8f  movzx   ecx, word ptr [rdi]
0x180016c92  mov     rax, [rbx+10h]
0x180016c96  shl     rcx, 5
0x180016c9a  mov     [rcx+rax], r14
0x180016c9e  movzx   edx, word ptr [rdi]
0x180016ca1  mov     rcx, [rbx+10h]
0x180016ca5  mov     rax, [r12+38h]
0x180016caa  shl     rdx, 5
0x180016cae  mov     [rdx+rcx+18h], rax
0x180016cb3  inc     word ptr [rdi]
0x180016cb6  inc     r10w
0x180016cba  jmp     loc_180016C23
0x180016cbf  xor     eax, eax
0x180016cc1  lea     r9, INDEXSUBTABLE2_CONTROL
0x180016cc8  mov     [rbp+var_20], eax
0x180016ccb  lea     rdx, [rbp+var_30]
0x180016ccf  xorps   xmm0, xmm0
0x180016cd2  mov     rcx, r14
0x180016cd5  movups  [rbp+var_30], xmm0
0x180016cd9  lea     r8d, [rax+14h]
0x180016cdd  lea     rax, [rbp+var_40]
0x180016ce1  mov     [rsp+70h+var_48], rax
0x180016ce6  mov     [rsp+70h+var_50], r15d
0x180016ceb  call    ReadGeneric
0x180016cf0  xor     edx, edx
0x180016cf2  test    ax, ax
0x180016cf5  jnz     loc_180016DAC
0x180016cfb  mov     r9d, dword ptr [rbp+var_30+8]
0x180016cff  cmp     [rdi], dx
0x180016d02  jnz     short loc_180016D10
0x180016d04  mov     rax, qword ptr [rbp+var_30+0Ch]
0x180016d08  mov     [rbx+18h], rax
0x180016d0c  mov     [rbx+4], r9d
0x180016d10  sub     si, r13w
0x180016d14  mov     r8d, edx
0x180016d17  inc     si
0x180016d1a  cmp     r8w, si
0x180016d1e  jnb     loc_180016DA8
0x180016d24  movzx   eax, word ptr [rdi]
0x180016d27  cmp     ax, [rbx+8]
0x180016d2b  jnb     short loc_180016DA1
0x180016d2d  mov     ecx, eax
0x180016d2f  lea     edx, [r8+r13]
0x180016d33  mov     rax, [rbx+10h]
0x180016d37  shl     rcx, 5
0x180016d3b  mov     [rcx+rax+10h], dx
0x180016d40  movzx   ecx, word ptr [rdi]
0x180016d43  mov     rax, [rbx+10h]
0x180016d47  shl     rcx, 5
0x180016d4b  movzx   edx, r8w
0x180016d4f  imul    edx, r9d
0x180016d53  mov     [rcx+rax+0Ch], r9d
0x180016d58  movzx   ecx, word ptr [rdi]
0x180016d5b  mov     rax, [rbx+10h]
0x180016d5f  add     edx, [r12+1Ch]
0x180016d64  add     edx, [r12+0Ch]
0x180016d69  shl     rcx, 5
0x180016d6d  mov     [rcx+rax+8], edx
  ... truncated ...
```
