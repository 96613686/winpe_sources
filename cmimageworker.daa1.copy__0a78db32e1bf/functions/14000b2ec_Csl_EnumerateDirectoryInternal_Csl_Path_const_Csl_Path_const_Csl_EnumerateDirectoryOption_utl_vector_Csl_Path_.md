# Csl::EnumerateDirectoryInternal(Csl::Path const &,Csl::Path const &,Csl::EnumerateDirectoryOption,utl::vector<Csl::Path,utl::allocator<Csl::Path>> &,ushort const *)

- ea: `0x14000b2ec`
- end: `0x14000bc3b`
- name: `?EnumerateDirectoryInternal@Csl@@YAJAEBVPath@1@0W4EnumerateDirectoryOption@1@AEAV?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@PEBG@Z`
- size: `2383`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, loader_planting`

## callers

- `0x14000ad64`
- `0x14000ae14`
- `0x14000b2ec`

## callees

- `0x1400020b0`
- `0x140002344`
- `0x140002b2c`
- `0x140006fc4`
- `0x140006fe4`
- `0x140008f90`
- `0x14000a544`
- `0x14000a5c4`
- `0x14000a68c`
- `0x14000a9b8`
- `0x14000ae14`
- `0x14000b2ec`
- `0x14000c948`
- `0x14000cd84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bad5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000b85b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000b8d1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000b970`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000b85b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000b8d1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000b970`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x14000b62f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x14000b62f`

## pseudocode

```c
__int64 __fastcall Csl::EnumerateDirectoryInternal(__int64 *a1, __int64 a2, int a3, __m128i *a4, _WORD *a5)
{
  int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // rdx
  void *v9; // rcx
  __m128i si128; // xmm6
  LPCWSTR v11; // rcx
  int v12; // ebx
  void *v13; // rcx
  bool v14; // zf
  __int64 i; // rbx
  __int64 v17; // rdi
  __int64 *v18; // rdi
  __int64 v19; // r14
  __int64 v20; // rbx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rax
  HANDLE FirstFile; // rax
  const char *v25; // r9
  unsigned int LastError; // eax
  LPCWSTR v27; // rcx
  unsigned int v28; // esi
  void *v29; // rdi
  _OWORD *v30; // rcx
  __int64 v31; // rdx
  char *v32; // rax
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm1
  __int64 v41; // r8
  __int64 v42; // rdx
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  void *v46; // rsi
  unsigned __int64 v47; // r14
  unsigned __int64 v48; // rdx
  char v49; // al
  LPCWSTR v50; // rcx
  void *v51; // rcx
  __int64 v52; // rdx
  LPCWSTR v53; // rcx
  void *v54; // rdi
  void *v55; // r12
  __int64 v56; // rdi
  unsigned int v57; // esi
  __int64 v58; // r14
  const char *v59; // r9
  unsigned int v60; // edi
  __int64 v61; // rcx
  __m128i *v62; // r13
  __m128i v63; // rdi
  __int64 v64; // r14
  __int64 v65; // rcx
  int lpSearchFilter; // [rsp+28h] [rbp-E0h]
  __m128i dwAdditionalFlags_8; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v68; // [rsp+48h] [rbp-C0h]
  void *v69[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int16 v70; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v71[4]; // [rsp+70h] [rbp-98h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+90h] [rbp-78h] BYREF
  _WORD v73[8]; // [rsp+A0h] [rbp-68h] BYREF
  void *v74[2]; // [rsp+B0h] [rbp-58h] BYREF
  __int16 v75; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v76; // [rsp+C2h] [rbp-46h]
  int v77; // [rsp+CAh] [rbp-3Eh]
  __int16 v78; // [rsp+CEh] [rbp-3Ah]
  __int64 v79; // [rsp+D0h] [rbp-38h]
  __m128i *v80; // [rsp+D8h] [rbp-30h]
  _WORD *v81; // [rsp+E0h] [rbp-28h]
  __int64 v82; // [rsp+E8h] [rbp-20h]
  HANDLE hFindFile; // [rsp+F8h] [rbp-10h] BYREF
  char v84; // [rsp+100h] [rbp-8h] BYREF
  void *v85[2]; // [rsp+350h] [rbp+248h] BYREF
  _WORD v86[12]; // [rsp+360h] [rbp+258h] BYREF
  _BYTE FindFileData[592]; // [rsp+378h] [rbp+270h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+630h] [rbp+528h]

  LODWORD(v71[0]) = a3;
  v6 = (int)a1;
  v7 = a1[1] - *a1;
  v79 = a2;
  v8 = *a1;
  v69[0] = &v70;
  v80 = a4;
  v69[1] = &v70;
  v70 = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v69,
                           v8,
                           v7 >> 1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)0x8007000ELL,
      lpSearchFilter);
    goto LABEL_3;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *(__m128i *)&v71[1] = si128;
  v71[3] = -1;
  if ( !(unsigned __int8)utl::vector<Csl::Path,utl::allocator<Csl::Path>>::emplace_back<Csl::Path,0>(&v71[1], v69) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3AB,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)0x8007000ELL,
      lpSearchFilter);
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&v71[1]);
LABEL_3:
    v9 = v69[0];
    if ( v69[0] == &v70 )
      return 2147942414LL;
