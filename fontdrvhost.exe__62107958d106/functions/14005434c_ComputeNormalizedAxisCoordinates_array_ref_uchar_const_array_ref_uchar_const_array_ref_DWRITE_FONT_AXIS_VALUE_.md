# ComputeNormalizedAxisCoordinates(array_ref<uchar const>,array_ref<uchar const>,array_ref<DWRITE_FONT_AXIS_VALUE_FIXED const>,std::vector<Fixed16_16,std::allocator<Fixed16_16>> &)

- ea: `0x14005434c`
- end: `0x140054aac`
- name: `?ComputeNormalizedAxisCoordinates@@YAXV?$array_ref@$$CBE@@0V?$array_ref@$$CBUDWRITE_FONT_AXIS_VALUE_FIXED@@@@AEAV?$vector@VFixed16_16@@V?$allocator@VFixed16_16@@@std@@@std@@@Z`
- size: `1888`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1400540cc`

## callees

- `0x14005434c`
- `0x140054ab4`
- `0x140054b54`
- `0x140054bc0`
- `0x140054c04`
- `0x14007327c`
- `0x140092e20`
- `0x140092e48`
- `0x140092ed0`
- `0x1400947e4`

## pseudocode

```c
void __fastcall ComputeNormalizedAxisCoordinates(__int64 *a1, unsigned __int8 **a2, __int64 *a3, __int64 *a4)
{
  __int64 v4; // r10
  __int64 v6; // r11
  __int64 v7; // r12
  __int64 v8; // r8
  __int64 v9; // rsi
  __int64 v10; // rdi
  unsigned __int64 v11; // rsi
  __int64 v12; // r12
  unsigned __int16 v13; // r13
  int v14; // ebp
  int v15; // r15d
  unsigned __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // r11d
  __int64 v19; // rdx
  __int64 i; // rbp
  unsigned __int8 *v21; // rdx
  unsigned __int8 *v22; // r8
  unsigned __int64 v23; // rdx
  __int64 v24; // rcx
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // rdi
  __int64 j; // r9
  unsigned __int8 *v28; // r15
  unsigned __int64 v29; // rdi
  unsigned __int16 v30; // bp
  int v31; // r11d
  int v32; // esi
  int v33; // r13d
  int v34; // r8d
  int *v35; // r9
  int v36; // r11d
  int v37; // edx
  unsigned int v38; // eax
  unsigned __int64 v39; // rax
  int v40; // r9d
  int v41; // r9d
  int v42; // edx
  int v43; // eax
  int v44; // eax
  int v45; // ecx
  __int64 v46; // r15
  __int64 v47; // rdx
  int v48; // r8d
  int *v49; // rax
  int v50; // r11d
  unsigned int v51; // eax
  unsigned int v52; // r9d
  unsigned int v53; // r10d
  int v54; // r11d
  ArgumentException *v55; // rax
  int v56; // r8d
  __int64 v57; // r9
  char v58[8]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v59; // [rsp+28h] [rbp-40h]
  unsigned int v61; // [rsp+80h] [rbp+18h] BYREF
  int v62; // [rsp+88h] [rbp+20h] BYREF

  v4 = *a4;
  v6 = a4[1];
  if ( *a4 != v6 )
  {
    a4[1] = v4;
    v6 = v4;
  }
  v7 = a3[1];
  v8 = *a3;
  v59 = v8;
  if ( v8 == v7 )
    return;
  v9 = a1[1];
  v10 = *a1;
  if ( *a1 == v9 )
    return;
  v11 = v9 - v10;
  if ( v11 < 0x10 )
    ((void (__noreturn *)(void))CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange)();
  v12 = (v7 - v8) >> 3;
  if ( (_DWORD)v12 != ((*(unsigned __int8 *)(v10 + 8) << 8) | *(unsigned __int8 *)(v10 + 9)) )
  {
    v55 = ArgumentException::ArgumentException((ArgumentException *)&v61);
    LogAndThrow<ArgumentException>(v55, 0x736978616D726ELL);
  }
  v13 = _byteswap_ushort(*(_WORD *)(v10 + 10));
  if ( v13 < 0x14u )
  {
    v61 = -2003283968;
    LogAndThrow<FileFormatException>(&v61, 0x736978616D726ELL);
  }
  v14 = *(unsigned __int8 *)(v10 + 4);
  v15 = *(unsigned __int8 *)(v10 + 5);
  v16 = (v6 - v4) >> 2;
  if ( (unsigned int)v12 < v16 )
  {
    v17 = v4 + 4LL * (unsigned int)v12;
LABEL_12:
    a4[1] = v17;
    goto LABEL_13;
  }
  if ( (unsigned int)v12 > v16 )
  {
    if ( (unsigned int)v12 > (unsigned __int64)((a4[2] - v4) >> 2) )
    {
      std::vector<Fixed16_16>::_Resize_reallocate<std::_Value_init_tag>(a4);
      v8 = v59;
      goto LABEL_13;
    }
    v17 = std::_Uninitialized_value_construct_n<std::allocator<Fixed16_16>>(v6, (unsigned int)v12 - v16);
    v8 = v59;
    goto LABEL_12;
  }
LABEL_13:
  v18 = 0x80000000;
  if ( (_DWORD)v12 )
  {
    v19 = 0;
    v61 = 0;
    for ( i = v15 | (unsigned int)(v14 << 8); ; i = v13 + (unsigned int)i )
    {
      if ( (unsigned int)i > v11 || v11 - (unsigned int)i < 0x14 )
        CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(
          4294967293LL,
          v19,
          v8,
          20);
      v46 = (unsigned int)v19;
      v47 = *(int *)(v8 + 8 * v19 + 4);
      v48 = *(unsigned __int8 *)(v10 + i + 11)
          | ((*(unsigned __int8 *)(v10 + i + 10)
            | ((*(unsigned __int8 *)(v10 + i + 9) | (*(unsigned __int8 *)(v10 + i + 8) << 8)) << 8)) << 8);
      if ( (int)v47 < v48 )
        break;
      if ( (int)v47 > v48 )
      {
        if ( v48 != 0x7FFFFFFF )
        {
          if ( v48 == 0x80000000 )
            v18 = 0x7FFFFFFF;
          else
            v18 = -v48;
        }
        if ( (unsigned int)(v47 + 0x7FFFFFFF) <= 0xFFFFFFFD && (unsigned int)(v18 + 0x7FFFFFFF) <= 0xFFFFFFFD )
          Fixed16_16::SaturateToInfinity(v47 - v48);
        v62 = *(unsigned __int8 *)(v10 + i + 15)
            | ((*(unsigned __int8 *)(v10 + i + 14)
              | (((*(unsigned __int8 *)(v10 + i + 12) << 8) | *(unsigned __int8 *)(v10 + i + 13)) << 8)) << 8);
        v49 = (int *)Fixed16_16::operator-(&v62, v58);
        v45 = Fixed16_16::Divide((__int64)v50 << 16, *v49);
        if ( v45 < 0 )
        {
          v45 = 0;
        }
        else if ( v45 > 0x10000 )
        {
          v45 = 0x10000;
        }
LABEL_60:
        v18 = 0x80000000;
        *(_DWORD *)(*a4 + 4 * v46) = v45;
        goto LABEL_61;
      }
      *(_DWORD *)(*a4 + 4 * v46) = 0;
LABEL_61:
      v19 = v61 + 1;
      v61 = v19;
      if ( (unsigned int)v19 >= (unsigned int)v12 )
        goto LABEL_19;
      v8 = v59;
    }
    if ( (_DWORD)v47 == 0x7FFFFFFF )
    {
      v40 = 0x80000000;
    }
    else if ( (_DWORD)v47 == 0x80000000 )
    {
      v40 = 0x7FFFFFFF;
    }
    else
    {
      v40 = -(int)v47;
    }
    if ( (unsigned int)(v48 + 0x7FFFFFFF) <= 0xFFFFFFFD )
    {
      if ( (unsigned int)(v40 + 0x7FFFFFFF) <= 0xFFFFFFFD )
        v40 = Fixed16_16::SaturateToInfinity(v48 - v47);
    }
    else
    {
      v40 = *(unsigned __int8 *)(v10 + i + 11)
          | ((*(unsigned __int8 *)(v10 + i + 10)
            | ((*(unsigned __int8 *)(v10 + i + 9) | (*(unsigned __int8 *)(v10 + i + 8) << 8)) << 8)) << 8);
    }
    if ( v40 == 0x7FFFFFFF )
    {
      v41 = v18;
    }
    else if ( v40 == v18 )
    {
      v41 = 0x7FFFFFFF;
    }
    else
    {
      v41 = -v40;
    }
    v42 = *(unsigned __int8 *)(v10 + i + 7)
        | ((*(unsigned __int8 *)(v10 + i + 6)
          | (((*(unsigned __int8 *)(v10 + i + 4) << 8) | *(unsigned __int8 *)(v10 + i + 5)) << 8)) << 8);
    if ( v42 == 0x7FFFFFFF )
    {
      v43 = v18;
    }
    else if ( v42 == v18 )
    {
      v43 = 0x7FFFFFFF;
    }
    else
    {
      v43 = -v42;
    }
    if ( (unsigned int)(v48 + 0x7FFFFFFF) <= 0xFFFFFFFD )
    {
      if ( (unsigned int)(v43 + 0x7FFFFFFF) <= 0xFFFFFFFD )
        v43 = Fixed16_16::SaturateToInfinity(v48 - (__int64)v42);
    }
    else
    {
      v43 = v48;
    }
    v44 = Fixed16_16::Divide((__int64)v41 << 16, v43);
    if ( v44 < -65536 )
      v44 = -65536;
    v45 = 0;
    if ( v44 <= 0 )
      v45 = v44;
    goto LABEL_60;
  }
LABEL_19:
  v21 = a2[1];
  v22 = *a2;
  if ( *a2 != v21 )
  {
    v23 = v21 - v22;
    if ( v23 < 8 )
      CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(
        4294967293LL,
        v23,
        v22,
        20);
    v24 = (v22[6] << 8) | (unsigned int)v22[7];
    if ( (_DWORD)v12 != (_DWORD)v24 )
    {
      v61 = -2003283968;
      LogAndThrow<FileFormatException>(&v61, 0x736978616D726ELL);
    }
    v25 = (unsigned __int64)(v22 + 8);
    v26 = v23 - 8;
    for ( j = 0; ; LOWORD(j) = j + 1 )
    {
      v61 = j;
      if ( (unsigned __int16)j >= (unsigned int)v12 )
        break;
      if ( v26 < 2 )
        CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(
          v24,
          v23,
          v25,
          j);
      v28 = (unsigned __int8 *)(v25 + 2);
      v29 = v26 - 2;
      v30 = _byteswap_ushort(*(_WORD *)v25);
      if ( v30 )
      {
        if ( v30 < 3u )
        {
          v61 = -2003283968;
          LogAndThrow<FileFormatException>(&v61, 0x736978616D726ELL);
        }
        v24 = v29 >> 2;
        if ( v29 >> 2 < v30 )
          ((void (__noreturn *)(void))CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange)();
        v23 = 1;
        v25 = 4 * (*(unsigned __int8 *)(v25 + 3) | (unsigned int)(__int16)(*v28 << 8));
        v59 = (unsigned __int16)j;
        while ( (unsigned __int16)v23 < v30 )
        {
          v31 = 4 * (v28[4 * (unsigned __int16)v23 + 1] | (__int16)(v28[4 * (unsigned __int16)v23] << 8));
          v24 = *a4 + 4LL * (unsigned __int16)j;
          if ( *(_DWORD *)v24 <= v31 )
          {
            v32 = 4 * (v28[4 * (unsigned __int16)v23 - 1] | (__int16)(v28[4 * (unsigned __int16)v23 - 2] << 8));
            v33 = 4 * (v28[4 * (unsigned __int16)v23 + 3] | (__int16)(v28[4 * (unsigned __int16)v23 + 2] << 8));
            v35 = (int *)Fixed16_16::operator-(v24, &v62);
            if ( v34 == 0x80000000 )
              v37 = 0x7FFFFFFF;
            else
              v37 = -v34;
            if ( v36 == 0x80000000 )
            {
              v37 = 0x80000000;
            }
            else if ( (unsigned int)(v37 + 0x7FFFFFFF) <= 0xFFFFFFFD )
            {
              v37 = Fixed16_16::SaturateToInfinity(v36 - (__int64)v34);
            }
            v57 = (int)Fixed16_16::Divide((__int64)*v35 << 16, v37);
            if ( v32 == 0x80000000 )
              v56 = 0x7FFFFFFF;
            else
              v56 = -v32;
            if ( v33 == 0x80000000 )
            {
              v56 = 0x80000000;
            }
            else if ( (unsigned int)(v56 + 0x7FFFFFFF) <= 0xFFFFFFFD )
            {
              v56 = Fixed16_16::SaturateToInfinity(v33 - (__int64)v32);
            }
            v51 = Fixed16_16::SaturateToInfinity((v56 * v57 + 0x8000) >> 16);
            if ( v51 )
            {
              if ( v52 + 0x7FFFFFFF > v53 )
              {
                v25 = v52;
LABEL_83:
                if ( v32 == v54 )
                {
                  v25 = (unsigned int)v32;
                }
                else if ( (int)v25 + 0x7FFFFFFF <= v53 )
                {
                  v25 = (unsigned int)Fixed16_16::SaturateToInfinity((int)v25 + (__int64)v32);
                }
                v38 = -65536;
                if ( (int)v25 < -65536 || (v38 = 0x10000, (int)v25 > 0x10000) )
                  v25 = v38;
                v24 = v59;
                *(_DWORD *)(*a4 + 4 * v59) = v25;
                break;
              }
              if ( (((_DWORD)v25 - 0x7FFFFFFF) & 0xFFFFFFFE) == 0 )
                goto LABEL_83;
            }
            v25 = v51;
            goto LABEL_83;
          }
          v25 = (unsigned int)v31;
          LOWORD(v23) = v23 + 1;
        }
        j = v61;
      }
      v39 = 4LL * v30;
      if ( v39 > v29 )
        CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(
          v24,
          v23,
          v25,
          j);
      v26 = v29 - v39;
      v25 = (unsigned __int64)&v28[v39];
    }
  }
}

