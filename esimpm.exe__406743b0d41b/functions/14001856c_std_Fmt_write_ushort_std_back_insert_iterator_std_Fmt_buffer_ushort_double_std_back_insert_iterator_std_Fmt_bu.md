# std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,double>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,double,std::_Basic_format_specs<ushort> const &,std::_Lazy_locale)

- ea: `0x14001856c`
- end: `0x140018c15`
- name: `??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@N@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@NAEBU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `1705`
- prototype: `__int16 **__fastcall(__int16 **, __int16 *, double, __int64, __int64)`
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
- `0x14001856c`
- `0x14001e5e8`
- `0x14001f0fc`
- `0x140020bf0`
- `0x14003e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x1400188a0`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x1400188a0`
- `api-ms-win-crt-private-l1-1-0!_o__dsign` at `0x140018687`
- `api-ms-win-crt-private-l1-1-0!_o__dsign` at `0x140018687`

## pseudocode

```c
__int16 **__fastcall std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,double>(
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
  v58 = 0;
  v12 = v9;
  if ( (int)v9 > 1074 )
    v12 = 1074;
  LODWORD(v60[0]) = v12;
  v13 = (unsigned int)(v9 - 1074);
  if ( (int)v9 <= 1074 )
    v13 = 0;
  v53 = v13;
  v49 = (unsigned int)_o__dsign(v13, v9, 1074, 2) != 0;
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
0x14001856c  mov     rax, rsp
0x14001856f  mov     [rax+10h], rbx
0x140018573  push    rbp
0x140018574  push    rsi
0x140018575  push    rdi
0x140018576  push    r12
0x140018578  push    r13
0x14001857a  push    r14
0x14001857c  push    r15
0x14001857e  lea     rbp, [rax-648h]
0x140018585  sub     rsp, 710h
0x14001858c  movaps  xmmword ptr [rax-48h], xmm6
0x140018590  mov     rax, cs:__security_cookie
0x140018597  xor     rax, rsp
0x14001859a  mov     [rbp+640h+var_50], rax
0x1400185a1  mov     r14, r9
0x1400185a4  movaps  xmm6, xmm2
0x1400185a7  mov     rbx, rdx
0x1400185aa  mov     [rbp+640h+var_690], rcx
0x1400185ae  mov     al, [r9+0Ah]
0x1400185b2  mov     byte ptr [rsp+740h+var_710+1], al
0x1400185b6  mov     r9d, 2
0x1400185bc  test    al, al
0x1400185be  jnz     short loc_1400185C5
0x1400185c0  mov     byte ptr [rsp+740h+var_710+1], r9b
0x1400185c5  xor     dil, dil
0x1400185c8  mov     r13b, 65h ; 'e'
0x1400185cb  mov     edx, [r14+4]
0x1400185cf  xor     r15b, r15b
0x1400185d2  movsx   ecx, byte ptr [r14+8]
0x1400185d7  mov     esi, 4
0x1400185dc  lea     r8d, [rsi-3]
0x1400185e0  sub     ecx, 41h ; 'A'
0x1400185e3  jz      short loc_140018651
0x1400185e5  sub     ecx, esi
0x1400185e7  jz      short loc_14001863E
0x1400185e9  sub     ecx, r8d
0x1400185ec  jz      short loc_14001862B
0x1400185ee  sub     ecx, r8d
0x1400185f1  jz      short loc_14001860F
0x1400185f3  sub     ecx, 1Ah
0x1400185f6  jz      short loc_140018654
0x1400185f8  sub     ecx, esi
0x1400185fa  jz      short loc_140018641
0x1400185fc  sub     ecx, r8d
0x1400185ff  jz      short loc_14001862E
0x140018601  cmp     ecx, r8d
0x140018604  jz      short loc_140018612
0x140018606  lea     esi, [r8+2]
0x14001860a  mov     r15b, r8b
0x14001860d  jmp     short loc_140018657
0x14001860f  mov     dil, r8b
0x140018612  cmp     edx, 0FFFFFFFFh
0x140018615  jnz     short loc_14001861E
0x140018617  mov     edx, 6
0x14001861c  jmp     short loc_140018624
0x14001861e  test    edx, edx
0x140018620  cmovz   edx, r8d
0x140018624  mov     esi, 3
0x140018629  jmp     short loc_140018657
0x14001862b  mov     dil, r8b
0x14001862e  mov     eax, 6
0x140018633  cmp     edx, 0FFFFFFFFh
0x140018636  cmovz   edx, eax
0x140018639  mov     esi, r9d
0x14001863c  jmp     short loc_140018657
0x14001863e  mov     dil, r8b
0x140018641  mov     eax, 6
0x140018646  cmp     edx, 0FFFFFFFFh
0x140018649  cmovz   edx, eax
0x14001864c  mov     esi, r8d
0x14001864f  jmp     short loc_140018657
0x140018651  mov     dil, r8b
0x140018654  mov     r13b, 70h ; 'p'
0x140018657  xorps   xmm0, xmm0
0x14001865a  movups  [rbp+640h+var_6C0], xmm0
0x14001865e  mov     r12d, edx
0x140018661  mov     r8d, 432h
0x140018667  cmp     edx, r8d
0x14001866a  cmovg   r12d, r8d
0x14001866e  mov     [rbp+640h+var_6A8], r12d
0x140018672  lea     ecx, [rdx-432h]
0x140018678  xor     eax, eax
0x14001867a  cmp     edx, r8d
0x14001867d  cmovle  ecx, eax
0x140018680  mov     [rsp+740h+var_700], ecx
0x140018684  movaps  xmm0, xmm6
0x140018687  call    cs:__imp__o__dsign
0x14001868d  mov     edx, eax
0x14001868f  test    eax, eax
0x140018691  setnz   byte ptr [rsp+740h+var_710+3]
0x140018696  ucomisd xmm6, xmm6
0x14001869a  setp    al
0x14001869d  cmp     al, 1
0x14001869f  jnz     short loc_1400186DC
0x1400186a1  lea     rax, [rbp+640h+var_5C0]
0x1400186a8  lea     rcx, [rbp+640h+var_5BF]
0x1400186af  xor     r12d, r12d
0x1400186b2  test    edx, edx
0x1400186b4  cmovz   rcx, rax
0x1400186b8  mov     qword ptr [rbp+640h+var_6C0], rcx
0x1400186bc  mov     eax, dword ptr cs:aNan; "nan"
0x1400186c2  mov     [rcx], ax
0x1400186c5  mov     al, byte ptr cs:aNan+2; "n"
0x1400186cb  mov     [rcx+2], al
0x1400186ce  mov     r9, qword ptr [rbp+640h+var_6C0]
0x1400186d2  add     r9, 3
0x1400186d6  mov     qword ptr [rbp+640h+var_6C0], r9
0x1400186da  jmp     short loc_140018731
0x1400186dc  movaps  xmm3, xmm6
0x1400186df  lea     r8, [rbp+640h+var_57]
0x1400186e6  lea     rdx, [rbp+640h+var_5C0]
0x1400186ed  lea     rcx, [rsp+740h+var_6F8+8]
0x1400186f2  cmp     r12d, 0FFFFFFFFh
0x1400186f6  jnz     short loc_140018712
0x1400186f8  xor     r12d, r12d
0x1400186fb  test    r15b, r15b
0x1400186fe  jz      short loc_140018707
0x140018700  call    ??$_Floating_to_chars@$0A@N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<0,double>(char *,char * const,double,std::chars_format,int)
0x140018705  jmp     short loc_140018723
0x140018707  mov     [rsp+740h+var_720], esi
0x14001870b  call    ??$_Floating_to_chars@$00N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<1,double>(char *,char * const,double,std::chars_format,int)
0x140018710  jmp     short loc_140018723
0x140018712  mov     dword ptr [rsp+740h+var_718], r12d
0x140018717  mov     [rsp+740h+var_720], esi
0x14001871b  call    ??$_Floating_to_chars@$01N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<2,double>(char *,char * const,double,std::chars_format,int)
0x140018720  xor     r12d, r12d
0x140018723  movaps  xmm0, [rsp+740h+var_6F8+8]
0x140018728  movaps  [rbp+640h+var_6C0], xmm0
0x14001872c  movq    r9, xmm0
0x140018731  lea     rdx, [rbp+640h+var_5C0]
0x140018738  mov     [rsp+740h+var_6D8], rdx
0x14001873d  mov     ecx, r9d
0x140018740  sub     ecx, edx
0x140018742  mov     [rsp+740h+var_708], ecx
0x140018746  cmp     byte ptr [rsp+740h+var_710+3], r12b
0x14001874b  jz      short loc_14001875B
0x14001874d  lea     rdx, [rbp+640h+var_5BF]
0x140018754  mov     [rsp+740h+var_6D8], rdx
0x140018759  jmp     short loc_140018768
0x14001875b  cmp     byte ptr [rsp+740h+var_710+1], 2
0x140018760  jz      short loc_140018768
0x140018762  inc     ecx
0x140018764  mov     [rsp+740h+var_708], ecx
0x140018768  test    dil, dil
0x14001876b  jz      short loc_140018799
0x14001876d  cmp     rdx, r9
0x140018770  jz      short loc_140018795
0x140018772  mov     cl, [rdx]
0x140018774  lea     eax, [rcx-61h]
0x140018777  cmp     al, 19h
0x140018779  ja      short loc_140018780
0x14001877b  sub     cl, 20h ; ' '
0x14001877e  mov     [rdx], cl
0x140018780  inc     rdx
0x140018783  cmp     rdx, r9
0x140018786  jnz     short loc_140018772
0x140018788  mov     r9, qword ptr [rbp+640h+var_6C0]
0x14001878c  mov     rdx, [rsp+740h+var_6D8]
0x140018791  mov     ecx, [rsp+740h+var_708]
0x140018795  add     r13b, 0E0h
0x140018799  movq    rax, xmm6
0x14001879e  shr     rax, 34h
0x1400187a2  mov     r8d, 7FFh
0x1400187a8  and     eax, r8d
0x1400187ab  cmp     eax, r8d
0x1400187ae  setnz   al
0x1400187b1  xor     al, 1
0x1400187b3  mov     byte ptr [rsp+740h+var_710], al
0x1400187b7  mov     dil, r12b
0x1400187ba  mov     byte ptr [rsp+740h+var_710+2], r12b
0x1400187bf  mov     r10, r9
0x1400187c2  mov     [rsp+740h+var_6D0], r9
0x1400187c7  mov     r11, r9
0x1400187ca  mov     [rbp+640h+var_698], r9
0x1400187ce  mov     [rbp+640h+var_6B0], r9
0x1400187d2  mov     r8d, r12d
0x1400187d5  mov     [rsp+740h+var_704], r12d
0x1400187da  mov     dword ptr [rsp+740h+var_6E0], r12d
0x1400187df  xorps   xmm0, xmm0
0x1400187e2  movups  [rbp+640h+var_600], xmm0
0x1400187e6  mov     qword ptr [rbp+640h+var_5F0], r12
0x1400187ea  mov     qword ptr [rbp+640h+var_5F0+8], 0Fh
0x1400187f2  mov     byte ptr [rbp+640h+var_600], r12b
0x1400187f6  jnz     loc_140018A64
0x1400187fc  mov     r12b, [r14+0Bh]
0x140018800  test    r12b, r12b
0x140018803  jnz     short loc_140018816
0x140018805  lea     r15, [r14+0Ch]
0x140018809  cmp     [r15], r12b
0x14001880c  jnz     short loc_140018816
0x14001880e  xor     r12d, r12d
0x140018811  jmp     loc_14001899D
0x140018816  mov     rax, rdx
0x140018819  cmp     rdx, r9
0x14001881c  jnb     short loc_140018849
0x14001881e  cmp     byte ptr [rax], 2Eh ; '.'
0x140018821  jnz     short loc_14001882C
0x140018823  mov     r11, rax
0x140018826  mov     [rbp+640h+var_698], rax
0x14001882a  jmp     short loc_140018839
0x14001882c  cmp     [rax], r13b
0x14001882f  jnz     short loc_140018839
0x140018831  mov     r10, rax
0x140018834  mov     [rsp+740h+var_6D0], rax
0x140018839  inc     rax
0x14001883c  cmp     rax, r9
0x14001883f  jb      short loc_14001881E
0x140018841  cmp     r10, r11
0x140018844  mov     rax, r10
0x140018847  jb      short loc_14001884C
0x140018849  mov     rax, r11
0x14001884c  mov     [rbp+640h+var_6B0], rax
0x140018850  test    r12b, r12b
0x140018853  jz      short loc_140018868
0x140018855  cmp     r11, r9
0x140018858  jnz     short loc_140018868
0x14001885a  inc     ecx
0x14001885c  mov     [rsp+740h+var_708], ecx
0x140018860  mov     dil, 1
0x140018863  mov     byte ptr [rsp+740h+var_710+2], dil
0x140018868  lea     r15, [r14+0Ch]
0x14001886c  xor     r12d, r12d
0x14001886f  cmp     [r15], r12b
0x140018872  jz      loc_14001899D
0x140018878  mov     rax, [rbp+640h+arg_20]
0x14001887f  test    rax, rax
0x140018882  jz      short loc_14001889E
0x140018884  mov     rdi, [rax+8]
0x140018888  mov     qword ptr [rsp+740h+var_6E8], rdi
0x14001888d  mov     rax, [rdi]
0x140018890  mov     rcx, rdi
0x140018893  mov     rax, [rax+8]
0x140018897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001889c  jmp     short loc_1400188AE
0x14001889e  mov     cl, 1
0x1400188a0  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x1400188a6  mov     rdi, rax
0x1400188a9  mov     qword ptr [rsp+740h+var_6E8], rax
0x1400188ae  lea     rcx, [rsp+740h+var_6F8+8]
0x1400188b3  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x1400188b8  mov     rcx, rax
0x1400188bb  mov     rax, [rax]
0x1400188be  lea     rdx, [rbp+640h+var_5E0]
0x1400188c2  mov     rax, [rax+28h]
0x1400188c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400188cb  lea     rcx, [rbp+640h+var_600]
0x1400188cf  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400188d4  movups  xmm0, [rbp+640h+var_5E0]
0x1400188d8  movups  [rbp+640h+var_600], xmm0
0x1400188dc  movups  xmm1, [rbp+640h+var_5D0]
0x1400188e0  movups  [rbp+640h+var_5F0], xmm1
0x1400188e4  mov     qword ptr [rbp+640h+var_5D0], r12
0x1400188e8  mov     qword ptr [rbp+640h+var_5D0+8], 0Fh
0x1400188f0  mov     byte ptr [rbp+640h+var_5E0], r12b
0x1400188f4  lea     rcx, [rbp+640h+var_5E0]
0x1400188f8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400188fd  nop
0x1400188fe  test    rdi, rdi
0x140018901  jz      short loc_14001892A
0x140018903  mov     rax, [rdi]
0x140018906  mov     rcx, rdi
0x140018909  mov     rax, [rax+10h]
0x14001890d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018912  mov     rcx, rax
0x140018915  test    rax, rax
0x140018918  jz      short loc_14001892A
0x14001891a  mov     rax, [rax]
0x14001891d  mov     edx, 1
0x140018922  mov     rax, [rax]
0x140018925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001892a  lea     rax, [rbp+640h+var_600]
0x14001892e  cmp     qword ptr [rbp+640h+var_5F0+8], 0Fh
0x140018933  cmova   rax, qword ptr [rbp+640h+var_600]
0x140018938  mov     r10, qword ptr [rbp+640h+var_5F0]
0x14001893c  mov     rdx, [rsp+740h+var_6D8]
0x140018941  mov     r8d, r12d
0x140018944  test    r10, r10
0x140018947  jz      short loc_14001897A
0x140018949  mov     r9, [rbp+640h+var_6B0]
0x14001894d  sub     r9, rdx
0x140018950  movsx   r11, byte ptr [rax]
0x140018954  cmp     r9, r11
0x140018957  jbe     short loc_14001897A
0x140018959  add     r10, rax
0x14001895c  movsx   rcx, r11b
0x140018960  sub     r9, rcx
0x140018963  inc     r8d
0x140018966  lea     rcx, [rax+1]
0x14001896a  cmp     rcx, r10
0x14001896d  cmovnz  rax, rcx
0x140018971  movsx   r11, byte ptr [rax]
0x140018975  cmp     r9, r11
0x140018978  ja      short loc_14001895C
0x14001897a  mov     dword ptr [rsp+740h+var_6E0], r8d
0x14001897f  mov     ecx, [rsp+740h+var_708]
0x140018983  add     ecx, r8d
0x140018986  mov     [rsp+740h+var_708], ecx
0x14001898a  mov     r9, qword ptr [rbp+640h+var_6C0]
0x14001898e  mov     dil, byte ptr [rsp+740h+var_710+2]
  ... truncated ...
```
