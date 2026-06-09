# Microsoft::Resources::Runtime::CResourceManagerInternal::LoadPriFiles(Microsoft::Resources::_MRMPROFILE_PHASE,Microsoft::Resources::LoadPriFlags,Microsoft::Resources::DynamicArray<Microsoft::Resources::StringResult *> *,Microsoft::Resources::DynamicArray<Microsoft::Resources::StringResult *> *,Microsoft::Resources::DynamicArray<Microsoft::Resources::StringResult *> *)

- ea: `0x180014284`
- end: `0x180014a47`
- name: `?LoadPriFiles@CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAJW4_MRMPROFILE_PHASE@34@W4LoadPriFlags@34@PEAV?$DynamicArray@PEAVStringResult@Resources@Microsoft@@@34@22@Z`
- size: `1987`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, Microsoft::Resources *)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180015944`
- `0x180059180`

## callees

- `0x18000fda8`
- `0x180012c78`
- `0x180012eac`
- `0x1800130e0`
- `0x180014284`
- `0x180017960`
- `0x18001d734`
- `0x180028510`
- `0x180028ad0`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x18002ec70`
- `0x1800325c0`
- `0x18003760c`
- `0x180037a7c`
- `0x180065ac8`
- `0x1800739f4`
- `0x180083ad4`
- `0x1800a4688`
- `0x1800a94b8`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800142b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800142b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800143b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014565`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800145f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014839`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014874`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800148c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800143b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014565`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800145f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014839`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014874`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800148c2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014653`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014653`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Resources::Runtime::CResourceManagerInternal::LoadPriFiles(
        __int64 a1,
        unsigned int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        Microsoft::Resources *a6)
{
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  int v10; // eax
  __int64 v11; // r15
  Microsoft::Resources *v12; // rcx
  __int64 i; // rsi
  Microsoft::Resources *v14; // rcx
  int PriFiles; // ebx
  __int64 v16; // rsi
  _DWORD *v17; // rdx
  __int64 v18; // r14
  unsigned int j; // esi
  Microsoft::Resources::UnifiedResourceView::PriFileInfo *v20; // rcx
  unsigned int v21; // r12d
  Microsoft::Resources *v22; // rax
  Microsoft::Resources::StringResult *v24; // rbx
  const unsigned __int16 *Ref; // rax
  int v26; // eax
  __int64 v27; // r14
  const unsigned __int16 *v28; // rdx
  unsigned int v29; // eax
  Microsoft::Resources::StringResult *v30; // rcx
  bool v31; // r9
  int v32; // r8d
  const struct Microsoft::Resources::ManagedResourceMap *v33; // rdx
  __int64 v34; // r8
  const WCHAR *v35; // r15
  Microsoft::Resources::StringResult *v36; // rcx
  const unsigned __int16 *v37; // rax
  bool v38; // r8
  const unsigned __int16 *v39; // r9
  int v40; // eax
  unsigned int v41; // r14d
  __int64 v42; // rax
  const WCHAR *v43; // r14
  int v44; // eax
  int v45; // eax
  int v46; // eax
  __int64 v47; // rax
  int v48; // ecx
  __int64 v49; // r8
  __int64 v50; // rax
  int v51; // ecx
  __int64 v52; // rdx
  __int64 v53; // rdx
  _DWORD *v54; // rax
  __int64 v55; // rdx
  _DWORD *v56; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-60h]
  int bIgnoreCasea; // [rsp+20h] [rbp-60h]
  const unsigned __int16 *bIgnoreCaseb; // [rsp+20h] [rbp-60h]
  int *p_lpMem; // [rsp+28h] [rbp-58h]
  struct _RTL_CRITICAL_SECTION *v61; // [rsp+30h] [rbp-50h] BYREF
  struct Microsoft::Resources::ManagedResourceMap *v62; // [rsp+38h] [rbp-48h] BYREF
  _BYTE *v63; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v64[24]; // [rsp+48h] [rbp-38h] BYREF
  _BYTE *v65; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v66[24]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  void *lpMem; // [rsp+D8h] [rbp+58h] BYREF

  v9 = (struct _RTL_CRITICAL_SECTION *)(a1 + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v61 = v9;
  if ( !a4 || (v10 = *(_DWORD *)(a4 + 12)) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25B,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v61);
    return 2147942487LL;
  }
  v11 = a5;
  if ( a5 && v10 != *(_DWORD *)(a5 + 12) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25C,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v61);
    return 2147942487LL;
  }
  v12 = a6;
  if ( a6 && v10 != *((_DWORD *)a6 + 3) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25D,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v61);
    return 2147942487LL;
  }
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a4 + 12); i = (unsigned int)(i + 1) )
  {
    v24 = *(Microsoft::Resources::StringResult **)(*(_QWORD *)a4 + 8 * i);
    if ( (!v24
       || !Microsoft::Resources::StringResult::GetRef(*(Microsoft::Resources::StringResult **)(*(_QWORD *)a4 + 8 * i)))
      && !Microsoft::Resources::InShutdownOrLogoff(v12)
      && (!v24 || !Microsoft::Resources::StringResult::GetRef(v24)) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    Ref = Microsoft::Resources::StringResult::GetRef(v24);
    v26 = Microsoft::Resources::Runtime::CResourceManagerInternal::VerifyPathWithPackagesInfo(a1, Ref, a2);
    PriFiles = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x265,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
        (const char *)(unsigned int)v26,
        bIgnoreCase);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v61);
      return (unsigned int)PriFiles;
    }
  }
  lpMem = 0;
  p_lpMem = (int *)&lpMem;
  bIgnoreCasea = a3;
  PriFiles = Microsoft::Resources::UnifiedResourceView::LoadPriFiles(*(_QWORD **)(a1 + 184), 0, a2, a4);
  if ( PriFiles < 0 )
  {
    if ( lpMem && !Microsoft::Resources::InShutdownOrLogoff(v14) && lpMem )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( PriFiles == -2147024894 )
      Microsoft::Resources::Runtime::CResourceManagerInternal::_TryAddEmptyResourceIndex((struct Microsoft::Resources::Runtime::CResourceManagerInternal *)a1);
  }
  else
  {
    v16 = 0;
    v17 = lpMem;
    while ( (unsigned int)v16 < v17[3] )
    {
      v27 = *(_QWORD *)(*(_QWORD *)v17 + 8 * v16);
      if ( !v27 )
      {
        if ( !Microsoft::Resources::InShutdownOrLogoff(v14) )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v17 = lpMem;
      }
      if ( *(_QWORD *)(v27 + 88) )
      {
        v28 = 0;
        if ( v11 )
        {
          v29 = *(_DWORD *)(v27 + 76);
          if ( *(_DWORD *)(v11 + 12) > v29 )
          {
            v30 = *(Microsoft::Resources::StringResult **)(*(_QWORD *)v11 + 8LL * v29);
            if ( v30 )
              v28 = Microsoft::Resources::StringResult::GetRef(v30);
          }
        }
        v31 = a2 == 3 || *(_BYTE *)(v27 + 81);
        bIgnoreCaseb = v28;
        v32 = *(_DWORD *)(v27 + 72);
        v33 = *(const struct Microsoft::Resources::ManagedResourceMap **)(v27 + 88);
        v18 = a1;
        PriFiles = Microsoft::Resources::Runtime::CResourceManagerInternal::_AddOrUpdateResourceIndex(
                     (Microsoft::Resources::Runtime::CResourceManagerInternal *)a1,
                     v33,
                     v32,
                     v31,
                     bIgnoreCaseb);
        v17 = lpMem;
        if ( PriFiles < 0 )
          goto LABEL_11;
        v16 = (unsigned int)(v16 + 1);
      }
      else
      {
        v16 = (unsigned int)(v16 + 1);
      }
    }
    v18 = a1;
LABEL_11:
    for ( j = 0; j < v17[3]; ++j )
    {
      v20 = *(Microsoft::Resources::UnifiedResourceView::PriFileInfo **)(*(_QWORD *)v17 + 8LL * j);
      if ( v20 )
      {
        Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v20, (unsigned int)v17);
        v17 = lpMem;
      }
    }
    if ( v17 )
      Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::`scalar deleting destructor'(v17);
    lpMem = 0;
    v21 = 0;
    v22 = a6;
    if ( a6 )
    {
      while ( v21 < *((_DWORD *)v22 + 3) )
      {
        v35 = Microsoft::Resources::StringResult::GetRef(*(Microsoft::Resources::StringResult **)(*(_QWORD *)v22
                                                                                                + 8LL * v21));
        if ( v35 )
        {
          v36 = 0;
          if ( v21 < *(_DWORD *)(a4 + 12) )
            v36 = *(Microsoft::Resources::StringResult **)(*(_QWORD *)a4 + 8 * v34);
          v62 = 0;
          v37 = Microsoft::Resources::StringResult::GetRef(v36);
          v40 = Microsoft::Resources::UnifiedResourceView::GetOrAddReferencedFile(
                  *(Microsoft::Resources::UnifiedResourceView **)(v18 + 184),
                  v37,
                  v38,
                  v39,
                  &v62,
                  p_lpMem);
          v41 = v40;
          if ( v40 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2A1,
              (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
              (const char *)(unsigned int)v40,
              bIgnoreCasea);
            if ( v9 )
              LeaveCriticalSection(v9);
            return v41;
          }
          if ( v62 )
          {
            v42 = (*(__int64 (__fastcall **)(struct Microsoft::Resources::ManagedResourceMap *))(*(_QWORD *)v62 + 8LL))(v62);
            v43 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
            v44 = CompareStringOrdinal(v35, -1, v43, -1, 1);
            if ( (unsigned int)IntToComparison((unsigned int)(v44 - 2)) )
            {
              DefStringResult_InitBuf(v64);
              v63 = v64;
              v45 = DefStringResult_SetCopy(v64, v43);
              v41 = v45;
              if ( v45 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2AB,
                  (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
                  (const char *)(unsigned int)v45,
                  bIgnoreCasea);
                Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v63);
                wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v61);
                return v41;
              }
              DefStringResult_InitBuf(v66);
              v65 = v66;
              v46 = DefStringResult_SetCopy(v66, v35);
              v41 = v46;
              if ( v46 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2AD,
                  (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
                  (const char *)(unsigned int)v46,
                  bIgnoreCasea);
                Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v65);
                Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v63);
                if ( v9 )
                  LeaveCriticalSection(v9);
                return v41;
              }
              if ( v63 && (*(_QWORD *)v63 || !*((_DWORD *)v63 + 2)) && (*((_DWORD *)v63 + 2) || !*(_QWORD *)v63) )
              {
                v47 = *((_QWORD *)v63 + 2);
                v48 = 0;
              }
              else
              {
                v47 = 0;
                v48 = -2147024809;
              }
              v49 = 0;
              if ( v48 >= 0 )
                v49 = v47;
              if ( v65 && (*(_QWORD *)v65 || !*((_DWORD *)v65 + 2)) && (*((_DWORD *)v65 + 2) || !*(_QWORD *)v65) )
              {
                v50 = *((_QWORD *)v65 + 2);
                v51 = 0;
              }
              else
              {
                v50 = 0;
                v51 = -2147024809;
              }
              v52 = 0;
              if ( v51 >= 0 )
                v52 = v50;
              v41 = Microsoft::Resources::Runtime::MrtMap<unsigned short const *,unsigned short const *,Microsoft::Resources::Runtime::Equal<unsigned short const *>>::Insert(
                      a1 + 136,
                      v52,
                      v49);
              if ( v41 == -2147024713 )
              {
                wil::details::in1diag3::Log_Hr(
                  retaddr,
                  (void *)0x2B4,
                  (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
                  (const char *)0x800700B7LL,
                  bIgnoreCasea);
              }
              else
              {
                if ( (v41 & 0x80000000) != 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2B7,
                    (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
                    (const char *)v41,
                    bIgnoreCasea);
                  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v65);
                  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v63);
                  if ( v9 )
                    LeaveCriticalSection(v9);
                  return v41;
                }
                if ( v63 )
                {
                  v53 = *(_QWORD *)v63;
                  v54 = v63 + 8;
                  if ( (*(_QWORD *)v63 || !*v54) && (*v54 || !v53) && v53 && *v54 )
                    DefStringResult_InitEmpty();
                }
                if ( v65 )
                {
                  v55 = *(_QWORD *)v65;
                  v56 = v65 + 8;
                  if ( (*(_QWORD *)v65 || !*v56) && (*v56 || !v55) && v55 && *v56 )
                    DefStringResult_InitEmpty();
                }
              }
              Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v65);
              Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v63);
            }
          }
        }
        ++v21;
        v18 = a1;
        v22 = a6;
      }
    }
  }
  if ( (a3 & 2) != 0 )
  {
    if ( PriFiles < 0 )
    {
      if ( (unsigned int)(PriFiles + 2147024894) > 1 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2E8,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
          (const char *)(unsigned int)PriFiles,
          bIgnoreCasea);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v61);
      }
      else if ( v9 )
      {
        LeaveCriticalSection(v9);
      }
      return (unsigned int)PriFiles;
    }
    goto LABEL_20;
  }
  if ( PriFiles >= 0 )
  {
LABEL_20:
    if ( v9 )
      LeaveCriticalSection(v9);
    return 0;
  }
  if ( PriFiles != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EC,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
      (const char *)(unsigned int)PriFiles,
      bIgnoreCasea);
    if ( v9 )
      LeaveCriticalSection(v9);
    return (unsigned int)PriFiles;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v61);
  return 2147942402LL;
}

```

