# std::_Copy_vbool<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>>(std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>)

- ea: `0x180013d84`
- end: `0x1800141dc`
- name: `??$_Copy_vbool@V?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@V12@@std@@YA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@0@V10@00@Z`
- size: `1112`
- prototype: `_OWORD *__fastcall(_OWORD *, _QWORD *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800243a8`

## callees

- `0x180003942`
- `0x180013d84`

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
0x180013d84  mov     [rsp+arg_0], rbx
0x180013d89  push    rbp
0x180013d8a  push    rsi
0x180013d8b  push    rdi
0x180013d8c  push    r12
0x180013d8e  push    r13
0x180013d90  push    r14
0x180013d92  push    r15
0x180013d94  sub     rsp, 30h
0x180013d98  mov     rbx, r9
0x180013d9b  lea     r13, [r8+8]
0x180013d9f  mov     r9, [r8]
0x180013da2  lea     r11, [rdx+8]
0x180013da6  mov     r14, rcx
0x180013da9  mov     [rsp+68h+arg_8], r9
0x180013dae  mov     rcx, [rdx]
0x180013db1  mov     [rsp+68h+var_48], rcx
0x180013db6  cmp     rcx, r9
0x180013db9  jnz     short loc_180013DD1
0x180013dbb  mov     rax, [r13+0]
0x180013dbf  cmp     [r11], rax
0x180013dc2  jnz     short loc_180013DD1
0x180013dc4  movaps  xmm0, xmmword ptr [rbx]
0x180013dc7  movdqu  xmmword ptr [r14], xmm0
0x180013dcc  jmp     loc_1800141C4
0x180013dd1  mov     r10, [r11]
0x180013dd4  lea     rdx, [r14+8]
0x180013dd8  mov     rsi, [r13+0]
0x180013ddc  mov     rax, r9
0x180013ddf  movaps  xmm0, xmmword ptr [rbx]
0x180013de2  sub     rax, rcx
0x180013de5  mov     r8, [rbx]
0x180013de8  sar     rax, 2
0x180013dec  shl     rax, 5
0x180013df0  sub     rax, r10
0x180013df3  mov     [rsp+68h+arg_10], r10
0x180013dfb  movdqu  xmmword ptr [r14], xmm0
0x180013e00  lea     rcx, [rax+rsi]
0x180013e04  test    rcx, rcx
0x180013e07  jns     short loc_180013E38
0x180013e09  mov     r9, [rdx]
0x180013e0c  mov     rax, rcx
0x180013e0f  neg     rax
0x180013e12  cmp     r9, rax
0x180013e15  jnb     short loc_180013E38
0x180013e17  lea     rdi, [r9+rcx]
0x180013e1b  mov     rax, 0FFFFFFFFFFFFFFFCh
0x180013e22  mov     rcx, rdi
0x180013e25  mov     [rdx], rdi
0x180013e28  not     rcx
0x180013e2b  shr     rcx, 5
0x180013e2f  shl     rcx, 2
0x180013e33  sub     rax, rcx
0x180013e36  jmp     short loc_180013E49
0x180013e38  add     [rdx], rcx
0x180013e3b  mov     rdi, [rdx]
0x180013e3e  mov     rax, rdi
0x180013e41  shr     rax, 5
0x180013e45  shl     rax, 2
0x180013e49  add     [r14], rax
0x180013e4c  mov     rcx, r10
0x180013e4f  mov     rax, [r14]
0x180013e52  or      r10d, 0FFFFFFFFh
0x180013e56  and     edi, 1Fh
0x180013e59  mov     [rsp+68h+var_40], rax
0x180013e5e  mov     r9d, r10d
0x180013e61  mov     [rdx], rdi
0x180013e64  mov     rdx, [rbx+8]
0x180013e68  mov     ebp, 20h ; ' '
0x180013e6d  shl     r9d, cl
0x180013e70  test    rdx, rdx
0x180013e73  jnz     short loc_180013E7A
0x180013e75  xor     r12d, r12d
0x180013e78  jmp     short loc_180013E84
0x180013e7a  mov     ecx, ebp
0x180013e7c  mov     r12d, r10d
0x180013e7f  sub     cl, dl
0x180013e81  shr     r12d, cl
0x180013e84  test    rsi, rsi
0x180013e87  jnz     short loc_180013E8E
0x180013e89  xor     r15d, r15d
0x180013e8c  jmp     short loc_180013E99
0x180013e8e  mov     ecx, ebp
0x180013e90  mov     r15d, r10d
0x180013e93  sub     cl, sil
0x180013e96  shr     r15d, cl
0x180013e99  mov     rcx, rdi
0x180013e9c  mov     ebx, r10d
0x180013e9f  shl     ebx, cl
0x180013ea1  mov     rax, rdi
0x180013ea4  neg     rax
0x180013ea7  mov     rax, [rsp+68h+var_40]
0x180013eac  sbb     rcx, rcx
0x180013eaf  not     rcx
0x180013eb2  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180013eb6  add     rax, rcx
0x180013eb9  mov     rcx, [rsp+68h+var_48]
0x180013ebe  mov     [rsp+68h+var_40], rax
0x180013ec3  cmp     rcx, [rsp+68h+arg_8]
0x180013ec8  jnz     short loc_180013F49
0x180013eca  mov     rbp, [rsp+68h+arg_10]
0x180013ed2  and     r9d, r15d
0x180013ed5  mov     rcx, [r11]
0x180013ed8  cmp     rdx, rbp
0x180013edb  jnb     short loc_180013EE2
0x180013edd  sub     rcx, rdx
0x180013ee0  jmp     short loc_180013EEB
0x180013ee2  mov     rax, rdx
0x180013ee5  sub     rax, rcx
0x180013ee8  mov     rcx, rax
0x180013eeb  mov     r11, [rsp+68h+var_48]
0x180013ef0  mov     r10d, r9d
0x180013ef3  and     r10d, [r11]
0x180013ef6  mov     eax, r10d
0x180013ef9  shr     r10d, cl
0x180013efc  shl     eax, cl
0x180013efe  cmp     rdx, rbp
0x180013f01  cmovnb  r10d, eax
0x180013f05  cmp     r8, [rsp+68h+var_40]
0x180013f0a  jnz     short loc_180013F21
0x180013f0c  neg     rdi
0x180013f0f  sbb     eax, eax
0x180013f11  and     eax, ebx
0x180013f13  or      eax, r12d
0x180013f16  and     eax, [r8]
0x180013f19  or      eax, r10d
0x180013f1c  jmp     loc_1800141B9
0x180013f21  mov     eax, [r8]
0x180013f24  mov     cl, sil
0x180013f27  and     eax, r12d
0x180013f2a  sub     cl, dil
0x180013f2d  or      eax, r10d
0x180013f30  mov     [r8], eax
0x180013f33  and     r9d, [r11]
0x180013f36  and     ebx, [r8+4]
0x180013f3a  shr     r9d, cl
0x180013f3d  or      r9d, ebx
0x180013f40  mov     [r8+4], r9d
0x180013f44  jmp     loc_1800141C4
0x180013f49  mov     r11, [r11]
0x180013f4c  cmp     r8, rax
0x180013f4f  jnz     short loc_180013FB6
0x180013f51  mov     r10, [rsp+68h+arg_10]
0x180013f59  cmp     rdx, r10
0x180013f5c  jnb     short loc_180013F63
0x180013f5e  sub     r11, rdx
0x180013f61  jmp     short loc_180013F6C
0x180013f63  mov     rax, rdx
0x180013f66  sub     rax, r11
0x180013f69  mov     r11, rax
0x180013f6c  and     r9d, [rcx]
0x180013f6f  mov     rcx, r11
0x180013f72  mov     eax, r9d
0x180013f75  shr     r9d, cl
0x180013f78  shl     eax, cl
0x180013f7a  cmp     rdx, r10
0x180013f7d  cmovnb  r9d, eax
0x180013f81  mov     rax, rdi
0x180013f84  neg     rax
0x180013f87  sbb     edx, edx
0x180013f89  and     edx, ebx
0x180013f8b  or      edx, r12d
0x180013f8e  and     edx, [r8]
0x180013f91  test    rsi, rsi
0x180013f94  jz      short loc_180013FAC
0x180013f96  mov     rax, [rsp+68h+arg_8]
0x180013f9b  mov     cl, dil
0x180013f9e  sub     cl, sil
0x180013fa1  mov     eax, [rax]
0x180013fa3  and     eax, r15d
0x180013fa6  shl     eax, cl
0x180013fa8  or      eax, edx
0x180013faa  jmp     short loc_180013FAE
0x180013fac  mov     eax, edx
0x180013fae  or      eax, r9d
0x180013fb1  jmp     loc_1800141B9
0x180013fb6  mov     rax, r11
0x180013fb9  mov     rdi, rdx
0x180013fbc  and     eax, 7
0x180013fbf  and     edi, 7
0x180013fc2  cmp     rax, rdi
0x180013fc5  jnz     loc_180014066
0x180013fcb  mov     r12, [rsp+68h+arg_8]
0x180013fd0  mov     r15, rsi
0x180013fd3  sub     rdx, rdi
0x180013fd6  and     r15d, 7
0x180013fda  sub     rsi, r15
0x180013fdd  shr     rdx, 3
0x180013fe1  sub     r11, rax
0x180013fe4  shr     rsi, 3
0x180013fe8  shr     r11, 3
0x180013fec  add     r12, rsi
0x180013fef  or      ebp, 0FFFFFFFFh
0x180013ff2  mov     ebx, 0FFh
0x180013ff7  lea     rdi, [rdx+r8]
0x180013ffb  mov     r13d, 8
0x180014001  lea     r9, [r11+rcx]
0x180014005  test    rax, rax
0x180014008  jz      short loc_180014028
0x18001400a  mov     ecx, r13d
0x18001400d  mov     edx, ebx
0x18001400f  sub     cl, al
0x180014011  sar     edx, cl
0x180014013  mov     ecx, eax
0x180014015  and     dl, [rdi]
0x180014017  mov     eax, ebp
0x180014019  shl     al, cl
0x18001401b  and     al, [r9]
0x18001401e  or      dl, al
0x180014020  inc     r9
0x180014023  mov     [rdi], dl
0x180014025  inc     rdi
0x180014028  mov     rsi, r12
0x18001402b  mov     rdx, r9; Src
0x18001402e  sub     rsi, r9
0x180014031  mov     rcx, rdi; void *
0x180014034  mov     r8, rsi; Size
0x180014037  call    memmove_0
0x18001403c  test    r15, r15
0x18001403f  jz      loc_1800141C4
0x180014045  mov     ecx, r13d
0x180014048  sub     cl, r15b
0x18001404b  sar     ebx, cl
0x18001404d  mov     rcx, r15
0x180014050  and     bl, [r12]
0x180014054  shl     bpl, cl
0x180014057  and     bpl, [rdi+rsi]
0x18001405b  or      bl, bpl
0x18001405e  mov     [rdi+rsi], bl
0x180014061  jmp     loc_1800141C4
0x180014066  and     r9d, [rcx]
0x180014069  lea     rdi, [rcx+4]
0x18001406d  and     r12d, [r8]
0x180014070  cmp     rdx, [rsp+68h+arg_10]
0x180014078  jnb     loc_18001411F
0x18001407e  sub     r11, rdx
0x180014081  mov     rcx, r11
0x180014084  sub     rbp, r11
0x180014087  shr     r9d, cl
0x18001408a  or      r9d, r12d
0x18001408d  shr     r10d, cl
0x180014090  mov     r12, [rsp+68h+arg_8]
0x180014095  mov     [r8], r9d
0x180014098  cmp     rdi, r12
0x18001409b  jz      short loc_1800140D5
0x18001409d  mov     r13d, r10d
0x1800140a0  not     r13d
0x1800140a3  mov     eax, [rdi]
0x1800140a5  mov     rcx, rbp
0x1800140a8  shl     eax, cl
0x1800140aa  mov     edx, r10d
0x1800140ad  and     edx, r9d
0x1800140b0  mov     rcx, r11
0x1800140b3  or      edx, eax
0x1800140b5  mov     [r8], edx
0x1800140b8  add     r8, 4
0x1800140bc  mov     eax, [rdi]
0x1800140be  add     rdi, 4
0x1800140c2  shr     eax, cl
0x1800140c4  mov     r9d, [r8]
0x1800140c7  and     r9d, r13d
0x1800140ca  or      r9d, eax
0x1800140cd  mov     [r8], r9d
0x1800140d0  cmp     rdi, r12
0x1800140d3  jnz     short loc_1800140A3
0x1800140d5  test    rsi, rsi
0x1800140d8  jz      loc_1800141C4
0x1800140de  mov     eax, [rdi]
0x1800140e0  mov     rcx, rbp
0x1800140e3  and     eax, r15d
0x1800140e6  shl     eax, cl
0x1800140e8  cmp     rsi, r11
0x1800140eb  jb      short loc_18001410E
0x1800140ed  and     r10d, [r8]
0x1800140f0  or      r10d, eax
0x1800140f3  mov     [r8], r10d
0x1800140f6  cmp     rsi, r11
0x1800140f9  jz      loc_1800141C4
0x1800140ff  mov     edx, [rdi]
0x180014101  mov     rcx, r11
0x180014104  and     edx, r15d
0x180014107  shr     edx, cl
0x180014109  jmp     loc_180014192
0x18001410e  or      r10d, ebx
0x180014111  and     r10d, [r8]
0x180014114  or      r10d, eax
0x180014117  mov     [r8], r10d
0x18001411a  jmp     loc_1800141C4
0x18001411f  mov     r10, [rsp+68h+arg_8]
0x180014124  sub     rdx, r11
0x180014127  mov     r11, [rsp+68h+var_48]
0x18001412c  mov     rcx, rdx
0x18001412f  shl     r9d, cl
0x180014132  sub     rbp, rdx
0x180014135  or      r9d, r12d
0x180014138  mov     rcx, rbp
0x18001413b  mov     [r8], r9d
0x18001413e  mov     r9d, [r11]
0x180014141  shr     r9d, cl
0x180014144  add     r8, 4
  ... truncated ...
```
