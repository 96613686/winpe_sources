# CWordBreakerSelector::SelectWordBreaker(wchar_t const *,ulong,WORD_BREAKER_SELECTOR_INPUT_TYPE,ulong *,ulong *,SPECIAL_SCRIPTS_FOUND_FLAGS *,CHUNK_LOCALE_SOURCE *)

- ea: `0x18000c838`
- end: `0x18000d0c8`
- name: `?SelectWordBreaker@CWordBreakerSelector@@QEAAJPEB_WKW4WORD_BREAKER_SELECTOR_INPUT_TYPE@@PEAK2PEAW4SPECIAL_SCRIPTS_FOUND_FLAGS@@PEAW4CHUNK_LOCALE_SOURCE@@@Z`
- size: `2192`
- prototype: `int __high(const wchar_t *, unsigned int, enum WORD_BREAKER_SELECTOR_INPUT_TYPE, unsigned int *, unsigned int *, enum SPECIAL_SCRIPTS_FOUND_FLAGS *, enum CHUNK_LOCALE_SOURCE *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180062b80`

## callees

- `0x18000c6d0`
- `0x18000c760`
- `0x18000c838`
- `0x18000d15c`
- `0x18000d1b8`
- `0x18000d4a0`
- `0x18000d544`
- `0x18008f92c`
- `0x180099860`
- `0x1800a5e0c`
- `0x180102130`
- `0x1801244c0`
- `0x18012540e`
- `0x18012a044`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cf9a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cf9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d00a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d00a`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18000d0b8`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18000d0b8`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18000ccb2`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18000ccb2`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x18000cc9c`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x18000cc9c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ce2f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ce2f`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x18000c96d`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x18000c9f9`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x18000c96d`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x18000c9f9`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x18000ca5a`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x18000cdac`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x18000ca5a`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x18000cdac`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18000cfe4`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18000cfe4`

## pseudocode

```c
__int64 __fastcall CWordBreakerSelector::SelectWordBreaker(
        CWordBreakerSelector *a1,
        const WCHAR *a2,
        DWORD a3,
        int a4,
        unsigned int *a5,
        _DWORD *a6,
        const WCHAR *a7,
        int *a8)
{
  int v8; // edi
  const WCHAR *v9; // r12
  unsigned int *v10; // r13
  int *v11; // r14
  __int64 v12; // rsi
  unsigned int v13; // ebx
  __int64 v14; // r8
  __int64 v15; // rdi
  unsigned int v16; // r15d
  HRESULT Services; // r14d
  __int64 v18; // r8
  HRESULT v19; // eax
  PMAPPING_SERVICE_INFO *v20; // rdi
  unsigned int v21; // eax
  __int64 v22; // rcx
  int v23; // edi
  unsigned int v24; // r13d
  const WCHAR *v25; // r12
  unsigned int v26; // edi
  unsigned int v27; // r14d
  LCID v28; // ebx
  __int64 v29; // rax
  unsigned int v30; // ecx
  LCID TopSystemPreferredUILanguage; // eax
  _QWORD *v33; // r9
  unsigned __int64 i; // rcx
  const WCHAR *v35; // rcx
  LCID v36; // r14d
  unsigned int v37; // eax
  int v38; // edi
  unsigned int v39; // r14d
  __int64 v40; // r10
  _WORD *v41; // rcx
  __int64 v42; // r12
  int v43; // ecx
  int v44; // ecx
  CWordBreakerAllowList *v45; // r9
  __int64 v46; // rcx
  unsigned int v47; // edi
  int v48; // ecx
  WCHAR *pOptions; // [rsp+20h] [rbp-1E8h]
  char v50; // [rsp+30h] [rbp-1D8h]
  unsigned int v52; // [rsp+38h] [rbp-1D0h] BYREF
  unsigned int v53; // [rsp+40h] [rbp-1C8h]
  DWORD v54; // [rsp+48h] [rbp-1C0h] BYREF
  int *v55; // [rsp+50h] [rbp-1B8h]
  unsigned int v56; // [rsp+58h] [rbp-1B0h] BYREF
  unsigned int v57; // [rsp+5Ch] [rbp-1ACh]
  const WCHAR *v58; // [rsp+60h] [rbp-1A8h] BYREF
  unsigned int v59; // [rsp+68h] [rbp-1A0h]
  DWORD dwLength; // [rsp+6Ch] [rbp-19Ch]
  CWordBreakerSelector *v61; // [rsp+70h] [rbp-198h]
  const WCHAR *v62; // [rsp+78h] [rbp-190h] BYREF
  __int128 v63; // [rsp+80h] [rbp-188h] BYREF
  unsigned int *v64; // [rsp+90h] [rbp-178h]
  struct _MAPPING_ENUM_OPTIONS pBag; // [rsp+A0h] [rbp-168h] BYREF
  _QWORD v66[4]; // [rsp+F0h] [rbp-118h] BYREF
  WCHAR LocaleName[8]; // [rsp+110h] [rbp-F8h] BYREF
  DWORD *v68; // [rsp+120h] [rbp-E8h]
  __int64 v69; // [rsp+128h] [rbp-E0h]
  unsigned int *v70; // [rsp+130h] [rbp-D8h]
  __int64 v71; // [rsp+138h] [rbp-D0h]
  __int128 *v72; // [rsp+140h] [rbp-C8h]
  __int64 v73; // [rsp+148h] [rbp-C0h]
  const WCHAR **v74; // [rsp+150h] [rbp-B8h]
  __int64 v75; // [rsp+158h] [rbp-B0h]
  const WCHAR **v76; // [rsp+160h] [rbp-A8h]
  __int64 v77; // [rsp+168h] [rbp-A0h]
  void *retaddr; // [rsp+208h] [rbp+0h]

  v8 = a4;
  dwLength = a3;
  v9 = a2;
  v62 = a2;
  v61 = a1;
  v10 = a5;
  v64 = a5;
  v66[0] = a6;
  v58 = a7;
  v11 = a8;
  v55 = a8;
  v12 = 0;
  *a5 = 0;
  *a6 = 0;
  *(_DWORD *)a7 = 0;
  *a8 = 0;
  v59 = 0;
  CWordBreakerSelector::_InitializeConfidentLADScore(a1);
  v56 = 0;
  v13 = 0;
  v57 = 0;
  v54 = 0;
  v50 = 0;
  if ( !(unsigned __int8)IsMappingGetServicesPresent() )
    goto LABEL_23;
  v15 = *((_QWORD *)v61 + 3);
  *(_DWORD *)a7 = 0;
  v63 = xmmword_180267068;
  v16 = 0;
  Services = 0;
  if ( !*(_BYTE *)(v15 + 12) )
  {
    AcquireSRWLockExclusive(&s_srwElsServiceLock);
    if ( !*(_BYTE *)(v15 + 12) )
    {
      memset_0(&pBag, 0, sizeof(pBag));
      pBag.Size = 80;
      pBag.pGuid = (GUID *)&v63;
      Services = MappingGetServices(&pBag, (PMAPPING_SERVICE_INFO *)v15, (DWORD *)(v15 + 8));
      if ( Services >= 0 )
      {
        if ( *(_DWORD *)(v15 + 8) )
          *(_BYTE *)(v15 + 12) = 1;
        else
          Services = -2147467259;
      }
    }
    ReleaseSRWLockExclusive(&s_srwElsServiceLock);
  }
  v13 = 0;
  v53 = 0;
  if ( Services < 0 )
    goto LABEL_7;
  memset_0(&pBag, 0, 0x40u);
  pBag.Size = 64;
  v18 = -1;
  do
    ++v18;
  while ( v9[v18] );
  v19 = MappingRecognizeText(*(PMAPPING_SERVICE_INFO *)v15, v9, v18, 0, 0, (PMAPPING_PROPERTY_BAG)&pBag);
  v53 = 0;
  if ( v19 >= 0 )
  {
    if ( !LODWORD(pBag.pszInputLanguage) )
      goto LABEL_71;
    v38 = 0;
    v39 = 0;
    do
    {
      v40 = 9 * v12;
      *(_QWORD *)&v63 = 9 * v12;
      v41 = *(_WORD **)&pBag.pszCategory[36 * v12 + 12];
      if ( v41 && *v41 )
      {
        while ( 1 )
        {
          if ( v16 >= 0x22 )
          {
            if ( (*(_DWORD *)v58 & 0x2000000) == 0 )
            {
              *(_DWORD *)v58 |= 0x2000000u;
              ++v38;
            }
            goto LABEL_70;
          }
          v42 = 3LL * (int)v16;
          if ( CompareStringOrdinal(
                 *(LPCWCH *)&pBag.pszCategory[4 * v40 + 12],
                 -1,
                 (&off_180245300)[3 * (int)v16],
                 -1,
                 1) == 2 )
            break;
          ++v16;
          v40 = v63;
        }
        v44 = *((_DWORD *)&off_180245300 + 6 * (int)v16 + 2);
        if ( (*(_DWORD *)v58 & v44) != 0 )
        {
LABEL_70:
          v16 = 0;
          goto LABEL_57;
        }
        *(_DWORD *)v58 |= v44;
        ++v38;
        v16 = 0;
        if ( LODWORD((&off_180245300)[v42 + 1]) )
        {
          v39 = (unsigned int)(&off_180245300)[v42 + 1];
          if ( *((_BYTE *)&off_180245300 + 8 * v42 + 12) )
          {
            if ( !v13 )
              v13 = (unsigned int)(&off_180245300)[v42 + 1];
          }
        }
      }
LABEL_57:
      v12 = (unsigned int)(v12 + 1);
    }
    while ( (unsigned int)v12 < LODWORD(pBag.pszInputLanguage) );
    v53 = v13;
    LODWORD(v12) = v57;
    v9 = v62;
    if ( v38 == 1 )
      v56 = v39;
    else
LABEL_71:
      v53 = v13;
    MappingFreePropertyBag((PMAPPING_PROPERTY_BAG)&pBag);
    v8 = a4;
    v11 = v55;
    if ( v56 )
    {
      *a5 = v56;
      *v11 = (a4 != 0) + 101;
    }
  }
  else
  {
LABEL_7:
    v11 = v55;
    v8 = a4;
  }
  if ( *a5 )
    goto LABEL_101;
  if ( !(unsigned __int8)IsMappingGetServicesPresent() )
    goto LABEL_23;
  v20 = (PMAPPING_SERVICE_INFO *)*((_QWORD *)v61 + 4);
  CLanguageAutoDetection::Initialize((CLanguageAutoDetection *)v20);
  if ( !*(_BYTE *)v20 )
  {
LABEL_22:
    v8 = a4;
    goto LABEL_23;
  }
  memset_0(&pBag, 0, 0x40u);
  pBag.Size = 64;
  v21 = MappingRecognizeText(v20[1], v9, dwLength, 0, 0, (PMAPPING_PROPERTY_BAG)&pBag);
  v23 = v21;
  if ( v21 )
  {
    if ( byte_1802DA182 < 0 )
      McTemplateU0q_EventWriteTransfer(v22, &MSSearchTraceId_RobotThread_LangAutoDetection_Fail, v21);
    v27 = 0;
    if ( v23 >= 0 )
    {
      v30 = 0;
      goto LABEL_20;
    }
LABEL_21:
    v11 = v55;
    goto LABEL_22;
  }
  v52 = 0;
  v24 = 0;
  LODWORD(v12) = 0;
  v25 = (const WCHAR *)*((_QWORD *)pBag.pszCategory + 3);
  v26 = 0;
  v57 = 0;
  v27 = 0;
  v28 = 0;
  do
  {
    if ( !v25 )
      break;
    v29 = -1;
    do
      ++v29;
    while ( v25[v29] );
    if ( !v29 )
      break;
    v35 = v25;
    v58 = v25;
    v25 += v29 + 1;
    if ( ResolveLocaleName(v35, LocaleName, 85) > 0 )
    {
      v36 = LocaleNameToLCID(LocaleName, 0);
      if ( v36 == 4096 )
        v36 = 127;
      if ( LODWORD(pBag.pszInputScript) >> 2 > v26 )
      {
        v37 = *(_DWORD *)&pBag.pszOutputLanguage[2 * v26];
        v54 = v37;
        if ( !v26 )
        {
          if ( (byte_1802DA182 & 0x40) != 0 )
          {
            McTemplateU0z_EventWriteTransfer(0, &MSSearchTraceId_RobotThread_LangAutoDetection_Succeed, v58);
            v37 = v54;
          }
          LODWORD(v12) = v36;
          v52 = v37;
          goto LABEL_51;
        }
        v28 = v36;
        v24 = v37;
      }
    }
    v37 = v52;
LABEL_51:
    ++v26;
    v57 = v24;
    v27 = v37;
  }
  while ( v26 < 2 );
  MappingFreePropertyBag((PMAPPING_PROPERTY_BAG)&pBag);
  if ( (byte_1802DA182 & 0x40) != 0 )
  {
    LODWORD(v58) = v24;
    LODWORD(v62) = v28;
    LODWORD(v63) = v52;
    v52 = v12;
    v54 = dwLength;
    v68 = &v54;
    v69 = 4;
    v70 = &v52;
    v71 = 4;
    v72 = &v63;
    v73 = 4;
    v74 = &v62;
    v75 = 4;
    v76 = &v58;
    v77 = 4;
    pOptions = LocaleName;
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Search_Core_Context,
      &MSSearchTraceId_RobotThread_LangAutoDetection_Scores,
      v14,
      6);
  }
  v54 = v12;
  v13 = v53;
  v10 = v64;
  v30 = v57;