## disassembly

```asm
0x180014284  mov     [rsp-38h+arg_8], rbx
0x180014289  mov     [rsp-38h+arg_10], r8d
0x18001428e  mov     [rsp-38h+arg_0], rcx
0x180014293  push    rbp
0x180014294  push    rsi
0x180014295  push    rdi
0x180014296  push    r12
0x180014298  push    r13
0x18001429a  push    r14
0x18001429c  push    r15
0x18001429e  mov     rbp, rsp
0x1800142a1  sub     rsp, 80h
0x1800142a8  mov     r13, r9
0x1800142ab  mov     r12d, edx
0x1800142ae  mov     r14, rcx
0x1800142b1  lea     rdi, [rcx+30h]
0x1800142b5  mov     rcx, rdi; lpCriticalSection
0x1800142b8  call    cs:__imp_EnterCriticalSection
0x1800142be  mov     [rbp+var_50], rdi
0x1800142c2  test    r13, r13
0x1800142c5  jz      loc_180014452
0x1800142cb  mov     eax, [r13+0Ch]
0x1800142cf  test    eax, eax
0x1800142d1  jz      loc_180014452
0x1800142d7  mov     r15, [rbp+arg_20]
0x1800142db  test    r15, r15
0x1800142de  jnz     loc_18001441E
0x1800142e4  mov     rcx, [rbp+arg_28]; this
0x1800142e8  test    rcx, rcx
0x1800142eb  jnz     loc_180014800
0x1800142f1  xor     esi, esi
0x1800142f3  cmp     esi, [r13+0Ch]
0x1800142f7  jb      loc_1800143D5
0x1800142fd  mov     [rbp+lpMem], 0
0x180014305  lea     rax, [rbp+lpMem]
0x180014309  mov     [rsp+80h+var_58], rax; int *
0x18001430e  mov     eax, [rbp+arg_10]
0x180014311  mov     [rsp+80h+bIgnoreCase], eax; int
0x180014315  mov     r9, r13
0x180014318  mov     r8d, r12d
0x18001431b  xor     edx, edx
0x18001431d  mov     rcx, [r14+0B8h]
0x180014324  call    ?LoadPriFiles@UnifiedResourceView@Resources@Microsoft@@QEAAJ_NW4_MRMPROFILE_PHASE@23@PEAV?$DynamicArray@PEAVStringResult@Resources@Microsoft@@@23@W4LoadPriFlags@23@PEAPEAV?$DynamicArray@PEAVPriFileInfo@UnifiedResourceView@Resources@Microsoft@@@23@@Z; Microsoft::Resources::UnifiedResourceView::LoadPriFiles(bool,Microsoft::Resources::_MRMPROFILE_PHASE,Microsoft::Resources::DynamicArray<Microsoft::Resources::StringResult *> *,Microsoft::Resources::LoadPriFlags,Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedResourceView::PriFileInfo *> * *)
0x180014329  mov     ebx, eax
0x18001432b  test    eax, eax
0x18001432d  js      loc_180014505
0x180014333  xor     esi, esi
0x180014335  mov     rdx, [rbp+lpMem]; unsigned int
0x180014339  cmp     esi, [rdx+0Ch]
0x18001433c  jb      loc_180014481
0x180014342  mov     r14, [rbp+arg_0]
0x180014346  xor     r15d, r15d
0x180014349  mov     esi, r15d
0x18001434c  cmp     [rdx+0Ch], r15d
0x180014350  jbe     short loc_180014376
0x180014352  cmp     r15d, [rdx+0Ch]
0x180014356  jnb     short loc_18001436F
0x180014358  mov     ecx, esi
0x18001435a  mov     rax, [rdx]
0x18001435d  mov     rcx, [rax+rcx*8]; this
0x180014361  test    rcx, rcx
0x180014364  jz      short loc_18001436F
0x180014366  call    ??_GPriFileInfo@UnifiedResourceView@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(uint)
0x18001436b  mov     rdx, [rbp+lpMem]
0x18001436f  inc     esi
0x180014371  cmp     esi, [rdx+0Ch]
0x180014374  jb      short loc_180014358
0x180014376  test    rdx, rdx
0x180014379  jz      short loc_180014383
0x18001437b  mov     rcx, rdx; lpMem
0x18001437e  call    ??_G?$DynamicArray@PEAVManagedSchema@Resources@Microsoft@@@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::`scalar deleting destructor'(uint)
0x180014383  mov     [rbp+lpMem], r15
0x180014387  mov     r12d, r15d
0x18001438a  mov     rax, [rbp+arg_28]
0x18001438e  test    rax, rax
0x180014391  jnz     loc_180014571
0x180014397  test    byte ptr [rbp+arg_10], 2
0x18001439b  jnz     loc_180014546
0x1800143a1  test    ebx, ebx
0x1800143a3  js      loc_1800147CF
0x1800143a9  test    rdi, rdi
0x1800143ac  jz      short loc_1800143B8
0x1800143ae  mov     rcx, rdi; lpCriticalSection
0x1800143b1  call    cs:__imp_LeaveCriticalSection
0x1800143b7  nop
0x1800143b8  xor     eax, eax
0x1800143ba  mov     rbx, [rsp+80h+arg_8]
0x1800143c2  add     rsp, 80h
0x1800143c9  pop     r15
0x1800143cb  pop     r14
0x1800143cd  pop     r13
0x1800143cf  pop     r12
0x1800143d1  pop     rdi
0x1800143d2  pop     rsi
0x1800143d3  pop     rbp
0x1800143d4  retn
0x1800143d5  mov     rax, [r13+0]
0x1800143d9  mov     rbx, [rax+rsi*8]
0x1800143dd  test    rbx, rbx
0x1800143e0  jz      loc_1800148E2
0x1800143e6  mov     rcx, rbx; this
0x1800143e9  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x1800143ee  test    rax, rax
0x1800143f1  jz      loc_1800148E2
0x1800143f7  mov     rcx, rbx; this
0x1800143fa  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x1800143ff  mov     rdx, rax
0x180014402  mov     r8d, r12d
0x180014405  mov     rcx, r14
0x180014408  call    ?VerifyPathWithPackagesInfo@CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAJPEBGW4_MRMPROFILE_PHASE@34@@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::VerifyPathWithPackagesInfo(ushort const *,Microsoft::Resources::_MRMPROFILE_PHASE)
0x18001440d  mov     ebx, eax
0x18001440f  test    eax, eax
0x180014411  js      loc_18001490E
0x180014417  inc     esi
0x180014419  jmp     loc_1800142F3
0x18001441e  cmp     eax, [r15+0Ch]
0x180014422  jz      loc_1800142E4
0x180014428  mov     rcx, [rbp+38h]; this
0x18001442c  mov     esi, 80070057h
0x180014431  mov     r9d, esi; char *
0x180014434  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x18001443b  mov     edx, 25Ch; void *
0x180014440  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014445  nop
0x180014446  lea     rcx, [rbp+var_50]
0x18001444a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001444f  nop
0x180014450  jmp     short loc_18001447A
0x180014452  mov     rcx, [rbp+38h]; this
0x180014456  mov     esi, 80070057h
0x18001445b  mov     r9d, esi; char *
0x18001445e  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180014465  mov     edx, 25Bh; void *
0x18001446a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001446f  nop
0x180014470  lea     rcx, [rbp+var_50]
0x180014474  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180014479  nop
0x18001447a  mov     eax, esi
0x18001447c  jmp     loc_1800143BA
0x180014481  mov     rax, [rdx]
0x180014484  mov     r14, [rax+rsi*8]
0x180014488  test    r14, r14
0x18001448b  jz      loc_180014936
0x180014491  cmp     qword ptr [r14+58h], 0
0x180014496  jz      loc_180014880
0x18001449c  xor     edx, edx
0x18001449e  test    r15, r15
0x1800144a1  jz      short loc_1800144C3
0x1800144a3  mov     eax, [r14+4Ch]
0x1800144a7  cmp     [r15+0Ch], eax
0x1800144ab  jbe     short loc_1800144C3
0x1800144ad  mov     ecx, eax
0x1800144af  mov     rax, [r15]
0x1800144b2  mov     rcx, [rax+rcx*8]; this
0x1800144b6  test    rcx, rcx
0x1800144b9  jz      short loc_1800144C3
0x1800144bb  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x1800144c0  mov     rdx, rax
0x1800144c3  cmp     r12d, 3
0x1800144c7  jz      short loc_1800144D4
0x1800144c9  cmp     byte ptr [r14+51h], 0
0x1800144ce  jz      loc_180014607
0x1800144d4  mov     r9b, 1; bool
0x1800144d7  mov     qword ptr [rsp+80h+bIgnoreCase], rdx; unsigned __int16 *
0x1800144dc  mov     r8d, [r14+48h]; int
0x1800144e0  mov     rdx, [r14+58h]; struct Microsoft::Resources::ManagedResourceMap *
0x1800144e4  mov     r14, [rbp+arg_0]
0x1800144e8  mov     rcx, r14; this
0x1800144eb  call    ?_AddOrUpdateResourceIndex@CResourceManagerInternal@Runtime@Resources@Microsoft@@AEAAJPEBVManagedResourceMap@34@H_NPEBG@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::_AddOrUpdateResourceIndex(Microsoft::Resources::ManagedResourceMap const *,int,bool,ushort const *)
0x1800144f0  mov     ebx, eax
0x1800144f2  mov     rdx, [rbp+lpMem]
0x1800144f6  test    eax, eax
0x1800144f8  js      loc_180014346
0x1800144fe  inc     esi
0x180014500  jmp     loc_180014339
0x180014505  xor     r15d, r15d
0x180014508  cmp     [rbp+lpMem], r15
0x18001450c  jnz     loc_1800149EA
0x180014512  cmp     ebx, 80070002h
0x180014518  jnz     loc_180014397
0x18001451e  mov     byte ptr [rbp+arg_0], r15b
0x180014522  lea     r8, [rbp+arg_0]
0x180014526  mov     rdx, r13
0x180014529  mov     rcx, r14; struct Microsoft::Resources::Runtime::CResourceManagerInternal *
0x18001452c  call    ?_TryAddEmptyResourceIndex@CResourceManagerInternal@Runtime@Resources@Microsoft@@AEAAJPEAV?$DynamicArray@PEAVStringResult@Resources@Microsoft@@@34@PEA_N@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::_TryAddEmptyResourceIndex(Microsoft::Resources::DynamicArray<Microsoft::Resources::StringResult *> *,bool *)
0x180014531  test    eax, eax
0x180014533  js      loc_180014397
0x180014539  cmp     byte ptr [rbp+arg_0], r15b
0x18001453d  cmovnz  ebx, r15d
0x180014541  jmp     loc_180014397
0x180014546  test    ebx, ebx
0x180014548  jns     loc_1800143A9
0x18001454e  lea     eax, [rbx+7FF8FFFEh]
0x180014554  cmp     eax, 1
0x180014557  ja      loc_180014A0B
0x18001455d  test    rdi, rdi
0x180014560  jz      short loc_18001456C
0x180014562  mov     rcx, rdi; lpCriticalSection
0x180014565  call    cs:__imp_LeaveCriticalSection
0x18001456b  nop
0x18001456c  jmp     loc_1800147F9
0x180014571  mov     esi, 80070057h
0x180014576  cmp     r12d, [rax+0Ch]
0x18001457a  jnb     loc_180014397
0x180014580  mov     r8d, r12d
0x180014583  mov     rcx, [rax]
0x180014586  mov     rcx, [rcx+r8*8]; this
0x18001458a  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x18001458f  mov     r15, rax
0x180014592  test    rax, rax
0x180014595  jz      loc_1800149A9
0x18001459b  xor     ecx, ecx
0x18001459d  cmp     r12d, [r13+0Ch]
0x1800145a1  jnb     short loc_1800145AB
0x1800145a3  mov     rcx, [r13+0]
0x1800145a7  mov     rcx, [rcx+r8*8]; this
0x1800145ab  mov     [rbp+var_48], 0
0x1800145b3  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x1800145b8  lea     rcx, [rbp+var_48]
0x1800145bc  mov     qword ptr [rsp+80h+bIgnoreCase], rcx; int
0x1800145c1  mov     rdx, rax; unsigned __int16 *
0x1800145c4  mov     rcx, [r14+0B8h]; this
0x1800145cb  call    ?GetOrAddReferencedFile@UnifiedResourceView@Resources@Microsoft@@QEAAJPEBG_N0PEAPEBVManagedResourceMap@23@PEAH@Z; Microsoft::Resources::UnifiedResourceView::GetOrAddReferencedFile(ushort const *,bool,ushort const *,Microsoft::Resources::ManagedResourceMap const * *,int *)
0x1800145d0  mov     r14d, eax
0x1800145d3  test    eax, eax
0x1800145d5  jns     short loc_18001460F
0x1800145d7  mov     rcx, [rbp+38h]; this
0x1800145db  mov     r9d, eax; char *
0x1800145de  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x1800145e5  mov     edx, 2A1h; void *
0x1800145ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800145ef  nop
0x1800145f0  test    rdi, rdi
0x1800145f3  jz      short loc_1800145FF
0x1800145f5  mov     rcx, rdi; lpCriticalSection
0x1800145f8  call    cs:__imp_LeaveCriticalSection
0x1800145fe  nop
0x1800145ff  mov     eax, r14d
0x180014602  jmp     loc_1800143BA
0x180014607  xor     r9b, r9b
0x18001460a  jmp     loc_1800144D7
0x18001460f  mov     rcx, [rbp+var_48]
0x180014613  test    rcx, rcx
0x180014616  jz      loc_1800149A9
0x18001461c  mov     rax, [rcx]
0x18001461f  mov     rax, [rax+8]
0x180014623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014628  mov     rdx, rax
0x18001462b  mov     rcx, [rax]
0x18001462e  mov     rax, [rcx+10h]
0x180014632  mov     rcx, rdx
0x180014635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001463a  mov     r14, rax
0x18001463d  mov     [rsp+80h+bIgnoreCase], 1; int
0x180014645  or      eax, 0FFFFFFFFh
0x180014648  mov     r9d, eax; cchCount2
0x18001464b  mov     r8, r14; lpString2
0x18001464e  mov     edx, eax; cchCount1
0x180014650  mov     rcx, r15; lpString1
0x180014653  call    cs:__imp_CompareStringOrdinal
0x180014659  lea     ecx, [rax-2]
0x18001465c  call    _IntToComparison
0x180014661  test    eax, eax
0x180014663  jz      loc_1800149A9
0x180014669  lea     rcx, [rbp+var_38]
0x18001466d  call    DefStringResult_InitBuf
0x180014672  lea     rcx, [rbp+var_38]
0x180014676  mov     [rbp+var_40], rcx
0x18001467a  mov     rdx, r14
0x18001467d  lea     rcx, [rbp+var_38]
0x180014681  call    DefStringResult_SetCopy
0x180014686  mov     r14d, eax
0x180014689  test    eax, eax
0x18001468b  js      loc_1800149B9
0x180014691  lea     rcx, [rbp+var_18]
0x180014695  call    DefStringResult_InitBuf
0x18001469a  lea     rcx, [rbp+var_18]
0x18001469e  mov     [rbp+var_20], rcx
0x1800146a2  mov     rdx, r15
0x1800146a5  lea     rcx, [rbp+var_18]
0x1800146a9  call    DefStringResult_SetCopy
0x1800146ae  mov     r14d, eax
0x1800146b1  xor     r15d, r15d
0x1800146b4  test    eax, eax
0x1800146b6  js      loc_180014841
0x1800146bc  mov     r9, [rbp+arg_0]
0x1800146c0  mov     rcx, [rbp+var_40]
0x1800146c4  test    rcx, rcx
0x1800146c7  jz      loc_1800148CE
0x1800146cd  cmp     [rcx], r15
0x1800146d0  jnz     short loc_1800146DC
0x1800146d2  cmp     [rcx+8], r15d
0x1800146d6  ja      loc_1800148CE
0x1800146dc  cmp     [rcx+8], r15d
0x1800146e0  jnz     short loc_1800146EB
0x1800146e2  cmp     [rcx], r15
0x1800146e5  jnz     loc_1800148CE
0x1800146eb  mov     rax, [rcx+10h]
0x1800146ef  mov     ecx, r15d
  ... truncated ...
```
