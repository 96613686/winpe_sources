# UpdateKeepWithCoverage

- ea: `0x180018b84`
- end: `0x180019345`
- name: `UpdateKeepWithCoverage`
- size: `1985`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180017f04`

## callees

- `0x180011538`
- `0x180011574`
- `0x180018b84`
- `0x18001a3bc`
- `0x18001a578`
- `0x18001a680`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall UpdateKeepWithCoverage(
        __int64 a1,
        __int64 a2,
        unsigned __int16 a3,
        __int16 a4,
        int a5,
        int a6,
        _WORD *a7,
        unsigned __int16 a8,
        __int16 a9,
        __int16 a10)
{
  _WORD *v10; // r14
  __int64 v11; // r12
  __int64 v12; // rdi
  __int64 v13; // r13
  unsigned int v14; // ebx
  __int64 result; // rax
  unsigned __int16 v16; // si
  __int64 v17; // r15
  unsigned __int16 GenericRepeat; // bx
  __int64 v19; // rcx
  int v20; // ecx
  int v21; // r11d
  int v22; // r10d
  unsigned __int16 v23; // dx
  unsigned int v24; // esi
  unsigned __int16 v25; // r14
  __int64 v26; // rdi
  int j; // eax
  int v28; // ecx
  __int64 v29; // r13
  int v30; // r14d
  __int64 v31; // rsi
  int v32; // edx
  unsigned __int16 k; // cx
  __int64 v34; // rcx
  unsigned int v35; // r14d
  unsigned __int16 v36; // di
  __int64 v37; // rsi
  unsigned __int16 v38; // cx
  __int64 v39; // r13
  unsigned __int16 v40; // r9
  char v41; // r12
  __int64 v42; // rdx
  unsigned int v43; // r14d
  unsigned __int16 v44; // di
  unsigned __int16 v45; // cx
  __int64 v46; // r13
  unsigned __int16 v47; // r9
  char v48; // r12
  __int64 v49; // rdx
  unsigned __int16 v50; // dx
  __int64 v51; // rcx
  int v52; // [rsp+40h] [rbp-79h]
  _WORD v53[2]; // [rsp+44h] [rbp-75h] BYREF
  unsigned __int16 v54; // [rsp+48h] [rbp-71h]
  _WORD v55[2]; // [rsp+4Ch] [rbp-6Dh] BYREF
  unsigned __int16 v56; // [rsp+50h] [rbp-69h]
  __int16 v57; // [rsp+52h] [rbp-67h]
  __int16 v58; // [rsp+54h] [rbp-65h] BYREF
  int i; // [rsp+58h] [rbp-61h]
  int v60; // [rsp+5Ch] [rbp-5Dh] BYREF
  __int64 v61; // [rsp+60h] [rbp-59h]
  __int64 v62; // [rsp+68h] [rbp-51h]
  int v63; // [rsp+70h] [rbp-49h]
  int v64; // [rsp+74h] [rbp-45h]
  __int64 v65; // [rsp+78h] [rbp-41h]
  unsigned int v66; // [rsp+80h] [rbp-39h]
  __int64 v67; // [rsp+88h] [rbp-31h]
  __int64 v68; // [rsp+90h] [rbp-29h]
  int v69; // [rsp+98h] [rbp-21h] BYREF
  __int16 v70; // [rsp+9Ch] [rbp-1Dh]
  __int64 v71; // [rsp+A0h] [rbp-19h] BYREF
  int v72; // [rsp+A8h] [rbp-11h]

  v10 = a7;
  v11 = 0;
  v69 = 0;
  v70 = 0;
  v12 = a2;
  v71 = 0;
  v13 = a1;
  v72 = 0;
  v57 = a4;
  v56 = a3;
  v61 = a2;
  v65 = a1;
  v62 = (__int64)a7;
  v58 = 0;
  v55[0] = 0;
  v60 = 0;
  if ( !a6 || !a7 )
    return 0;
  v14 = a6 + a5;
  result = ReadWord(a1, (__int64)&v58, a6 + a5);
  if ( (_WORD)result )
    return result;
  if ( v58 == 1 )
  {
    result = ReadGeneric(v13, (__int64)&v69, 4u, (unsigned __int8 *)GSUBCOVERAGEFORMAT1_CONTROL, v14, v55);
    if ( (_WORD)result )
      return result;
    v16 = HIWORD(v69);
    v54 = HIWORD(v69);
    v68 = Mem_Alloc(2LL * HIWORD(v69));
    v11 = v68;
    if ( v68 )
    {
      v17 = 0;
      v67 = 0;
      GenericRepeat = ReadGenericRepeat(v13, v68, (unsigned int)&WORD_CONTROL, v14 + v55[0], (__int64)&v60, v16, 2);
      if ( GenericRepeat )
      {
        v19 = v11;
        goto LABEL_22;
      }
      goto LABEL_12;
    }
    return 1005;
  }
  if ( v58 != 2 )
    return 1080;
  result = ReadGeneric(v13, (__int64)&v71, 4u, (unsigned __int8 *)GSUBCOVERAGEFORMAT2_CONTROL, v14, v55);
  if ( !(_WORD)result )
  {
    v16 = WORD1(v71);
    v54 = WORD1(v71);
    v67 = Mem_Alloc(8LL * WORD1(v71));
    v17 = v67;
    if ( v67 )
    {
      GenericRepeat = ReadGenericRepeat(
                        v13,
                        v67,
                        (unsigned int)&GSUBRANGERECORD_CONTROL,
                        v14 + v55[0],
                        (__int64)&v60,
                        v16,
                        8);
      if ( GenericRepeat )
        goto LABEL_10;
      v68 = 0;
LABEL_12:
      v20 = 0;
      v63 = 0;
      v52 = 0;
      v21 = 0;
      v22 = 0;
      for ( i = 0; ; i = v22 )
      {
        if ( (unsigned __int16)v20 >= v16 || GenericRepeat )
        {
LABEL_102:
          Mem_Free(v11);
LABEL_10:
          v19 = v17;
LABEL_22:
          Mem_Free(v19);
          return GenericRepeat;
        }
        if ( v58 == 1 )
        {
          v23 = *(_WORD *)(v11 + 2LL * (unsigned __int16)v20);
        }
        else
        {
          v23 = *(_WORD *)(v17 + 8LL * (unsigned __int16)v20) + v21;
          if ( v23 < *(_WORD *)(v17 + 8LL * (unsigned __int16)v20 + 2) )
          {
            LOWORD(v21) = v21 + 1;
            v63 = v21;
            goto LABEL_27;
          }
          LOWORD(v63) = 0;
        }
        LOWORD(v20) = v20 + 1;
        v52 = v20;
LABEL_27:
        if ( v23 >= v56 )
          goto LABEL_60;
        if ( *(unsigned __int8 *)(v23 + v12) != v57 )
          goto LABEL_59;
        switch ( a9 )
        {
          case 1:
            if ( a10 == 1 )
            {
              v50 = *v10 + v23;
              if ( v50 >= v56 )
                goto LABEL_59;
              v51 = v50;
            }
            else
            {
              if ( (unsigned __int16)v22 >= a8 )
              {
                GenericRepeat = 1080;
                goto LABEL_59;
              }
              if ( v10[(unsigned __int16)v22] >= v56 )
                goto LABEL_59;
              v51 = (unsigned __int16)v10[(unsigned __int16)v22];
            }
            if ( !*(_BYTE *)(v51 + v12) )
              *(_BYTE *)(v51 + v12) = v57 + 1;
            break;
          case 2:
            v53[0] = 0;
            if ( (unsigned __int16)v22 >= a8 )
            {
LABEL_75:
              GenericRepeat = 1080;
              break;
            }
            if ( v10[(unsigned __int16)v22] )
            {
              v43 = a5 + (unsigned __int16)v10[(unsigned __int16)v22];
              GenericRepeat = ReadWord(v13, (__int64)v53, v43);
              if ( !GenericRepeat )
              {
                v44 = v53[0];
                v37 = Mem_Alloc(2LL * v53[0]);
                if ( v37 )
                {
                  GenericRepeat = ReadGenericRepeat(
                                    v13,
                                    v37,
                                    (unsigned int)&WORD_CONTROL,
                                    v43 + 2,
                                    (__int64)&v60,
                                    v44,
                                    2);
                  if ( !GenericRepeat )
                  {
                    v45 = 0;
                    if ( v44 )
                    {
                      v46 = v61;
                      v47 = v56;
                      v48 = v57;
                      do
                      {
                        if ( *(_WORD *)(v37 + 2LL * v45) < v47 )
                        {
                          v49 = *(unsigned __int16 *)(v37 + 2LL * v45);
                          if ( !*(_BYTE *)(v49 + v46) )
                            *(_BYTE *)(v49 + v46) = v48 + 1;
                        }
                        ++v45;
                      }
                      while ( v45 < v44 );
LABEL_72:
                      v17 = v67;
                      v11 = v68;
                      v13 = v65;
                    }
                  }
LABEL_73:
                  v34 = v37;
LABEL_58:
                  Mem_Free(v34);
                  v22 = i;
                  v12 = v61;
                  v16 = v54;
                  v10 = (_WORD *)v62;
LABEL_59:
                  v20 = v52;
                  goto LABEL_60;
                }
                goto LABEL_79;
              }
LABEL_80:
              v10 = (_WORD *)v62;
            }
            break;
          case 3:
            v53[0] = 0;
            if ( (unsigned __int16)v22 >= a8 )
              goto LABEL_75;
            if ( v10[(unsigned __int16)v22] )
            {
              v35 = a5 + (unsigned __int16)v10[(unsigned __int16)v22];
              GenericRepeat = ReadWord(v13, (__int64)v53, v35);
              if ( !GenericRepeat )
              {
                v36 = v53[0];
                v37 = Mem_Alloc(2LL * v53[0]);
                if ( v37 )
                {
                  GenericRepeat = ReadGenericRepeat(
                                    v13,
                                    v37,
                                    (unsigned int)&WORD_CONTROL,
                                    v35 + 2,
                                    (__int64)&v60,
                                    v36,
                                    2);
                  if ( !GenericRepeat )
                  {
                    v38 = 0;
                    if ( v36 )
                    {
                      v39 = v61;
                      v40 = v56;
                      v41 = v57;
                      do
                      {
                        if ( *(_WORD *)(v37 + 2LL * v38) < v40 )
                        {
                          v42 = *(unsigned __int16 *)(v37 + 2LL * v38);
                          if ( !*(_BYTE *)(v42 + v39) )
                            *(_BYTE *)(v42 + v39) = v41 + 1;
                        }
                        ++v38;
                      }
                      while ( v38 < v36 );
                      goto LABEL_72;
                    }
                  }
                  goto LABEL_73;
                }
                goto LABEL_79;
              }
              goto LABEL_80;
            }
            break;
          case 4:
            v53[0] = 0;
            v69 = 0;
            v70 = 0;
            if ( (unsigned __int16)v22 < a8 )
            {
              v71 = (unsigned __int16)v22;
              if ( v10[(unsigned __int16)v22] )
              {
                v24 = a5 + (unsigned __int16)v10[(unsigned __int16)v22];
                GenericRepeat = ReadWord(v13, (__int64)v53, v24);
                if ( GenericRepeat )
                {
                  v16 = v54;
                  break;
                }
                v25 = v53[0];
                v26 = Mem_Alloc(2LL * v53[0]);
                if ( v26 )
                {
                  GenericRepeat = ReadGenericRepeat(
                                    v13,
                                    v26,
                                    (unsigned int)&WORD_CONTROL,
                                    v24 + 2,
                                    (__int64)&v60,
                                    v25,
                                    2);
                  if ( !GenericRepeat )
                  {
                    for ( j = 0; ; LOWORD(j) = v64 + 1 )
                    {
                      v64 = j;
                      if ( (unsigned __int16)j >= v25 )
                        break;
                      v28 = *(unsigned __int16 *)(v26 + 2LL * (unsigned __int16)j);
                      if ( (_WORD)v28 )
                      {
                        v66 = v28 + a5 + *(unsigned __int16 *)(v62 + 2 * v71);
                        GenericRepeat = ReadGeneric(
                                          v13,
                                          (__int64)&v69,
                                          4u,
                                          (unsigned __int8 *)GSUBLIGATURE_CONTROL,
                                          v66,
                                          v55);
                        if ( GenericRepeat )
                          goto LABEL_101;
                        if ( (unsigned __int16)v69 < v56 )
                        {
                          v29 = (unsigned __int16)v69;
                          if ( !*(_BYTE *)(v61 + (unsigned __int16)v69) )
                          {
                            v30 = HIWORD(v69);
                            v31 = Mem_Alloc(2LL * HIWORD(v69) - 2);
                            if ( !v31 )
                            {
                              Mem_Free(v26);
                              Mem_Free(v11);
                              Mem_Free(v17);
                              return 1005;
                            }
                            GenericRepeat = ReadGenericRepeat(
                                              v65,
                                              v31,
                                              (unsigned int)&WORD_CONTROL,
                                              v66 + v55[0],
                                              (__int64)&v60,
                                              (unsigned __int16)v30 - 1,
                                              2);
                            if ( GenericRepeat )
                            {
                              Mem_Free(v31);
LABEL_101:
                              Mem_Free(v26);
                              goto LABEL_102;
                            }
                            v32 = v30 - 1;
                            for ( k = 0; k < v32; ++k )
                            {
                              if ( *(_WORD *)(v31 + 2LL * k) >= v56 )
                                break;
                              if ( !*(_BYTE *)(*(unsigned __int16 *)(v31 + 2LL * k) + v61) )
                                break;
                            }
                            if ( k == v32 && !*(_BYTE *)(v61 + v29) )
                              *(_BYTE *)(v61 + v29) = v57 + 1;
                            Mem_Free(v31);
                            v25 = v53[0];
                          }
                          v13 = v65;
                        }
                      }
                      HIWORD(j) = HIWORD(v64);
                    }
                  }
                  v34 = v26;
                  goto LABEL_58;
                }
LABEL_79:
                v12 = v61;
                GenericRepeat = 1005;
                v22 = i;
                v16 = v54;
                goto LABEL_80;
              }
            }
            else
            {
              GenericRepeat = 1080;
            }
            break;
        }
        v20 = v52;
LABEL_60:
        v21 = v63;
        LOWORD(v22) = v22 + 1;
      }
    }
    return 1005;
  }
  return result;
}

```