LABEL_20:
  if ( !(_DWORD)v12 )
    goto LABEL_21;
  *(_DWORD *)v66[0] = v12;
  v52 = 0;
  if ( v27 >= *((_DWORD *)v61 + 15) + v30 )
  {
    v50 = 1;
    v8 = a4;
    v43 = (a4 != 0) + 221;
LABEL_67:
    *v10 = v12;
    goto LABEL_68;
  }
  v50 = 0;
  v33 = (_QWORD *)*((_QWORD *)v61 + 1);
  if ( v33 )
  {
    for ( i = 0; i < (__int64)(v33[1] - *v33) >> 2; ++i )
    {
      if ( *(_DWORD *)(*v33 + 4 * i) == (_DWORD)v12 )
      {
        v8 = a4;
        v43 = (a4 != 0) + 231;
        goto LABEL_67;
      }
    }
  }
  if ( IsNonSpaceLanguageWithWordBreaker(v12) )
  {
    v8 = a4;
    v43 = (a4 != 0) + 241;
    goto LABEL_67;
  }
  if ( !v45 || !CWordBreakerAllowList::GetTopSubstituteLocale(v45, v12, &v52) )
    goto LABEL_21;
  v47 = v52;
  if ( (byte_1802DA182 & 0x40) != 0 )
    McTemplateU0qq_EventWriteTransfer(
      v46,
      &MSSearchTraceId_WordBreakerSelector_SubstituteLocale,
      (unsigned int)v12,
      v52,
      pOptions);
  *v10 = v47;
  v8 = a4;
  v43 = (a4 != 0) + 251;
