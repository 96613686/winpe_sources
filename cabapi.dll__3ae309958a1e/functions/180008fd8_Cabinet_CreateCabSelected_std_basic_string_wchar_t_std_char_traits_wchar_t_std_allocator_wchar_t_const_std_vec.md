# Cabinet::CreateCabSelected(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,CompressionType)

- ea: `0x180008fd8`
- end: `0x180009b57`
- name: `?CreateCabSelected@Cabinet@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@10W4CompressionType@@@Z`
- size: `2943`
- prototype: `__int64 __fastcall(wchar_t *String1, __int64 *, __int64 *, __int64 **, int)`
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180006d20`
- `0x180008d80`

## callees

- `0x180001540`
- `0x180001f76`
- `0x180001fd6`
- `0x180002e54`
- `0x180002f70`
- `0x180003648`
- `0x18000553c`
- `0x1800080a0`
- `0x1800081d8`
- `0x180008248`
- `0x1800082b8`
- `0x180008414`
- `0x1800084b4`
- `0x180008fd8`
- `0x18000a74c`
- `0x18000b4c0`
- `0x18000b658`
- `0x18000bcac`
- `0x18000c38c`
- `0x18000ec80`
- `0x180010124`

## import_xrefs

- `Cabinet!__imp_FCICreate` at `0x1800094e3`
- `Cabinet!__imp_FCICreate` at `0x1800094e3`
- `Cabinet!__imp_FCIAddFile` at `0x180009827`
- `Cabinet!__imp_FCIAddFile` at `0x1800098d5`
- `Cabinet!__imp_FCIAddFile` at `0x180009827`
- `Cabinet!__imp_FCIAddFile` at `0x1800098d5`
- `Cabinet!__imp_FCIFlushFolder` at `0x180009867`
- `Cabinet!__imp_FCIFlushFolder` at `0x180009867`
- `Cabinet!__imp_FCIFlushCabinet` at `0x180009a4a`
- `Cabinet!__imp_FCIFlushCabinet` at `0x180009a4a`
- `Cabinet!__imp_FCIDestroy` at `0x1800091ec`
- `Cabinet!__imp_FCIDestroy` at `0x1800095db`
- `Cabinet!__imp_FCIDestroy` at `0x1800099f9`
- `Cabinet!__imp_FCIDestroy` at `0x180009b17`
- `Cabinet!__imp_FCIDestroy` at `0x1800091ec`
- `Cabinet!__imp_FCIDestroy` at `0x1800095db`
- `Cabinet!__imp_FCIDestroy` at `0x1800099f9`
- `Cabinet!__imp_FCIDestroy` at `0x180009b17`

## pseudocode

```c
__int64 __fastcall Cabinet::CreateCabSelected(wchar_t *String1, __int64 *a2, __int64 *a3, __int64 **a4, int a5)
{
  __int64 **v5; // rbx
  TCOMP v9; // r15
  __int64 v10; // rdx
  unsigned int v11; // ebx
  __int64 v13; // rdx
  signed int PathAndFilename; // edi
  __int64 v15; // r8
  __int64 v16; // rdx
  __int128 *v17; // rax
  __int64 v18; // rdx
  char *v19; // rax
  __int64 v20; // r9
  __int64 v21; // r10
  __int64 v22; // rcx
  __int64 v23; // rdx
  char *szCabPath; // r8
  char v25; // r11
  char *v26; // rax
  char *v27; // rax
  char *szCab; // rdx
  char v29; // r8
  char *v30; // rax
  __int64 *v31; // r8
  HFCI v32; // r10
  __int64 v33; // rdx
  __int64 v34; // rbx
  __int64 v35; // r14
  __int64 v36; // r13
  __int64 v37; // r8
  wchar_t *v38; // rdx
  unsigned __int64 v39; // rcx
  wchar_t **v40; // r11
  __int64 traits_2_0_unsigned_short; // rax
  __int64 v42; // r11
  __int64 v43; // rdx
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // r8
  wchar_t **v47; // rax
  int v48; // edi
  wchar_t **v49; // rax
  wchar_t **v50; // rdx
  const wchar_t *v51; // rdx
  const wchar_t *v52; // rcx
  CHAR *v53; // r8
  CHAR *v54; // rdx
  CHAR *v55; // r8
  CHAR *v56; // rdx
  unsigned int v57; // esi
  int pfnopen; // [rsp+20h] [rbp-E0h]
  int pfnopena; // [rsp+20h] [rbp-E0h]
  int v60; // [rsp+70h] [rbp-90h]
  __int128 v61; // [rsp+78h] [rbp-88h] BYREF
  __int128 v62; // [rsp+88h] [rbp-78h]
  __int64 v63; // [rsp+98h] [rbp-68h]
  HFCI *p_hfci; // [rsp+A0h] [rbp-60h]
  HFCI hfci; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t *String2[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v67; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v68; // [rsp+C8h] [rbp-38h]
  LPSTR pszFileName[2]; // [rsp+D0h] [rbp-30h] BYREF
  __m128i v70; // [rsp+E0h] [rbp-20h]
  LPSTR pszSourceFile[2]; // [rsp+F0h] [rbp-10h] BYREF
  __m128i v72; // [rsp+100h] [rbp+0h]
  __int128 v73; // [rsp+110h] [rbp+10h] BYREF
  __m128i si128; // [rsp+120h] [rbp+20h]
  __int128 v75; // [rsp+130h] [rbp+30h] BYREF
  __m128i v76; // [rsp+140h] [rbp+40h]
  WCHAR WideCharStr[8]; // [rsp+150h] [rbp+50h] BYREF
  __m128i v78; // [rsp+160h] [rbp+60h]
  __int128 v79; // [rsp+170h] [rbp+70h] BYREF
  __m128i v80; // [rsp+180h] [rbp+80h]
  ERF perf; // [rsp+190h] [rbp+90h] BYREF
  _OWORD Src[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE pv[16]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v84[16]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v85[16]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v86[16]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v87[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v88[32]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v89[64]; // [rsp+240h] [rbp+140h] BYREF
  CCAB pccab; // [rsp+280h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+608h] [rbp+508h]

  v63 = -2;
  v5 = a4;
  v9 = 0;
  v60 = 0;
  if ( !*((_QWORD *)String1 + 2) )
  {
    v10 = 524;
LABEL_3:
    v11 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
      (const char *)0x80070057LL,
      pfnopen);
    return v11;
  }
  if ( !a4[2] )
  {
    v10 = 525;
    goto LABEL_3;
  }
  if ( a2[1] - *a2 != a3[1] - *a3 )
  {
    v10 = 526;
    goto LABEL_3;
  }
  memset_0(&pccab, 0, sizeof(pccab));
  *(_QWORD *)&perf.erfOper = 0;
  perf.fError = 0;
  hfci = 0;
  p_hfci = &hfci;
  CabContext::CabContext((unsigned int)pv, (_DWORD)String1, 2, 0, 0);
  v73 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v73) = 0;
  *(_OWORD *)WideCharStr = 0;
  v78 = si128;
  WideCharStr[0] = 0;
  v75 = 0;
  v76 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v75) = 0;
  *(_OWORD *)pszSourceFile = 0;
  v72 = v76;
  LOBYTE(pszSourceFile[0]) = 0;
  *(_OWORD *)String2 = 0;
  v67 = 0;
  v68 = 7;
  LOWORD(String2[0]) = 0;
  *(_OWORD *)pszFileName = 0;
  v70 = v76;
  LOBYTE(pszFileName[0]) = 0;
  PathAndFilename = Utils::ValidateFilePaths(a2, 0, 0);
  if ( PathAndFilename < 0 )
  {
    v16 = 541;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
      (const char *)(unsigned int)PathAndFilename,
      pfnopena);
LABEL_12:
    std::string::~string(pszFileName);
    std::wstring::~wstring(String2);
    std::string::~string(pszSourceFile);
    std::string::~string(&v75);
    std::wstring::~wstring(WideCharStr);
    std::wstring::~wstring(&v73);
    std::wstring::~wstring(v89);
    std::wstring::~wstring(v88);
    std::wstring::~wstring(v87);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v86);
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v85);
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v84);
    if ( hfci )
      FCIDestroy(hfci);
    return (unsigned int)PathAndFilename;
  }
  LOBYTE(v15) = 1;
  LOBYTE(v13) = 1;
  PathAndFilename = Utils::ValidateFilePaths(a3, v13, v15);
  if ( PathAndFilename < 0 )
  {
    v16 = 543;
    goto LABEL_11;
  }
  PathAndFilename = Utils::GetPathAndFilename(String1, &v73, WideCharStr);
  if ( PathAndFilename < 0 )
  {
    v16 = 545;
    goto LABEL_11;
  }
  v17 = &v73;
  if ( si128.m128i_i64[1] > 7uLL )
    v17 = (__int128 *)v73;
  *(_QWORD *)&v61 = v17;
  *((_QWORD *)&v61 + 1) = si128.m128i_i64[0];
  EnsureDirectoryExistsHr(&v61);
  Src[0] = 0;
  Src[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src[0]) = 0;
  v79 = 0;
  v80 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v79) = 0;
  PathAndFilename = Utils::ConvertPointerToString(pv, Src);
  if ( PathAndFilename < 0 )
  {
    v18 = 553;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
      (const char *)(unsigned int)PathAndFilename,
      pfnopena);
    std::string::~string(&v79);
    std::wstring::~wstring(Src);
    goto LABEL_12;
  }
  std::wstring::operator+=(Src, L"Z");
  PathAndFilename = Utils::ConvertUnicodeToMultiByte((LPCWCH)Src, &v79);
  if ( PathAndFilename < 0 )
  {
    v18 = 560;
    goto LABEL_23;
  }
  PathAndFilename = Utils::ConvertUnicodeToMultiByte(WideCharStr, &v75);
  if ( PathAndFilename < 0 )
  {
    v18 = 562;
    goto LABEL_23;
  }
  pccab.setID = 555;
  *(_QWORD *)&pccab.iCab = 1;
  pccab.szDisk[0] = 0;
  pccab.cb = 0x7FFFFFFF;
  pccab.cbFolderThresh = 0x7FFFFFFF;
  v19 = (char *)&v79;
  if ( v80.m128i_i64[1] > 0xFuLL )
    v19 = (char *)v79;
  v20 = 2147483646;
  v21 = 2147483646;
  v22 = 256;
  v23 = 256;
  szCabPath = pccab.szCabPath;
  do
  {
    if ( !v21 )
      break;
    v25 = *v19;
    if ( !*v19 )
      break;
    ++v19;
    *szCabPath++ = v25;
    --v21;
    --v23;
  }
  while ( v23 );
  PathAndFilename = v23 == 0 ? 0x8007007A : 0;
  v26 = szCabPath - 1;
  if ( v23 )
    v26 = szCabPath;
  *v26 = 0;
  if ( !v23 )
  {
    v18 = 571;
    goto LABEL_23;
  }
  v27 = (char *)&v75;
  if ( v76.m128i_i64[1] > 0xFuLL )
    v27 = (char *)v75;
  szCab = pccab.szCab;
  do
  {
    if ( !v20 )
      break;
    v29 = *v27;
    if ( !*v27 )
      break;
    ++v27;
    *szCab++ = v29;
    --v20;
    --v22;
  }
  while ( v22 );
  PathAndFilename = v22 == 0 ? 0x8007007A : 0;
  v30 = szCab - 1;
  if ( v22 )
    v30 = szCab;
  *v30 = 0;
  if ( !v22 )
  {
    v18 = 573;
    goto LABEL_23;
  }
  if ( v88 != (_BYTE *)v5 )
  {
    v31 = v5[2];
    if ( (unsigned __int64)v5[3] > 7 )
      v5 = (__int64 **)*v5;
    std::wstring::_Assign<wchar_t>(v88, v5, v31);
  }
  v32 = FCICreate(
          &perf,
          _scrt_stub_for_is_c_termination_complete,
          FdiCallbacks::CallbackAlloc,
          (PFNFCIFREE)FdiCallbacks::CallbackFree,
          FciCallbacks::CallbackFciFileOpen,
          FciCallbacks::CallbackFciFileRead,
          FciCallbacks::CallbackFciFileWrite,
          FciCallbacks::CallbackFciFileClose,
          FciCallbacks::CallbackFciFileSeek,
          (PFNFCIDELETE)FciCallbacks::CallbackFciFileDelete,
          FciCallbacks::CallbackFciGetTempFile,
          &pccab,
          pv);
  hfci = v32;
  if ( !v32 )
  {
    if ( (unsigned int)(perf.erfOper - 1) > 0xA )
    {
      v11 = -2145877265;
    }
    else
    {
      v11 = perf.erfOper - 2145877280;
      if ( perf.erfOper - 2145877280 >= 0 )
        goto LABEL_59;
    }
    v33 = 592;
LABEL_58:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
      (const char *)v11,
      pfnopena);
