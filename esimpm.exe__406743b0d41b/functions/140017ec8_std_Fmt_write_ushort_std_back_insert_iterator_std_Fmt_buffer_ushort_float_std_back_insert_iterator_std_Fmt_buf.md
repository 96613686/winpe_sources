# std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,float>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,float,std::_Basic_format_specs<ushort> const &,std::_Lazy_locale)

- ea: `0x140017ec8`
- end: `0x140018564`
- name: `??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@M@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@MAEBU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `1692`
- prototype: `__int16 **__fastcall(__int16 **, __int16 *, double, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14001af1c`

## callees

- `0x140002f60`
- `0x1400161e8`
- `0x140017ec8`
- `0x14001e5e8`
- `0x14001f0fc`
- `0x140020bf0`
- `0x1400229dc`
- `0x140022ad4`
- `0x140022bd8`
- `0x14003e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x1400181ed`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x1400181ed`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x140017fe4`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x140017fe4`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int16 **__fastcall std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,float>(
        __int16 **a1,
        __int16 *a2,
        double a3,
        __int64 a4,
        __int64 a5)
{
  char v7; // di
  char v8; // r13
  __int64 v9; // rdx
  char v10; // r15
  int v11; // esi
  int v12; // r12d
  __int64 v13; // rcx
  _OWORD *v14; // rax
  char *v15; // r9
  char *v16; // rdx
  unsigned int v17; // ecx
  bool v18; // al
  char v19; // di
  char *v20; // r10
  char *v21; // r11
  int v22; // r8d
  char v23; // r12
  _BYTE *v24; // r15
  char *v25; // rax
  char *v26; // rax
  struct std::locale::_Locimp *v27; // rdi
  __int64 v28; // rax
  void (__fastcall ***v29)(_QWORD, __int64); // rax
  char *v30; // rax
  int v31; // r8d
  unsigned __int64 v32; // r9
  unsigned __int64 v33; // r11
  char *v34; // r10
  int v35; // esi
  int v36; // esi
  int v37; // eax
  signed int v38; // ecx
  bool v39; // zf
  char v40; // al
  int v42; // esi
  int v43; // edi
  char v44; // al
  int v45; // edi
  __int16 *v46; // rax
  __int16 **v47; // rbx
  char v48; // [rsp+39h] [rbp-CFh] BYREF
  char v49; // [rsp+3Ah] [rbp-CEh] BYREF
  bool v50; // [rsp+3Bh] [rbp-CDh] BYREF
  int v51; // [rsp+3Ch] [rbp-CCh] BYREF
  unsigned int v52; // [rsp+40h] [rbp-C8h] BYREF
  int v53; // [rsp+44h] [rbp-C4h] BYREF
  int v54; // [rsp+48h] [rbp-C0h]
  int v55; // [rsp+4Ch] [rbp-BCh] BYREF
  char *v56; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v57[3]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v58; // [rsp+70h] [rbp-98h] BYREF
  struct std::locale::_Locimp *v59; // [rsp+78h] [rbp-90h]
  char *v60; // [rsp+80h] [rbp-88h] BYREF
  __int16 *v61[2]; // [rsp+88h] [rbp-80h] BYREF
  char *v62; // [rsp+98h] [rbp-70h] BYREF
  __int16 **v63; // [rsp+A0h] [rbp-68h]
  _QWORD v64[16]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v65; // [rsp+128h] [rbp+20h] BYREF
  __int128 v66; // [rsp+138h] [rbp+30h]
  __int128 v67; // [rsp+148h] [rbp+40h] BYREF
  __int128 v68; // [rsp+158h] [rbp+50h]
  char v69; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v70[1384]; // [rsp+169h] [rbp+61h] BYREF
  _BYTE v71[7]; // [rsp+6D1h] [rbp+5C9h] BYREF

  v63 = a1;
  v48 = *(_BYTE *)(a4 + 10);
  if ( !v48 )
    v48 = 2;
  v7 = 0;
  v8 = 101;
  v9 = *(unsigned int *)(a4 + 4);
  v10 = 0;
  v11 = 4;
  switch ( *(_BYTE *)(a4 + 8) )
  {
    case 'A':
      v7 = 1;
      goto LABEL_27;
    case 'E':
      v7 = 1;
      goto LABEL_23;
    case 'F':
      v7 = 1;
LABEL_19:
      if ( (_DWORD)v9 == -1 )
        v9 = 6;
      v11 = 2;
      goto LABEL_28;
    case 'G':
      v7 = 1;
LABEL_13:
      if ( (_DWORD)v9 == -1 )
      {
        v9 = 6;
      }
      else if ( !(_DWORD)v9 )
      {
        v9 = 1;
      }
      v11 = 3;
      goto LABEL_28;
    case 'a':
LABEL_27:
      v8 = 112;
      goto LABEL_28;
  }
  if ( *(_BYTE *)(a4 + 8) != 101 )
  {
    if ( *(_BYTE *)(a4 + 8) != 102 )
    {
      if ( *(_BYTE *)(a4 + 8) != 103 )
      {
        v11 = 3;
        v10 = 1;
        goto LABEL_28;
      }
      goto LABEL_13;
    }
    goto LABEL_19;
  }
LABEL_23:
  if ( (_DWORD)v9 == -1 )
    v9 = 6;
  v11 = 1;
LABEL_28:
  *(_OWORD *)&v57[1] = 0;
  v12 = v9;
  if ( (int)v9 > 1074 )
    v12 = 1074;
  LODWORD(v61[0]) = v12;
  v13 = (unsigned int)(v9 - 1074);
  if ( (int)v9 <= 1074 )
    v13 = 0;
  v54 = v13;
  v50 = (unsigned int)_o__fdsign(v13, v9, 1074, 2) != 0;
  if ( v12 == -1 )
  {
    if ( v10 )
      v14 = (_OWORD *)std::to_chars(&v58, &v69, v71);
    else
      v14 = (_OWORD *)std::to_chars(&v58, &v69, v71);
  }
  else
  {
    v14 = (_OWORD *)std::to_chars(&v58, &v69, v71);
  }
  *(_OWORD *)&v57[1] = *v14;
  v15 = (char *)v57[1];
  v16 = &v69;
  v56 = &v69;
  v17 = LODWORD(v57[1]) - (unsigned int)&v69;
  v52 = v17;
  if ( v50 )
  {
    v16 = v70;
    v56 = v70;
  }
  else if ( v48 != 2 )
  {
    v52 = ++v17;
  }
  if ( v7 )
  {
    if ( v16 != (char *)v57[1] )
    {
      do
      {
        if ( (unsigned __int8)(*v16 - 97) <= 0x19u )
          *v16 -= 32;
        ++v16;
      }
      while ( v16 != v15 );
      v15 = (char *)v57[1];
      v16 = v56;
      v17 = v52;
    }
    v8 -= 32;
  }
  v18 = (_mm_cvtsi128_si32(*(__m128i *)&a3) & 0x7F800000) == 2139095040;
  v19 = 0;
  v49 = 0;
  v20 = v15;
  v57[0] = v15;
  v21 = v15;
  v62 = v15;
  v60 = v15;
  v22 = 0;
  v53 = 0;
  v55 = 0;
  v65 = 0;
  *(_QWORD *)&v66 = 0;
  *((_QWORD *)&v66 + 1) = 15;
  LOBYTE(v65) = 0;
  if ( !v18 )
  {
    v23 = *(_BYTE *)(a4 + 11);
    if ( v23 || (v24 = (_BYTE *)(a4 + 12), *(_BYTE *)(a4 + 12)) )
    {
      v25 = v16;
      if ( v16 >= v15 )
        goto LABEL_58;
      do
      {
        if ( *v25 == 46 )
        {
          v21 = v25;
          v62 = v25;
        }
        else if ( *v25 == v8 )
        {
          v20 = v25;
          v57[0] = v25;
        }
        ++v25;
      }
      while ( v25 < v15 );
      v26 = v20;
      if ( v20 >= v21 )
LABEL_58:
        v26 = v21;
      v60 = v26;
      if ( v23 && v21 == v15 )
      {
        v52 = ++v17;
        v19 = 1;
        v49 = 1;
      }
      v24 = (_BYTE *)(a4 + 12);
      if ( *(_BYTE *)(a4 + 12) )
      {
        if ( a5 )
        {
          v27 = *(struct std::locale::_Locimp **)(a5 + 8);
          v59 = v27;
          (*(void (__fastcall **)(struct std::locale::_Locimp *, char *, _QWORD))(*(_QWORD *)v27 + 8LL))(v27, v16, 0);
        }
        else
        {
          v27 = std::locale::_Init(1);
          v59 = v27;
        }
        v28 = std::use_facet<std::numpunct<unsigned short>>(&v58);
        (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v28 + 40LL))(v28, &v67);
        std::string::_Tidy_deallocate(&v65);
        v65 = v67;
        v66 = v68;
        *(_QWORD *)&v68 = 0;
        *((_QWORD *)&v68 + 1) = 15;
        LOBYTE(v67) = 0;
        std::string::_Tidy_deallocate(&v67);
        if ( v27 )
        {
          v29 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v27 + 16LL))(v27);
          if ( v29 )
            (**v29)(v29, 1);
        }
        v30 = (char *)&v65;
        if ( *((_QWORD *)&v66 + 1) > 0xFu )
          v30 = (char *)v65;
        v16 = v56;
        v31 = 0;
        if ( (_QWORD)v66 )
        {
          v32 = v60 - v56;
          v33 = *v30;
          if ( v60 - v56 > v33 )
          {
            v34 = &v30[v66];
            do
            {
              v32 -= (char)v33;
              ++v31;
              if ( v30 + 1 != v34 )
                ++v30;
              v33 = *v30;
            }
            while ( v32 > v33 );
          }
        }
        v55 = v31;
        v17 = v31 + v52;
        v52 += v31;
        v15 = (char *)v57[1];
        v19 = v49;
        v20 = (char *)v57[0];
        v22 = v53;
      }
    }
    v35 = v11 - 1;
    if ( v35 )
    {
      v36 = v35 - 1;
      if ( !v36 )
      {
        v22 = v54;
LABEL_101:
        v53 = v22;
LABEL_102:
        v18 = 0;
        goto LABEL_103;
      }
      if ( v36 == 1 )
      {
        if ( *(_BYTE *)(a4 + 11) && ((*(_BYTE *)(a4 + 8) - 71) & 0xDF) == 0 )
        {
          v37 = (_DWORD)v20 - (_DWORD)v16;
          if ( !v19 )
            --v37;
          v22 = LODWORD(v61[0]) + v54 - v37;
          v53 = v22;
          if ( v20 == v15 && COERCE_FLOAT(LODWORD(a3) & _xmm) < 1.0 && *(float *)&a3 != 0.0 )
          {
            while ( v16 < v15 )
            {
              if ( *v16 == 48 )
              {
                v53 = ++v22;
              }
              else if ( *v16 != 46 )
              {
                goto LABEL_102;
              }
              ++v16;
            }
          }
        }
        goto LABEL_102;
      }
    }
    v22 = v54;
    if ( v54 && !*(_BYTE *)(a4 + 11) && !*v24 )
    {
      do
        v57[0] = --v20;
      while ( *v20 != v8 );
    }
    goto LABEL_101;
  }