LABEL_68:
  v11 = v55;
  *v55 = v43;
LABEL_23:
  if ( !*v10 )
  {
    if ( v13 )
    {
      *v10 = v13;
      if ( v13 == 127 )
        v48 = (v8 != 0) + 261;
      else
        v48 = (v8 != 0) + 271;
      *v11 = v48;
    }
    if ( !*v10 )
    {
      if ( (byte_1802DA182 & 0x40) != 0 )
      {
        LODWORD(v58) = v12;
        v66[2] = &v58;
        v66[3] = 4;
        McGenEventWrite_EventWriteTransfer(
          &Microsoft_Windows_Search_Core_Context,
          &MSSearchTraceId_WordBreakerSelector_Fallback,
          v14,
          2);
      }
      TopSystemPreferredUILanguage = CWordBreakerSelector::GetTopSystemPreferredUILanguage();
      if ( !TopSystemPreferredUILanguage )
        TopSystemPreferredUILanguage = GetSystemDefaultLCID();
      *v10 = TopSystemPreferredUILanguage;
      *v11 = (v8 != 0) + 301;
    }
  }
LABEL_101:
  try
  {
    if ( v56 )
    {
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<0,0>(
        (char *)v61 + 40,
        v66,
        &v56);
    }
    else if ( v50 )
    {
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<0,0>(
        (char *)v61 + 40,
        v66,
        &v54);
    }
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      749,
      "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\wbselect.cxx");
  }
  return v59;
}