LABEL_77:
    operator delete(v9, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  if ( (a3 & 4) != 0 && *a5 == 42 && a5[1] )
  {
    v68 = -1;
    v74[0] = &v75;
    v76 = 0;
    v74[1] = &v75;
    v77 = 0;
    v78 = 0;
    dwAdditionalFlags_8 = si128;
    v75 = 0;
    v12 = Csl::EnumerateDirectoryInternal(v6, (unsigned int)v74, 7, (unsigned int)&dwAdditionalFlags_8, (__int64)L"*");
    if ( v74[0] != &v75 )
      operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v12 == -2147024894 )
    {
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&dwAdditionalFlags_8);
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&v71[1]);
      v13 = v69[0];
      v14 = v69[0] == &v70;
LABEL_83:
      if ( !v14 )
        operator delete(v13, (const struct std::nothrow_t *)&std::nothrow);
      return 2147942402LL;
    }
    else
    {
      if ( v12 >= 0 )
      {
        v17 = dwAdditionalFlags_8.m128i_i64[1];
        for ( i = dwAdditionalFlags_8.m128i_i64[0]; ; i += 32 )
        {
          if ( i == v17 )
          {
            LODWORD(v71[0]) = a3 & 0xFFFFFFFB;
            utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&dwAdditionalFlags_8);
            si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
            goto LABEL_24;
          }
          if ( !(unsigned __int8)utl::vector<Csl::Path,utl::allocator<Csl::Path>>::emplace_back<Csl::Path,0>(&v71[1], i) )
            break;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3CC,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
          (const char *)0x8007000ELL,
          lpSearchFilter);
        utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&dwAdditionalFlags_8);
LABEL_76:
        utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&v71[1]);
        v9 = v69[0];
        if ( v69[0] == &v70 )
          return 2147942414LL;
        goto LABEL_77;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C6,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
        (const char *)(unsigned int)v12,
        lpSearchFilter);
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&dwAdditionalFlags_8);
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&v71[1]);
      if ( v69[0] != &v70 )
        operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
      return (unsigned int)v12;
    }
  }
  else
  {
LABEL_24:
    v18 = (__int64 *)v71[1];
    v19 = -1;
    dwAdditionalFlags_8 = si128;
    v20 = si128.m128i_i64[1];
    v68 = -1;
    while ( v18 != (__int64 *)v71[2] )
    {
      memset_0(FindFileData, 0, sizeof(FindFileData));
      v21 = v18[1] - *v18;
      v22 = *v18;
      lpFileName[0] = v73;
      lpFileName[1] = v73;
      v73[0] = 0;
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               lpFileName,
                               v22,
                               v21 >> 1) )
      {
        v52 = 988;
LABEL_70:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v52,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
          (const char *)0x8007000ELL,
          lpSearchFilter);