LABEL_103:
  v38 = v22 + v17;
  v52 = v38;
  if ( !*(_BYTE *)(a4 + 13) || *(_BYTE *)(a4 + 9) || (v39 = !v18, v40 = 1, !v39) )
    v40 = 0;
  LOBYTE(v51) = v40;
  v64[0] = &v48;
  v64[1] = &v50;
  v64[2] = &v51;
  v64[3] = &v52;
  v64[4] = a4;
  v64[5] = &a5;
  v64[6] = &v56;
  v64[7] = &v60;
  v64[8] = &v65;
  v64[9] = &v55;
  v64[10] = &v62;
  v64[11] = &v57[1];
  v64[12] = &v49;
  v64[13] = v57;
  v64[14] = &v53;
  if ( v40 )
  {
    `std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,long double>'::`2'::_lambda_1_::operator()(
      v64,
      v63,
      a2);
    std::string::_Tidy_deallocate(&v65);
    return v63;
  }
  v42 = 0;
  v43 = 0;
  v44 = *(_BYTE *)(a4 + 9);
  if ( !v44 )
    v44 = 2;
  if ( v38 < *(_DWORD *)a4 )
  {
    switch ( v44 )
    {
      case 1:
        v45 = *(_DWORD *)a4;
        break;
      case 2:
        v42 = *(_DWORD *)a4 - v38;
        goto LABEL_119;
      case 3:
        v42 = (*(_DWORD *)a4 - v38) / 2;
        v45 = *(_DWORD *)a4 - v42;
        break;
      default:
        goto LABEL_119;
    }
    v43 = v45 - v38;
  }