```

## disassembly

```asm
0x18000c838  push    rbx
0x18000c83a  push    rsi
0x18000c83b  push    rdi
0x18000c83c  push    r12
0x18000c83e  push    r13
0x18000c840  push    r14
0x18000c842  push    r15
0x18000c844  sub     rsp, 1D0h
0x18000c84b  mov     rax, cs:__security_cookie
0x18000c852  xor     rax, rsp
0x18000c855  mov     [rsp+208h+var_48], rax
0x18000c85d  mov     edi, r9d
0x18000c860  mov     [rsp+208h+var_1D4], r9d
0x18000c865  mov     [rsp+208h+dwLength], r8d
0x18000c86a  mov     r12, rdx
0x18000c86d  mov     [rsp+208h+var_190], rdx
0x18000c872  mov     rax, rcx
0x18000c875  mov     [rsp+208h+var_198], rcx
0x18000c87a  mov     r13, [rsp+208h+arg_20]
0x18000c882  mov     [rsp+208h+var_178], r13
0x18000c88a  mov     rcx, [rsp+208h+arg_28]
0x18000c892  mov     [rsp+208h+var_118], rcx
0x18000c89a  mov     r15, [rsp+208h+arg_30]
0x18000c8a2  mov     [rsp+208h+var_1A8], r15
0x18000c8a7  mov     r14, [rsp+208h+arg_38]
0x18000c8af  mov     [rsp+208h+var_1B8], r14
0x18000c8b4  xor     esi, esi
0x18000c8b6  mov     [r13+0], esi
0x18000c8ba  mov     [rcx], esi
0x18000c8bc  mov     [r15], esi
0x18000c8bf  mov     [r14], esi
0x18000c8c2  mov     [rsp+208h+var_1A0], esi
0x18000c8c6  mov     rcx, rax; this
0x18000c8c9  call    ?_InitializeConfidentLADScore@CWordBreakerSelector@@AEAAXXZ; CWordBreakerSelector::_InitializeConfidentLADScore(void)
0x18000c8ce  mov     [rsp+208h+var_1B0], esi
0x18000c8d2  mov     ebx, esi
0x18000c8d4  mov     [rsp+208h+var_1AC], esi
0x18000c8d8  mov     [rsp+208h+var_1C0], esi
0x18000c8dc  mov     [rsp+208h+var_1D8], bl
0x18000c8e0  call    IsMappingGetServicesPresent
0x18000c8e5  test    al, al
0x18000c8e7  jz      loc_18000CE93
0x18000c8ed  mov     rdi, [rsp+208h+var_198]
0x18000c8f2  mov     rdi, [rdi+18h]
0x18000c8f6  mov     [r15], ebx
0x18000c8f9  movups  xmm0, cs:xmmword_180267068
0x18000c900  movdqu  [rsp+208h+var_188], xmm0
0x18000c909  xor     r15d, r15d
0x18000c90c  mov     r14d, r15d
0x18000c90f  cmp     [rdi+0Ch], r15b
0x18000c913  jz      loc_18000CF93
0x18000c919  mov     ebx, r15d
0x18000c91c  mov     [rsp+208h+var_1C8], ebx
0x18000c920  test    r14d, r14d
0x18000c923  js      short loc_18000C97F
0x18000c925  xor     edx, edx; Val
0x18000c927  lea     r8d, [rdx+40h]; Size
0x18000c92b  lea     rcx, [rsp+208h+pBag]; void *
0x18000c933  call    memset_0
0x18000c938  mov     [rsp+208h+pBag.Size], 40h ; '@'
0x18000c944  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000c948  inc     r8; dwLength
0x18000c94b  cmp     [r12+r8*2], r15w
0x18000c950  jnz     short loc_18000C948
0x18000c952  lea     rax, [rsp+208h+pBag]
0x18000c95a  mov     [rsp+208h+pbag], rax; pbag
0x18000c95f  mov     [rsp+208h+pOptions], r15; pOptions
0x18000c964  xor     r9d, r9d; dwIndex
0x18000c967  mov     rdx, r12; pszText
0x18000c96a  mov     rcx, [rdi]; pServiceInfo
0x18000c96d  call    cs:__imp_MappingRecognizeText
0x18000c973  mov     [rsp+208h+var_1C8], ebx
0x18000c977  test    eax, eax
0x18000c979  jns     loc_18000CD3B
0x18000c97f  mov     r14, [rsp+208h+var_1B8]
0x18000c984  mov     edi, [rsp+208h+var_1D4]
0x18000c988  cmp     [r13+0], r15d
0x18000c98c  jnz     loc_18000CBE0
0x18000c992  call    IsMappingGetServicesPresent
0x18000c997  test    al, al
0x18000c999  jz      loc_18000CE93
0x18000c99f  mov     rax, [rsp+208h+var_198]
0x18000c9a4  mov     rdi, [rax+20h]
0x18000c9a8  mov     rcx, rdi; this
0x18000c9ab  call    ?Initialize@CLanguageAutoDetection@@AEAA_NXZ; CLanguageAutoDetection::Initialize(void)
0x18000c9b0  cmp     [rdi], r15b
0x18000c9b3  jz      loc_18000CEA7
0x18000c9b9  xor     edx, edx; Val
0x18000c9bb  lea     r8d, [rdx+40h]; Size
0x18000c9bf  lea     rcx, [rsp+208h+pBag]; void *
0x18000c9c7  call    memset_0
0x18000c9cc  mov     [rsp+208h+pBag.Size], 40h ; '@'
0x18000c9d8  lea     rax, [rsp+208h+pBag]
0x18000c9e0  mov     [rsp+208h+pbag], rax; pbag
0x18000c9e5  mov     [rsp+208h+pOptions], r15; pOptions
0x18000c9ea  xor     r9d, r9d; dwIndex
0x18000c9ed  mov     r8d, [rsp+208h+dwLength]; dwLength
0x18000c9f2  mov     rdx, r12; pszText
0x18000c9f5  mov     rcx, [rdi+8]; pServiceInfo
0x18000c9f9  call    cs:__imp_MappingRecognizeText
0x18000c9ff  mov     edi, eax
0x18000ca01  test    eax, eax
0x18000ca03  jnz     loc_18000D03C
0x18000ca09  mov     [rsp+208h+var_1D0], r15d
0x18000ca0e  mov     r13d, r15d
0x18000ca11  mov     esi, r15d
0x18000ca14  mov     rax, [rsp+208h+pBag.prgResultRanges]
0x18000ca1c  mov     r12, [rax+18h]
0x18000ca20  mov     edi, r15d
0x18000ca23  mov     [rsp+208h+var_1AC], r15d
0x18000ca28  mov     r14d, r15d
0x18000ca2b  mov     r15d, 7Fh
0x18000ca31  mov     ebx, r14d
0x18000ca34  xor     ecx, ecx
0x18000ca36  test    r12, r12
0x18000ca39  jz      short loc_18000CA52
0x18000ca3b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ca3f  inc     rax
0x18000ca42  cmp     [r12+rax*2], cx
0x18000ca47  jnz     short loc_18000CA3F
0x18000ca49  test    rax, rax
0x18000ca4c  jnz     loc_18000CC7E
0x18000ca52  lea     rcx, [rsp+208h+pBag]; pBag
0x18000ca5a  call    cs:__imp_MappingFreePropertyBag
0x18000ca60  test    cs:byte_1802DA182, 40h
0x18000ca67  jz      loc_18000CB33
0x18000ca6d  mov     dword ptr [rsp+208h+var_1A8], r13d
0x18000ca72  mov     dword ptr [rsp+208h+var_190], ebx
0x18000ca76  mov     eax, [rsp+208h+var_1D0]
0x18000ca7a  mov     dword ptr [rsp+208h+var_188], eax
0x18000ca81  mov     [rsp+208h+var_1D0], esi
0x18000ca85  mov     eax, [rsp+208h+dwLength]
0x18000ca89  mov     [rsp+208h+var_1C0], eax
0x18000ca8d  lea     rax, [rsp+208h+var_1C0]
0x18000ca92  mov     [rsp+208h+var_E8], rax
0x18000ca9a  mov     [rsp+208h+var_E0], 4
0x18000caa6  lea     rax, [rsp+208h+var_1D0]
0x18000caab  mov     [rsp+208h+var_D8], rax
0x18000cab3  mov     [rsp+208h+var_D0], 4
0x18000cabf  lea     rax, [rsp+208h+var_188]
0x18000cac7  mov     [rsp+208h+var_C8], rax
0x18000cacf  mov     [rsp+208h+var_C0], 4
0x18000cadb  lea     rax, [rsp+208h+var_190]
0x18000cae0  mov     [rsp+208h+var_B8], rax
0x18000cae8  mov     [rsp+208h+var_B0], 4
0x18000caf4  lea     rax, [rsp+208h+var_1A8]
0x18000caf9  mov     [rsp+208h+var_A8], rax
0x18000cb01  mov     [rsp+208h+var_A0], 4
0x18000cb0d  lea     rax, [rsp+208h+LocaleName]
0x18000cb15  mov     [rsp+208h+pOptions], rax
0x18000cb1a  mov     r9d, 6
0x18000cb20  lea     rdx, MSSearchTraceId_RobotThread_LangAutoDetection_Scores
0x18000cb27  lea     rcx, Microsoft_Windows_Search_Core_Context
0x18000cb2e  call    McGenEventWrite_EventWriteTransfer
0x18000cb33  mov     [rsp+208h+var_1C0], esi
0x18000cb37  mov     ebx, [rsp+208h+var_1C8]
0x18000cb3b  mov     r13, [rsp+208h+var_178]
0x18000cb43  mov     ecx, [rsp+208h+var_1AC]
0x18000cb47  xor     edi, edi
0x18000cb49  test    esi, esi
0x18000cb4b  jnz     loc_18000CC1D
0x18000cb51  mov     r14, [rsp+208h+var_1B8]
0x18000cb56  mov     edi, [rsp+208h+var_1D4]
0x18000cb5a  xor     eax, eax
0x18000cb5c  cmp     [r13+0], eax
0x18000cb60  jnz     loc_18000CC76
0x18000cb66  test    ebx, ebx
0x18000cb68  jnz     loc_18000D08B
0x18000cb6e  xor     r15d, r15d
0x18000cb71  cmp     [r13+0], r15d
0x18000cb75  jnz     short loc_18000CBE0
0x18000cb77  test    cs:byte_1802DA182, 40h
0x18000cb7e  jz      short loc_18000CBC1
0x18000cb80  mov     dword ptr [rsp+208h+var_1A8], esi
0x18000cb84  lea     rax, [rsp+208h+var_1A8]
0x18000cb89  mov     [rsp+208h+var_108], rax
0x18000cb91  mov     [rsp+208h+var_100], 4
0x18000cb9d  lea     rax, [rsp+208h+var_118]
0x18000cba5  mov     [rsp+208h+pOptions], rax
0x18000cbaa  lea     r9d, [r15+2]
0x18000cbae  lea     rdx, MSSearchTraceId_WordBreakerSelector_Fallback
0x18000cbb5  lea     rcx, Microsoft_Windows_Search_Core_Context
0x18000cbbc  call    McGenEventWrite_EventWriteTransfer
0x18000cbc1  call    ?GetTopSystemPreferredUILanguage@CWordBreakerSelector@@SAKXZ; CWordBreakerSelector::GetTopSystemPreferredUILanguage(void)
0x18000cbc6  test    eax, eax
0x18000cbc8  jz      loc_18000D0B8
0x18000cbce  mov     [r13+0], eax
0x18000cbd2  neg     edi
0x18000cbd4  sbb     eax, eax
0x18000cbd6  neg     eax
0x18000cbd8  add     eax, 12Dh
0x18000cbdd  mov     [r14], eax
0x18000cbe0  cmp     [rsp+208h+var_1B0], r15d
0x18000cbe5  jnz     loc_18000CDDE
0x18000cbeb  cmp     [rsp+208h+var_1D8], r15b
0x18000cbf0  jnz     loc_18000CF4F
0x18000cbf6  mov     eax, [rsp+208h+var_1A0]
0x18000cbfa  mov     rcx, [rsp+208h+var_48]
0x18000cc02  xor     rcx, rsp; StackCookie
0x18000cc05  call    __security_check_cookie
0x18000cc0a  add     rsp, 1D0h
0x18000cc11  pop     r15
0x18000cc13  pop     r14
0x18000cc15  pop     r13
0x18000cc17  pop     r12
0x18000cc19  pop     rdi
0x18000cc1a  pop     rsi
0x18000cc1b  pop     rbx
0x18000cc1c  retn
0x18000cc1d  mov     rax, [rsp+208h+var_118]
0x18000cc25  mov     [rax], esi
0x18000cc27  mov     [rsp+208h+var_1D0], edi
0x18000cc2b  mov     rdx, [rsp+208h+var_198]
0x18000cc30  add     ecx, [rdx+3Ch]
0x18000cc33  cmp     r14d, ecx
0x18000cc36  jnb     loc_18000CE4E
0x18000cc3c  mov     [rsp+208h+var_1D8], dil
0x18000cc41  mov     r9, [rdx+8]
0x18000cc45  test    r9, r9
0x18000cc48  jz      loc_18000CEB2
0x18000cc4e  mov     rcx, rdi
0x18000cc51  mov     rdx, [r9]
0x18000cc54  mov     rax, [r9+8]
0x18000cc58  sub     rax, rdx
0x18000cc5b  sar     rax, 2
0x18000cc5f  cmp     rcx, rax
0x18000cc62  jnb     loc_18000CEB2
0x18000cc68  cmp     [rdx+rcx*4], esi
0x18000cc6b  jz      loc_18000D05D
0x18000cc71  inc     rcx
0x18000cc74  jmp     short loc_18000CC5F
0x18000cc76  xor     r15d, r15d
0x18000cc79  jmp     loc_18000CBE0
0x18000cc7e  mov     rcx, r12; lpNameToResolve
0x18000cc81  mov     [rsp+208h+var_1A8], rcx
0x18000cc86  lea     r12, [r12+rax*2]
0x18000cc8a  add     r12, 2
0x18000cc8e  mov     r8d, 55h ; 'U'; cchLocaleName
0x18000cc94  lea     rdx, [rsp+208h+LocaleName]; lpLocaleName
0x18000cc9c  call    cs:__imp_ResolveLocaleName
0x18000cca2  xor     ecx, ecx
0x18000cca4  test    eax, eax
0x18000cca6  jle     short loc_18000CD1F
0x18000cca8  xor     edx, edx; dwFlags
0x18000ccaa  lea     rcx, [rsp+208h+LocaleName]; lpName
0x18000ccb2  call    cs:__imp_LocaleNameToLCID
0x18000ccb8  mov     r14d, eax
0x18000ccbb  cmp     eax, 1000h
0x18000ccc0  cmovz   r14d, r15d
0x18000ccc4  mov     ecx, [rsp+208h+pBag.dwServiceDataSize]
0x18000cccb  shr     ecx, 2
0x18000ccce  cmp     ecx, edi
0x18000ccd0  jbe     loc_18000D035
0x18000ccd6  mov     edx, edi
0x18000ccd8  mov     rcx, [rsp+208h+pBag.pServiceData]
0x18000cce0  mov     eax, [rcx+rdx*4]
0x18000cce3  mov     [rsp+208h+var_1C0], eax
0x18000cce7  xor     ecx, ecx
0x18000cce9  test    edi, edi
0x18000cceb  jnz     short loc_18000CD16
0x18000cced  test    cs:byte_1802DA182, 40h
0x18000ccf4  jz      short loc_18000CD0D
0x18000ccf6  mov     r8, [rsp+208h+var_1A8]
0x18000ccfb  lea     rdx, MSSearchTraceId_RobotThread_LangAutoDetection_Succeed
0x18000cd02  call    McTemplateU0z_EventWriteTransfer
0x18000cd07  mov     eax, [rsp+208h+var_1C0]
0x18000cd0b  xor     ecx, ecx
0x18000cd0d  mov     esi, r14d
0x18000cd10  mov     [rsp+208h+var_1D0], eax
0x18000cd14  jmp     short loc_18000CD23
0x18000cd16  cmp     edi, 1
0x18000cd19  jz      loc_18000CF6F
0x18000cd1f  mov     eax, [rsp+208h+var_1D0]
0x18000cd23  inc     edi
0x18000cd25  mov     [rsp+208h+var_1AC], r13d
0x18000cd2a  mov     r14d, eax
0x18000cd2d  cmp     edi, 2
0x18000cd30  jb      loc_18000CA36
0x18000cd36  jmp     loc_18000CA52
0x18000cd3b  cmp     [rsp+208h+pBag.dwRangesCount], r15d
0x18000cd43  jbe     loc_18000CE9E
0x18000cd49  mov     edi, r15d
0x18000cd4c  mov     r14d, r15d
0x18000cd4f  lea     rdx, off_180245300; "Hira"
0x18000cd56  lea     r10, [rsi+rsi*8]
0x18000cd5a  mov     qword ptr [rsp+208h+var_188], r10
0x18000cd62  mov     rax, [rsp+208h+pBag.prgResultRanges]
0x18000cd6a  mov     rcx, [rax+r10*8+18h]
0x18000cd6f  test    rcx, rcx
0x18000cd72  jz      short loc_18000CD7E
0x18000cd74  cmp     [rcx], r15w
0x18000cd78  jnz     loc_18000CDFE
0x18000cd7e  inc     esi
0x18000cd80  cmp     esi, [rsp+208h+pBag.dwRangesCount]
0x18000cd87  jb      short loc_18000CD56
0x18000cd89  mov     [rsp+208h+var_1C8], ebx
0x18000cd8d  cmp     edi, 1
0x18000cd90  mov     esi, [rsp+208h+var_1AC]
0x18000cd94  mov     r12, [rsp+208h+var_190]
0x18000cd99  jnz     loc_18000CE9E
  ... truncated ...
```
