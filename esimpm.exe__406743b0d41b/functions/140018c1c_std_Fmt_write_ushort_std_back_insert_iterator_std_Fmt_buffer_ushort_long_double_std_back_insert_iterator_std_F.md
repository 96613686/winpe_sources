# std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,long double>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,long double,std::_Basic_format_specs<ushort> const &,std::_Lazy_locale)

- ea: `0x140018c1c`
- end: `0x1400192c5`
- name: `??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@O@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@OAEBU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `1705`
- prototype: `__int16 **__fastcall(__int16 **, __int16 *, long double, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14001af1c`

## callees

- `0x140002f60`
- `0x1400161e8`
- `0x140016948`
- `0x140016a74`
- `0x140016c20`
- `0x140018c1c`
- `0x14001e5e8`
- `0x14001f0fc`
- `0x140020bf0`
- `0x14003e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x140018f50`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x140018f50`
- `api-ms-win-crt-private-l1-1-0!_o__ldsign` at `0x140018d37`
- `api-ms-win-crt-private-l1-1-0!_o__ldsign` at `0x140018d37`

## pseudocode

```c
__int16 **__fastcall std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,long double>(
        __int16 **a1,
        __int16 *a2,
        long double a3,
        __int64 a4,
        __int64 a5)
{
  char v7; // di
  char v8; // r13
  int v9; // edx
  char v10; // r15
  int v11; // esi
  int v12; // r12d
  int v13; // ecx
  char *v14; // r9
  char *v15; // rdx
  int v16; // ecx
  bool v17; // al
  char v18; // di
  char *v19; // r10
  char *v20; // r11
  int v21; // r8d
  char v22; // r12
  _BYTE *v23; // r15
  char *v24; // rax
  char *v25; // rax
  struct std::locale::_Locimp *v26; // rdi
  __int64 v27; // rax
  void (__fastcall ***v28)(_QWORD, __int64); // rax
  char *v29; // rax
  int v30; // r8d
  unsigned __int64 v31; // r9
  unsigned __int64 v32; // r11
  char *v33; // r10
  int v34; // esi
  int v35; // esi
  int v36; // eax
  int v37; // ecx
  bool v38; // zf
  char v39; // al
  int v41; // esi
  int v42; // edi
  char v43; // al
  int v44; // edi
  __int16 *v45; // rax
  __int16 **v46; // rbx
  char v47; // [rsp+39h] [rbp-CFh] BYREF
  char v48; // [rsp+3Ah] [rbp-CEh] BYREF
  bool v49; // [rsp+3Bh] [rbp-CDh] BYREF
  int v50; // [rsp+3Ch] [rbp-CCh] BYREF
  int v51; // [rsp+40h] [rbp-C8h] BYREF
  int v52; // [rsp+44h] [rbp-C4h] BYREF
  int v53; // [rsp+48h] [rbp-C0h]
  __int128 v54; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v55; // [rsp+68h] [rbp-A0h] BYREF
  char *v56; // [rsp+70h] [rbp-98h] BYREF
  char *v57; // [rsp+78h] [rbp-90h] BYREF
  __int128 v58; // [rsp+88h] [rbp-80h] BYREF
  char *v59; // [rsp+98h] [rbp-70h] BYREF
  __int16 *v60[2]; // [rsp+A0h] [rbp-68h] BYREF
  char *v61; // [rsp+B0h] [rbp-58h] BYREF
  __int16 **v62; // [rsp+B8h] [rbp-50h]
  _QWORD v63[16]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v64; // [rsp+148h] [rbp+40h] BYREF
  __int128 v65; // [rsp+158h] [rbp+50h]
  __int128 v66; // [rsp+168h] [rbp+60h] BYREF
  __int128 v67; // [rsp+178h] [rbp+70h]
  char v68; // [rsp+188h] [rbp+80h] BYREF
  _BYTE v69[1384]; // [rsp+189h] [rbp+81h] BYREF
  _BYTE v70[7]; // [rsp+6F1h] [rbp+5E9h] BYREF

  v62 = a1;
  v47 = *(_BYTE *)(a4 + 10);
  if ( !v47 )
    v47 = 2;
  v7 = 0;
  v8 = 101;
  v9 = *(_DWORD *)(a4 + 4);
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
      if ( v9 == -1 )
        v9 = 6;
      v11 = 2;
      goto LABEL_28;
    case 'G':
      v7 = 1;
LABEL_13:
      if ( v9 == -1 )
      {
        v9 = 6;
      }
      else if ( !v9 )
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
  if ( v9 == -1 )
    v9 = 6;
  v11 = 1;
LABEL_28:
  v58 = 0;
  v12 = v9;
  if ( v9 > 1074 )
    v12 = 1074;
  LODWORD(v60[0]) = v12;
  v13 = v9 - 1074;
  if ( v9 <= 1074 )
    v13 = 0;
  v53 = v13;
  v49 = _ldsign(a3) != 0;
  if ( v12 == -1 )
  {
    if ( v10 )
      std::_Floating_to_chars<0,double>(&v54, &v68, v70);
    else
      std::_Floating_to_chars<1,double>(&v54, &v68, v70);
  }
  else
  {
    std::_Floating_to_chars<2,double>(&v54, &v68, v70);
  }
  v58 = v54;
  v14 = (char *)v54;
  v15 = &v68;
  v56 = &v68;
  v16 = v54 - (unsigned int)&v68;
  v51 = v16;
  if ( v49 )
  {
    v15 = v69;
    v56 = v69;
  }
  else if ( v47 != 2 )
  {
    v51 = ++v16;
  }
  if ( v7 )
  {
    if ( v15 != (char *)v54 )
    {
      do
      {
        if ( (unsigned __int8)(*v15 - 97) <= 0x19u )
          *v15 -= 32;
        ++v15;
      }
      while ( v15 != v14 );
      v14 = (char *)v58;
      v15 = v56;
      v16 = v51;
    }
    v8 -= 32;
  }
  v17 = ((*(_QWORD *)&a3 >> 52) & 0x7FF) == 2047;
  v18 = 0;
  v48 = 0;
  v19 = v14;
  v57 = v14;
  v20 = v14;
  v61 = v14;
  v59 = v14;
  v21 = 0;
  v52 = 0;
  LODWORD(v55) = 0;
  v64 = 0;
  *(_QWORD *)&v65 = 0;
  *((_QWORD *)&v65 + 1) = 15;
  LOBYTE(v64) = 0;
  if ( ((*(_QWORD *)&a3 >> 52) & 0x7FF) != 0x7FF )
  {
    v22 = *(_BYTE *)(a4 + 11);
    if ( v22 || (v23 = (_BYTE *)(a4 + 12), *(_BYTE *)(a4 + 12)) )
    {
      v24 = v15;
      if ( v15 >= v14 )
        goto LABEL_58;
      do
      {
        if ( *v24 == 46 )
        {
          v20 = v24;
          v61 = v24;
        }
        else if ( *v24 == v8 )
        {
          v19 = v24;
          v57 = v24;
        }
        ++v24;
      }
      while ( v24 < v14 );
      v25 = v19;
      if ( v19 >= v20 )
LABEL_58:
        v25 = v20;
      v59 = v25;
      if ( v22 && v20 == v14 )
      {
        v51 = ++v16;
        v18 = 1;
        v48 = 1;
      }
      v23 = (_BYTE *)(a4 + 12);
      if ( *(_BYTE *)(a4 + 12) )
      {
        if ( a5 )
        {
          v26 = *(struct std::locale::_Locimp **)(a5 + 8);
          *((_QWORD *)&v54 + 1) = v26;
          (*(void (__fastcall **)(struct std::locale::_Locimp *, char *, _QWORD))(*(_QWORD *)v26 + 8LL))(v26, v15, 0);
        }
        else
        {
          v26 = std::locale::_Init(1);
          *((_QWORD *)&v54 + 1) = v26;
        }
        v27 = std::use_facet<std::numpunct<unsigned short>>(&v54);
        (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v27 + 40LL))(v27, &v66);
        std::string::_Tidy_deallocate(&v64);
        v64 = v66;
        v65 = v67;
        *(_QWORD *)&v67 = 0;
        *((_QWORD *)&v67 + 1) = 15;
        LOBYTE(v66) = 0;
        std::string::_Tidy_deallocate(&v66);
        if ( v26 )
        {
          v28 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v26 + 16LL))(v26);
          if ( v28 )
            (**v28)(v28, 1);
        }
        v29 = (char *)&v64;
        if ( *((_QWORD *)&v65 + 1) > 0xFu )
          v29 = (char *)v64;
        v15 = v56;
        v30 = 0;
        if ( (_QWORD)v65 )
        {
          v31 = v59 - v56;
          v32 = *v29;
          if ( v59 - v56 > v32 )
          {
            v33 = &v29[v65];
            do
            {
              v31 -= (char)v32;
              ++v30;
              if ( v29 + 1 != v33 )
                ++v29;
              v32 = *v29;
            }
            while ( v31 > v32 );
          }
        }
        LODWORD(v55) = v30;
        v16 = v30 + v51;
        v51 += v30;
        v14 = (char *)v58;
        v18 = v48;
        v19 = v57;
        v21 = v52;
      }
    }
    v34 = v11 - 1;
    if ( v34 )
    {
      v35 = v34 - 1;
      if ( !v35 )
      {
        v21 = v53;
LABEL_101:
        v52 = v21;
LABEL_102:
        v17 = 0;
        goto LABEL_103;
      }
      if ( v35 == 1 )
      {
        if ( *(_BYTE *)(a4 + 11) && ((*(_BYTE *)(a4 + 8) - 71) & 0xDF) == 0 )
        {
          v36 = (_DWORD)v19 - (_DWORD)v15;
          if ( !v18 )
            --v36;
          v21 = LODWORD(v60[0]) + v53 - v36;
          v52 = v21;
          if ( v19 == v14 && COERCE_DOUBLE(*(_QWORD *)&a3 & _xmm) < 1.0 && a3 != 0.0 )
          {
            while ( v15 < v14 )
            {
              if ( *v15 == 48 )
              {
                v52 = ++v21;
              }
              else if ( *v15 != 46 )
              {
                goto LABEL_102;
              }
              ++v15;
            }
          }
        }
        goto LABEL_102;
      }
    }
    v21 = v53;
    if ( v53 && !*(_BYTE *)(a4 + 11) && !*v23 )
    {
      do
        v57 = --v19;
      while ( *v19 != v8 );
    }
    goto LABEL_101;
  }
LABEL_103:
  v37 = v21 + v16;
  v51 = v37;
  if ( !*(_BYTE *)(a4 + 13) || *(_BYTE *)(a4 + 9) || (v38 = !v17, v39 = 1, !v38) )
    v39 = 0;
  LOBYTE(v50) = v39;
  v63[0] = &v47;
  v63[1] = &v49;
  v63[2] = &v50;
  v63[3] = &v51;
  v63[4] = a4;
  v63[5] = &a5;
  v63[6] = &v56;
  v63[7] = &v59;
  v63[8] = &v64;
  v63[9] = &v55;
  v63[10] = &v61;
  v63[11] = &v58;
  v63[12] = &v48;
  v63[13] = &v57;
  v63[14] = &v52;
  if ( v39 )
  {
    `std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,long double>'::`2'::_lambda_1_::operator()(
      v63,
      v62,
      a2);
    std::string::_Tidy_deallocate(&v64);
    return v62;
  }
  v41 = 0;
  v42 = 0;
  v43 = *(_BYTE *)(a4 + 9);
  if ( !v43 )
    v43 = 2;
  if ( v37 < *(_DWORD *)a4 )
  {
    switch ( v43 )
    {
      case 1:
        v44 = *(_DWORD *)a4;
        break;
      case 2:
        v41 = *(_DWORD *)a4 - v37;
        goto LABEL_119;
      case 3:
        v41 = (*(_DWORD *)a4 - v37) / 2;
        v44 = *(_DWORD *)a4 - v41;
        break;
      default:
        goto LABEL_119;
    }
    v42 = v44 - v37;
  }
