# std::_Copy_vbool<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>>(std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>)

- ea: `0x18001b718`
- end: `0x18001bb70`
- name: `??$_Copy_vbool@V?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@V12@@std@@YA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@0@V10@00@Z`
- size: `1112`
- prototype: `_OWORD *__fastcall(_OWORD *, _QWORD *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c5d0`

## callees

- `0x1800029c1`
- `0x18001b718`

## pseudocode

```c
_OWORD *__fastcall std::_Copy_vbool<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>>(
        _OWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4)
{
  unsigned __int64 *v5; // r13
  unsigned int *v6; // r9
  unsigned __int64 *v7; // r11
  unsigned int *v9; // rcx
  unsigned __int64 v10; // r10
  __int64 *v11; // rdx
  unsigned __int64 v12; // rsi
  int *v13; // r8
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rdi
  unsigned __int64 v20; // rdx
  int v21; // r9d
  unsigned int v22; // r12d
  unsigned int v23; // r15d
  int v24; // ebx
  int *v25; // rax
  int v26; // r9d
  unsigned __int64 v27; // rcx
  char v28; // cl
  unsigned int v29; // eax
  unsigned int v30; // r10d
  unsigned int v31; // eax
  int v32; // eax
  unsigned __int64 v33; // r11
  char v34; // r11
  unsigned int v35; // eax
  unsigned int v36; // r9d
  unsigned int v37; // eax
  int v38; // eax
  __int64 v39; // rax
  __int64 v40; // rdi
  __int64 v41; // r15
  _BYTE *v42; // r12
  _BYTE *v43; // rdi
  _BYTE *v44; // r9
  char v45; // dl
  __int64 v46; // rsi
  unsigned int v47; // r9d
  unsigned int *v48; // rdi
  int v49; // r12d
  unsigned __int64 v50; // r11
  char v51; // bp
  int v52; // r9d
  unsigned int v53; // r10d
  unsigned int v54; // eax
  int v55; // eax
  unsigned int v56; // edx
  unsigned __int64 v57; // rdx
  unsigned __int64 v58; // rbp
  unsigned int v59; // r9d
  int v60; // ebx
  unsigned int *v62; // [rsp+20h] [rbp-48h]
  __int64 v63; // [rsp+28h] [rbp-40h]
  int *v64; // [rsp+28h] [rbp-40h]
  unsigned int *v65; // [rsp+78h] [rbp+10h]
  unsigned __int64 v66; // [rsp+80h] [rbp+18h]

  v5 = a3 + 1;
  v6 = (unsigned int *)*a3;
  v7 = a2 + 1;
  v65 = (unsigned int *)*a3;
  v9 = (unsigned int *)*a2;
  v62 = (unsigned int *)*a2;
  if ( *a2 == *a3 && *v7 == *v5 )
  {
    *a1 = *(_OWORD *)a4;
    return a1;
  }
  v10 = *v7;
  v11 = (__int64 *)a1 + 1;
  v12 = *v5;
  v13 = *(int **)a4;
  v14 = 32 * (v6 - v9) - *v7;
  v66 = *v7;
  *a1 = *(_OWORD *)a4;
  v15 = v14 + v12;
  if ( (__int64)(v14 + v12) >= 0 || (v16 = *v11, *v11 >= (unsigned __int64)-(__int64)v15) )
  {
    *v11 += v15;
    v17 = *v11;
    v18 = 4 * ((unsigned __int64)*v11 >> 5);
  }
  else
  {
    LOBYTE(v17) = v16 + v15;
    *v11 = v16 + v15;
    v18 = -4LL - 4 * (~(v16 + v15) >> 5);
  }
  *(_QWORD *)a1 += v18;
  v19 = v17 & 0x1F;
  v63 = *(_QWORD *)a1;
  *v11 = v19;
  v20 = *(_QWORD *)(a4 + 8);
  v21 = -1 << v10;
  if ( v20 )
    v22 = 0xFFFFFFFF >> (32 - v20);
  else
    v22 = 0;
  if ( v12 )
    v23 = 0xFFFFFFFF >> (32 - v12);
  else
    v23 = 0;
  v24 = -1 << v19;
  v25 = (int *)((-(__int64)(v19 == 0) & 0xFFFFFFFFFFFFFFFCuLL) + v63);
  v64 = v25;
  if ( v62 == v65 )
  {
    v26 = v23 & v21;
    v27 = *v7;
    if ( v20 >= v66 )
      v28 = v20 - v27;
    else
      v28 = v27 - v20;
    v29 = *v62 & v26;
    v30 = v29 >> v28;
    v31 = v29 << v28;
    if ( v20 >= v66 )
      v30 = v31;
    if ( v13 != v64 )
    {
      *v13 = v30 | v22 & *v13;
      v13[1] = v13[1] & v24 | ((*v62 & v26) >> (v12 - v19));
      return a1;
    }
    v32 = v30 | *v13 & (v22 | (v19 != 0 ? v24 : 0));
LABEL_55:
    *v13 = v32;
    return a1;
  }
  v33 = *v7;
  if ( v13 == v25 )
  {
    if ( v20 >= v66 )
      v34 = v20 - v33;
    else
      v34 = v33 - v20;
    v35 = *v62 & v21;
    v36 = v35 >> v34;
    v37 = v35 << v34;
    if ( v20 >= v66 )
      v36 = v37;
    if ( v12 )
      v38 = *v13 & (v22 | (v19 != 0 ? v24 : 0)) | ((v23 & *v65) << (v19 - v12));
    else
      v38 = *v13 & (v22 | (v19 != 0 ? v24 : 0));
    v32 = v36 | v38;
    goto LABEL_55;
  }
  v39 = v33 & 7;
  v40 = v20 & 7;
  if ( v39 == v40 )
  {
    v41 = v12 & 7;
    v42 = (char *)v65 + ((v12 - v41) >> 3);
    v43 = (char *)v13 + ((v20 - v40) >> 3);
    v44 = (char *)v62 + ((v33 - v39) >> 3);
    if ( (v33 & 7) != 0 )
    {
      v45 = *v44++ & (-1 << v39) | *v43 & (255 >> (8 - v39));
      *v43++ = v45;
    }
    v46 = v42 - v44;
    memmove_0(v43, v44, v42 - v44);
    if ( v41 )
      v43[v46] = v43[v46] & (-1 << v41) | *v42 & (255 >> (8 - v41));
    return a1;
  }
  v47 = *v62 & v21;
  v48 = v62 + 1;
  v49 = *v13 & v22;
  if ( v20 >= v66 )
  {
    v57 = v20 - v33;
    v58 = 32 - v57;
    *v13 = v49 | (v47 << v57);
    v59 = *v62 >> (32 - v57);
    ++v13;
    while ( v48 != v65 )
    {
      *v13++ = v59 | (*v48 << v57);
      v59 = *v48++ >> v58;
    }
    if ( v12 < v58 )
    {
      v60 = *v13 & v24;
      if ( !*v5 )
      {
        *v13 = v60 | v59;
        return a1;
      }
      v32 = v60 | v59 | ((v23 & *v48) << v57);
      goto LABEL_55;
    }
    *v13 = v59 | (*v48 << v57);
    if ( *v5 == v58 )
      return a1;
    v56 = ~v24 & (*v48 >> v58);
LABEL_52:
    v13[1] = v24 & v13[1] | v56;
    return a1;
  }
  v50 = v33 - v20;
  v51 = 32 - v50;
  v52 = v49 | (v47 >> v50);
  v53 = 0xFFFFFFFF >> v50;
  for ( *v13 = v52; v48 != v65; *v13 = v52 )
  {
    *v13++ = (*v48 << v51) | v52 & v53;
    v54 = *v48++;
    v52 = (v54 >> v50) | ~v53 & *v13;
  }
  if ( v12 )
  {
    v55 = (v23 & *v48) << v51;
    if ( v12 < v50 )
    {
      *v13 = v55 | *v13 & (v24 | v53);
      return a1;
    }
    *v13 = v55 | *v13 & v53;
    if ( v12 != v50 )
    {
      v56 = (v23 & *v48) >> v50;
      goto LABEL_52;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18001b718  mov     [rsp+arg_0], rbx
0x18001b71d  push    rbp
0x18001b71e  push    rsi
0x18001b71f  push    rdi
0x18001b720  push    r12
0x18001b722  push    r13
0x18001b724  push    r14
0x18001b726  push    r15
0x18001b728  sub     rsp, 30h
0x18001b72c  mov     rbx, r9
0x18001b72f  lea     r13, [r8+8]
0x18001b733  mov     r9, [r8]
0x18001b736  lea     r11, [rdx+8]
0x18001b73a  mov     r14, rcx
0x18001b73d  mov     [rsp+68h+arg_8], r9
0x18001b742  mov     rcx, [rdx]
0x18001b745  mov     [rsp+68h+var_48], rcx
0x18001b74a  cmp     rcx, r9
0x18001b74d  jnz     short loc_18001B765
0x18001b74f  mov     rax, [r13+0]
0x18001b753  cmp     [r11], rax
0x18001b756  jnz     short loc_18001B765
0x18001b758  movaps  xmm0, xmmword ptr [rbx]
0x18001b75b  movdqu  xmmword ptr [r14], xmm0
0x18001b760  jmp     loc_18001BB58
0x18001b765  mov     r10, [r11]
0x18001b768  lea     rdx, [r14+8]
0x18001b76c  mov     rsi, [r13+0]
0x18001b770  mov     rax, r9
0x18001b773  movaps  xmm0, xmmword ptr [rbx]
0x18001b776  sub     rax, rcx
0x18001b779  mov     r8, [rbx]
0x18001b77c  sar     rax, 2
0x18001b780  shl     rax, 5
0x18001b784  sub     rax, r10
0x18001b787  mov     [rsp+68h+arg_10], r10
0x18001b78f  movdqu  xmmword ptr [r14], xmm0
0x18001b794  lea     rcx, [rax+rsi]
0x18001b798  test    rcx, rcx
0x18001b79b  jns     short loc_18001B7CC
0x18001b79d  mov     r9, [rdx]
0x18001b7a0  mov     rax, rcx
0x18001b7a3  neg     rax
0x18001b7a6  cmp     r9, rax
0x18001b7a9  jnb     short loc_18001B7CC
0x18001b7ab  lea     rdi, [r9+rcx]
0x18001b7af  mov     rax, 0FFFFFFFFFFFFFFFCh
0x18001b7b6  mov     rcx, rdi
0x18001b7b9  mov     [rdx], rdi
0x18001b7bc  not     rcx
0x18001b7bf  shr     rcx, 5
0x18001b7c3  shl     rcx, 2
0x18001b7c7  sub     rax, rcx
0x18001b7ca  jmp     short loc_18001B7DD
0x18001b7cc  add     [rdx], rcx
0x18001b7cf  mov     rdi, [rdx]
0x18001b7d2  mov     rax, rdi
0x18001b7d5  shr     rax, 5
0x18001b7d9  shl     rax, 2
0x18001b7dd  add     [r14], rax
0x18001b7e0  mov     rcx, r10
0x18001b7e3  mov     rax, [r14]
0x18001b7e6  or      r10d, 0FFFFFFFFh
0x18001b7ea  and     edi, 1Fh
0x18001b7ed  mov     [rsp+68h+var_40], rax
0x18001b7f2  mov     r9d, r10d
0x18001b7f5  mov     [rdx], rdi
0x18001b7f8  mov     rdx, [rbx+8]
0x18001b7fc  mov     ebp, 20h ; ' '
0x18001b801  shl     r9d, cl
0x18001b804  test    rdx, rdx
0x18001b807  jnz     short loc_18001B80E
0x18001b809  xor     r12d, r12d
0x18001b80c  jmp     short loc_18001B818
0x18001b80e  mov     ecx, ebp
0x18001b810  mov     r12d, r10d
0x18001b813  sub     cl, dl
0x18001b815  shr     r12d, cl
0x18001b818  test    rsi, rsi
0x18001b81b  jnz     short loc_18001B822
0x18001b81d  xor     r15d, r15d
0x18001b820  jmp     short loc_18001B82D
0x18001b822  mov     ecx, ebp
0x18001b824  mov     r15d, r10d
0x18001b827  sub     cl, sil
0x18001b82a  shr     r15d, cl
0x18001b82d  mov     rcx, rdi
0x18001b830  mov     ebx, r10d
0x18001b833  shl     ebx, cl
0x18001b835  mov     rax, rdi
0x18001b838  neg     rax
0x18001b83b  mov     rax, [rsp+68h+var_40]
0x18001b840  sbb     rcx, rcx
0x18001b843  not     rcx
0x18001b846  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18001b84a  add     rax, rcx
0x18001b84d  mov     rcx, [rsp+68h+var_48]
0x18001b852  mov     [rsp+68h+var_40], rax
0x18001b857  cmp     rcx, [rsp+68h+arg_8]
0x18001b85c  jnz     short loc_18001B8DD
0x18001b85e  mov     rbp, [rsp+68h+arg_10]
0x18001b866  and     r9d, r15d
0x18001b869  mov     rcx, [r11]
0x18001b86c  cmp     rdx, rbp
0x18001b86f  jnb     short loc_18001B876
0x18001b871  sub     rcx, rdx
0x18001b874  jmp     short loc_18001B87F
0x18001b876  mov     rax, rdx
0x18001b879  sub     rax, rcx
0x18001b87c  mov     rcx, rax
0x18001b87f  mov     r11, [rsp+68h+var_48]
0x18001b884  mov     r10d, r9d
0x18001b887  and     r10d, [r11]
0x18001b88a  mov     eax, r10d
0x18001b88d  shr     r10d, cl
0x18001b890  shl     eax, cl
0x18001b892  cmp     rdx, rbp
0x18001b895  cmovnb  r10d, eax
0x18001b899  cmp     r8, [rsp+68h+var_40]
0x18001b89e  jnz     short loc_18001B8B5
0x18001b8a0  neg     rdi
0x18001b8a3  sbb     eax, eax
0x18001b8a5  and     eax, ebx
0x18001b8a7  or      eax, r12d
0x18001b8aa  and     eax, [r8]
0x18001b8ad  or      eax, r10d
0x18001b8b0  jmp     loc_18001BB4D
0x18001b8b5  mov     eax, [r8]
0x18001b8b8  mov     cl, sil
0x18001b8bb  and     eax, r12d
0x18001b8be  sub     cl, dil
0x18001b8c1  or      eax, r10d
0x18001b8c4  mov     [r8], eax
0x18001b8c7  and     r9d, [r11]
0x18001b8ca  and     ebx, [r8+4]
0x18001b8ce  shr     r9d, cl
0x18001b8d1  or      r9d, ebx
0x18001b8d4  mov     [r8+4], r9d
0x18001b8d8  jmp     loc_18001BB58
0x18001b8dd  mov     r11, [r11]
0x18001b8e0  cmp     r8, rax
0x18001b8e3  jnz     short loc_18001B94A
0x18001b8e5  mov     r10, [rsp+68h+arg_10]
0x18001b8ed  cmp     rdx, r10
0x18001b8f0  jnb     short loc_18001B8F7
0x18001b8f2  sub     r11, rdx
0x18001b8f5  jmp     short loc_18001B900
0x18001b8f7  mov     rax, rdx
0x18001b8fa  sub     rax, r11
0x18001b8fd  mov     r11, rax
0x18001b900  and     r9d, [rcx]
0x18001b903  mov     rcx, r11
0x18001b906  mov     eax, r9d
0x18001b909  shr     r9d, cl
0x18001b90c  shl     eax, cl
0x18001b90e  cmp     rdx, r10
0x18001b911  cmovnb  r9d, eax
0x18001b915  mov     rax, rdi
0x18001b918  neg     rax
0x18001b91b  sbb     edx, edx
0x18001b91d  and     edx, ebx
0x18001b91f  or      edx, r12d
0x18001b922  and     edx, [r8]
0x18001b925  test    rsi, rsi
0x18001b928  jz      short loc_18001B940
0x18001b92a  mov     rax, [rsp+68h+arg_8]
0x18001b92f  mov     cl, dil
0x18001b932  sub     cl, sil
0x18001b935  mov     eax, [rax]
0x18001b937  and     eax, r15d
0x18001b93a  shl     eax, cl
0x18001b93c  or      eax, edx
0x18001b93e  jmp     short loc_18001B942
0x18001b940  mov     eax, edx
0x18001b942  or      eax, r9d
0x18001b945  jmp     loc_18001BB4D
0x18001b94a  mov     rax, r11
0x18001b94d  mov     rdi, rdx
0x18001b950  and     eax, 7
0x18001b953  and     edi, 7
0x18001b956  cmp     rax, rdi
0x18001b959  jnz     loc_18001B9FA
0x18001b95f  mov     r12, [rsp+68h+arg_8]
0x18001b964  mov     r15, rsi
0x18001b967  sub     rdx, rdi
0x18001b96a  and     r15d, 7
0x18001b96e  sub     rsi, r15
0x18001b971  shr     rdx, 3
0x18001b975  sub     r11, rax
0x18001b978  shr     rsi, 3
0x18001b97c  shr     r11, 3
0x18001b980  add     r12, rsi
0x18001b983  or      ebp, 0FFFFFFFFh
0x18001b986  mov     ebx, 0FFh
0x18001b98b  lea     rdi, [rdx+r8]
0x18001b98f  mov     r13d, 8
0x18001b995  lea     r9, [r11+rcx]
0x18001b999  test    rax, rax
0x18001b99c  jz      short loc_18001B9BC
0x18001b99e  mov     ecx, r13d
0x18001b9a1  mov     edx, ebx
0x18001b9a3  sub     cl, al
0x18001b9a5  sar     edx, cl
0x18001b9a7  mov     ecx, eax
0x18001b9a9  and     dl, [rdi]
0x18001b9ab  mov     eax, ebp
0x18001b9ad  shl     al, cl
0x18001b9af  and     al, [r9]
0x18001b9b2  or      dl, al
0x18001b9b4  inc     r9
0x18001b9b7  mov     [rdi], dl
0x18001b9b9  inc     rdi
0x18001b9bc  mov     rsi, r12
0x18001b9bf  mov     rdx, r9; Src
0x18001b9c2  sub     rsi, r9
0x18001b9c5  mov     rcx, rdi; void *
0x18001b9c8  mov     r8, rsi; Size
0x18001b9cb  call    memmove_0
0x18001b9d0  test    r15, r15
0x18001b9d3  jz      loc_18001BB58
0x18001b9d9  mov     ecx, r13d
0x18001b9dc  sub     cl, r15b
0x18001b9df  sar     ebx, cl
0x18001b9e1  mov     rcx, r15
0x18001b9e4  and     bl, [r12]
0x18001b9e8  shl     bpl, cl
0x18001b9eb  and     bpl, [rdi+rsi]
0x18001b9ef  or      bl, bpl
0x18001b9f2  mov     [rdi+rsi], bl
0x18001b9f5  jmp     loc_18001BB58
0x18001b9fa  and     r9d, [rcx]
0x18001b9fd  lea     rdi, [rcx+4]
0x18001ba01  and     r12d, [r8]
0x18001ba04  cmp     rdx, [rsp+68h+arg_10]
0x18001ba0c  jnb     loc_18001BAB3
0x18001ba12  sub     r11, rdx
0x18001ba15  mov     rcx, r11
0x18001ba18  sub     rbp, r11
0x18001ba1b  shr     r9d, cl
0x18001ba1e  or      r9d, r12d
0x18001ba21  shr     r10d, cl
0x18001ba24  mov     r12, [rsp+68h+arg_8]
0x18001ba29  mov     [r8], r9d
0x18001ba2c  cmp     rdi, r12
0x18001ba2f  jz      short loc_18001BA69
0x18001ba31  mov     r13d, r10d
0x18001ba34  not     r13d
0x18001ba37  mov     eax, [rdi]
0x18001ba39  mov     rcx, rbp
0x18001ba3c  shl     eax, cl
0x18001ba3e  mov     edx, r10d
0x18001ba41  and     edx, r9d
0x18001ba44  mov     rcx, r11
0x18001ba47  or      edx, eax
0x18001ba49  mov     [r8], edx
0x18001ba4c  add     r8, 4
0x18001ba50  mov     eax, [rdi]
0x18001ba52  add     rdi, 4
0x18001ba56  shr     eax, cl
0x18001ba58  mov     r9d, [r8]
0x18001ba5b  and     r9d, r13d
0x18001ba5e  or      r9d, eax
0x18001ba61  mov     [r8], r9d
0x18001ba64  cmp     rdi, r12
0x18001ba67  jnz     short loc_18001BA37
0x18001ba69  test    rsi, rsi
0x18001ba6c  jz      loc_18001BB58
0x18001ba72  mov     eax, [rdi]
0x18001ba74  mov     rcx, rbp
0x18001ba77  and     eax, r15d
0x18001ba7a  shl     eax, cl
0x18001ba7c  cmp     rsi, r11
0x18001ba7f  jb      short loc_18001BAA2
0x18001ba81  and     r10d, [r8]
0x18001ba84  or      r10d, eax
0x18001ba87  mov     [r8], r10d
0x18001ba8a  cmp     rsi, r11
0x18001ba8d  jz      loc_18001BB58
0x18001ba93  mov     edx, [rdi]
0x18001ba95  mov     rcx, r11
0x18001ba98  and     edx, r15d
0x18001ba9b  shr     edx, cl
0x18001ba9d  jmp     loc_18001BB26
0x18001baa2  or      r10d, ebx
0x18001baa5  and     r10d, [r8]
0x18001baa8  or      r10d, eax
0x18001baab  mov     [r8], r10d
0x18001baae  jmp     loc_18001BB58
0x18001bab3  mov     r10, [rsp+68h+arg_8]
0x18001bab8  sub     rdx, r11
0x18001babb  mov     r11, [rsp+68h+var_48]
0x18001bac0  mov     rcx, rdx
0x18001bac3  shl     r9d, cl
0x18001bac6  sub     rbp, rdx
0x18001bac9  or      r9d, r12d
0x18001bacc  mov     rcx, rbp
0x18001bacf  mov     [r8], r9d
0x18001bad2  mov     r9d, [r11]
0x18001bad5  shr     r9d, cl
0x18001bad8  add     r8, 4
  ... truncated ...
```