LABEL_119:
  v58 = a4 + 16;
  v59 = (struct std::locale::_Locimp *)*(unsigned __int8 *)(a4 + 14);
  while ( v42 > 0 )
  {
    a2 = std::ranges::_Copy_fn::operator()<std::basic_string_view<unsigned short> const &,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
           v61,
           (__int64)&v58,
           (__int64)a2)[1];
    --v42;
  }
  v46 = *(__int16 **)`std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,long double>'::`2'::_lambda_1_::operator()(
                       v64,
                       v61,
                       a2);
  while ( v43 > 0 )
  {
    v46 = std::ranges::_Copy_fn::operator()<std::basic_string_view<unsigned short> const &,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
            v61,
            (__int64)&v58,
            (__int64)v46)[1];
    --v43;
  }
  v47 = v63;
  *v63 = v46;
  std::string::_Tidy_deallocate(&v65);
  return v47;
}

```

## disassembly

```asm
0x140017ec8  mov     rax, rsp
0x140017ecb  mov     [rax+10h], rbx
0x140017ecf  push    rbp
0x140017ed0  push    rsi
0x140017ed1  push    rdi
0x140017ed2  push    r12
0x140017ed4  push    r13
0x140017ed6  push    r14
0x140017ed8  push    r15
0x140017eda  lea     rbp, [rax-628h]
0x140017ee1  sub     rsp, 6F0h
0x140017ee8  movaps  xmmword ptr [rax-48h], xmm6
0x140017eec  mov     rax, cs:__security_cookie
0x140017ef3  xor     rax, rsp
0x140017ef6  mov     [rbp+620h+var_50], rax
0x140017efd  mov     r14, r9
0x140017f00  movaps  xmm6, xmm2
0x140017f03  mov     rbx, rdx
0x140017f06  mov     [rbp+620h+var_688], rcx
0x140017f0a  mov     al, [r9+0Ah]
0x140017f0e  mov     byte ptr [rsp+720h+var_6F0+1], al
0x140017f12  mov     r9d, 2
0x140017f18  test    al, al
0x140017f1a  jnz     short loc_140017F21
0x140017f1c  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x140017f21  xor     dil, dil
0x140017f24  mov     r13b, 65h ; 'e'
0x140017f27  mov     edx, [r14+4]
0x140017f2b  xor     r15b, r15b
0x140017f2e  movsx   ecx, byte ptr [r14+8]
0x140017f33  mov     esi, 4
0x140017f38  lea     r8d, [rsi-3]
0x140017f3c  sub     ecx, 41h ; 'A'
0x140017f3f  jz      short loc_140017FAD
0x140017f41  sub     ecx, esi
0x140017f43  jz      short loc_140017F9A
0x140017f45  sub     ecx, r8d
0x140017f48  jz      short loc_140017F87
0x140017f4a  sub     ecx, r8d
0x140017f4d  jz      short loc_140017F6B
0x140017f4f  sub     ecx, 1Ah
0x140017f52  jz      short loc_140017FB0
0x140017f54  sub     ecx, esi
0x140017f56  jz      short loc_140017F9D
0x140017f58  sub     ecx, r8d
0x140017f5b  jz      short loc_140017F8A
0x140017f5d  cmp     ecx, r8d
0x140017f60  jz      short loc_140017F6E
0x140017f62  lea     esi, [r8+2]
0x140017f66  mov     r15b, r8b
0x140017f69  jmp     short loc_140017FB3
0x140017f6b  mov     dil, r8b
0x140017f6e  cmp     edx, 0FFFFFFFFh
0x140017f71  jnz     short loc_140017F7A
0x140017f73  mov     edx, 6
0x140017f78  jmp     short loc_140017F80
0x140017f7a  test    edx, edx
0x140017f7c  cmovz   edx, r8d
0x140017f80  mov     esi, 3
0x140017f85  jmp     short loc_140017FB3
0x140017f87  mov     dil, r8b
0x140017f8a  mov     eax, 6
0x140017f8f  cmp     edx, 0FFFFFFFFh
0x140017f92  cmovz   edx, eax
0x140017f95  mov     esi, r9d
0x140017f98  jmp     short loc_140017FB3
0x140017f9a  mov     dil, r8b
0x140017f9d  mov     eax, 6
0x140017fa2  cmp     edx, 0FFFFFFFFh
0x140017fa5  cmovz   edx, eax
0x140017fa8  mov     esi, r8d
0x140017fab  jmp     short loc_140017FB3
0x140017fad  mov     dil, r8b
0x140017fb0  mov     r13b, 70h ; 'p'
0x140017fb3  xorps   xmm0, xmm0
0x140017fb6  movups  xmmword ptr [rsp+720h+var_6D0+8], xmm0
0x140017fbb  mov     r12d, edx
0x140017fbe  mov     r8d, 432h
0x140017fc4  cmp     edx, r8d
0x140017fc7  cmovg   r12d, r8d
0x140017fcb  mov     [rbp+620h+var_6A0], r12d
0x140017fcf  lea     ecx, [rdx-432h]
0x140017fd5  xor     eax, eax
0x140017fd7  cmp     edx, r8d
0x140017fda  cmovle  ecx, eax
0x140017fdd  mov     dword ptr [rsp+720h+var_6E0], ecx
0x140017fe1  movaps  xmm0, xmm6
0x140017fe4  call    cs:__imp__o__fdsign
0x140017fea  mov     edx, eax
0x140017fec  test    eax, eax
0x140017fee  setnz   byte ptr [rsp+720h+var_6F0+3]
0x140017ff3  ucomiss xmm6, xmm6
0x140017ff6  setp    al
0x140017ff9  cmp     al, 1
0x140017ffb  jnz     short loc_140018035
0x140017ffd  lea     rax, [rbp+620h+var_5C0]
0x140018001  lea     rcx, [rbp+620h+var_5BF]
0x140018005  xor     r12d, r12d
0x140018008  test    edx, edx
0x14001800a  cmovz   rcx, rax
0x14001800e  mov     qword ptr [rsp+720h+var_6D0+8], rcx
0x140018013  mov     eax, dword ptr cs:aNan; "nan"
0x140018019  mov     [rcx], ax
0x14001801c  mov     al, byte ptr cs:aNan+2; "n"
0x140018022  mov     [rcx+2], al
0x140018025  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x14001802a  add     r9, 3
0x14001802e  mov     qword ptr [rsp+720h+var_6D0+8], r9
0x140018033  jmp     short loc_140018086
0x140018035  movaps  xmm3, xmm6
0x140018038  lea     r8, [rbp+620h+var_57]
0x14001803f  lea     rdx, [rbp+620h+var_5C0]
0x140018043  lea     rcx, [rsp+720h+var_6B8]
0x140018048  cmp     r12d, 0FFFFFFFFh
0x14001804c  jnz     short loc_140018068
0x14001804e  xor     r12d, r12d
0x140018051  test    r15b, r15b
0x140018054  jz      short loc_14001805D
0x140018056  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0M@Z; std::to_chars(char * const,char * const,float)
0x14001805b  jmp     short loc_140018079
0x14001805d  mov     [rsp+720h+var_700], esi
0x140018061  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0MW4chars_format@1@@Z; std::to_chars(char * const,char * const,float,std::chars_format)
0x140018066  jmp     short loc_140018079
0x140018068  mov     dword ptr [rsp+720h+var_6F8], r12d
0x14001806d  mov     [rsp+720h+var_700], esi
0x140018071  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0MW4chars_format@1@H@Z; std::to_chars(char * const,char * const,float,std::chars_format,int)
0x140018076  xor     r12d, r12d
0x140018079  movups  xmm0, xmmword ptr [rax]
0x14001807c  movups  xmmword ptr [rsp+720h+var_6D0+8], xmm0
0x140018081  movq    r9, xmm0
0x140018086  lea     rdx, [rbp+620h+var_5C0]
0x14001808a  mov     [rsp+720h+var_6D8], rdx
0x14001808f  mov     ecx, r9d
0x140018092  sub     ecx, edx
0x140018094  mov     [rsp+720h+var_6E8], ecx
0x140018098  cmp     byte ptr [rsp+720h+var_6F0+3], r12b
0x14001809d  jz      short loc_1400180AA
0x14001809f  lea     rdx, [rbp+620h+var_5BF]
0x1400180a3  mov     [rsp+720h+var_6D8], rdx
0x1400180a8  jmp     short loc_1400180B7
0x1400180aa  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x1400180af  jz      short loc_1400180B7
0x1400180b1  inc     ecx
0x1400180b3  mov     [rsp+720h+var_6E8], ecx
0x1400180b7  test    dil, dil
0x1400180ba  jz      short loc_1400180E9
0x1400180bc  cmp     rdx, r9
0x1400180bf  jz      short loc_1400180E5
0x1400180c1  mov     cl, [rdx]
0x1400180c3  lea     eax, [rcx-61h]
0x1400180c6  cmp     al, 19h
0x1400180c8  ja      short loc_1400180CF
0x1400180ca  sub     cl, 20h ; ' '
0x1400180cd  mov     [rdx], cl
0x1400180cf  inc     rdx
0x1400180d2  cmp     rdx, r9
0x1400180d5  jnz     short loc_1400180C1
0x1400180d7  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x1400180dc  mov     rdx, [rsp+720h+var_6D8]
0x1400180e1  mov     ecx, [rsp+720h+var_6E8]
0x1400180e5  add     r13b, 0E0h
0x1400180e9  movd    eax, xmm6
0x1400180ed  mov     r8d, 7F800000h
0x1400180f3  and     eax, r8d
0x1400180f6  cmp     eax, r8d
0x1400180f9  setnz   al
0x1400180fc  xor     al, 1
0x1400180fe  mov     byte ptr [rsp+720h+var_6F0], al
0x140018102  mov     dil, r12b
0x140018105  mov     byte ptr [rsp+720h+var_6F0+2], r12b
0x14001810a  mov     r10, r9
0x14001810d  mov     qword ptr [rsp+720h+var_6D0], r9
0x140018112  mov     r11, r9
0x140018115  mov     [rbp+620h+var_690], r9
0x140018119  mov     [rsp+720h+var_6A8], r9
0x14001811e  mov     r8d, r12d
0x140018121  mov     [rsp+720h+var_6E4], r12d
0x140018126  mov     dword ptr [rsp+720h+var_6E0+4], r12d
0x14001812b  xorps   xmm0, xmm0
0x14001812e  movups  [rbp+620h+var_600], xmm0
0x140018132  mov     qword ptr [rbp+620h+var_5F0], r12
0x140018136  mov     qword ptr [rbp+620h+var_5F0+8], 0Fh
0x14001813e  mov     byte ptr [rbp+620h+var_600], r12b
0x140018142  jnz     loc_1400183B1
0x140018148  mov     r12b, [r14+0Bh]
0x14001814c  test    r12b, r12b
0x14001814f  jnz     short loc_140018162
0x140018151  lea     r15, [r14+0Ch]
0x140018155  cmp     [r15], r12b
0x140018158  jnz     short loc_140018162
0x14001815a  xor     r12d, r12d
0x14001815d  jmp     loc_1400182EC
0x140018162  mov     rax, rdx
0x140018165  cmp     rdx, r9
0x140018168  jnb     short loc_140018195
0x14001816a  cmp     byte ptr [rax], 2Eh ; '.'
0x14001816d  jnz     short loc_140018178
0x14001816f  mov     r11, rax
0x140018172  mov     [rbp+620h+var_690], rax
0x140018176  jmp     short loc_140018185
0x140018178  cmp     [rax], r13b
0x14001817b  jnz     short loc_140018185
0x14001817d  mov     r10, rax
0x140018180  mov     qword ptr [rsp+720h+var_6D0], rax
0x140018185  inc     rax
0x140018188  cmp     rax, r9
0x14001818b  jb      short loc_14001816A
0x14001818d  cmp     r10, r11
0x140018190  mov     rax, r10
0x140018193  jb      short loc_140018198
0x140018195  mov     rax, r11
0x140018198  mov     [rsp+720h+var_6A8], rax
0x14001819d  test    r12b, r12b
0x1400181a0  jz      short loc_1400181B5
0x1400181a2  cmp     r11, r9
0x1400181a5  jnz     short loc_1400181B5
0x1400181a7  inc     ecx
0x1400181a9  mov     [rsp+720h+var_6E8], ecx
0x1400181ad  mov     dil, 1
0x1400181b0  mov     byte ptr [rsp+720h+var_6F0+2], dil
0x1400181b5  lea     r15, [r14+0Ch]
0x1400181b9  xor     r12d, r12d
0x1400181bc  cmp     [r15], r12b
0x1400181bf  jz      loc_1400182EC
0x1400181c5  mov     rax, [rbp+620h+arg_20]
0x1400181cc  test    rax, rax
0x1400181cf  jz      short loc_1400181EB
0x1400181d1  mov     rdi, [rax+8]
0x1400181d5  mov     [rsp+720h+var_6B0], rdi
0x1400181da  mov     rax, [rdi]
0x1400181dd  mov     rcx, rdi
0x1400181e0  mov     rax, [rax+8]
0x1400181e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400181e9  jmp     short loc_1400181FB
0x1400181eb  mov     cl, 1
0x1400181ed  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x1400181f3  mov     rdi, rax
0x1400181f6  mov     [rsp+720h+var_6B0], rax
0x1400181fb  lea     rcx, [rsp+720h+var_6B8]
0x140018200  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x140018205  mov     rcx, rax
0x140018208  mov     rax, [rax]
0x14001820b  lea     rdx, [rbp+620h+var_5E0]
0x14001820f  mov     rax, [rax+28h]
0x140018213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018218  lea     rcx, [rbp+620h+var_600]
0x14001821c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140018221  movups  xmm0, [rbp+620h+var_5E0]
0x140018225  movups  [rbp+620h+var_600], xmm0
0x140018229  movups  xmm1, [rbp+620h+var_5D0]
0x14001822d  movups  [rbp+620h+var_5F0], xmm1
0x140018231  mov     qword ptr [rbp+620h+var_5D0], r12
0x140018235  mov     qword ptr [rbp+620h+var_5D0+8], 0Fh
0x14001823d  mov     byte ptr [rbp+620h+var_5E0], r12b
0x140018241  lea     rcx, [rbp+620h+var_5E0]
0x140018245  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001824a  nop
0x14001824b  test    rdi, rdi
0x14001824e  jz      short loc_140018277
0x140018250  mov     rax, [rdi]
0x140018253  mov     rcx, rdi
0x140018256  mov     rax, [rax+10h]
0x14001825a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001825f  mov     rcx, rax
0x140018262  test    rax, rax
0x140018265  jz      short loc_140018277
0x140018267  mov     rax, [rax]
0x14001826a  mov     edx, 1
0x14001826f  mov     rax, [rax]
0x140018272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018277  lea     rax, [rbp+620h+var_600]
0x14001827b  cmp     qword ptr [rbp+620h+var_5F0+8], 0Fh
0x140018280  cmova   rax, qword ptr [rbp+620h+var_600]
0x140018285  mov     r10, qword ptr [rbp+620h+var_5F0]
0x140018289  mov     rdx, [rsp+720h+var_6D8]
0x14001828e  mov     r8d, r12d
0x140018291  test    r10, r10
0x140018294  jz      short loc_1400182C8
0x140018296  mov     r9, [rsp+720h+var_6A8]
0x14001829b  sub     r9, rdx
0x14001829e  movsx   r11, byte ptr [rax]
0x1400182a2  cmp     r9, r11
0x1400182a5  jbe     short loc_1400182C8
0x1400182a7  add     r10, rax
0x1400182aa  movsx   rcx, r11b
0x1400182ae  sub     r9, rcx
0x1400182b1  inc     r8d
0x1400182b4  lea     rcx, [rax+1]
0x1400182b8  cmp     rcx, r10
0x1400182bb  cmovnz  rax, rcx
0x1400182bf  movsx   r11, byte ptr [rax]
0x1400182c3  cmp     r9, r11
0x1400182c6  ja      short loc_1400182AA
0x1400182c8  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x1400182cd  mov     ecx, [rsp+720h+var_6E8]
0x1400182d1  add     ecx, r8d
0x1400182d4  mov     [rsp+720h+var_6E8], ecx
0x1400182d8  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x1400182dd  mov     dil, byte ptr [rsp+720h+var_6F0+2]
0x1400182e2  mov     r10, qword ptr [rsp+720h+var_6D0]
  ... truncated ...
```