LABEL_119:
  *(_QWORD *)&v54 = a4 + 16;
  *((_QWORD *)&v54 + 1) = *(unsigned __int8 *)(a4 + 14);
  while ( v41 > 0 )
  {
    a2 = std::ranges::_Copy_fn::operator()<std::basic_string_view<unsigned short> const &,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
           v60,
           (__int64)&v54,
           (__int64)a2)[1];
    --v41;
  }
  v45 = *(__int16 **)`std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,long double>'::`2'::_lambda_1_::operator()(
                       v63,
                       v60,
                       a2);
  while ( v42 > 0 )
  {
    v45 = std::ranges::_Copy_fn::operator()<std::basic_string_view<unsigned short> const &,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
            v60,
            (__int64)&v54,
            (__int64)v45)[1];
    --v42;
  }
  v46 = v62;
  *v62 = v45;
  std::string::_Tidy_deallocate(&v64);
  return v46;
}

```

## disassembly

```asm
0x140018c1c  mov     rax, rsp
0x140018c1f  mov     [rax+10h], rbx
0x140018c23  push    rbp
0x140018c24  push    rsi
0x140018c25  push    rdi
0x140018c26  push    r12
0x140018c28  push    r13
0x140018c2a  push    r14
0x140018c2c  push    r15
0x140018c2e  lea     rbp, [rax-648h]
0x140018c35  sub     rsp, 710h
0x140018c3c  movaps  xmmword ptr [rax-48h], xmm6
0x140018c40  mov     rax, cs:__security_cookie
0x140018c47  xor     rax, rsp
0x140018c4a  mov     [rbp+640h+var_50], rax
0x140018c51  mov     r14, r9
0x140018c54  movaps  xmm6, xmm2
0x140018c57  mov     rbx, rdx
0x140018c5a  mov     [rbp+640h+var_690], rcx
0x140018c5e  mov     al, [r9+0Ah]
0x140018c62  mov     byte ptr [rsp+740h+var_710+1], al
0x140018c66  mov     r9d, 2
0x140018c6c  test    al, al
0x140018c6e  jnz     short loc_140018C75
0x140018c70  mov     byte ptr [rsp+740h+var_710+1], r9b
0x140018c75  xor     dil, dil
0x140018c78  mov     r13b, 65h ; 'e'
0x140018c7b  mov     edx, [r14+4]
0x140018c7f  xor     r15b, r15b
0x140018c82  movsx   ecx, byte ptr [r14+8]
0x140018c87  mov     esi, 4
0x140018c8c  lea     r8d, [rsi-3]
0x140018c90  sub     ecx, 41h ; 'A'
0x140018c93  jz      short loc_140018D01
0x140018c95  sub     ecx, esi
0x140018c97  jz      short loc_140018CEE
0x140018c99  sub     ecx, r8d
0x140018c9c  jz      short loc_140018CDB
0x140018c9e  sub     ecx, r8d
0x140018ca1  jz      short loc_140018CBF
0x140018ca3  sub     ecx, 1Ah
0x140018ca6  jz      short loc_140018D04
0x140018ca8  sub     ecx, esi
0x140018caa  jz      short loc_140018CF1
0x140018cac  sub     ecx, r8d
0x140018caf  jz      short loc_140018CDE
0x140018cb1  cmp     ecx, r8d
0x140018cb4  jz      short loc_140018CC2
0x140018cb6  lea     esi, [r8+2]
0x140018cba  mov     r15b, r8b
0x140018cbd  jmp     short loc_140018D07
0x140018cbf  mov     dil, r8b
0x140018cc2  cmp     edx, 0FFFFFFFFh
0x140018cc5  jnz     short loc_140018CCE
0x140018cc7  mov     edx, 6
0x140018ccc  jmp     short loc_140018CD4
0x140018cce  test    edx, edx
0x140018cd0  cmovz   edx, r8d
0x140018cd4  mov     esi, 3
0x140018cd9  jmp     short loc_140018D07
0x140018cdb  mov     dil, r8b
0x140018cde  mov     eax, 6
0x140018ce3  cmp     edx, 0FFFFFFFFh
0x140018ce6  cmovz   edx, eax
0x140018ce9  mov     esi, r9d
0x140018cec  jmp     short loc_140018D07
0x140018cee  mov     dil, r8b
0x140018cf1  mov     eax, 6
0x140018cf6  cmp     edx, 0FFFFFFFFh
0x140018cf9  cmovz   edx, eax
0x140018cfc  mov     esi, r8d
0x140018cff  jmp     short loc_140018D07
0x140018d01  mov     dil, r8b
0x140018d04  mov     r13b, 70h ; 'p'
0x140018d07  xorps   xmm0, xmm0
0x140018d0a  movups  [rbp+640h+var_6C0], xmm0
0x140018d0e  mov     r12d, edx
0x140018d11  mov     r8d, 432h
0x140018d17  cmp     edx, r8d
0x140018d1a  cmovg   r12d, r8d
0x140018d1e  mov     [rbp+640h+var_6A8], r12d
0x140018d22  lea     ecx, [rdx-432h]
0x140018d28  xor     eax, eax
0x140018d2a  cmp     edx, r8d
0x140018d2d  cmovle  ecx, eax
0x140018d30  mov     [rsp+740h+var_700], ecx
0x140018d34  movaps  xmm0, xmm6; X
0x140018d37  call    cs:__imp__ldsign
0x140018d3d  mov     edx, eax
0x140018d3f  test    eax, eax
0x140018d41  setnz   byte ptr [rsp+740h+var_710+3]
0x140018d46  ucomisd xmm6, xmm6
0x140018d4a  setp    al
0x140018d4d  cmp     al, 1
0x140018d4f  jnz     short loc_140018D8C
0x140018d51  lea     rax, [rbp+640h+var_5C0]
0x140018d58  lea     rcx, [rbp+640h+var_5BF]
0x140018d5f  xor     r12d, r12d
0x140018d62  test    edx, edx
0x140018d64  cmovz   rcx, rax
0x140018d68  mov     qword ptr [rbp+640h+var_6C0], rcx
0x140018d6c  mov     eax, dword ptr cs:aNan; "nan"
0x140018d72  mov     [rcx], ax
0x140018d75  mov     al, byte ptr cs:aNan+2; "n"
0x140018d7b  mov     [rcx+2], al
0x140018d7e  mov     r9, qword ptr [rbp+640h+var_6C0]
0x140018d82  add     r9, 3
0x140018d86  mov     qword ptr [rbp+640h+var_6C0], r9
0x140018d8a  jmp     short loc_140018DE1
0x140018d8c  movaps  xmm3, xmm6
0x140018d8f  lea     r8, [rbp+640h+var_57]
0x140018d96  lea     rdx, [rbp+640h+var_5C0]
0x140018d9d  lea     rcx, [rsp+740h+var_6F8+8]
0x140018da2  cmp     r12d, 0FFFFFFFFh
0x140018da6  jnz     short loc_140018DC2
0x140018da8  xor     r12d, r12d
0x140018dab  test    r15b, r15b
0x140018dae  jz      short loc_140018DB7
0x140018db0  call    ??$_Floating_to_chars@$0A@N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<0,double>(char *,char * const,double,std::chars_format,int)
0x140018db5  jmp     short loc_140018DD3
0x140018db7  mov     [rsp+740h+var_720], esi
0x140018dbb  call    ??$_Floating_to_chars@$00N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<1,double>(char *,char * const,double,std::chars_format,int)
0x140018dc0  jmp     short loc_140018DD3
0x140018dc2  mov     dword ptr [rsp+740h+var_718], r12d
0x140018dc7  mov     [rsp+740h+var_720], esi
0x140018dcb  call    ??$_Floating_to_chars@$01N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<2,double>(char *,char * const,double,std::chars_format,int)
0x140018dd0  xor     r12d, r12d
0x140018dd3  movaps  xmm0, [rsp+740h+var_6F8+8]
0x140018dd8  movaps  [rbp+640h+var_6C0], xmm0
0x140018ddc  movq    r9, xmm0
0x140018de1  lea     rdx, [rbp+640h+var_5C0]
0x140018de8  mov     [rsp+740h+var_6D8], rdx
0x140018ded  mov     ecx, r9d
0x140018df0  sub     ecx, edx
0x140018df2  mov     [rsp+740h+var_708], ecx
0x140018df6  cmp     byte ptr [rsp+740h+var_710+3], r12b
0x140018dfb  jz      short loc_140018E0B
0x140018dfd  lea     rdx, [rbp+640h+var_5BF]
0x140018e04  mov     [rsp+740h+var_6D8], rdx
0x140018e09  jmp     short loc_140018E18
0x140018e0b  cmp     byte ptr [rsp+740h+var_710+1], 2
0x140018e10  jz      short loc_140018E18
0x140018e12  inc     ecx
0x140018e14  mov     [rsp+740h+var_708], ecx
0x140018e18  test    dil, dil
0x140018e1b  jz      short loc_140018E49
0x140018e1d  cmp     rdx, r9
0x140018e20  jz      short loc_140018E45
0x140018e22  mov     cl, [rdx]
0x140018e24  lea     eax, [rcx-61h]
0x140018e27  cmp     al, 19h
0x140018e29  ja      short loc_140018E30
0x140018e2b  sub     cl, 20h ; ' '
0x140018e2e  mov     [rdx], cl
0x140018e30  inc     rdx
0x140018e33  cmp     rdx, r9
0x140018e36  jnz     short loc_140018E22
0x140018e38  mov     r9, qword ptr [rbp+640h+var_6C0]
0x140018e3c  mov     rdx, [rsp+740h+var_6D8]
0x140018e41  mov     ecx, [rsp+740h+var_708]
0x140018e45  add     r13b, 0E0h
0x140018e49  movq    rax, xmm6
0x140018e4e  shr     rax, 34h
0x140018e52  mov     r8d, 7FFh
0x140018e58  and     eax, r8d
0x140018e5b  cmp     eax, r8d
0x140018e5e  setnz   al
0x140018e61  xor     al, 1
0x140018e63  mov     byte ptr [rsp+740h+var_710], al
0x140018e67  mov     dil, r12b
0x140018e6a  mov     byte ptr [rsp+740h+var_710+2], r12b
0x140018e6f  mov     r10, r9
0x140018e72  mov     [rsp+740h+var_6D0], r9
0x140018e77  mov     r11, r9
0x140018e7a  mov     [rbp+640h+var_698], r9
0x140018e7e  mov     [rbp+640h+var_6B0], r9
0x140018e82  mov     r8d, r12d
0x140018e85  mov     [rsp+740h+var_704], r12d
0x140018e8a  mov     dword ptr [rsp+740h+var_6E0], r12d
0x140018e8f  xorps   xmm0, xmm0
0x140018e92  movups  [rbp+640h+var_600], xmm0
0x140018e96  mov     qword ptr [rbp+640h+var_5F0], r12
0x140018e9a  mov     qword ptr [rbp+640h+var_5F0+8], 0Fh
0x140018ea2  mov     byte ptr [rbp+640h+var_600], r12b
0x140018ea6  jnz     loc_140019114
0x140018eac  mov     r12b, [r14+0Bh]
0x140018eb0  test    r12b, r12b
0x140018eb3  jnz     short loc_140018EC6
0x140018eb5  lea     r15, [r14+0Ch]
0x140018eb9  cmp     [r15], r12b
0x140018ebc  jnz     short loc_140018EC6
0x140018ebe  xor     r12d, r12d
0x140018ec1  jmp     loc_14001904D
0x140018ec6  mov     rax, rdx
0x140018ec9  cmp     rdx, r9
0x140018ecc  jnb     short loc_140018EF9
0x140018ece  cmp     byte ptr [rax], 2Eh ; '.'
0x140018ed1  jnz     short loc_140018EDC
0x140018ed3  mov     r11, rax
0x140018ed6  mov     [rbp+640h+var_698], rax
0x140018eda  jmp     short loc_140018EE9
0x140018edc  cmp     [rax], r13b
0x140018edf  jnz     short loc_140018EE9
0x140018ee1  mov     r10, rax
0x140018ee4  mov     [rsp+740h+var_6D0], rax
0x140018ee9  inc     rax
0x140018eec  cmp     rax, r9
0x140018eef  jb      short loc_140018ECE
0x140018ef1  cmp     r10, r11
0x140018ef4  mov     rax, r10
0x140018ef7  jb      short loc_140018EFC
0x140018ef9  mov     rax, r11
0x140018efc  mov     [rbp+640h+var_6B0], rax
0x140018f00  test    r12b, r12b
0x140018f03  jz      short loc_140018F18
0x140018f05  cmp     r11, r9
0x140018f08  jnz     short loc_140018F18
0x140018f0a  inc     ecx
0x140018f0c  mov     [rsp+740h+var_708], ecx
0x140018f10  mov     dil, 1
0x140018f13  mov     byte ptr [rsp+740h+var_710+2], dil
0x140018f18  lea     r15, [r14+0Ch]
0x140018f1c  xor     r12d, r12d
0x140018f1f  cmp     [r15], r12b
0x140018f22  jz      loc_14001904D
0x140018f28  mov     rax, [rbp+640h+arg_20]
0x140018f2f  test    rax, rax
0x140018f32  jz      short loc_140018F4E
0x140018f34  mov     rdi, [rax+8]
0x140018f38  mov     qword ptr [rsp+740h+var_6E8], rdi
0x140018f3d  mov     rax, [rdi]
0x140018f40  mov     rcx, rdi
0x140018f43  mov     rax, [rax+8]
0x140018f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018f4c  jmp     short loc_140018F5E
0x140018f4e  mov     cl, 1
0x140018f50  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x140018f56  mov     rdi, rax
0x140018f59  mov     qword ptr [rsp+740h+var_6E8], rax
0x140018f5e  lea     rcx, [rsp+740h+var_6F8+8]
0x140018f63  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x140018f68  mov     rcx, rax
0x140018f6b  mov     rax, [rax]
0x140018f6e  lea     rdx, [rbp+640h+var_5E0]
0x140018f72  mov     rax, [rax+28h]
0x140018f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018f7b  lea     rcx, [rbp+640h+var_600]
0x140018f7f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140018f84  movups  xmm0, [rbp+640h+var_5E0]
0x140018f88  movups  [rbp+640h+var_600], xmm0
0x140018f8c  movups  xmm1, [rbp+640h+var_5D0]
0x140018f90  movups  [rbp+640h+var_5F0], xmm1
0x140018f94  mov     qword ptr [rbp+640h+var_5D0], r12
0x140018f98  mov     qword ptr [rbp+640h+var_5D0+8], 0Fh
0x140018fa0  mov     byte ptr [rbp+640h+var_5E0], r12b
0x140018fa4  lea     rcx, [rbp+640h+var_5E0]
0x140018fa8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140018fad  nop
0x140018fae  test    rdi, rdi
0x140018fb1  jz      short loc_140018FDA
0x140018fb3  mov     rax, [rdi]
0x140018fb6  mov     rcx, rdi
0x140018fb9  mov     rax, [rax+10h]
0x140018fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018fc2  mov     rcx, rax
0x140018fc5  test    rax, rax
0x140018fc8  jz      short loc_140018FDA
0x140018fca  mov     rax, [rax]
0x140018fcd  mov     edx, 1
0x140018fd2  mov     rax, [rax]
0x140018fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018fda  lea     rax, [rbp+640h+var_600]
0x140018fde  cmp     qword ptr [rbp+640h+var_5F0+8], 0Fh
0x140018fe3  cmova   rax, qword ptr [rbp+640h+var_600]
0x140018fe8  mov     r10, qword ptr [rbp+640h+var_5F0]
0x140018fec  mov     rdx, [rsp+740h+var_6D8]
0x140018ff1  mov     r8d, r12d
0x140018ff4  test    r10, r10
0x140018ff7  jz      short loc_14001902A
0x140018ff9  mov     r9, [rbp+640h+var_6B0]
0x140018ffd  sub     r9, rdx
0x140019000  movsx   r11, byte ptr [rax]
0x140019004  cmp     r9, r11
0x140019007  jbe     short loc_14001902A
0x140019009  add     r10, rax
0x14001900c  movsx   rcx, r11b
0x140019010  sub     r9, rcx
0x140019013  inc     r8d
0x140019016  lea     rcx, [rax+1]
0x14001901a  cmp     rcx, r10
0x14001901d  cmovnz  rax, rcx
0x140019021  movsx   r11, byte ptr [rax]
0x140019025  cmp     r9, r11
0x140019028  ja      short loc_14001900C
0x14001902a  mov     dword ptr [rsp+740h+var_6E0], r8d
0x14001902f  mov     ecx, [rsp+740h+var_708]
0x140019033  add     ecx, r8d
0x140019036  mov     [rsp+740h+var_708], ecx
0x14001903a  mov     r9, qword ptr [rbp+640h+var_6C0]
0x14001903e  mov     dil, byte ptr [rsp+740h+var_710+2]
  ... truncated ...
```