LABEL_59:
    std::string::~string(&v79);
    std::wstring::~wstring(Src);
    std::string::~string(pszFileName);
    std::wstring::~wstring(String2);
    std::string::~string(pszSourceFile);
    std::string::~string(&v75);
    std::wstring::~wstring(WideCharStr);
    std::wstring::~wstring(&v73);
    std::wstring::~wstring(v89);
    std::wstring::~wstring(v88);
    std::wstring::~wstring(v87);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v86);
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v85);
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v84);
    if ( hfci )
      FCIDestroy(hfci);
    return v11;
  }
  if ( a5 )
  {
    switch ( a5 )
    {
      case 1:
        v9 = 1;
        break;
      case 2:
        v9 = 5379;
        break;
      case 3:
        v9 = 3843;
        break;
      default:
        v33 = 610;
LABEL_138:
        v11 = -2147024809;
        goto LABEL_58;
    }
  }
  v34 = *a3;
  v35 = *a2;
  v36 = a2[1];
  if ( *a2 == v36 )
  {
LABEL_139:
    if ( !FCIFlushCabinet(
            v32,
            0,
            FciCallbacks::CallbackFciGetNextCabinet,
            (PFNFCISTATUS)_scrt_stub_for_is_c_termination_complete) )
    {
      if ( (unsigned int)(perf.erfOper - 1) > 8 )
      {
        PathAndFilename = -2145877281;
      }
      else
      {
        PathAndFilename = perf.erfOper - 2145877296;
        if ( perf.erfOper - 2145877296 >= 0 )
          goto LABEL_142;
      }
      v18 = 697;
      goto LABEL_23;
    }
LABEL_142:
    std::string::~string(&v79);
    std::wstring::~wstring(Src);
    std::string::~string(pszFileName);
    std::wstring::~wstring(String2);
    std::string::~string(pszSourceFile);
    std::string::~string(&v75);
    std::wstring::~wstring(WideCharStr);
    std::wstring::~wstring(&v73);
    std::wstring::~wstring(v89);
    std::wstring::~wstring(v88);
    std::wstring::~wstring(v87);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v86);
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v85);
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v84);
    if ( hfci )
      FCIDestroy(hfci);
    return 0;
  }
  while ( 1 )
  {
    if ( *(_QWORD *)(v35 + 16) )
    {
      v37 = *(_QWORD *)(v34 + 16);
      if ( v37 )
        break;
    }
LABEL_125:
    v35 += 32;
    if ( v35 == v36 )
      goto LABEL_139;
    v34 += 32;
  }
  if ( String2 != (wchar_t **)v34 )
  {
    if ( *(_QWORD *)(v34 + 24) <= 7u )
      v38 = (wchar_t *)v34;
    else
      v38 = *(wchar_t **)v34;
    std::wstring::_Assign<wchar_t>(String2, v38, v37);
  }
  v39 = v67;
  v40 = String2;
  if ( v68 > 7 )
    v40 = (wchar_t **)String2[0];
  if ( v67 )
  {
    traits_2_0_unsigned_short = anonymous_namespace_::_Finding::_Find_impl__anonymous_namespace_::_Finding::_Find_traits_2_0_unsigned_short_(
                                  v40,
                                  (char *)v40 + 2 * v67,
                                  58);
    if ( traits_2_0_unsigned_short != v43 )
    {
      v44 = (traits_2_0_unsigned_short - v42) >> 1;
      if ( v44 != -1 )
      {
        v45 = v44 + 1;
        v61 = 0;
        v62 = 0;
        if ( v67 < v44 + 1 )
          std::_String_val<std::_Simple_types<wchar_t>>::_Xran();
        v46 = -1;
        if ( v67 - v45 != -1 )
          v46 = v67 - v45;
        v47 = String2;
        if ( v68 > 7 )
          v47 = (wchar_t **)String2[0];
        std::wstring::_Construct<1,wchar_t const *>(&v61, (char *)v47 + 2 * v45, v46);
        v48 = v60 | 1;
        goto LABEL_96;
      }
    }
    v39 = v67;
  }
  v48 = v60;
  while ( v39 )
  {
    v49 = String2;
    if ( v68 > 7 )
      v49 = (wchar_t **)String2[0];
    if ( *(_WORD *)v49 != 92 )
      break;
    v61 = 0;
    v62 = 0;
    v50 = String2;
    if ( v68 > 7 )
      v50 = (wchar_t **)String2[0];
    std::wstring::_Construct<1,wchar_t const *>(&v61, (char *)v50 + 2, v39 - 1);
    v48 |= 2u;
LABEL_96:
    v60 = v48;
    std::wstring::operator=(String2, &v61);
    std::wstring::~wstring(&v61);
    v39 = v67;
  }
  v51 = (const wchar_t *)String2;
  if ( v68 > 7 )
    v51 = String2[0];
  if ( *((_QWORD *)String1 + 3) <= 7u )
    v52 = String1;
  else
    v52 = *(const wchar_t **)String1;
  if ( !wcsicmp(v52, v51) )
  {
    v33 = 636;
    goto LABEL_138;
  }
  PathAndFilename = Utils::ConvertUnicodeToMultiByte((LPCWCH)v35, pszSourceFile);
  if ( PathAndFilename < 0 )
  {
    v18 = 643;
    goto LABEL_23;
  }
  PathAndFilename = Utils::ConvertUnicodeToMultiByte((LPCWCH)String2, pszFileName);
  if ( PathAndFilename < 0 )
  {
    v18 = 645;
    goto LABEL_23;
  }
  v53 = (CHAR *)pszFileName;
  if ( v70.m128i_i64[1] > 0xFuLL )
    v53 = pszFileName[0];
  v54 = (CHAR *)pszSourceFile;
  if ( v72.m128i_i64[1] > 0xFuLL )
    v54 = pszSourceFile[0];
  if ( FCIAddFile(
         hfci,
         v54,
         v53,
         0,
         FciCallbacks::CallbackFciGetNextCabinet,
         (PFNFCISTATUS)_scrt_stub_for_is_c_termination_complete,
         FciCallbacks::CallbackFciGetOpenInfo,
         v9) )
  {
    goto LABEL_124;
  }
  if ( (unsigned int)(perf.erfOper - 1) > 8 )
  {
    PathAndFilename = -2145877281;
LABEL_134:
    v18 = 685;
    goto LABEL_23;
  }
  PathAndFilename = perf.erfOper - 2145877296;
  if ( perf.erfOper != 9 )
    goto LABEL_123;
  if ( !FCIFlushFolder(
          hfci,
          FciCallbacks::CallbackFciGetNextCabinet,
          (PFNFCISTATUS)_scrt_stub_for_is_c_termination_complete) )
  {
    if ( (unsigned int)(perf.erfOper - 1) > 8 )
    {
      PathAndFilename = -2145877281;
LABEL_128:
      v18 = 668;
      goto LABEL_23;
    }
    PathAndFilename = perf.erfOper - 2145877296;
    if ( perf.erfOper - 2145877296 < 0 )
      goto LABEL_128;
  }
  v55 = (CHAR *)pszFileName;
  if ( v70.m128i_i64[1] > 0xFuLL )
    v55 = pszFileName[0];
  v56 = (CHAR *)pszSourceFile;
  if ( v72.m128i_i64[1] > 0xFuLL )
    v56 = pszSourceFile[0];
  if ( FCIAddFile(
         hfci,
         v56,
         v55,
         0,
         FciCallbacks::CallbackFciGetNextCabinet,
         (PFNFCISTATUS)_scrt_stub_for_is_c_termination_complete,
         FciCallbacks::CallbackFciGetOpenInfo,
         v9) )
  {
LABEL_124:
    v32 = hfci;
    goto LABEL_125;
  }
  if ( (unsigned int)(perf.erfOper - 1) <= 8 )
  {
    PathAndFilename = 0;
    v57 = perf.erfOper - 2145877296;
    if ( perf.erfOper - 2145877296 < 0 )
      goto LABEL_130;
LABEL_123:
    if ( PathAndFilename < 0 )
      goto LABEL_134;
    goto LABEL_124;
  }
  v57 = -2145877281;
