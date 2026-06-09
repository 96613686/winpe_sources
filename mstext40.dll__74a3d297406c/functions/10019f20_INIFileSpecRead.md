# INIFileSpecRead

- ea: `0x10019f20`
- end: `0x1001ad3d`
- name: `INIFileSpecRead`
- size: `3613`
- prototype: `int __stdcall(LPCWCH pszSrc, int, int, _DWORD *)`
- caller_count: `1`
- callee_count: `22`
- tags: ``

## callers

- `0x1001c250`

## callees

- `0x10009010`
- `0x10009070`
- `0x1000a260`
- `0x1000b070`
- `0x1000b200`
- `0x1000c150`
- `0x10019860`
- `0x100198d0`
- `0x10019a50`
- `0x10019c60`
- `0x10019ce0`
- `0x10019f20`
- `0x1001b460`
- `0x1001b5d0`
- `0x1001baf0`
- `0x1001bf40`
- `0x1001bfb0`
- `0x1002b81a`
- `0x1002c253`
- `0x1002c32f`
- `0x1002c490`
- `0x1002c9ad`

## pseudocode

```c
int __stdcall INIFileSpecRead(LPCWCH pszSrc, int a2, int a3, _DWORD *a4)
{
  const wchar_t *v4; // ebx
  WCHAR *v6; // ecx
  int v7; // edx
  WCHAR v8; // ax
  unsigned int v9; // kr00_4
  unsigned int v10; // ecx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  unsigned __int16 SpecInt; // ax
  unsigned __int16 v15; // ax
  unsigned __int16 v16; // ax
  unsigned __int16 v17; // ax
  int v18; // eax
  int v19; // esi
  _WORD *v20; // edi
  _WORD *v21; // ebx
  _WORD *i; // esi
  int v23; // esi
  wchar_t *v24; // ecx
  wchar_t *v25; // edi
  int v27; // ecx
  wchar_t *v28; // edi
  int v29; // edi
  int v30; // ebx
  wchar_t *v31; // ecx
  int v33; // edi
  wchar_t *v34; // ecx
  wchar_t *v35; // edx
  wchar_t *v37; // esi
  wchar_t *v38; // eax
  wchar_t *v39; // esi
  wchar_t *v40; // eax
  const wchar_t *v41; // esi
  int v42; // edi
  int v43; // eax
  _WORD *v44; // esi
  _WORD *v45; // esi
  int v46; // eax
  bool v47; // cc
  _WORD *v48; // esi
  char *v49; // eax
  char *v50; // esi
  int v51; // eax
  bool v52; // zf
  const wchar_t *v53; // ecx
  unsigned int v54; // edx
  const wchar_t *v55; // ebx
  int v56; // eax
  __int16 v57; // dx
  __int16 v58; // ax
  __int16 v59; // si
  __int16 v60; // cx
  _DWORD *v61; // eax
  _DWORD *v62; // esi
  wchar_t *v63; // [esp+Ch] [ebp-1A8h] BYREF
  int v64; // [esp+10h] [ebp-1A4h]
  wchar_t *Str; // [esp+14h] [ebp-1A0h]
  int v66; // [esp+18h] [ebp-19Ch]
  _WORD *v67; // [esp+1Ch] [ebp-198h]
  const unsigned __int16 *v68; // [esp+20h] [ebp-194h]
  _WORD *Part; // [esp+24h] [ebp-190h]
  _WORD *v70; // [esp+28h] [ebp-18Ch]
  const unsigned __int16 *v71; // [esp+2Ch] [ebp-188h]
  _WORD *v72; // [esp+30h] [ebp-184h]
  int v73; // [esp+34h] [ebp-180h]
  _WORD *v74; // [esp+38h] [ebp-17Ch]
  _WORD *v75; // [esp+3Ch] [ebp-178h]
  wchar_t *Source; // [esp+40h] [ebp-174h]
  int v77; // [esp+44h] [ebp-170h]
  _DWORD *v78; // [esp+48h] [ebp-16Ch]
  LPCWCH v79; // [esp+4Ch] [ebp-168h]
  _BYTE Destination[72]; // [esp+50h] [ebp-164h] BYREF
  wchar_t pszDest[8]; // [esp+98h] [ebp-11Ch] BYREF
  WCHAR WideCharStr[66]; // [esp+A8h] [ebp-10Ch] BYREF
  wchar_t v83[66]; // [esp+12Ch] [ebp-88h] BYREF

  v4 = pszSrc;
  v73 = 0;
  v79 = pszSrc;
  v64 = 0xFFFF;
  v66 = 0xFFFF;
  memset(Destination, 0, sizeof(Destination));
  InitializeSpec(a3);
  if ( !*pszSrc )
    return 0;
  v6 = WideCharStr;
  v7 = 65;
  while ( v7 != -2147483581 )
  {
    v8 = *(WCHAR *)((char *)v6 + a2 - (_DWORD)WideCharStr);
    if ( !v8 )
      break;
    *v6++ = v8;
    if ( !--v7 )
    {
      --v6;
      break;
    }
  }
  *v6 = 0;
  v9 = wcslen(WideCharStr);
  if ( pszDest[v9 + 7] == 46 )
  {
    v10 = 2 * v9 - 2;
    if ( v10 >= 0x82 )
      __report_rangecheckfailure();
    *(WCHAR *)((char *)WideCharStr + v10) = 0;
  }
  ReadProfileParameter(pszSrc, WideCharStr, L"MaxScanRows", &::Source, 0x81u);
  if ( ::Source )
  {
    *(_WORD *)(a3 + 16) |= 4u;
    v11 = StringToInt(&::Source);
    *(_DWORD *)(a3 + 48) = v11;
    if ( v11 == 0xFFFF )
    {
      ErrorSetExtendedInfoSz1Sz2(-8236, WideCharStr, L"MaxScanRows", 2);
      return -5402;
    }
  }
  v12 = CheckProfile(pszSrc, WideCharStr, L"ColNameHeader", (int)L"True", 1, (int)L"False", 0);
  *(_DWORD *)(a3 + 28) = v12;
  if ( v12 == -1 )
  {
    ErrorSetExtendedInfoSz1Sz2(-8236, WideCharStr, L"ColNameHeader", 2);
    return -5402;
  }
  if ( ::Source )
    *(_WORD *)(a3 + 16) |= 1u;
  *a4 = 0;
  ReadProfileParameter(pszSrc, WideCharStr, L"CharacterSet", &::Source, 0x81u);
  if ( ::Source )
  {
    *a4 = 1;
    *(_WORD *)(a3 + 16) |= 2u;
    if ( !DecodeCharacterSet(&::Source, a3 + 36, 0) )
    {
      *a4 = 0;
      return -5402;
    }
  }
  ReadProfileParameter(pszSrc, WideCharStr, L"Format", &::Source, 0x81u);
  if ( ::Source )
  {
    *(_WORD *)(a3 + 16) |= 0x10u;
    if ( !DecodeFormat(&::Source, a3 + 52, a3 + 56) )
    {
      ErrorSetExtendedInfoSz1Sz2(-8236, WideCharStr, L"Format", 2);
      return -5402;
    }
  }
  ReadProfileParameter(pszSrc, WideCharStr, L"FixedFormat", &::Source, 0x81u);
  if ( ::Source )
  {
    *(_WORD *)(a3 + 16) |= 0x10u;
    if ( ascii_wcsicmp(&::Source, L"RaggedEdge") )
    {
      if ( ascii_wcsicmp(&::Source, L"TrueFixedLength") )
      {
        ErrorSetExtendedInfoSz1Sz2(-8236, WideCharStr, L"FixedFormat", 2);
        return -5402;
      }
    }
  }
  ReadProfileParameter(pszSrc, WideCharStr, L"TextDelimiter", &::Source, 0x81u);
  if ( ::Source )
  {
    *(_WORD *)(a3 + 16) |= 0x20u;
    if ( wcslen(&::Source) <= 1 )
    {
      LOWORD(v13) = ::Source;
    }
    else
    {
      v13 = ascii_wcsicmp(&::Source, L"None");
      if ( v13 )
      {
        ErrorSetExtendedInfoSz1Sz2(-8236, WideCharStr, L"TextDelimiter", 2);
        return -5402;
      }
    }
    *(_WORD *)(a3 + 72) = v13;
  }
  ReadProfileParameter(pszSrc, WideCharStr, L"DateTimeFormat", &::Source, 0x81u);
  if ( ::Source )
  {
    *(_WORD *)(a3 + 16) |= 0x40u;
    wcsncpy((wchar_t *)(a3 + 80), &::Source, 0x41u);
    if ( !ParseDateTimePicture(a3 + 80, a3 + 748) )
    {
      ErrorSetExtendedInfoSz1Sz2(-8236, WideCharStr, L"DateTimeFormat", 2);
      return -5402;
    }
    *(_DWORD *)(a3 + 820) = 1;
    *(_WORD *)(a3 + 210) = 0;
    *(_WORD *)(a3 + 340) = 0;
  }
  ReadProfileParameter(pszSrc, WideCharStr, L"CurrencySymbol", &::Source, 0x81u);
  if ( ::Source )
  {
    *(_WORD *)(a3 + 16) |= 0x80u;
    wcsncpy((wchar_t *)(a3 + 688), &::Source, 9u);
  }
  SpecInt = GetSpecInt(WideCharStr, L"CurrencyPosFormat", *(_DWORD *)(a3 + 712), pszSrc);
  *(_DWORD *)(a3 + 712) = SpecInt;
  if ( SpecInt > 3u )
  {
    ErrorSetExtendedInfoSz1Sz2(-8236, WideCharStr, L"CurrencyPosFormat", 2);
    return -5402;
  }
  if ( ::Source )
    *(_WORD *)(a3 + 16) |= 0x100u;
  v15 = GetSpecInt(WideCharStr, L"CurrencyNegFormat", *(_DWORD *)(a3 + 716), pszSrc);
  *(_DWORD *)(a3 + 716) = v15;
  if ( v15 > 0xFu )
  {
    ErrorSetExtendedInfoSz1Sz2(-8236, WideCharStr, L"CurrencyNegFormat", 2);
    return -5402;
  }
  if ( ::Source )
    *(_WORD *)(a3 + 16) |= 0x200u;
  v16 = GetSpecInt(WideCharStr, L"CurrencyDigits", *(_DWORD *)(a3 + 720), pszSrc);
  *(_DWORD *)(a3 + 720) = v16;
  if ( v16 > 4u )
  {
    ErrorSetExtendedInfoSz1Sz2(-8236, WideCharStr, L"CurrencyDigits", 2);
    return -5402;
  }
  if ( ::Source )
    *(_WORD *)(a3 + 16) |= 0x400u;
  ReadProfileParameter(pszSrc, WideCharStr, L"DecimalSymbol", &::Source, 0x81u);
  if ( ::Source )
  {
    *(_WORD *)(a3 + 16) |= 0x800u;
    *(_WORD *)(a3 + 730) = ::Source;
    *(_WORD *)(a3 + 724) = ::Source;
  }
  ReadProfileParameter(pszSrc, WideCharStr, L"CurrencyDecimalSymbol", &::Source, 0x81u);
  if ( ::Source )
  {
    *(_WORD *)(a3 + 16) |= 0x2000u;
    *(_WORD *)(a3 + 724) = ::Source;
  }
  ReadProfileParameter(pszSrc, WideCharStr, L"CurrencyThousandsSymbol", &::Source, 0x81u);
  if ( ::Source )
  {
    *(_WORD *)(a3 + 16) |= 0x4000u;
    *(_WORD *)(a3 + 726) = ::Source;
  }
  v17 = GetSpecInt(WideCharStr, L"NumberDigits", *(_DWORD *)(a3 + 736), pszSrc);
  *(_DWORD *)(a3 + 736) = v17;
  if ( v17 > 0x10u )
  {
    ErrorSetExtendedInfoSz1Sz2(-8236, WideCharStr, L"NumberDigits", 2);
    return -5402;
  }
  if ( ::Source )
    *(_WORD *)(a3 + 16) |= 0x1000u;
  ReadProfileParameter(pszSrc, WideCharStr, L"NumbersHaveLeadingZeros", &::Source, 0x81u);
  if ( ::Source )
  {
    *(_WORD *)(a3 + 16) |= 0x8000u;
    v18 = CheckProfile(pszSrc, WideCharStr, L"NumbersHaveLeadingZeros", (int)L"True", 1, (int)L"False", 0);
    *(_DWORD *)(a3 + 740) = v18;
    if ( v18 == -1 )
    {
      ErrorSetExtendedInfoSz1Sz2(-8236, WideCharStr, L"NumbersHaveLeadingZeros", 2);
      return -5402;
    }
  }
  *(_DWORD *)(a3 + 32) = (unsigned __int16)GetSpecInt(WideCharStr, L"StartRow", 0, pszSrc);
  if ( ::Source )
    *(_WORD *)(a3 + 16) |= 8u;
  v19 = 1;
  v78 = 0;
  v77 = 1;
  StringCchPrintfW(pszDest, 8u, L"%s%d", L"Col", 1);
  ReadProfileParameter(pszSrc, WideCharStr, pszDest, &::Source, 0x81u);
  while ( ::Source )
  {
    v63 = &::Source;
    Source = (wchar_t *)GetPart(&v63);
    Str = (wchar_t *)GetPart(&v63);
    v20 = 0;
    v21 = 0;
    v71 = 0;
    v72 = 0;
    v74 = 0;
    v70 = 0;
    v75 = 0;
    v68 = 0;
    v67 = 0;
    Part = 0;
    for ( i = (_WORD *)GetPart(&v63); i; i = (_WORD *)GetPart(&v63) )
    {
      if ( !*i )
        break;
      if ( ascii_wcsicmp(i, L"Width") )
      {
        if ( ascii_wcsicmp(i, L"Precision") )
        {
          if ( ascii_wcsicmp(i, L"Scale") )
          {
            if ( ascii_wcsicmp(i, L"Unicode") )
            {
              if ( ascii_wcsicmp(i, L"Attribute") )
                goto LABEL_94;
              v67 = i;
              Part = (_WORD *)GetPart(&v63);
            }
            else
            {
              v21 = i;
              v68 = (const unsigned __int16 *)GetPart(&v63);
            }
          }
          else
          {
            v70 = i;
            v75 = (_WORD *)GetPart(&v63);
          }
        }
        else
        {
          v72 = i;
          v74 = (_WORD *)GetPart(&v63);
        }
      }
      else
      {
        v20 = i;
        v71 = (const unsigned __int16 *)GetPart(&v63);
      }
    }
    if ( !*Source || !*Str || v20 && !*v71 || v72 && !*v74 || v70 && !*v75 || v21 && !*v68 || v67 && !*Part )
    {
LABEL_94:
      ErrorSetExtendedInfoSz1Sz2(-8236, WideCharStr, pszDest, 2);
      v29 = -5402;
      goto LABEL_181;
    }
    v23 = 0;
    while ( 1 )
    {
      v24 = (&off_1003E548)[2 * v23];
      v25 = v24 + 1;
      while ( *v24++ )
        ;
      v27 = (char *)v24 - (char *)v25;
      v28 = Str;
      if ( !ascii_wcsnicmp(Str, (&off_1003E548)[2 * v23], v27 >> 1) )
        break;
      if ( ++v23 >= 18 )
        goto LABEL_94;
    }
    v30 = dword_1003E54C[2 * v23];
    v31 = v28 + 1;
    while ( *v28++ )
      ;
    v33 = (char *)v28 - (char *)v31;
    v34 = (&off_1003E548)[2 * v23];
    if ( v33 >> 1 == wcslen(v34) )
    {
      if ( v30 == -1 )
        goto LABEL_94;
      if ( v30 != 8 )
        goto LABEL_111;
      v37 = Str;
    }
    else
    {
      if ( v30 != 8 )
        goto LABEL_94;
      v35 = v34 + 1;
      while ( *v34++ )
        ;
      v37 = Str;
      if ( Str[v34 - v35] != 40 )
        goto LABEL_94;
    }
    memset(Destination, 0, sizeof(Destination));
    v38 = wcschr(v37, 0x28u);
    v39 = v38;
    if ( v38 )
    {
      v40 = wcschr(v38, 0x29u);
      if ( !v40 )
        goto LABEL_94;
      v41 = v39 + 1;
      *v40 = 0;
      if ( !ParseDateTimePicture(v41, Destination) )
        goto LABEL_94;
      wcsncpy((wchar_t *)&Destination[8], v41, 0x20u);
      *(_WORD *)&Destination[2] |= 0x800u;
      *(_WORD *)&Destination[4] = *(_WORD *)(a3 + 752);
    }
    else
    {
      *(__m128i *)Destination = _mm_loadu_si128((const __m128i *)(a3 + 748));
      *(__m128i *)&Destination[16] = _mm_loadu_si128((const __m128i *)(a3 + 764));
      *(__m128i *)&Destination[32] = _mm_loadu_si128((const __m128i *)(a3 + 780));
      *(__m128i *)&Destination[48] = _mm_loadu_si128((const __m128i *)(a3 + 796));
      *(_QWORD *)&Destination[64] = *(_QWORD *)(a3 + 812);
    }
LABEL_111:
    v42 = -1;
    if ( v71 && *v71 )
    {
      if ( wcslen(v71) > 5 )
        goto LABEL_94;
      v43 = StringToInt(v71);
      v42 = v43;
      if ( !v43 || v43 == 0xFFFF )
        goto LABEL_94;
    }
    else if ( v30 == 12 || v30 == 11 )
    {
      v42 = 65500;
    }
    else if ( v30 == 10 || v30 == 9 )
    {
      v42 = 255;
    }
    if ( v30 == 16 )
    {
      v44 = v75;
      v64 = 28;
      v66 = 2;
      if ( v75 && *v75 && !ascii_wcsicmp(v70, L"Scale") )
        v66 = StringToInt(v44);
      v45 = v74;
      if ( v74 && *v74 && !ascii_wcsicmp(v72, L"Precision") )
      {
        v46 = StringToInt(v45);
        v64 = v46;
      }
      else
      {
        v46 = v64;
      }
      if ( v66 > 38 )
        goto LABEL_94;
      v47 = v46 <= 38;
      goto LABEL_147;
    }
    if ( v30 == 12 )
    {
      v48 = Part;
      if ( Part && *Part && !ascii_wcsicmp(v67, L"Attribute") )
        v73 = StringToInt(v48);
      else
        v73 = 0;
      goto LABEL_148;
    }
    if ( (v30 == 10 || v30 == 9) && v42 > 255 )
    {
      v42 = 255;
      goto LABEL_148;
    }
    if ( v30 != 11 )
    {
      v47 = v42 <= 32766;
LABEL_147:
      if ( !v47 )
        goto LABEL_94;
    }
LABEL_148:
    v49 = (char *)MemAllocate(0xF8u);
    v50 = v49;
    if ( !v49 )
    {
      v29 = -1011;
      goto LABEL_181;
    }
    memset(v49, 0, 0xF8u);
    v51 = v73;
    *((_DWORD *)v50 + 2) = v30;
    *((_DWORD *)v50 + 6) = v51;
    if ( (v51 & 0x8000) != 0 )
      *((_DWORD *)v50 + 7) = 1;
    *((_DWORD *)v50 + 3) = v42;
    if ( v68 && *v68 )
    {
      memset(v83, 0, 0x82u);
      INIHexStringToBytes(v83, 130, v68, 2 * wcslen(v68));
      wcsncpy((wchar_t *)v50 + 18, v83, 0x41u);
    }
    else
    {
      wcsncpy((wchar_t *)v50 + 18, Source, 0x41u);
    }
    if ( v30 == 8 )
    {
      *(__m128i *)(v50 + 172) = _mm_loadu_si128((const __m128i *)Destination);
      *(__m128i *)(v50 + 188) = _mm_loadu_si128((const __m128i *)&Destination[16]);
      *(__m128i *)(v50 + 204) = _mm_loadu_si128((const __m128i *)&Destination[32]);
      *(__m128i *)(v50 + 220) = _mm_loadu_si128((const __m128i *)&Destination[48]);
      *(_QWORD *)(v50 + 236) = *(_QWORD *)&Destination[64];
    }
    else if ( v30 == 16 )
    {
      v50[244] = v66;
      v50[245] = v64;
    }
    if ( v78 )
      *v78 = v50;
    else
      *(_DWORD *)(a3 + 8) = v50;
    v78 = v50;
    v19 = ++v77;
    StringCchPrintfW(pszDest, 8u, L"%s%d", L"Col", v77);
    v4 = v79;
    ReadProfileParameter(v79, WideCharStr, pszDest, &::Source, 0x81u);
  }
  v52 = *(_DWORD *)(a3 + 52) == 1;
  *(_DWORD *)(a3 + 12) = v19 - 1;
  if ( v52 )
  {
    v53 = *(const wchar_t **)(a3 + 8);
    if ( v53 )
    {
      v54 = 0;
      v55 = 0;
      while ( 1 )
      {
        v56 = *((_DWORD *)v53 + 3);
        if ( !v56 )
          break;
        v54 += v56;
        if ( v54 > 0xFDE6 )
        {
          ErrorSetExtendedInfoSz1Sz2(-8236, WideCharStr, v53 + 18, 2);
          v29 = -5402;
          goto LABEL_181;
        }
        if ( v53 == *(const wchar_t **)(a3 + 8) )
          *((_DWORD *)v53 + 4) = 1;
        else
          *((_DWORD *)v53 + 4) = *((_DWORD *)v55 + 3) + *((_DWORD *)v55 + 4);
        v55 = v53;
        v53 = *(const wchar_t **)v53;
        if ( !v53 )
          goto LABEL_174;
      }
      ErrorSetExtendedInfoSz1Sz2(-8238, WideCharStr, v53 + 18, 2);
      v29 = -5401;
    }
    else
    {
      ErrorSetExtendedInfoSz1Sz2(-8237, v4, WideCharStr, 2);
      v29 = -5400;
    }
  }
  else
  {
LABEL_174:
    if ( *(_DWORD *)(a3 + 52) )
      return 0;
    v57 = *(_WORD *)(a3 + 730);
    v58 = *(_WORD *)(a3 + 56);
    if ( v57 != v58 )
    {
      v59 = *(_WORD *)(a3 + 724);
      if ( v59 != v58 )
      {
        v60 = *(_WORD *)(a3 + 72);
        if ( v60 != v57 && v60 != v59 && v60 != v58 )
          return 0;
      }
    }
    v29 = -5406;
  }
LABEL_181:
  v61 = *(_DWORD **)(a3 + 8);
  if ( v61 )
  {
    do
    {
      v62 = (_DWORD *)*v61;
      MemFree(v61);
      v61 = v62;
    }
    while ( v62 );
  }
  return v29;
}

```