LABEL_71:
        v53 = lpFileName[0];
        if ( lpFileName[0] != v73 )
          operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
        v54 = (void *)dwAdditionalFlags_8.m128i_i64[0];
        if ( dwAdditionalFlags_8.m128i_i64[0] != -1 )
        {
          utl::_RangeDestroyApc<utl::allocator<Csl::FindFirstFileInformation>>(
            v53,
            dwAdditionalFlags_8.m128i_i64[0],
            (v20 - dwAdditionalFlags_8.m128i_i64[0]) / 632);
          v51 = v54;
          goto LABEL_75;
        }
        goto LABEL_76;
      }
      v81 = a5;
      v23 = -1;
      do
        ++v23;
      while ( a5[v23] );
      v82 = v23;
      if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)lpFileName) )
      {
        v52 = 989;
        goto LABEL_70;
      }
      FirstFile = FindFirstFileExW(lpFileName[0], FindExInfoBasic, FindFileData, FindExSearchNameMatch, 0, 2u);
      if ( FirstFile == (HANDLE)-1LL )
      {
        if ( GetLastError() != 2 )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x3EE,
                        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
                        v25);
          v27 = lpFileName[0];
          v28 = LastError;
          if ( lpFileName[0] != v73 )
            operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
          v29 = (void *)dwAdditionalFlags_8.m128i_i64[0];
          if ( dwAdditionalFlags_8.m128i_i64[0] != -1 )
          {
            utl::_RangeDestroyApc<utl::allocator<Csl::FindFirstFileInformation>>(
              v27,
              dwAdditionalFlags_8.m128i_i64[0],
              (v20 - dwAdditionalFlags_8.m128i_i64[0]) / 632);
            operator delete(v29, (const struct std::nothrow_t *)&std::nothrow);
          }
          utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&v71[1]);
          if ( v69[0] != &v70 )
            operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
          return v28;
        }
      }
      else
      {
        hFindFile = FirstFile;
        v85[0] = v86;
        v30 = FindFileData;
        v86[0] = 0;
        v31 = 4;
        v85[1] = v86;
        v32 = &v84;
        do
        {
          v33 = v30[1];
          *(_OWORD *)v32 = *v30;
          v34 = v30[2];
          *((_OWORD *)v32 + 1) = v33;
          v35 = v30[3];
          *((_OWORD *)v32 + 2) = v34;
          v36 = v30[4];
          *((_OWORD *)v32 + 3) = v35;
          v37 = v30[5];
          *((_OWORD *)v32 + 4) = v36;
          v38 = v30[6];
          *((_OWORD *)v32 + 5) = v37;
          v39 = v30[7];
          v30 += 8;
          *((_OWORD *)v32 + 6) = v38;
          *((_OWORD *)v32 + 7) = v39;
          v32 += 128;
          --v31;
        }
        while ( v31 );
        v40 = v30[1];
        v41 = v18[1] - *v18;
        v42 = *v18;
        *(_OWORD *)v32 = *v30;
        v43 = v30[2];
        *((_OWORD *)v32 + 1) = v40;
        v44 = v30[3];
        *((_OWORD *)v32 + 2) = v43;
        v45 = v30[4];
        *((_OWORD *)v32 + 3) = v44;
        *((_OWORD *)v32 + 4) = v45;
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 v85,
                                 v42,
                                 v41 >> 1) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3F5,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
            (const char *)0x8007000ELL,
            lpSearchFilter);
          if ( v85[0] != v86 )
            operator delete(v85[0], (const struct std::nothrow_t *)&std::nothrow);
          if ( (char *)hFindFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            FindClose(hFindFile);
          goto LABEL_71;
        }
        if ( v20 == v19 )
        {
          v46 = (void *)dwAdditionalFlags_8.m128i_i64[0];
          v47 = 0x9B8B577E613716AFuLL * ((v19 - dwAdditionalFlags_8.m128i_i64[0]) >> 3);
          v48 = 7 * (v47 >> 2) + 8;
          if ( v48 > 0x33D91D2A2067B2LL )
            v48 = 0x33D91D2A2067B2LL;
          if ( v47 >= v48 )
            goto LABEL_56;
          v49 = utl::vector<Csl::FindFirstFileInformation,utl::allocator<Csl::FindFirstFileInformation>>::_SetCapacity(&dwAdditionalFlags_8);
          v20 = dwAdditionalFlags_8.m128i_i64[1];
          if ( !v49 )
          {
            v46 = (void *)dwAdditionalFlags_8.m128i_i64[0];
LABEL_56:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3F7,
              (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
              (const char *)0x8007000ELL,
              lpSearchFilter);
            if ( v85[0] != v86 )
              operator delete(v85[0], (const struct std::nothrow_t *)&std::nothrow);
            if ( (char *)hFindFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              FindClose(hFindFile);
            v50 = lpFileName[0];
            if ( lpFileName[0] != v73 )
              operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
            if ( v46 != (void *)-1LL )
            {
              utl::_RangeDestroyApc<utl::allocator<Csl::FindFirstFileInformation>>(v50, v46, (v20 - (__int64)v46) / 632);
              v51 = v46;
LABEL_75:
              operator delete(v51, (const struct std::nothrow_t *)&std::nothrow);
              goto LABEL_76;
            }
            goto LABEL_76;
          }
          v19 = v68;
        }
        Csl::FindFirstFileInformation::FindFirstFileInformation(v20, &hFindFile);
        v20 += 632;
        dwAdditionalFlags_8.m128i_i64[1] = v20;
        if ( v85[0] != v86 )
          operator delete(v85[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( (char *)hFindFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          FindClose(hFindFile);
      }
      v11 = lpFileName[0];
      if ( lpFileName[0] != v73 )
        operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
      v18 += 4;
    }
    v55 = (void *)dwAdditionalFlags_8.m128i_i64[0];
    if ( dwAdditionalFlags_8.m128i_i64[0] == v20 )
    {
      if ( dwAdditionalFlags_8.m128i_i64[0] != -1 )
      {
        utl::_RangeDestroyApc<utl::allocator<Csl::FindFirstFileInformation>>(
          v11,
          dwAdditionalFlags_8.m128i_i64[0],
          (v20 - dwAdditionalFlags_8.m128i_i64[0]) / 632);
        operator delete(v55, (const struct std::nothrow_t *)&std::nothrow);
      }
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&v71[1]);
      v13 = v69[0];
      v14 = v69[0] == &v70;
      goto LABEL_83;
    }
    v56 = dwAdditionalFlags_8.m128i_i64[0];
    v57 = v71[0];
    v58 = v79;
    dwAdditionalFlags_8 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v68 = -1;
    while ( v56 != v20 )
    {
      Csl::EnumerateDirectoryInternal(v56, v58, v57, a5, &dwAdditionalFlags_8);
      v56 += 632;
    }
    if ( GetLastError() == 18 )
    {
      v62 = v80;
      v63 = dwAdditionalFlags_8;
      v64 = v68;
      dwAdditionalFlags_8 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      v68 = -1;
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(v80);
      *v62 = v63;
      v62[1].m128i_i64[0] = v64;
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&dwAdditionalFlags_8);
      if ( v55 != (void *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<Csl::FindFirstFileInformation>>(v65, v55, (v20 - (__int64)v55) / 632);
        operator delete(v55, (const struct std::nothrow_t *)&std::nothrow);
      }
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&v71[1]);
      if ( v69[0] != &v70 )
        operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
      return 0;
    }
    else
    {
      v60 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x415,
              (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
              v59);
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&dwAdditionalFlags_8);
      if ( v55 != (void *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<Csl::FindFirstFileInformation>>(v61, v55, (v20 - (__int64)v55) / 632);
        operator delete(v55, (const struct std::nothrow_t *)&std::nothrow);
      }
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&v71[1]);
      if ( v69[0] != &v70 )
        operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
      return v60;
    }
  }
}

