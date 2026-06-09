# std::_Copy_vbool<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>>(std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>)

- ea: `0x18001c204`
- end: `0x18001c65d`
- name: `??$_Copy_vbool@V?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@V12@@std@@YA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@0@V10@00@Z`
- size: `1113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d0ac`

## callees

- `0x1800029e1`
- `0x18001c204`

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
0x18001c204  mov     [rsp+arg_0], rbx
0x18001c209  push    rbp
0x18001c20a  push    rsi
0x18001c20b  push    rdi
0x18001c20c  push    r12
0x18001c20e  push    r13
0x18001c210  push    r14
0x18001c212  push    r15
0x18001c214  sub     rsp, 30h
0x18001c218  mov     rbx, r9
0x18001c21b  lea     r13, [r8+8]
0x18001c21f  mov     r9, [r8]
0x18001c222  lea     r11, [rdx+8]
0x18001c226  mov     r14, rcx
0x18001c229  mov     [rsp+68h+arg_8], r9
0x18001c22e  mov     rcx, [rdx]
0x18001c231  mov     [rsp+68h+var_48], rcx
0x18001c236  cmp     rcx, r9
0x18001c239  jnz     short loc_18001C251
0x18001c23b  mov     rax, [r13+0]
0x18001c23f  cmp     [r11], rax
0x18001c242  jnz     short loc_18001C251
0x18001c244  movaps  xmm0, xmmword ptr [rbx]
0x18001c247  movdqu  xmmword ptr [r14], xmm0
0x18001c24c  jmp     loc_18001C644
0x18001c251  mov     r10, [r11]
0x18001c254  lea     rdx, [r14+8]
0x18001c258  mov     rsi, [r13+0]
0x18001c25c  mov     rax, r9
0x18001c25f  movaps  xmm0, xmmword ptr [rbx]
0x18001c262  sub     rax, rcx
0x18001c265  mov     r8, [rbx]
0x18001c268  sar     rax, 2
0x18001c26c  shl     rax, 5
0x18001c270  sub     rax, r10
0x18001c273  mov     [rsp+68h+arg_10], r10
0x18001c27b  movdqu  xmmword ptr [r14], xmm0
0x18001c280  lea     rcx, [rax+rsi]
0x18001c284  test    rcx, rcx
0x18001c287  jns     short loc_18001C2B8
0x18001c289  mov     r9, [rdx]
0x18001c28c  mov     rax, rcx
0x18001c28f  neg     rax
0x18001c292  cmp     r9, rax
0x18001c295  jnb     short loc_18001C2B8
0x18001c297  lea     rdi, [r9+rcx]
0x18001c29b  mov     rax, 0FFFFFFFFFFFFFFFCh
0x18001c2a2  mov     rcx, rdi
0x18001c2a5  mov     [rdx], rdi
0x18001c2a8  not     rcx
0x18001c2ab  shr     rcx, 5
0x18001c2af  shl     rcx, 2
0x18001c2b3  sub     rax, rcx
0x18001c2b6  jmp     short loc_18001C2C9
0x18001c2b8  add     [rdx], rcx
0x18001c2bb  mov     rdi, [rdx]
0x18001c2be  mov     rax, rdi
0x18001c2c1  shr     rax, 5
0x18001c2c5  shl     rax, 2
0x18001c2c9  add     [r14], rax
0x18001c2cc  mov     rcx, r10
0x18001c2cf  mov     rax, [r14]
0x18001c2d2  or      r10d, 0FFFFFFFFh
0x18001c2d6  and     edi, 1Fh
0x18001c2d9  mov     [rsp+68h+var_40], rax
0x18001c2de  mov     r9d, r10d
0x18001c2e1  mov     [rdx], rdi
0x18001c2e4  mov     rdx, [rbx+8]
0x18001c2e8  mov     ebp, 20h ; ' '
0x18001c2ed  shl     r9d, cl
0x18001c2f0  test    rdx, rdx
0x18001c2f3  jnz     short loc_18001C2FA
0x18001c2f5  xor     r12d, r12d
0x18001c2f8  jmp     short loc_18001C304
0x18001c2fa  mov     ecx, ebp
0x18001c2fc  mov     r12d, r10d
0x18001c2ff  sub     cl, dl
0x18001c301  shr     r12d, cl
0x18001c304  test    rsi, rsi
0x18001c307  jnz     short loc_18001C30E
0x18001c309  xor     r15d, r15d
0x18001c30c  jmp     short loc_18001C319
0x18001c30e  mov     ecx, ebp
0x18001c310  mov     r15d, r10d
0x18001c313  sub     cl, sil
0x18001c316  shr     r15d, cl
0x18001c319  mov     rcx, rdi
0x18001c31c  mov     ebx, r10d
0x18001c31f  shl     ebx, cl
0x18001c321  mov     rax, rdi
0x18001c324  neg     rax
0x18001c327  mov     rax, [rsp+68h+var_40]
0x18001c32c  sbb     rcx, rcx
0x18001c32f  not     rcx
0x18001c332  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18001c336  add     rax, rcx
0x18001c339  mov     rcx, [rsp+68h+var_48]
0x18001c33e  mov     [rsp+68h+var_40], rax
0x18001c343  cmp     rcx, [rsp+68h+arg_8]
0x18001c348  jnz     short loc_18001C3C9
0x18001c34a  mov     rbp, [rsp+68h+arg_10]
0x18001c352  and     r9d, r15d
0x18001c355  mov     rcx, [r11]
0x18001c358  cmp     rdx, rbp
0x18001c35b  jnb     short loc_18001C362
0x18001c35d  sub     rcx, rdx
0x18001c360  jmp     short loc_18001C36B
0x18001c362  mov     rax, rdx
0x18001c365  sub     rax, rcx
0x18001c368  mov     rcx, rax
0x18001c36b  mov     r11, [rsp+68h+var_48]
0x18001c370  mov     r10d, r9d
0x18001c373  and     r10d, [r11]
0x18001c376  mov     eax, r10d
0x18001c379  shr     r10d, cl
0x18001c37c  shl     eax, cl
0x18001c37e  cmp     rdx, rbp
0x18001c381  cmovnb  r10d, eax
0x18001c385  cmp     r8, [rsp+68h+var_40]
0x18001c38a  jnz     short loc_18001C3A1
0x18001c38c  neg     rdi
0x18001c38f  sbb     eax, eax
0x18001c391  and     eax, ebx
0x18001c393  or      eax, r12d
0x18001c396  and     eax, [r8]
0x18001c399  or      eax, r10d
0x18001c39c  jmp     loc_18001C639
0x18001c3a1  mov     eax, [r8]
0x18001c3a4  mov     cl, sil
0x18001c3a7  and     eax, r12d
0x18001c3aa  sub     cl, dil
0x18001c3ad  or      eax, r10d
0x18001c3b0  mov     [r8], eax
0x18001c3b3  and     r9d, [r11]
0x18001c3b6  and     ebx, [r8+4]
0x18001c3ba  shr     r9d, cl
0x18001c3bd  or      r9d, ebx
0x18001c3c0  mov     [r8+4], r9d
0x18001c3c4  jmp     loc_18001C644
0x18001c3c9  mov     r11, [r11]
0x18001c3cc  cmp     r8, rax
0x18001c3cf  jnz     short loc_18001C436
0x18001c3d1  mov     r10, [rsp+68h+arg_10]
0x18001c3d9  cmp     rdx, r10
0x18001c3dc  jnb     short loc_18001C3E3
0x18001c3de  sub     r11, rdx
0x18001c3e1  jmp     short loc_18001C3EC
0x18001c3e3  mov     rax, rdx
0x18001c3e6  sub     rax, r11
0x18001c3e9  mov     r11, rax
0x18001c3ec  and     r9d, [rcx]
0x18001c3ef  mov     rcx, r11
0x18001c3f2  mov     eax, r9d
0x18001c3f5  shr     r9d, cl
0x18001c3f8  shl     eax, cl
0x18001c3fa  cmp     rdx, r10
0x18001c3fd  cmovnb  r9d, eax
0x18001c401  mov     rax, rdi
0x18001c404  neg     rax
0x18001c407  sbb     edx, edx
0x18001c409  and     edx, ebx
0x18001c40b  or      edx, r12d
0x18001c40e  and     edx, [r8]
0x18001c411  test    rsi, rsi
0x18001c414  jz      short loc_18001C42C
0x18001c416  mov     rax, [rsp+68h+arg_8]
0x18001c41b  mov     cl, dil
0x18001c41e  sub     cl, sil
0x18001c421  mov     eax, [rax]
0x18001c423  and     eax, r15d
0x18001c426  shl     eax, cl
0x18001c428  or      eax, edx
0x18001c42a  jmp     short loc_18001C42E
0x18001c42c  mov     eax, edx
0x18001c42e  or      eax, r9d
0x18001c431  jmp     loc_18001C639
0x18001c436  mov     rax, r11
0x18001c439  mov     rdi, rdx
0x18001c43c  and     eax, 7
0x18001c43f  and     edi, 7
0x18001c442  cmp     rax, rdi
0x18001c445  jnz     loc_18001C4E6
0x18001c44b  mov     r12, [rsp+68h+arg_8]
0x18001c450  mov     r15, rsi
0x18001c453  sub     rdx, rdi
0x18001c456  and     r15d, 7
0x18001c45a  sub     rsi, r15
0x18001c45d  shr     rdx, 3
0x18001c461  sub     r11, rax
0x18001c464  shr     rsi, 3
0x18001c468  shr     r11, 3
0x18001c46c  add     r12, rsi
0x18001c46f  or      ebp, 0FFFFFFFFh
0x18001c472  mov     ebx, 0FFh
0x18001c477  lea     rdi, [rdx+r8]
0x18001c47b  mov     r13d, 8
0x18001c481  lea     r9, [r11+rcx]
0x18001c485  test    rax, rax
0x18001c488  jz      short loc_18001C4A8
0x18001c48a  mov     ecx, r13d
0x18001c48d  mov     edx, ebx
0x18001c48f  sub     cl, al
0x18001c491  sar     edx, cl
0x18001c493  mov     ecx, eax
0x18001c495  and     dl, [rdi]
0x18001c497  mov     eax, ebp
0x18001c499  shl     al, cl
0x18001c49b  and     al, [r9]
0x18001c49e  or      dl, al
0x18001c4a0  inc     r9
0x18001c4a3  mov     [rdi], dl
0x18001c4a5  inc     rdi
0x18001c4a8  mov     rsi, r12
0x18001c4ab  mov     rdx, r9; Src
0x18001c4ae  sub     rsi, r9
0x18001c4b1  mov     rcx, rdi; void *
0x18001c4b4  mov     r8, rsi; Size
0x18001c4b7  call    memmove_0
0x18001c4bc  test    r15, r15
0x18001c4bf  jz      loc_18001C644
0x18001c4c5  mov     ecx, r13d
0x18001c4c8  sub     cl, r15b
0x18001c4cb  sar     ebx, cl
0x18001c4cd  mov     rcx, r15
0x18001c4d0  and     bl, [r12]
0x18001c4d4  shl     bpl, cl
0x18001c4d7  and     bpl, [rdi+rsi]
0x18001c4db  or      bl, bpl
0x18001c4de  mov     [rdi+rsi], bl
0x18001c4e1  jmp     loc_18001C644
0x18001c4e6  and     r9d, [rcx]
0x18001c4e9  lea     rdi, [rcx+4]
0x18001c4ed  and     r12d, [r8]
0x18001c4f0  cmp     rdx, [rsp+68h+arg_10]
0x18001c4f8  jnb     loc_18001C59F
0x18001c4fe  sub     r11, rdx
0x18001c501  mov     rcx, r11
0x18001c504  sub     rbp, r11
0x18001c507  shr     r9d, cl
0x18001c50a  or      r9d, r12d
0x18001c50d  shr     r10d, cl
0x18001c510  mov     r12, [rsp+68h+arg_8]
0x18001c515  mov     [r8], r9d
0x18001c518  cmp     rdi, r12
0x18001c51b  jz      short loc_18001C555
0x18001c51d  mov     r13d, r10d
0x18001c520  not     r13d
0x18001c523  mov     eax, [rdi]
0x18001c525  mov     rcx, rbp
0x18001c528  shl     eax, cl
0x18001c52a  mov     edx, r10d
0x18001c52d  and     edx, r9d
0x18001c530  mov     rcx, r11
0x18001c533  or      edx, eax
0x18001c535  mov     [r8], edx
0x18001c538  add     r8, 4
0x18001c53c  mov     eax, [rdi]
0x18001c53e  add     rdi, 4
0x18001c542  shr     eax, cl
0x18001c544  mov     r9d, [r8]
0x18001c547  and     r9d, r13d
0x18001c54a  or      r9d, eax
0x18001c54d  mov     [r8], r9d
0x18001c550  cmp     rdi, r12
0x18001c553  jnz     short loc_18001C523
0x18001c555  test    rsi, rsi
0x18001c558  jz      loc_18001C644
0x18001c55e  mov     eax, [rdi]
0x18001c560  mov     rcx, rbp
0x18001c563  and     eax, r15d
0x18001c566  shl     eax, cl
0x18001c568  cmp     rsi, r11
0x18001c56b  jb      short loc_18001C58E
0x18001c56d  and     r10d, [r8]
0x18001c570  or      r10d, eax
0x18001c573  mov     [r8], r10d
0x18001c576  cmp     rsi, r11
0x18001c579  jz      loc_18001C644
0x18001c57f  mov     edx, [rdi]
0x18001c581  mov     rcx, r11
0x18001c584  and     edx, r15d
0x18001c587  shr     edx, cl
0x18001c589  jmp     loc_18001C612
0x18001c58e  or      r10d, ebx
0x18001c591  and     r10d, [r8]
0x18001c594  or      r10d, eax
0x18001c597  mov     [r8], r10d
0x18001c59a  jmp     loc_18001C644
0x18001c59f  mov     r10, [rsp+68h+arg_8]
0x18001c5a4  sub     rdx, r11
0x18001c5a7  mov     r11, [rsp+68h+var_48]
0x18001c5ac  mov     rcx, rdx
0x18001c5af  shl     r9d, cl
0x18001c5b2  sub     rbp, rdx
0x18001c5b5  or      r9d, r12d
0x18001c5b8  mov     rcx, rbp
0x18001c5bb  mov     [r8], r9d
0x18001c5be  mov     r9d, [r11]
0x18001c5c1  shr     r9d, cl
0x18001c5c4  add     r8, 4
  ... truncated ...
```