## disassembly

```asm
0x10019f20  sub     esp, 1A8h
0x10019f26  mov     eax, ___security_cookie
0x10019f2b  xor     eax, esp
0x10019f2d  mov     [esp+1A8h+var_4], eax
0x10019f34  push    ebx
0x10019f35  mov     ebx, [esp+1ACh+pszSrc]
0x10019f3c  xor     eax, eax
0x10019f3e  push    ebp
0x10019f3f  mov     ebp, [esp+1B0h+arg_8]
0x10019f46  push    edi
0x10019f47  mov     edi, [esp+1B4h+arg_C]
0x10019f4e  push    48h ; 'H'; Size
0x10019f50  push    eax; Val
0x10019f51  mov     [esp+1BCh+var_180], eax
0x10019f55  lea     eax, [esp+1BCh+Destination]
0x10019f59  push    eax; void *
0x10019f5a  mov     [esp+1C0h+var_168], ebx
0x10019f5e  mov     [esp+1C0h+var_1A4], 0FFFFh
0x10019f66  mov     [esp+1C0h+var_19C], 0FFFFh
0x10019f6e  call    _memset
0x10019f73  add     esp, 0Ch
0x10019f76  push    ebp
0x10019f77  call    _InitializeSpec@4; InitializeSpec(x)
0x10019f7c  cmp     word ptr [ebx], 0
0x10019f80  jnz     short loc_10019F89
0x10019f82  xor     eax, eax
0x10019f84  jmp     loc_1001AD1E
0x10019f89  push    esi
0x10019f8a  mov     esi, [esp+1B8h+arg_4]
0x10019f91  lea     ecx, [esp+1B8h+WideCharStr]
0x10019f98  mov     eax, ecx
0x10019f9a  mov     edx, 41h ; 'A'
0x10019f9f  sub     esi, eax
0x10019fa1  lea     eax, [edx+7FFFFFBDh]
0x10019fa7  test    eax, eax
0x10019fa9  jz      short loc_10019FBF
0x10019fab  movzx   eax, word ptr [esi+ecx]
0x10019faf  test    ax, ax
0x10019fb2  jz      short loc_10019FBF
0x10019fb4  mov     [ecx], ax
0x10019fb7  add     ecx, 2
0x10019fba  dec     edx
0x10019fbb  jnz     short loc_10019FA1
0x10019fbd  jmp     short loc_10019FC3
0x10019fbf  test    edx, edx
0x10019fc1  jnz     short loc_10019FC6
0x10019fc3  sub     ecx, 2
0x10019fc6  xor     eax, eax
0x10019fc8  mov     [ecx], ax
0x10019fcb  lea     ecx, [esp+1B8h+WideCharStr]
0x10019fd2  lea     edx, [ecx+2]
0x10019fd5  mov     ax, [ecx]
0x10019fd8  add     ecx, 2
0x10019fdb  test    ax, ax
0x10019fde  jnz     short loc_10019FD5
0x10019fe0  sub     ecx, edx
0x10019fe2  sar     ecx, 1
0x10019fe4  cmp     [esp+ecx*2+1B8h+var_10E], 2Eh ; '.'
0x10019fed  jnz     short loc_1001A00C
0x10019fef  lea     ecx, ds:0FFFFFFFEh[ecx*2]
0x10019ff6  cmp     ecx, 82h
0x10019ffc  jnb     loc_1001AD38
0x1001a002  xor     eax, eax
0x1001a004  mov     [esp+ecx+1B8h+WideCharStr], ax
0x1001a00c  push    81h; nSize
0x1001a011  push    offset Source; LPWSTR
0x1001a016  push    offset aMaxscanrows; "MaxScanRows"
0x1001a01b  lea     eax, [esp+1C4h+WideCharStr]
0x1001a022  push    eax; lpWideCharStr
0x1001a023  push    ebx; LPCWCH
0x1001a024  call    _ReadProfileParameter@20; ReadProfileParameter(x,x,x,x,x)
0x1001a029  cmp     Source, 0
0x1001a031  jz      short loc_1001A058
0x1001a033  or      word ptr [ebp+10h], 4
0x1001a038  push    offset Source
0x1001a03d  call    StringToInt
0x1001a042  mov     [ebp+30h], eax
0x1001a045  cmp     eax, 0FFFFh
0x1001a04a  jnz     short loc_1001A058
0x1001a04c  push    2
0x1001a04e  push    offset aMaxscanrows; "MaxScanRows"
0x1001a053  jmp     loc_1001AD06
0x1001a058  push    0; int
0x1001a05a  push    offset aFalse; "False"
0x1001a05f  push    1; int
0x1001a061  push    offset aTrue; "True"
0x1001a066  push    offset aColnameheader; "ColNameHeader"
0x1001a06b  lea     eax, [esp+1CCh+WideCharStr]
0x1001a072  push    eax; lpWideCharStr
0x1001a073  push    ebx; LPCWCH
0x1001a074  call    CheckProfile
0x1001a079  mov     [ebp+1Ch], eax
0x1001a07c  cmp     eax, 0FFFFFFFFh
0x1001a07f  jnz     short loc_1001A08D
0x1001a081  push    2
0x1001a083  push    offset aColnameheader; "ColNameHeader"
0x1001a088  jmp     loc_1001AD06
0x1001a08d  cmp     Source, 0
0x1001a095  jz      short loc_1001A09C
0x1001a097  or      word ptr [ebp+10h], 1
0x1001a09c  push    81h; nSize
0x1001a0a1  push    offset Source; LPWSTR
0x1001a0a6  push    offset aCharacterset; "CharacterSet"
0x1001a0ab  lea     eax, [esp+1C4h+WideCharStr]
0x1001a0b2  mov     dword ptr [edi], 0
0x1001a0b8  push    eax; lpWideCharStr
0x1001a0b9  push    ebx; LPCWCH
0x1001a0ba  call    _ReadProfileParameter@20; ReadProfileParameter(x,x,x,x,x)
0x1001a0bf  cmp     Source, 0
0x1001a0c7  jz      short loc_1001A0EF
0x1001a0c9  push    0; int
0x1001a0cb  lea     eax, [ebp+24h]
0x1001a0ce  mov     dword ptr [edi], 1
0x1001a0d4  or      word ptr [ebp+10h], 2
0x1001a0d9  push    eax; int
0x1001a0da  push    offset Source; String
0x1001a0df  call    _DecodeCharacterSet@12; DecodeCharacterSet(x,x,x)
0x1001a0e4  test    eax, eax
0x1001a0e6  jnz     short loc_1001A0EF
0x1001a0e8  mov     [edi], eax
0x1001a0ea  jmp     loc_1001AD18
0x1001a0ef  push    81h; nSize
0x1001a0f4  push    offset Source; LPWSTR
0x1001a0f9  push    offset aFormat; "Format"
0x1001a0fe  lea     eax, [esp+1C4h+WideCharStr]
0x1001a105  push    eax; lpWideCharStr
0x1001a106  push    ebx; LPCWCH
0x1001a107  call    _ReadProfileParameter@20; ReadProfileParameter(x,x,x,x,x)
0x1001a10c  cmp     Source, 0
0x1001a114  jz      short loc_1001A13D
0x1001a116  or      word ptr [ebp+10h], 10h
0x1001a11b  lea     eax, [ebp+38h]
0x1001a11e  push    eax
0x1001a11f  lea     eax, [ebp+34h]
0x1001a122  push    eax
0x1001a123  push    offset Source
0x1001a128  call    _DecodeFormat@12; DecodeFormat(x,x,x)
0x1001a12d  test    eax, eax
0x1001a12f  jnz     short loc_1001A13D
0x1001a131  push    2
0x1001a133  push    offset aFormat; "Format"
0x1001a138  jmp     loc_1001AD06
0x1001a13d  push    81h; nSize
0x1001a142  push    offset Source; LPWSTR
0x1001a147  push    offset aFixedformat; "FixedFormat"
0x1001a14c  lea     eax, [esp+1C4h+WideCharStr]
0x1001a153  push    eax; lpWideCharStr
0x1001a154  push    ebx; LPCWCH
0x1001a155  call    _ReadProfileParameter@20; ReadProfileParameter(x,x,x,x,x)
0x1001a15a  cmp     Source, 0
0x1001a162  jz      short loc_1001A1A1
0x1001a164  or      word ptr [ebp+10h], 10h
0x1001a169  push    offset aRaggededge; "RaggedEdge"
0x1001a16e  push    offset Source
0x1001a173  call    _ascii_wcsicmp
0x1001a178  add     esp, 8
0x1001a17b  test    eax, eax
0x1001a17d  jz      short loc_1001A1A1
0x1001a17f  push    offset aTruefixedlengt; "TrueFixedLength"
0x1001a184  push    offset Source
0x1001a189  call    _ascii_wcsicmp
0x1001a18e  add     esp, 8
0x1001a191  test    eax, eax
0x1001a193  jz      short loc_1001A1A1
0x1001a195  push    2
0x1001a197  push    offset aFixedformat; "FixedFormat"
0x1001a19c  jmp     loc_1001AD06
0x1001a1a1  push    81h; nSize
0x1001a1a6  push    offset Source; LPWSTR
0x1001a1ab  push    offset aTextdelimiter; "TextDelimiter"
0x1001a1b0  lea     eax, [esp+1C4h+WideCharStr]
0x1001a1b7  push    eax; lpWideCharStr
0x1001a1b8  push    ebx; LPCWCH
0x1001a1b9  call    _ReadProfileParameter@20; ReadProfileParameter(x,x,x,x,x)
0x1001a1be  cmp     Source, 0
0x1001a1c6  jz      short loc_1001A215
0x1001a1c8  or      word ptr [ebp+10h], 20h
0x1001a1cd  mov     ecx, offset Source
0x1001a1d2  lea     edx, [ecx+2]
0x1001a1d5  mov     ax, [ecx]
0x1001a1d8  add     ecx, 2
0x1001a1db  test    ax, ax
0x1001a1de  jnz     short loc_1001A1D5
0x1001a1e0  sub     ecx, edx
0x1001a1e2  sar     ecx, 1
0x1001a1e4  cmp     ecx, 1
0x1001a1e7  jbe     short loc_1001A20B
0x1001a1e9  push    offset aNone; "None"
0x1001a1ee  push    offset Source
0x1001a1f3  call    _ascii_wcsicmp
0x1001a1f8  add     esp, 8
0x1001a1fb  test    eax, eax
0x1001a1fd  jz      short loc_1001A211
0x1001a1ff  push    2
0x1001a201  push    offset aTextdelimiter; "TextDelimiter"
0x1001a206  jmp     loc_1001AD06
0x1001a20b  mov     ax, Source
0x1001a211  mov     [ebp+48h], ax
0x1001a215  push    81h; nSize
0x1001a21a  push    offset Source; LPWSTR
0x1001a21f  push    offset aDatetimeformat; "DateTimeFormat"
0x1001a224  lea     eax, [esp+1C4h+WideCharStr]
0x1001a22b  push    eax; lpWideCharStr
0x1001a22c  push    ebx; LPCWCH
0x1001a22d  call    _ReadProfileParameter@20; ReadProfileParameter(x,x,x,x,x)
0x1001a232  cmp     Source, 0
0x1001a23a  jz      short loc_1001A28B
0x1001a23c  or      word ptr [ebp+10h], 40h
0x1001a241  lea     esi, [ebp+50h]
0x1001a244  push    41h ; 'A'; Count
0x1001a246  push    offset Source; Source
0x1001a24b  push    esi; Destination
0x1001a24c  call    _wcsncpy
0x1001a251  add     esp, 0Ch
0x1001a254  lea     eax, [ebp+2ECh]
0x1001a25a  push    eax
0x1001a25b  push    esi
0x1001a25c  call    ParseDateTimePicture
0x1001a261  test    eax, eax
0x1001a263  jnz     short loc_1001A271
0x1001a265  push    2
0x1001a267  push    offset aDatetimeformat; "DateTimeFormat"
0x1001a26c  jmp     loc_1001AD06
0x1001a271  xor     eax, eax
0x1001a273  mov     dword ptr [ebp+334h], 1
0x1001a27d  mov     [ebp+0D2h], ax
0x1001a284  mov     [ebp+154h], ax
0x1001a28b  push    81h; nSize
0x1001a290  push    offset Source; LPWSTR
0x1001a295  push    offset aCurrencysymbol; "CurrencySymbol"
0x1001a29a  lea     eax, [esp+1C4h+WideCharStr]
0x1001a2a1  push    eax; lpWideCharStr
0x1001a2a2  push    ebx; LPCWCH
0x1001a2a3  call    _ReadProfileParameter@20; ReadProfileParameter(x,x,x,x,x)
0x1001a2a8  cmp     Source, 0
0x1001a2b0  jz      short loc_1001A2D1
0x1001a2b2  mov     eax, 80h
0x1001a2b7  or      [ebp+10h], ax
0x1001a2bb  lea     eax, [ebp+2B0h]
0x1001a2c1  push    9; Count
0x1001a2c3  push    offset Source; Source
0x1001a2c8  push    eax; Destination
0x1001a2c9  call    _wcsncpy
0x1001a2ce  add     esp, 0Ch
0x1001a2d1  push    ebx; LPCWCH
0x1001a2d2  push    dword ptr [ebp+2C8h]; __int16
0x1001a2d8  lea     eax, [esp+1C0h+WideCharStr]
0x1001a2df  push    offset aCurrencyposfor; "CurrencyPosFormat"
0x1001a2e4  push    eax; lpWideCharStr
0x1001a2e5  call    GetSpecInt
0x1001a2ea  movzx   eax, ax
0x1001a2ed  mov     [ebp+2C8h], eax
0x1001a2f3  cmp     eax, 3
0x1001a2f6  ja      loc_1001ACFF
0x1001a2fc  cmp     Source, 0
0x1001a304  jz      short loc_1001A30F
0x1001a306  mov     eax, 100h
0x1001a30b  or      [ebp+10h], ax
0x1001a30f  push    ebx; LPCWCH
0x1001a310  push    dword ptr [ebp+2CCh]; __int16
0x1001a316  lea     eax, [esp+1C0h+WideCharStr]
0x1001a31d  push    offset aCurrencynegfor; "CurrencyNegFormat"
0x1001a322  push    eax; lpWideCharStr
0x1001a323  call    GetSpecInt
0x1001a328  movzx   eax, ax
0x1001a32b  mov     [ebp+2CCh], eax
0x1001a331  cmp     eax, 0Fh
0x1001a334  ja      loc_1001ACF6
0x1001a33a  cmp     Source, 0
0x1001a342  jz      short loc_1001A34D
0x1001a344  mov     eax, 200h
0x1001a349  or      [ebp+10h], ax
0x1001a34d  push    ebx; LPCWCH
0x1001a34e  push    dword ptr [ebp+2D0h]; __int16
0x1001a354  lea     eax, [esp+1C0h+WideCharStr]
0x1001a35b  push    offset aCurrencydigits; "CurrencyDigits"
0x1001a360  push    eax; lpWideCharStr
0x1001a361  call    GetSpecInt
0x1001a366  movzx   eax, ax
0x1001a369  mov     [ebp+2D0h], eax
0x1001a36f  cmp     eax, 4
0x1001a372  ja      loc_1001ACED
0x1001a378  cmp     Source, 0
0x1001a380  jz      short loc_1001A38B
0x1001a382  mov     eax, 400h
0x1001a387  or      [ebp+10h], ax
0x1001a38b  push    81h; nSize
0x1001a390  push    offset Source; LPWSTR
0x1001a395  push    offset aDecimalsymbol; "DecimalSymbol"
0x1001a39a  lea     eax, [esp+1C4h+WideCharStr]
0x1001a3a1  push    eax; lpWideCharStr
0x1001a3a2  push    ebx; LPCWCH
0x1001a3a3  call    _ReadProfileParameter@20; ReadProfileParameter(x,x,x,x,x)
0x1001a3a8  cmp     Source, 0
0x1001a3b0  mov     eax, 800h
0x1001a3b5  jz      short loc_1001A3D7
0x1001a3b7  or      [ebp+10h], ax
0x1001a3bb  movzx   eax, Source
0x1001a3c2  mov     [ebp+2DAh], ax
0x1001a3c9  movzx   eax, Source
  ... truncated ...
```