## disassembly

```asm
0x180018b84  mov     [rsp-8+arg_10], rbx
0x180018b89  push    rbp
0x180018b8a  push    rsi
0x180018b8b  push    rdi
0x180018b8c  push    r12
0x180018b8e  push    r13
0x180018b90  push    r14
0x180018b92  push    r15
0x180018b94  lea     rbp, [rsp-7]
0x180018b99  sub     rsp, 0C0h
0x180018ba0  mov     rax, cs:__security_cookie
0x180018ba7  xor     rax, rsp
0x180018baa  mov     [rbp+37h+var_40], rax
0x180018bae  mov     r14, [rbp+37h+arg_30]
0x180018bb2  xor     eax, eax
0x180018bb4  xor     r12d, r12d
0x180018bb7  mov     [rbp+37h+var_58], eax
0x180018bba  mov     [rbp+37h+var_54], ax
0x180018bbe  mov     rdi, rdx
0x180018bc1  mov     [rbp+37h+var_50], rax
0x180018bc5  mov     r13, rcx
0x180018bc8  mov     [rbp+37h+var_48], eax
0x180018bcb  mov     eax, [rbp+37h+arg_28]
0x180018bce  mov     [rbp+37h+var_9E], r9w
0x180018bd3  mov     [rbp+37h+var_A0], r8w
0x180018bd8  mov     [rbp+37h+var_90], rdx
0x180018bdc  mov     [rbp+37h+var_78], rcx
0x180018be0  mov     [rbp+37h+var_88], r14
0x180018be4  mov     [rbp+37h+var_9C], r12w
0x180018be9  mov     [rbp+37h+var_A4], r12w
0x180018bee  mov     [rbp+37h+var_94], r12d
0x180018bf2  test    eax, eax
0x180018bf4  jz      loc_18001931B
0x180018bfa  test    r14, r14
0x180018bfd  jz      loc_18001931B
0x180018c03  mov     ebx, [rbp+37h+arg_20]
0x180018c06  lea     rdx, [rbp+37h+var_9C]
0x180018c0a  add     ebx, eax
0x180018c0c  mov     r8d, ebx
0x180018c0f  call    ReadWord
0x180018c14  test    ax, ax
0x180018c17  jnz     loc_18001931E
0x180018c1d  movzx   ecx, [rbp+37h+var_9C]
0x180018c21  sub     ecx, 1
0x180018c24  jz      loc_180018D19
0x180018c2a  cmp     ecx, 1
0x180018c2d  jz      short loc_180018C39
0x180018c2f  mov     eax, 438h
0x180018c34  jmp     loc_18001931E
0x180018c39  lea     rax, [rbp+37h+var_A4]
0x180018c3d  mov     r8d, 4
0x180018c43  mov     [rsp+0F0h+var_C8], rax
0x180018c48  lea     r9, GSUBCOVERAGEFORMAT2_CONTROL
0x180018c4f  lea     rdx, [rbp+37h+var_50]
0x180018c53  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x180018c57  mov     rcx, r13
0x180018c5a  call    ReadGeneric
0x180018c5f  test    ax, ax
0x180018c62  jnz     loc_18001931E
0x180018c68  movzx   esi, word ptr [rbp+37h+var_50+2]
0x180018c6c  mov     ecx, esi
0x180018c6e  mov     [rbp+37h+var_A8], si
0x180018c72  shl     rcx, 3; Size
0x180018c76  call    Mem_Alloc
0x180018c7b  mov     [rbp+37h+var_68], rax
0x180018c7f  mov     r15, rax
0x180018c82  test    rax, rax
0x180018c85  jz      loc_180018D69
0x180018c8b  movzx   r9d, [rbp+37h+var_A4]
0x180018c90  lea     rax, [rbp+37h+var_94]
0x180018c94  mov     [rsp+0F0h+var_C0], 8
0x180018c9b  lea     r8, GSUBRANGERECORD_CONTROL
0x180018ca2  add     r9d, ebx
0x180018ca5  mov     word ptr [rsp+0F0h+var_C8], si
0x180018caa  mov     rdx, r15
0x180018cad  mov     [rsp+0F0h+var_D0], rax
0x180018cb2  mov     rcx, r13
0x180018cb5  call    ReadGenericRepeat
0x180018cba  movzx   ebx, ax
0x180018cbd  test    ax, ax
0x180018cc0  jz      short loc_180018CCA
0x180018cc2  mov     rcx, r15
0x180018cc5  jmp     loc_180018DBB
0x180018cca  mov     [rbp+37h+var_60], r12
0x180018cce  xor     r9d, r9d
0x180018cd1  mov     ecx, r9d
0x180018cd4  mov     [rbp+37h+var_80], r9d
0x180018cd8  mov     [rbp+37h+var_B0], ecx
0x180018cdb  mov     r11d, r9d
0x180018cde  mov     r10d, r9d
0x180018ce1  mov     [rbp+37h+var_98], r9d
0x180018ce5  mov     r8d, 438h
0x180018ceb  cmp     cx, si
0x180018cee  jnb     loc_1800192F1
0x180018cf4  test    bx, bx
0x180018cf7  jnz     loc_1800192F1
0x180018cfd  mov     edx, 1
0x180018d02  movzx   eax, cx
0x180018d05  cmp     [rbp+37h+var_9C], dx
0x180018d09  jnz     loc_180018DC8
0x180018d0f  movzx   edx, word ptr [r12+rax*2]
0x180018d14  jmp     loc_180018DE8
0x180018d19  lea     rax, [rbp+37h+var_A4]
0x180018d1d  mov     r8d, 4
0x180018d23  mov     [rsp+0F0h+var_C8], rax
0x180018d28  lea     r9, GSUBCOVERAGEFORMAT1_CONTROL
0x180018d2f  lea     rdx, [rbp+37h+var_58]
0x180018d33  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x180018d37  mov     rcx, r13
0x180018d3a  call    ReadGeneric
0x180018d3f  test    ax, ax
0x180018d42  jnz     loc_18001931E
0x180018d48  movzx   esi, word ptr [rbp+37h+var_58+2]
0x180018d4c  mov     ecx, esi
0x180018d4e  mov     [rbp+37h+var_A8], si
0x180018d52  add     rcx, rcx; Size
0x180018d55  call    Mem_Alloc
0x180018d5a  xor     r8d, r8d
0x180018d5d  mov     [rbp+37h+var_60], rax
0x180018d61  mov     r12, rax
0x180018d64  test    rax, rax
0x180018d67  jnz     short loc_180018D73
0x180018d69  mov     eax, 3EDh
0x180018d6e  jmp     loc_18001931E
0x180018d73  movzx   r9d, [rbp+37h+var_A4]
0x180018d78  lea     rax, [rbp+37h+var_94]
0x180018d7c  mov     r15, r8
0x180018d7f  mov     [rbp+37h+var_68], r8
0x180018d83  mov     [rsp+0F0h+var_C0], 2
0x180018d8a  lea     r8, WORD_CONTROL
0x180018d91  add     r9d, ebx
0x180018d94  mov     word ptr [rsp+0F0h+var_C8], si
0x180018d99  mov     rdx, r12
0x180018d9c  mov     [rsp+0F0h+var_D0], rax
0x180018da1  mov     rcx, r13
0x180018da4  call    ReadGenericRepeat
0x180018da9  xor     r9d, r9d
0x180018dac  movzx   ebx, ax
0x180018daf  test    ax, ax
0x180018db2  jz      loc_180018CD1
0x180018db8  mov     rcx, r12
0x180018dbb  call    Mem_Free
0x180018dc0  movzx   eax, bx
0x180018dc3  jmp     loc_18001931E
0x180018dc8  movzx   edx, r11w
0x180018dcc  add     dx, [r15+rax*8]
0x180018dd1  cmp     dx, [r15+rax*8+2]
0x180018dd7  jnb     short loc_180018DE3
0x180018dd9  inc     r11w
0x180018ddd  mov     [rbp+37h+var_80], r11d
0x180018de1  jmp     short loc_180018DEE
0x180018de3  mov     word ptr [rbp+37h+var_80], r9w
0x180018de8  inc     cx
0x180018deb  mov     [rbp+37h+var_B0], ecx
0x180018dee  movzx   r9d, [rbp+37h+var_A0]
0x180018df3  cmp     dx, r9w
0x180018df7  jnb     loc_18001906B
0x180018dfd  movzx   r11d, [rbp+37h+var_9E]
0x180018e02  movzx   eax, dx
0x180018e05  movzx   ecx, byte ptr [rax+rdi]
0x180018e09  cmp     cx, r11w
0x180018e0d  jnz     loc_180019068
0x180018e13  movzx   ecx, [rbp+37h+arg_40]
0x180018e1a  sub     ecx, 1
0x180018e1d  jz      loc_180019275
0x180018e23  sub     ecx, 1
0x180018e26  jz      loc_18001916F
0x180018e2c  sub     ecx, 1
0x180018e2f  jz      loc_18001907F
0x180018e35  xor     r9d, r9d
0x180018e38  cmp     ecx, 1
0x180018e3b  jnz     loc_1800192A7
0x180018e41  xor     eax, eax
0x180018e43  mov     [rbp+37h+var_AC], r9w
0x180018e48  mov     [rbp+37h+var_58], eax
0x180018e4b  mov     [rbp+37h+var_54], ax
0x180018e4f  cmp     r10w, [rbp+37h+arg_38]
0x180018e54  jb      short loc_180018E5E
0x180018e56  mov     ebx, r8d
0x180018e59  jmp     loc_1800192A7
0x180018e5e  movzx   eax, r10w
0x180018e62  mov     [rbp+37h+var_50], rax
0x180018e66  cmp     [r14+rax*2], r9w
0x180018e6b  jz      loc_1800192A7
0x180018e71  movzx   esi, word ptr [r14+rax*2]
0x180018e76  lea     rdx, [rbp+37h+var_AC]
0x180018e7a  add     esi, [rbp+37h+arg_20]
0x180018e7d  mov     rcx, r13
0x180018e80  mov     r8d, esi
0x180018e83  call    ReadWord
0x180018e88  xor     r9d, r9d
0x180018e8b  movzx   ebx, ax
0x180018e8e  test    ax, ax
0x180018e91  jnz     loc_1800192D5
0x180018e97  movzx   r14d, [rbp+37h+var_AC]
0x180018e9c  mov     ecx, r14d
0x180018e9f  add     rcx, rcx; Size
0x180018ea2  call    Mem_Alloc
0x180018ea7  xor     r9d, r9d
0x180018eaa  mov     rdi, rax
0x180018ead  test    rax, rax
0x180018eb0  jz      loc_1800191D2
0x180018eb6  mov     [rsp+0F0h+var_C0], 2
0x180018ebd  lea     rax, [rbp+37h+var_94]
0x180018ec1  mov     word ptr [rsp+0F0h+var_C8], r14w
0x180018ec7  lea     r9d, [rsi+2]
0x180018ecb  lea     r8, WORD_CONTROL
0x180018ed2  mov     [rsp+0F0h+var_D0], rax
0x180018ed7  mov     rdx, rdi
0x180018eda  mov     rcx, r13
0x180018edd  call    ReadGenericRepeat
0x180018ee2  xor     esi, esi
0x180018ee4  movzx   ebx, ax
0x180018ee7  test    ax, ax
0x180018eea  jnz     loc_18001904A
0x180018ef0  mov     eax, esi
0x180018ef2  mov     [rbp+37h+var_7C], eax
0x180018ef5  cmp     ax, r14w
0x180018ef9  jnb     loc_18001904A
0x180018eff  movzx   eax, ax
0x180018f02  movzx   ecx, word ptr [rdi+rax*2]
0x180018f06  test    cx, cx
0x180018f09  jz      loc_18001903F
0x180018f0f  mov     rax, [rbp+37h+var_50]
0x180018f13  lea     r9, GSUBLIGATURE_CONTROL
0x180018f1a  mov     rdx, [rbp+37h+var_88]
0x180018f1e  mov     r8d, 4
0x180018f24  movzx   eax, word ptr [rdx+rax*2]
0x180018f28  lea     rdx, [rbp+37h+var_58]
0x180018f2c  add     eax, [rbp+37h+arg_20]
0x180018f2f  add     eax, ecx
0x180018f31  lea     rcx, [rbp+37h+var_A4]
0x180018f35  mov     [rsp+0F0h+var_C8], rcx
0x180018f3a  mov     rcx, r13
0x180018f3d  mov     [rbp+37h+var_70], eax
0x180018f40  mov     dword ptr [rsp+0F0h+var_D0], eax
0x180018f44  call    ReadGeneric
0x180018f49  movzx   ebx, ax
0x180018f4c  test    ax, ax
0x180018f4f  jnz     loc_1800192E9
0x180018f55  movzx   eax, [rbp+37h+var_A0]
0x180018f59  cmp     word ptr [rbp+37h+var_58], ax
0x180018f5d  jnb     loc_18001903F
0x180018f63  movzx   r13d, word ptr [rbp+37h+var_58]
0x180018f68  mov     rax, [rbp+37h+var_90]
0x180018f6c  cmp     [rax+r13], sil
0x180018f70  jnz     loc_18001903B
0x180018f76  movzx   r14d, word ptr [rbp+37h+var_58+2]
0x180018f7b  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[r14*2]; Size
0x180018f83  call    Mem_Alloc
0x180018f88  mov     rsi, rax
0x180018f8b  test    rax, rax
0x180018f8e  jz      loc_1800192FE
0x180018f94  movzx   r9d, [rbp+37h+var_A4]
0x180018f99  lea     ecx, [r14-1]
0x180018f9d  add     r9d, [rbp+37h+var_70]
0x180018fa1  lea     rax, [rbp+37h+var_94]
0x180018fa5  mov     [rsp+0F0h+var_C0], 2
0x180018fac  lea     r8, WORD_CONTROL
0x180018fb3  mov     word ptr [rsp+0F0h+var_C8], cx
0x180018fb8  mov     rdx, rsi
0x180018fbb  mov     rcx, [rbp+37h+var_78]
0x180018fbf  mov     [rsp+0F0h+var_D0], rax
0x180018fc4  call    ReadGenericRepeat
0x180018fc9  xor     r10d, r10d
0x180018fcc  movzx   ebx, ax
0x180018fcf  test    ax, ax
0x180018fd2  jnz     loc_1800192E1
0x180018fd8  mov     edx, r14d
0x180018fdb  lea     r11d, [r10+1]
0x180018fdf  sub     edx, r11d
0x180018fe2  mov     ecx, r10d
0x180018fe5  test    edx, edx
0x180018fe7  jle     short loc_180019011
0x180018fe9  mov     r8, [rbp+37h+var_90]
0x180018fed  movzx   r9d, [rbp+37h+var_A0]
0x180018ff2  movzx   eax, cx
0x180018ff5  cmp     [rsi+rax*2], r9w
0x180018ffa  jnb     short loc_180019011
0x180018ffc  movzx   eax, word ptr [rsi+rax*2]
0x180019000  cmp     [rax+r8], r10b
0x180019004  jz      short loc_180019011
0x180019006  add     cx, r11w
0x18001900a  movzx   eax, cx
0x18001900d  cmp     eax, edx
0x18001900f  jl      short loc_180018FF2
0x180019011  movzx   eax, cx
0x180019014  cmp     eax, edx
0x180019016  jnz     short loc_18001902C
0x180019018  mov     rcx, [rbp+37h+var_90]
0x18001901c  cmp     [rcx+r13], r10b
0x180019020  jnz     short loc_18001902C
0x180019022  mov     al, byte ptr [rbp+37h+var_9E]
0x180019025  add     al, r11b
0x180019028  mov     [rcx+r13], al
0x18001902c  mov     rcx, rsi
0x18001902f  call    Mem_Free
0x180019034  movzx   r14d, [rbp+37h+var_AC]
0x180019039  xor     esi, esi
0x18001903b  mov     r13, [rbp+37h+var_78]
  ... truncated ...
```