LABEL_130:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A9,
    (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
    (const char *)v57,
    pfnopena);
  std::string::~string(&v79);
  std::wstring::~wstring(Src);
  std::string::~string(pszFileName);
  std::wstring::~wstring(String2);
  std::string::~string(pszSourceFile);
  std::string::~string(&v75);
  std::wstring::~wstring(WideCharStr);
  std::wstring::~wstring(&v73);
  std::wstring::~wstring(v89);
  std::wstring::~wstring(v88);
  std::wstring::~wstring(v87);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v86);
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v85);
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v84);
  if ( hfci )
    FCIDestroy(hfci);
  return v57;
}

```

## disassembly

```asm
0x180008fd8  push    rbp
0x180008fda  push    rbx
0x180008fdb  push    rsi
0x180008fdc  push    rdi
0x180008fdd  push    r12
0x180008fdf  push    r13
0x180008fe1  push    r14
0x180008fe3  push    r15
0x180008fe5  lea     rbp, [rsp-4C8h]
0x180008fed  sub     rsp, 5C8h
0x180008ff4  mov     [rbp+500h+var_568], 0FFFFFFFFFFFFFFFEh
0x180008ffc  mov     rax, cs:__security_cookie
0x180009003  xor     rax, rsp
0x180009006  mov     [rbp+500h+var_50], rax
0x18000900d  mov     rbx, r9
0x180009010  mov     r14, r8
0x180009013  mov     rsi, rdx
0x180009016  mov     r12, rcx
0x180009019  xor     r15d, r15d
0x18000901c  mov     [rsp+600h+var_590], r15d
0x180009021  cmp     [rcx+10h], r15
0x180009025  jnz     short loc_18000904E
0x180009027  mov     edx, 20Ch; void *
0x18000902c  mov     ebx, 80070057h
0x180009031  mov     rcx, [rbp+508h]; this
0x180009038  mov     r9d, ebx; char *
0x18000903b  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x180009042  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009047  mov     eax, ebx
0x180009049  jmp     loc_180009B1F
0x18000904e  cmp     [r9+10h], r15
0x180009052  jnz     short loc_18000905B
0x180009054  mov     edx, 20Dh
0x180009059  jmp     short loc_18000902C
0x18000905b  mov     rcx, [r8+8]
0x18000905f  sub     rcx, [r8]
0x180009062  mov     rax, [rdx+8]
0x180009066  sub     rax, [rdx]
0x180009069  cmp     rax, rcx
0x18000906c  jz      short loc_180009075
0x18000906e  mov     edx, 20Eh
0x180009073  jmp     short loc_18000902C
0x180009075  xor     edx, edx; Val
0x180009077  mov     r8d, 324h; Size
0x18000907d  lea     rcx, [rbp+500h+var_380]; void *
0x180009084  call    memset_0
0x180009089  xor     eax, eax
0x18000908b  mov     qword ptr [rbp+500h+perf.erfOper], rax
0x180009092  mov     [rbp+500h+perf.fError], eax
0x180009098  mov     [rbp+500h+hfci], r15
0x18000909c  lea     rax, [rbp+500h+hfci]
0x1800090a0  mov     [rbp+500h+var_560], rax
0x1800090a4  mov     [rsp+600h+pfnopen], r15; int
0x1800090a9  xor     r9d, r9d
0x1800090ac  lea     r8d, [r9+2]
0x1800090b0  mov     rdx, r12
0x1800090b3  lea     rcx, [rbp+500h+var_440]
0x1800090ba  call    ??0CabContext@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KPEAPEAEPEAK@Z; CabContext::CabContext(std::wstring const &,ulong,uchar * *,ulong *)
0x1800090bf  nop
0x1800090c0  xorps   xmm0, xmm0
0x1800090c3  movups  [rbp+500h+var_4F0], xmm0
0x1800090c7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800090cf  movdqu  [rbp+500h+var_4E0], xmm1
0x1800090d4  mov     word ptr [rbp+500h+var_4F0], r15w
0x1800090d9  movups  xmmword ptr [rbp+500h+WideCharStr], xmm0
0x1800090dd  movdqu  [rbp+500h+var_4A0], xmm1
0x1800090e2  mov     [rbp+500h+WideCharStr], r15w
0x1800090e7  movups  [rbp+500h+var_4D0], xmm0
0x1800090eb  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800090f3  movdqu  [rbp+500h+var_4C0], xmm1
0x1800090f8  mov     byte ptr [rbp+500h+var_4D0], r15b
0x1800090fc  movups  xmmword ptr [rbp+500h+pszSourceFile], xmm0
0x180009100  movdqu  [rbp+500h+var_500], xmm1
0x180009105  mov     byte ptr [rbp+500h+pszSourceFile], r15b
0x180009109  movups  xmmword ptr [rbp+500h+String2], xmm0
0x18000910d  mov     [rbp+500h+var_540], r15
0x180009111  mov     [rbp+500h+var_538], 7
0x180009119  mov     word ptr [rbp+500h+String2], r15w
0x18000911e  movups  xmmword ptr [rbp+500h+pszFileName], xmm0
0x180009122  movdqu  [rbp+500h+var_520], xmm1
0x180009127  mov     byte ptr [rbp+500h+pszFileName], r15b
0x18000912b  xor     r8d, r8d
0x18000912e  xor     edx, edx
0x180009130  mov     rcx, rsi
0x180009133  call    ?ValidateFilePaths@Utils@@SAJAEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@_N1@Z; Utils::ValidateFilePaths(std::vector<std::wstring> const &,bool,bool)
0x180009138  mov     edi, eax
0x18000913a  test    eax, eax
0x18000913c  jns     loc_1800091F9
0x180009142  mov     edx, 21Dh; void *
0x180009147  mov     rcx, [rbp+508h]; this
0x18000914e  mov     r9d, edi; char *
0x180009151  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x180009158  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000915d  nop
0x18000915e  lea     rcx, [rbp+500h+pszFileName]
0x180009162  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180009167  nop
0x180009168  lea     rcx, [rbp+500h+String2]
0x18000916c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009171  nop
0x180009172  lea     rcx, [rbp+500h+pszSourceFile]
0x180009176  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000917b  nop
0x18000917c  lea     rcx, [rbp+500h+var_4D0]
0x180009180  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180009185  nop
0x180009186  lea     rcx, [rbp+500h+WideCharStr]
0x18000918a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000918f  nop
0x180009190  lea     rcx, [rbp+500h+var_4F0]
0x180009194  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009199  nop
0x18000919a  lea     rcx, [rbp+500h+var_3C0]
0x1800091a1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800091a6  lea     rcx, [rbp+500h+var_3E0]
0x1800091ad  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800091b2  lea     rcx, [rbp+500h+var_400]
0x1800091b9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800091be  lea     rcx, [rbp+500h+var_410]
0x1800091c5  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800091ca  lea     rcx, [rbp+500h+var_420]
0x1800091d1  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x1800091d6  lea     rcx, [rbp+500h+var_430]
0x1800091dd  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x1800091e2  nop
0x1800091e3  mov     rcx, [rbp+500h+hfci]; hfci
0x1800091e7  test    rcx, rcx
0x1800091ea  jz      short loc_1800091F2
0x1800091ec  call    cs:__imp_FCIDestroy
0x1800091f2  mov     eax, edi
0x1800091f4  jmp     loc_180009B1F
0x1800091f9  mov     r13d, 1
0x1800091ff  mov     r8b, r13b
0x180009202  mov     dl, r13b
0x180009205  mov     rcx, r14
0x180009208  call    ?ValidateFilePaths@Utils@@SAJAEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@_N1@Z; Utils::ValidateFilePaths(std::vector<std::wstring> const &,bool,bool)
0x18000920d  mov     edi, eax
0x18000920f  test    eax, eax
0x180009211  jns     short loc_18000921D
0x180009213  mov     edx, 21Fh
0x180009218  jmp     loc_180009147
0x18000921d  lea     r8, [rbp+500h+WideCharStr]
0x180009221  lea     rdx, [rbp+500h+var_4F0]
0x180009225  mov     rcx, r12
0x180009228  call    ?GetPathAndFilename@Utils@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV23@1@Z; Utils::GetPathAndFilename(std::wstring const &,std::wstring *,std::wstring *)
0x18000922d  mov     edi, eax
0x18000922f  test    eax, eax
0x180009231  jns     short loc_18000923D
0x180009233  mov     edx, 221h
0x180009238  jmp     loc_180009147
0x18000923d  mov     rcx, qword ptr [rbp+500h+var_4E0]
0x180009241  lea     rax, [rbp+500h+var_4F0]
0x180009245  cmp     qword ptr [rbp+500h+var_4E0+8], 7
0x18000924a  cmova   rax, qword ptr [rbp+500h+var_4F0]
0x18000924f  mov     qword ptr [rsp+600h+var_588], rax
0x180009254  mov     qword ptr [rbp+500h+var_588+8], rcx
0x180009258  lea     rcx, [rsp+600h+var_588]
0x18000925d  call    ?EnsureDirectoryExistsHr@@YAJAEBV?$basic_zstring_view@_W@wil@@@Z; EnsureDirectoryExistsHr(wil::basic_zstring_view<wchar_t> const &)
0x180009262  xorps   xmm0, xmm0
0x180009265  movups  [rbp+500h+Src], xmm0
0x18000926c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180009274  movdqu  [rbp+500h+var_450], xmm1
0x18000927c  mov     word ptr [rbp+500h+Src], r15w
0x180009284  movups  [rbp+500h+var_490], xmm0
0x180009288  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180009290  movdqu  [rbp+500h+var_480], xmm1
0x180009298  mov     byte ptr [rbp+500h+var_490], r15b
0x18000929c  lea     rdx, [rbp+500h+Src]
0x1800092a3  lea     rcx, [rbp+500h+var_440]
0x1800092aa  call    ?ConvertPointerToString@Utils@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Utils::ConvertPointerToString(void *,std::wstring *)
0x1800092af  mov     edi, eax
0x1800092b1  test    eax, eax
0x1800092b3  jns     short loc_1800092EC
0x1800092b5  mov     edx, 229h; void *
0x1800092ba  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x1800092c1  mov     r9d, edi; char *
0x1800092c4  mov     rcx, [rbp+508h]; this
0x1800092cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800092d0  nop
0x1800092d1  lea     rcx, [rbp+500h+var_490]
0x1800092d5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800092da  nop
0x1800092db  lea     rcx, [rbp+500h+Src]
0x1800092e2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800092e7  jmp     loc_18000915E
0x1800092ec  lea     rdx, aZ; "Z"
0x1800092f3  lea     rcx, [rbp+500h+Src]; Src
0x1800092fa  call    ??Y?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator+=(wchar_t const * const)
0x1800092ff  lea     rdx, [rbp+500h+var_490]; void *
0x180009303  lea     rcx, [rbp+500h+Src]; lpWideCharStr
0x18000930a  call    ?ConvertUnicodeToMultiByte@Utils@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; Utils::ConvertUnicodeToMultiByte(std::wstring const &,std::string *)
0x18000930f  mov     edi, eax
0x180009311  test    eax, eax
0x180009313  jns     short loc_18000931C
0x180009315  mov     edx, 230h
0x18000931a  jmp     short loc_1800092BA
0x18000931c  lea     rdx, [rbp+500h+var_4D0]; void *
0x180009320  lea     rcx, [rbp+500h+WideCharStr]; lpWideCharStr
0x180009324  call    ?ConvertUnicodeToMultiByte@Utils@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; Utils::ConvertUnicodeToMultiByte(std::wstring const &,std::string *)
0x180009329  mov     edi, eax
0x18000932b  test    eax, eax
0x18000932d  jns     short loc_180009336
0x18000932f  mov     edx, 232h
0x180009334  jmp     short loc_1800092BA
0x180009336  mov     eax, 22Bh
0x18000933b  mov     [rbp+500h+var_380.setID], ax
0x180009342  mov     qword ptr [rbp+500h+var_380.iCab], 1
0x18000934d  mov     [rbp+500h+var_380.szDisk], r15b
0x180009354  mov     eax, 7FFFFFFFh
0x180009359  mov     [rbp+500h+var_380.cb], eax
0x18000935f  mov     [rbp+500h+var_380.cbFolderThresh], eax
0x180009365  lea     rax, [rbp+500h+var_490]
0x180009369  cmp     qword ptr [rbp+500h+var_480+8], 0Fh
0x180009371  cmova   rax, qword ptr [rbp+500h+var_490]
0x180009376  mov     r9d, 7FFFFFFEh
0x18000937c  mov     r10d, r9d
0x18000937f  mov     ecx, 100h
0x180009384  mov     edx, ecx
0x180009386  lea     r8, [rbp+500h+var_380.szCabPath]
0x18000938d  test    r10, r10
0x180009390  jz      short loc_1800093AB
0x180009392  mov     r11b, [rax]
0x180009395  test    r11b, r11b
0x180009398  jz      short loc_1800093AB
0x18000939a  add     rax, r13
0x18000939d  mov     [r8], r11b
0x1800093a0  add     r8, r13
0x1800093a3  sub     r10, r13
0x1800093a6  sub     rdx, r13
0x1800093a9  jnz     short loc_18000938D
0x1800093ab  mov     rax, rdx
0x1800093ae  neg     rax
0x1800093b1  sbb     edi, edi
0x1800093b3  not     edi
0x1800093b5  mov     r10d, 8007007Ah
0x1800093bb  and     edi, r10d
0x1800093be  lea     rax, [r8-1]
0x1800093c2  test    rdx, rdx
0x1800093c5  cmovnz  rax, r8
0x1800093c9  mov     [rax], r15b
0x1800093cc  jnz     short loc_1800093D8
0x1800093ce  mov     edx, 23Bh
0x1800093d3  jmp     loc_1800092BA
0x1800093d8  lea     rax, [rbp+500h+var_4D0]
0x1800093dc  cmp     qword ptr [rbp+500h+var_4C0+8], 0Fh
0x1800093e1  cmova   rax, qword ptr [rbp+500h+var_4D0]
0x1800093e6  lea     rdx, [rbp+500h+var_380.szCab]
0x1800093ed  test    r9, r9
0x1800093f0  jz      short loc_18000940B
0x1800093f2  mov     r8b, [rax]
0x1800093f5  test    r8b, r8b
0x1800093f8  jz      short loc_18000940B
0x1800093fa  add     rax, r13
0x1800093fd  mov     [rdx], r8b
0x180009400  add     rdx, r13
0x180009403  sub     r9, r13
0x180009406  sub     rcx, r13
0x180009409  jnz     short loc_1800093ED
0x18000940b  mov     rax, rcx
0x18000940e  neg     rax
0x180009411  sbb     edi, edi
0x180009413  not     edi
0x180009415  and     edi, r10d
0x180009418  lea     rax, [rdx-1]
0x18000941c  test    rcx, rcx
0x18000941f  cmovnz  rax, rdx
0x180009423  mov     [rax], r15b
0x180009426  jnz     short loc_180009432
0x180009428  mov     edx, 23Dh
0x18000942d  jmp     loc_1800092BA
0x180009432  lea     rax, [rbp+500h+var_3E0]
0x180009439  cmp     rax, rbx
0x18000943c  jz      short loc_18000945B
0x18000943e  mov     r8, [rbx+10h]
0x180009442  cmp     qword ptr [rbx+18h], 7
0x180009447  jbe     short loc_18000944C
0x180009449  mov     rbx, [rbx]
0x18000944c  mov     rdx, rbx
0x18000944f  lea     rcx, [rbp+500h+var_3E0]
0x180009456  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000945b  lea     rax, [rbp+500h+var_440]
0x180009462  mov     [rsp+600h+pv], rax; pv
0x180009467  lea     rax, [rbp+500h+var_380]
0x18000946e  mov     [rsp+600h+pccab], rax; pccab
0x180009473  lea     rax, ?CallbackFciGetTempFile@FciCallbacks@@SAHPEADHPEAX@Z; FciCallbacks::CallbackFciGetTempFile(char *,int,void *)
0x18000947a  mov     [rsp+600h+pfnfcigtf], rax; pfnfcigtf
0x18000947f  lea     rax, ?CallbackFciFileDelete@FciCallbacks@@SAHPEADPEAHPEAX@Z; FciCallbacks::CallbackFciFileDelete(char *,int *,void *)
0x180009486  mov     [rsp+600h+pfndelete], rax; pfndelete
0x18000948b  lea     rax, ?CallbackFciFileSeek@FciCallbacks@@SAJ_JJHPEAHPEAX@Z; FciCallbacks::CallbackFciFileSeek(__int64,long,int,int *,void *)
0x180009492  mov     [rsp+600h+pfnseek], rax; pfnseek
0x180009497  lea     rax, ?CallbackFciFileClose@FciCallbacks@@SAH_JPEAHPEAX@Z; FciCallbacks::CallbackFciFileClose(__int64,int *,void *)
0x18000949e  mov     [rsp+600h+pfnclose], rax; pfnclose
0x1800094a3  lea     rax, ?CallbackFciFileWrite@FciCallbacks@@SAI_JPEAXIPEAH1@Z; FciCallbacks::CallbackFciFileWrite(__int64,void *,uint,int *,void *)
0x1800094aa  mov     [rsp+600h+pfnwrite], rax; pfnwrite
0x1800094af  lea     rax, ?CallbackFciFileRead@FciCallbacks@@SAI_JPEAXIPEAH1@Z; FciCallbacks::CallbackFciFileRead(__int64,void *,uint,int *,void *)
0x1800094b6  mov     [rsp+600h+pfnread], rax; pfnread
0x1800094bb  lea     rax, ?CallbackFciFileOpen@FciCallbacks@@SA_JPEADHHPEAHPEAX@Z; FciCallbacks::CallbackFciFileOpen(char *,int,int,int *,void *)
0x1800094c2  mov     [rsp+600h+pfnopen], rax; int
0x1800094c7  lea     r9, ?CallbackFree@FdiCallbacks@@SAXPEAX@Z; pfnf
0x1800094ce  lea     r8, ?CallbackAlloc@FdiCallbacks@@SAPEAXK@Z; pfna
  ... truncated ...
```