```

## disassembly

```asm
0x14005434c  mov     [rsp+arg_0], rbx
0x140054351  mov     [rsp+arg_8], rdx
0x140054356  push    rbp
0x140054357  push    rsi
0x140054358  push    rdi
0x140054359  push    r12
0x14005435b  push    r13
0x14005435d  push    r14
0x14005435f  push    r15
0x140054361  sub     rsp, 30h
0x140054365  mov     r10, [r9]
0x140054368  mov     r14, r9
0x14005436b  mov     r11, [r9+8]
0x14005436f  cmp     r10, r11
0x140054372  jz      short loc_14005437B
0x140054374  mov     [r9+8], r10
0x140054378  mov     r11, r10
0x14005437b  mov     r12, [r8+8]
0x14005437f  mov     r8, [r8]
0x140054382  mov     [rsp+68h+var_40], r8
0x140054387  cmp     r8, r12
0x14005438a  jz      loc_140054487
0x140054390  mov     rsi, [rcx+8]
0x140054394  mov     rdi, [rcx]
0x140054397  cmp     rdi, rsi
0x14005439a  jz      loc_140054487
0x1400543a0  sub     rsi, rdi
0x1400543a3  cmp     rsi, 10h
0x1400543a7  jb      loc_1400544C5
0x1400543ad  movzx   eax, byte ptr [rdi+8]
0x1400543b1  sub     r12, r8
0x1400543b4  movzx   ecx, byte ptr [rdi+9]
0x1400543b8  mov     rbx, 736978616D726Eh
0x1400543c2  shl     eax, 8
0x1400543c5  or      ecx, eax
0x1400543c7  sar     r12, 3
0x1400543cb  cmp     r12d, ecx
0x1400543ce  jnz     loc_140054982
0x1400543d4  movzx   r13d, byte ptr [rdi+0Ah]
0x1400543d9  mov     r9d, 14h
0x1400543df  movzx   eax, byte ptr [rdi+0Bh]
0x1400543e3  shl     r13w, 8
0x1400543e8  or      r13w, ax
0x1400543ec  cmp     r13w, r9w
0x1400543f0  jb      loc_14005499B
0x1400543f6  movzx   ebp, byte ptr [rdi+4]
0x1400543fa  mov     rcx, r11
0x1400543fd  movzx   r15d, byte ptr [rdi+5]
0x140054402  sub     rcx, r10
0x140054405  sar     rcx, 2
0x140054409  mov     edx, r12d
0x14005440c  cmp     rdx, rcx
0x14005440f  jb      loc_1400544BC
0x140054415  jbe     short loc_140054445
0x140054417  mov     rax, [r14+10h]
0x14005441b  sub     rax, r10
0x14005441e  sar     rax, 2
0x140054422  cmp     rdx, rax
0x140054425  ja      loc_1400549B7
0x14005442b  sub     rdx, rcx
0x14005442e  mov     rcx, r11
0x140054431  call    ??$_Uninitialized_value_construct_n@V?$allocator@VFixed16_16@@@std@@@std@@YAPEAVFixed16_16@@PEAV1@_KAEAV?$allocator@VFixed16_16@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Fixed16_16>>(Fixed16_16 *,unsigned __int64,std::allocator<Fixed16_16> &)
0x140054436  mov     r8, [rsp+68h+var_40]
0x14005443b  mov     r9d, 14h
0x140054441  mov     [r14+8], rax
0x140054445  mov     ecx, 0FFFFFFFDh
0x14005444a  mov     r11d, 80000000h
0x140054450  mov     r10d, 1
0x140054456  test    r12d, r12d
0x140054459  jz      short loc_14005449C
0x14005445b  xor     edx, edx
0x14005445d  shl     ebp, 8
0x140054460  mov     [rsp+68h+arg_10], edx
0x140054467  or      ebp, r15d
0x14005446a  mov     r10d, ebp
0x14005446d  cmp     r10, rsi
0x140054470  ja      short loc_140054481
0x140054472  mov     rax, rsi
0x140054475  sub     rax, r10
0x140054478  cmp     rax, r9
0x14005447b  jnb     loc_140054773
0x140054481  call    ?FailOutOfRange@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@QEBAXXZ; CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(void)
0x140054487  mov     rbx, [rsp+68h+arg_0]
0x14005448c  add     rsp, 30h
0x140054490  pop     r15
0x140054492  pop     r14
0x140054494  pop     r13
0x140054496  pop     r12
0x140054498  pop     rdi
0x140054499  pop     rsi
0x14005449a  pop     rbp
0x14005449b  retn
0x14005449c  mov     rax, [rsp+68h+arg_8]
0x1400544a1  mov     rdx, [rax+8]
0x1400544a5  mov     r8, [rax]
0x1400544a8  cmp     r8, rdx
0x1400544ab  jz      short loc_140054487
0x1400544ad  sub     rdx, r8
0x1400544b0  cmp     rdx, 8
0x1400544b4  jnb     short loc_1400544CB
0x1400544b6  call    ?FailOutOfRange@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@QEBAXXZ; CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(void)
0x1400544bc  lea     rax, [r10+rdx*4]
0x1400544c0  jmp     loc_140054441
0x1400544c5  call    ?FailOutOfRange@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@QEBAXXZ; CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(void)
0x1400544cb  movzx   eax, byte ptr [r8+6]
0x1400544d0  movzx   ecx, byte ptr [r8+7]
0x1400544d5  shl     eax, 8
0x1400544d8  or      ecx, eax
0x1400544da  cmp     r12d, ecx
0x1400544dd  jnz     loc_1400549F4
0x1400544e3  add     r8, 8
0x1400544e7  lea     rdi, [rdx-8]
0x1400544eb  xor     r9d, r9d
0x1400544ee  movzx   eax, r9w
0x1400544f2  mov     [rsp+68h+arg_10], r9d
0x1400544fa  cmp     eax, r12d
0x1400544fd  jnb     short loc_140054487
0x1400544ff  cmp     rdi, 2
0x140054503  jnb     short loc_14005450B
0x140054505  call    ?FailOutOfRange@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@QEBAXXZ; CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(void)
0x14005450b  movzx   eax, byte ptr [r8]
0x14005450f  lea     r15, [r8+2]
0x140054513  movzx   ebp, byte ptr [r8+1]
0x140054518  lea     rdi, [rdi-2]
0x14005451c  shl     ax, 8
0x140054520  or      bp, ax
0x140054523  jbe     loc_14005462B
0x140054529  cmp     bp, 3
0x14005452d  jb      loc_140054A8A
0x140054533  mov     rcx, rdi
0x140054536  movzx   eax, bp
0x140054539  shr     rcx, 2
0x14005453d  cmp     rcx, rax
0x140054540  jb      loc_140054A84
0x140054546  movzx   eax, byte ptr [r15]
0x14005454a  movzx   edx, r10w
0x14005454e  shl     ax, 8
0x140054552  mov     esi, 1
0x140054557  movsx   r8d, ax
0x14005455b  movzx   eax, byte ptr [r15+1]
0x140054560  or      r8d, eax
0x140054563  movzx   r10d, r9w
0x140054567  shl     r8d, 2
0x14005456b  mov     [rsp+68h+var_40], r10
0x140054570  cmp     dx, bp
0x140054573  jnb     loc_140054623
0x140054579  movzx   r9d, dx
0x14005457d  movzx   eax, byte ptr [r15+r9*4]
0x140054582  shl     ax, 8
0x140054586  movsx   ecx, ax
0x140054589  movzx   eax, byte ptr [r15+r9*4+1]
0x14005458f  or      ecx, eax
0x140054591  mov     rax, [r14]
0x140054594  lea     r11d, ds:0[rcx*4]
0x14005459c  lea     rcx, [rax+r10*4]
0x1400545a0  cmp     [rcx], r11d
0x1400545a3  jg      loc_140054768
0x1400545a9  movzx   eax, byte ptr [r15+r9*4-2]
0x1400545af  shl     ax, 8
0x1400545b3  movsx   edx, ax
0x1400545b6  movzx   eax, byte ptr [r15+r9*4-1]
0x1400545bc  or      edx, eax
0x1400545be  movzx   eax, byte ptr [r15+r9*4+2]
0x1400545c4  shl     ax, 8
0x1400545c8  lea     esi, ds:0[rdx*4]
0x1400545cf  movsx   edx, ax
0x1400545d2  movzx   eax, byte ptr [r15+r9*4+3]
0x1400545d8  or      edx, eax
0x1400545da  lea     r13d, ds:0[rdx*4]
0x1400545e2  lea     rdx, [rsp+68h+arg_18]
0x1400545ea  call    ??GFixed16_16@@QEBA?AV0@V0@@Z; Fixed16_16::operator-(Fixed16_16)
0x1400545ef  mov     r9, rax
0x1400545f2  mov     eax, 80000000h
0x1400545f7  cmp     r8d, eax
0x1400545fa  jz      loc_140054A10
0x140054600  mov     edx, r8d
0x140054603  neg     edx
0x140054605  jmp     loc_140054A15
0x14005460a  mov     eax, 10000h
0x14005460f  cmp     r8d, eax
0x140054612  jle     short loc_140054617
0x140054614  mov     r8d, eax
0x140054617  mov     rax, [r14]
0x14005461a  mov     rcx, [rsp+68h+var_40]
0x14005461f  mov     [rax+rcx*4], r8d
0x140054623  mov     r9d, [rsp+68h+arg_10]
0x14005462b  movzx   eax, bp
0x14005462e  shl     rax, 2
0x140054632  cmp     rax, rdi
0x140054635  ja      loc_140054AA6
0x14005463b  sub     rdi, rax
0x14005463e  lea     r8, [rax+r15]
0x140054642  mov     r10d, 1
0x140054648  add     r9w, r10w
0x14005464c  jmp     loc_1400544EE
0x140054651  cmp     edx, 7FFFFFFFh
0x140054657  jz      loc_140054758
0x14005465d  cmp     edx, r11d
0x140054660  jz      loc_1400549CF
0x140054666  mov     r9d, edx
0x140054669  neg     r9d
0x14005466c  lea     eax, [r8+7FFFFFFFh]
0x140054673  cmp     eax, ecx
0x140054675  jbe     loc_140054919
0x14005467b  mov     r9d, r8d
0x14005467e  mov     ecx, 7FFFFFFFh
0x140054683  cmp     r9d, ecx
0x140054686  jz      loc_140054750
0x14005468c  cmp     r9d, r11d
0x14005468f  jz      loc_1400549DA
0x140054695  neg     r9d
0x140054698  movzx   eax, byte ptr [rdi+rbp+4]
0x14005469d  movzx   edx, byte ptr [rdi+rbp+5]
0x1400546a2  shl     eax, 8
0x1400546a5  or      edx, eax
0x1400546a7  movzx   eax, byte ptr [rdi+rbp+6]
0x1400546ac  shl     edx, 8
0x1400546af  or      edx, eax
0x1400546b1  movzx   eax, byte ptr [rdi+rbp+7]
0x1400546b6  shl     edx, 8
0x1400546b9  or      edx, eax
0x1400546bb  cmp     edx, ecx
0x1400546bd  jz      loc_140054760
0x1400546c3  cmp     edx, r11d
0x1400546c6  jz      loc_1400549E2
0x1400546cc  mov     eax, edx
0x1400546ce  neg     eax
0x1400546d0  lea     ecx, [r8+7FFFFFFFh]
0x1400546d7  mov     r10d, 0FFFFFFFDh
0x1400546dd  cmp     ecx, r10d
0x1400546e0  jbe     loc_14005493B
0x1400546e6  mov     eax, r8d
0x1400546e9  movsxd  rcx, r9d
0x1400546ec  mov     edx, eax; int
0x1400546ee  shl     rcx, 10h; __int64
0x1400546f2  call    ?Divide@Fixed16_16@@CAH_JH@Z; Fixed16_16::Divide(__int64,int)
0x1400546f7  mov     ecx, 0FFFF0000h
0x1400546fc  cmp     eax, ecx
0x1400546fe  cmovl   eax, ecx
0x140054701  xor     ecx, ecx
0x140054703  test    eax, eax
0x140054705  cmovle  ecx, eax
0x140054708  mov     rax, [r14]
0x14005470b  mov     r11d, 80000000h
0x140054711  mov     r9d, 14h
0x140054717  mov     [rax+r15*4], ecx
0x14005471b  mov     ecx, 0FFFFFFFDh
0x140054720  mov     edx, [rsp+68h+arg_10]
0x140054727  mov     r10d, 1
0x14005472d  add     edx, r10d
0x140054730  mov     [rsp+68h+arg_10], edx
0x140054737  cmp     edx, r12d
0x14005473a  jnb     loc_14005449C
0x140054740  mov     r8, [rsp+68h+var_40]
0x140054745  movzx   eax, r13w
0x140054749  add     ebp, eax
0x14005474b  jmp     loc_14005446A
0x140054750  mov     r9d, r11d
0x140054753  jmp     loc_140054698
0x140054758  mov     r9d, r11d
0x14005475b  jmp     loc_14005466C
0x140054760  mov     eax, r11d
0x140054763  jmp     loc_1400546D0
0x140054768  mov     r8d, r11d
0x14005476b  add     dx, si
0x14005476e  jmp     loc_140054570
0x140054773  movzx   eax, byte ptr [rdi+rbp+9]
0x140054778  mov     r15d, edx
0x14005477b  movsxd  rdx, dword ptr [r8+rdx*8+4]
0x140054780  movzx   r8d, byte ptr [rdi+rbp+8]
0x140054786  shl     r8d, 8
0x14005478a  or      r8d, eax
0x14005478d  movzx   eax, byte ptr [rdi+rbp+0Ah]
0x140054792  shl     r8d, 8
0x140054796  or      r8d, eax
0x140054799  movzx   eax, byte ptr [rdi+rbp+0Bh]
0x14005479e  shl     r8d, 8
0x1400547a2  or      r8d, eax
0x1400547a5  cmp     edx, r8d
0x1400547a8  jl      loc_140054651
0x1400547ae  jle     loc_140054841
0x1400547b4  cmp     r8d, 7FFFFFFFh
0x1400547bb  jz      short loc_1400547CC
0x1400547bd  cmp     r8d, r11d
0x1400547c0  jz      loc_1400549E9
0x1400547c6  mov     r11d, r8d
0x1400547c9  neg     r11d
0x1400547cc  lea     eax, [rdx+7FFFFFFFh]
0x1400547d2  cmp     eax, ecx
0x1400547d4  jbe     loc_14005495D
0x1400547da  mov     r11d, edx
0x1400547dd  movzx   eax, byte ptr [rdi+rbp+0Ch]
0x1400547e2  lea     rdx, [rsp+68h+var_48]
0x1400547e7  movzx   ecx, byte ptr [rdi+rbp+0Dh]
0x1400547ec  shl     eax, 8
0x1400547ef  or      ecx, eax
0x1400547f1  movzx   eax, byte ptr [rdi+rbp+0Eh]
0x1400547f6  shl     ecx, 8
0x1400547f9  or      ecx, eax
0x1400547fb  movzx   eax, byte ptr [rdi+rbp+0Fh]
  ... truncated ...
```