```

## disassembly

```asm
0x14000b2ec  mov     rax, rsp
0x14000b2ef  push    rbp
0x14000b2f0  push    rbx
0x14000b2f1  push    rsi
0x14000b2f2  push    rdi
0x14000b2f3  push    r12
0x14000b2f5  push    r13
0x14000b2f7  push    r14
0x14000b2f9  push    r15
0x14000b2fb  lea     rbp, [rax-528h]
0x14000b302  sub     rsp, 5E8h
0x14000b309  movaps  xmmword ptr [rax-58h], xmm6
0x14000b30d  mov     rax, cs:__security_cookie
0x14000b314  xor     rax, rsp
0x14000b317  mov     [rbp+520h+var_60], rax
0x14000b31e  mov     r13, [rbp+520h+arg_20]
0x14000b325  lea     rax, [rsp+620h+var_5C8]
0x14000b32a  mov     esi, r8d
0x14000b32d  mov     dword ptr [rsp+620h+var_5B8], r8d
0x14000b332  mov     r8, [rcx+8]
0x14000b336  mov     rbx, rcx
0x14000b339  sub     r8, [rcx]
0x14000b33c  xor     r14d, r14d
0x14000b33f  mov     [rbp+520h+var_558], rdx
0x14000b343  mov     rdx, [rcx]
0x14000b346  lea     rcx, [rsp+620h+var_5D8]
0x14000b34b  mov     [rsp+620h+var_5D8], rax
0x14000b350  lea     rax, [rsp+620h+var_5C8]
0x14000b355  sar     r8, 1
0x14000b358  mov     [rbp+520h+var_550], r9
0x14000b35c  mov     qword ptr [rsp+620h+var_5D0], rax
0x14000b361  mov     [rsp+620h+var_5C8], r14w
0x14000b367  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14000b36c  test    al, al
0x14000b36e  jnz     short loc_14000B3AD
0x14000b370  mov     rcx, [rbp+528h]; this
0x14000b377  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000b37e  mov     r9d, 8007000Eh; char *
0x14000b384  mov     edx, 3A8h; void *
0x14000b389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b38e  mov     rcx, [rsp+620h+var_5D8]
0x14000b393  lea     rax, [rsp+620h+var_5C8]
0x14000b398  cmp     rcx, rax
0x14000b39b  jz      loc_14000BA14
0x14000b3a1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14000b3a8  jmp     loc_14000BA0F
0x14000b3ad  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14000b3b5  lea     rdx, [rsp+620h+var_5D8]
0x14000b3ba  or      r12, 0FFFFFFFFFFFFFFFFh
0x14000b3be  lea     rcx, [rsp+620h+var_5B8+8]
0x14000b3c3  movdqu  xmmword ptr [rsp+620h+var_5B8+8], xmm6
0x14000b3c9  mov     [rbp+520h+var_5A0], r12
0x14000b3cd  call    ??$emplace_back@VPath@Csl@@$0A@@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@QEAA_N$$QEAVPath@Csl@@@Z; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::emplace_back<Csl::Path,0>(Csl::Path &&)
0x14000b3d2  test    al, al
0x14000b3d4  jnz     short loc_14000B400
0x14000b3d6  mov     rcx, [rbp+528h]; this
0x14000b3dd  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000b3e4  mov     r9d, 8007000Eh; char *
0x14000b3ea  mov     edx, 3ABh; void *
0x14000b3ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b3f4  lea     rcx, [rsp+620h+var_5B8+8]
0x14000b3f9  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14000b3fe  jmp     short loc_14000B38E
0x14000b400  lea     r15, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14000b407  test    sil, 4
0x14000b40b  jz      loc_14000B57A
0x14000b411  cmp     word ptr [r13+0], 2Ah ; '*'
0x14000b417  jnz     loc_14000B57A
0x14000b41d  cmp     [r13+2], r14w
0x14000b422  jz      loc_14000B57A
0x14000b428  lea     rax, [rbp+520h+var_568]
0x14000b42c  mov     [rsp+620h+var_5E0], r12
0x14000b431  mov     [rbp+520h+var_578], rax
0x14000b435  lea     r9, [rsp+620h+dwAdditionalFlags+8]
0x14000b43a  lea     rax, [rbp+520h+var_568]
0x14000b43e  mov     [rbp+520h+var_566], r14
0x14000b442  mov     [rbp+520h+var_570], rax
0x14000b446  lea     rdx, [rbp+520h+var_578]
0x14000b44a  lea     rax, asc_14003692C; "*"
0x14000b451  mov     [rbp+520h+var_55E], r14d
0x14000b455  mov     r8d, 7
0x14000b45b  mov     [rsp+620h+lpSearchFilter], rax; int
0x14000b460  mov     rcx, rbx
0x14000b463  mov     [rbp+520h+var_55A], r14w
0x14000b468  movdqu  xmmword ptr [rsp+620h+dwAdditionalFlags+8], xmm6
0x14000b46e  mov     [rbp+520h+var_568], r14w
0x14000b473  call    ?EnumerateDirectoryInternal@Csl@@YAJAEBVPath@1@0W4EnumerateDirectoryOption@1@AEAV?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@PEBG@Z; Csl::EnumerateDirectoryInternal(Csl::Path const &,Csl::Path const &,Csl::EnumerateDirectoryOption,utl::vector<Csl::Path,utl::allocator<Csl::Path>> &,ushort const *)
0x14000b478  mov     rcx, [rbp+520h+var_578]; void *
0x14000b47c  mov     ebx, eax
0x14000b47e  lea     rax, [rbp+520h+var_568]
0x14000b482  cmp     rcx, rax
0x14000b485  jz      short loc_14000B48F
0x14000b487  mov     rdx, r15; struct std::nothrow_t *
0x14000b48a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000b48f  cmp     ebx, 80070002h
0x14000b495  jnz     short loc_14000B4BD
0x14000b497  lea     rcx, [rsp+620h+dwAdditionalFlags+8]
0x14000b49c  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14000b4a1  lea     rcx, [rsp+620h+var_5B8+8]
0x14000b4a6  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14000b4ab  mov     rcx, [rsp+620h+var_5D8]
0x14000b4b0  lea     rax, [rsp+620h+var_5C8]
0x14000b4b5  cmp     rcx, rax
0x14000b4b8  jmp     loc_14000BA76
0x14000b4bd  test    ebx, ebx
0x14000b4bf  jns     short loc_14000B50E
0x14000b4c1  mov     rcx, [rbp+528h]; this
0x14000b4c8  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000b4cf  mov     r9d, ebx; char *
0x14000b4d2  mov     edx, 3C6h; void *
0x14000b4d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b4dc  lea     rcx, [rsp+620h+dwAdditionalFlags+8]
0x14000b4e1  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14000b4e6  lea     rcx, [rsp+620h+var_5B8+8]
0x14000b4eb  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14000b4f0  mov     rcx, [rsp+620h+var_5D8]; void *
0x14000b4f5  lea     rax, [rsp+620h+var_5C8]
0x14000b4fa  cmp     rcx, rax
0x14000b4fd  jz      short loc_14000B507
0x14000b4ff  mov     rdx, r15; struct std::nothrow_t *
0x14000b502  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000b507  mov     eax, ebx
0x14000b509  jmp     loc_14000BC0F
0x14000b50e  mov     rbx, qword ptr [rsp+620h+dwAdditionalFlags+8]
0x14000b513  mov     rdi, [rsp+620h+var_5E8]
0x14000b518  cmp     rbx, rdi
0x14000b51b  jz      short loc_14000B561
0x14000b51d  mov     rdx, rbx
0x14000b520  lea     rcx, [rsp+620h+var_5B8+8]
0x14000b525  call    ??$emplace_back@VPath@Csl@@$0A@@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@QEAA_N$$QEAVPath@Csl@@@Z; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::emplace_back<Csl::Path,0>(Csl::Path &&)
0x14000b52a  test    al, al
0x14000b52c  jz      short loc_14000B534
0x14000b52e  add     rbx, 20h ; ' '
0x14000b532  jmp     short loc_14000B518
0x14000b534  mov     rcx, [rbp+528h]; this
0x14000b53b  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000b542  mov     r9d, 8007000Eh; char *
0x14000b548  mov     edx, 3CCh; void *
0x14000b54d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b552  lea     rcx, [rsp+620h+dwAdditionalFlags+8]
0x14000b557  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14000b55c  jmp     loc_14000B9F3
0x14000b561  and     esi, 0FFFFFFFBh
0x14000b564  lea     rcx, [rsp+620h+dwAdditionalFlags+8]
0x14000b569  mov     dword ptr [rsp+620h+var_5B8], esi
0x14000b56d  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14000b572  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14000b57a  mov     rdi, qword ptr [rsp+620h+var_5B8+8]
0x14000b57f  mov     r14, r12
0x14000b582  movdqu  xmmword ptr [rsp+620h+dwAdditionalFlags+8], xmm6
0x14000b588  mov     rbx, [rsp+620h+var_5E8]
0x14000b58d  mov     [rsp+620h+var_5E0], r12
0x14000b592  cmp     rdi, qword ptr [rsp+620h+var_5B8+10h]
0x14000b597  jz      loc_14000BA1E
0x14000b59d  xor     edx, edx; Val
0x14000b59f  lea     rcx, [rbp+520h+FindFileData]; void *
0x14000b5a6  mov     r8d, 250h; Size
0x14000b5ac  call    memset_0
0x14000b5b1  mov     r8, [rdi+8]
0x14000b5b5  lea     rax, [rbp+520h+var_588]
0x14000b5b9  sub     r8, [rdi]
0x14000b5bc  lea     rcx, [rbp+520h+lpFileName]
0x14000b5c0  mov     rdx, [rdi]
0x14000b5c3  xor     esi, esi
0x14000b5c5  mov     [rbp+520h+lpFileName], rax
0x14000b5c9  lea     rax, [rbp+520h+var_588]
0x14000b5cd  sar     r8, 1
0x14000b5d0  mov     [rbp+520h+var_590], rax
0x14000b5d4  mov     [rbp+520h+var_588], si
0x14000b5d8  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14000b5dd  test    al, al
0x14000b5df  jz      loc_14000B985
0x14000b5e5  mov     [rbp+520h+var_548], r13
0x14000b5e9  mov     rax, r12
0x14000b5ec  inc     rax
0x14000b5ef  cmp     [r13+rax*2+0], si
0x14000b5f5  jnz     short loc_14000B5EC
0x14000b5f7  lea     rdx, [rbp+520h+var_548]
0x14000b5fb  mov     [rbp+520h+var_540], rax
0x14000b5ff  lea     rcx, [rbp+520h+lpFileName]; this
0x14000b603  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14000b608  test    al, al
0x14000b60a  jz      loc_14000B97E
0x14000b610  mov     rcx, [rbp+520h+lpFileName]; lpFileName
0x14000b614  lea     r8, [rbp+520h+FindFileData]; lpFindFileData
0x14000b61b  xor     r9d, r9d; fSearchOp
0x14000b61e  mov     [rsp+620h+dwAdditionalFlags], 2; dwAdditionalFlags
0x14000b626  mov     [rsp+620h+lpSearchFilter], rsi; int
0x14000b62b  lea     edx, [r9+1]; fInfoLevelId
0x14000b62f  call    cs:__imp_FindFirstFileExW
0x14000b636  nop     dword ptr [rax+rax+00h]
0x14000b63b  mov     rcx, rax
0x14000b63e  cmp     rax, r12
0x14000b641  jnz     loc_14000B6EE
0x14000b647  call    cs:__imp_GetLastError
0x14000b64e  nop     dword ptr [rax+rax+00h]
0x14000b653  cmp     eax, 2
0x14000b656  jz      loc_14000B867
0x14000b65c  mov     rcx, [rbp+528h]; this
0x14000b663  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000b66a  mov     edx, 3EEh; void *
0x14000b66f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000b674  mov     rcx, [rbp+520h+lpFileName]; void *
0x14000b678  mov     esi, eax
0x14000b67a  lea     rax, [rbp+520h+var_588]
0x14000b67e  cmp     rcx, rax
0x14000b681  jz      short loc_14000B68B
0x14000b683  mov     rdx, r15; struct std::nothrow_t *
0x14000b686  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000b68b  mov     rdi, qword ptr [rsp+620h+dwAdditionalFlags+8]
0x14000b690  cmp     rdi, r12
0x14000b693  jz      short loc_14000B6C6
0x14000b695  sub     rbx, rdi
0x14000b698  mov     rax, 67B23A5440CF6475h
0x14000b6a2  imul    rbx
0x14000b6a5  sar     rdx, 8
0x14000b6a9  mov     r8, rdx
0x14000b6ac  shr     r8, 3Fh
0x14000b6b0  add     r8, rdx
0x14000b6b3  mov     rdx, rdi
0x14000b6b6  call    ??$_RangeDestroyApc@V?$allocator@UFindFirstFileInformation@Csl@@@utl@@@utl@@YAXAEAV?$allocator@UFindFirstFileInformation@Csl@@@0@PEAUFindFirstFileInformation@Csl@@_K@Z; utl::_RangeDestroyApc<utl::allocator<Csl::FindFirstFileInformation>>(utl::allocator<Csl::FindFirstFileInformation> &,Csl::FindFirstFileInformation *,unsigned __int64)
0x14000b6bb  mov     rdx, r15; struct std::nothrow_t *
0x14000b6be  mov     rcx, rdi; void *
0x14000b6c1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000b6c6  lea     rcx, [rsp+620h+var_5B8+8]
0x14000b6cb  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14000b6d0  mov     rcx, [rsp+620h+var_5D8]; void *
0x14000b6d5  lea     rax, [rsp+620h+var_5C8]
0x14000b6da  cmp     rcx, rax
0x14000b6dd  jz      short loc_14000B6E7
0x14000b6df  mov     rdx, r15; struct std::nothrow_t *
0x14000b6e2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000b6e7  mov     eax, esi
0x14000b6e9  jmp     loc_14000BC0F
0x14000b6ee  lea     rax, [rbp+520h+var_2C8]
0x14000b6f5  mov     [rbp+520h+hFindFile], rcx
0x14000b6f9  mov     [rbp+520h+var_2D8], rax
0x14000b700  lea     rcx, [rbp+520h+FindFileData]
0x14000b707  lea     rax, [rbp+520h+var_2C8]
0x14000b70e  mov     [rbp+520h+var_2C8], si
0x14000b715  mov     edx, 4
0x14000b71a  mov     [rbp+520h+var_2D0], rax
0x14000b721  lea     rax, [rbp+520h+var_528]
0x14000b725  lea     r8d, [rdx+7Ch]
0x14000b729  movups  xmm0, xmmword ptr [rcx]
0x14000b72c  movups  xmm1, xmmword ptr [rcx+10h]
0x14000b730  movups  xmmword ptr [rax], xmm0
0x14000b733  movups  xmm0, xmmword ptr [rcx+20h]
0x14000b737  movups  xmmword ptr [rax+10h], xmm1
0x14000b73b  movups  xmm1, xmmword ptr [rcx+30h]
0x14000b73f  movups  xmmword ptr [rax+20h], xmm0
0x14000b743  movups  xmm0, xmmword ptr [rcx+40h]
0x14000b747  movups  xmmword ptr [rax+30h], xmm1
0x14000b74b  movups  xmm1, xmmword ptr [rcx+50h]
0x14000b74f  movups  xmmword ptr [rax+40h], xmm0
0x14000b753  movups  xmm0, xmmword ptr [rcx+60h]
0x14000b757  movups  xmmword ptr [rax+50h], xmm1
0x14000b75b  movups  xmm1, xmmword ptr [rcx+70h]
0x14000b75f  add     rcx, r8
0x14000b762  movups  xmmword ptr [rax+60h], xmm0
0x14000b766  movups  xmmword ptr [rax+70h], xmm1
0x14000b76a  add     rax, r8
0x14000b76d  sub     rdx, 1
0x14000b771  jnz     short loc_14000B729
0x14000b773  movups  xmm0, xmmword ptr [rcx]
0x14000b776  mov     r8, [rdi+8]
0x14000b77a  movups  xmm1, xmmword ptr [rcx+10h]
0x14000b77e  sub     r8, [rdi]
0x14000b781  mov     rdx, [rdi]
0x14000b784  movups  xmmword ptr [rax], xmm0
0x14000b787  sar     r8, 1
0x14000b78a  movups  xmm0, xmmword ptr [rcx+20h]
0x14000b78e  movups  xmmword ptr [rax+10h], xmm1
0x14000b792  movups  xmm1, xmmword ptr [rcx+30h]
0x14000b796  movups  xmmword ptr [rax+20h], xmm0
0x14000b79a  movups  xmm0, xmmword ptr [rcx+40h]
0x14000b79e  lea     rcx, [rbp+520h+var_2D8]
0x14000b7a5  movups  xmmword ptr [rax+30h], xmm1
0x14000b7a9  movups  xmmword ptr [rax+40h], xmm0
0x14000b7ad  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14000b7b2  test    al, al
0x14000b7b4  jz      loc_14000B929
0x14000b7ba  cmp     rbx, r14
0x14000b7bd  jnz     short loc_14000B81A
0x14000b7bf  mov     rsi, qword ptr [rsp+620h+dwAdditionalFlags+8]
0x14000b7c4  mov     rax, 9B8B577E613716AFh
0x14000b7ce  sub     r14, rsi
0x14000b7d1  sar     r14, 3
0x14000b7d5  imul    r14, rax
0x14000b7d9  mov     rax, r14
0x14000b7dc  shr     rax, 2
0x14000b7e0  imul    rdx, rax, 7
0x14000b7e4  mov     rax, 33D91D2A2067B2h
0x14000b7ee  add     rdx, 8
0x14000b7f2  cmp     rdx, rax
0x14000b7f5  cmova   rdx, rax
0x14000b7f9  cmp     r14, rdx
0x14000b7fc  jnb     loc_14000B88A
0x14000b802  lea     rcx, [rsp+620h+dwAdditionalFlags+8]
0x14000b807  call    ?_SetCapacity@?$vector@UFindFirstFileInformation@Csl@@V?$allocator@UFindFirstFileInformation@Csl@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Csl::FindFirstFileInformation,utl::allocator<Csl::FindFirstFileInformation>>::_SetCapacity(unsigned __int64)
  ... truncated ...
```
