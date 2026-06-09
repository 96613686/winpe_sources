# Microsoft::VisualStudio::PkgDef::CPkgDefManagement::LocateMasterPkgDef(ushort const *)

- ea: `0x14001d8a0`
- end: `0x14001e386`
- name: `?LocateMasterPkgDef@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAJPEBG@Z`
- size: `2790`
- prototype: `__int64 __fastcall(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14001d17c`

## callees

- `0x140002c10`
- `0x140002dd0`
- `0x140003070`
- `0x140003160`
- `0x140004950`
- `0x140009b10`
- `0x140013e2c`
- `0x140014710`
- `0x140018048`
- `0x14001b3e0`
- `0x14001d8a0`
- `0x14001e390`
- `0x140022db0`
- `0x14002a5b0`
- `0x14002a644`
- `0x140033ab0`
- `0x140046514`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsupr_s` at `0x14001e050`
- `api-ms-win-crt-string-l1-1-0!_wcsupr_s` at `0x14001e050`
- `SHLWAPI!PathFileExistsW` at `0x14001dc67`
- `SHLWAPI!PathFileExistsW` at `0x14001dcfb`
- `SHLWAPI!PathFileExistsW` at `0x14001dd69`
- `SHLWAPI!PathFileExistsW` at `0x14001ddd7`
- `SHLWAPI!PathFileExistsW` at `0x14001de45`
- `SHLWAPI!PathFileExistsW` at `0x14001dfd5`
- `SHLWAPI!PathFileExistsW` at `0x14001e0ea`
- `SHLWAPI!PathFileExistsW` at `0x14001e114`
- `SHLWAPI!PathFileExistsW` at `0x14001dc67`
- `SHLWAPI!PathFileExistsW` at `0x14001dcfb`
- `SHLWAPI!PathFileExistsW` at `0x14001dd69`
- `SHLWAPI!PathFileExistsW` at `0x14001ddd7`
- `SHLWAPI!PathFileExistsW` at `0x14001de45`
- `SHLWAPI!PathFileExistsW` at `0x14001dfd5`
- `SHLWAPI!PathFileExistsW` at `0x14001e0ea`
- `SHLWAPI!PathFileExistsW` at `0x14001e114`
- `SHLWAPI!PathIsDirectoryW` at `0x14001dbb1`
- `SHLWAPI!PathIsDirectoryW` at `0x14001dc34`
- `SHLWAPI!PathIsDirectoryW` at `0x14001dbb1`
- `SHLWAPI!PathIsDirectoryW` at `0x14001dc34`

## string_xrefs

- `0x14001dc47`: `AppId path is not a directory`
- `0x14001dd45`: `Common7\IDE`
- `0x14001ddb3`: `Common7\IDE`
- `0x14001de21`: `Common7\IDE`
- `0x14001de5c`: `Could not locate master pkgdef file in directory`
- `0x14001d8d1`: `PkgDefManagement already initialized`
- `0x14001da34`: `DiscoverHostingAppPath failed for executable path: '%s'`
- `0x14001daf6`: `GetCanonicalName failed for application executable path '%s'`
- `0x14001def6`: `LocateMasterPkgDefInDirectory failed for app executable path '%s'`
- `0x14001e1e3`: `LocateMasterPkgDefFromExe failed for app executable path '%s'`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Microsoft::VisualStudio::PkgDef::CPkgDefManagement::LocateMasterPkgDef(
        Microsoft::VisualStudio::PkgDef::CPkgDefManagement *this,
        const unsigned __int16 *a2)
{
  LPCWSTR *v4; // r12
  LPCWSTR v5; // rdx
  int CanonicalName; // r14d
  unsigned __int16 *v7; // rdi
  struct ATL::IAtlStringMgr *v8; // rax
  const WCHAR *v9; // rbx
  char v10; // r15
  LPCWSTR v11; // r8
  struct ATL::IAtlStringMgr *Instance; // rax
  const WCHAR *v13; // rbx
  char v14; // di
  LPCWSTR v15; // r8
  LPCWSTR v16; // rdx
  unsigned __int16 *v17; // rbx
  LPCWSTR v18; // rdx
  LPCWSTR v19; // rdx
  BOOL IsDirectoryW; // eax
  LPCWSTR v21; // r14
  LPCWSTR v22; // rdx
  const unsigned __int16 *v23; // r8
  const unsigned __int16 *v24; // rcx
  LPCWSTR v25; // rdx
  char *v26; // r12
  LPCWSTR v27; // rdx
  LPCWSTR v28; // rdx
  LPCWSTR v29; // rdx
  LPCWSTR v30; // rdx
  LPCWSTR v31; // rdx
  struct ATL::IAtlStringMgr *v32; // rax
  const WCHAR *v33; // rbx
  char v34; // r15
  LPCWSTR v35; // r8
  LPCWSTR v36; // rdx
  LPCWSTR v37; // rdx
  const unsigned __int16 *v38; // rcx
  wchar_t **Extension; // rax
  wchar_t **v40; // rbx
  __int64 v41; // r13
  int v42; // ebx
  LPCWSTR v43; // rdx
  const WCHAR *v44; // rbx
  const unsigned __int16 *v45; // r8
  LPCWSTR v46; // rdx
  struct ATL::IAtlStringMgr *v47; // rax
  const WCHAR *v48; // rbx
  char v49; // r15
  LPCWSTR v50; // r8
  LPCWSTR v51; // rdx
  unsigned __int16 *v52; // rbx
  LPCWSTR v53; // rdx
  int v54; // eax
  unsigned __int16 *v55; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int16 *v56; // [rsp+28h] [rbp-8h] BYREF
  LPCWSTR pszPath; // [rsp+80h] [rbp+50h] BYREF
  LPCWSTR v58; // [rsp+88h] [rbp+58h] BYREF

  if ( *((_QWORD *)this + 2) )
  {
    CLogger::LogError(L"PkgDefManagement already initialized", -2147418113, 0);
    return 2147549183LL;
  }
  v4 = (LPCWSTR *)((char *)this + 88);
  if ( a2 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &pszPath,
      a2);
    ATL::CSimpleStringT<unsigned short,0>::operator=(v4, &pszPath);
    v5 = pszPath - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
    }
  }
  else
  {
    CanonicalName = DiscoverHostingAppPath((char *)this + 88);
    if ( CanonicalName < 0 )
    {
      Instance = ATL::CAtlStringMgr::GetInstance();
      if ( !Instance )
        ATL::AtlThrowImpl(-2147467259);
      _mm_lfence();
      v55 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                               + 24);
      if ( *v4 )
      {
        _mm_lfence();
        v13 = (const WCHAR *)(ATL::CSimpleStringT<unsigned short,0>::CloneData(*v4 - 12) + 24);
        pszPath = v13;
        v14 = 1;
        v15 = v13;
      }
      else
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v58,
          L"NULL");
        v14 = 2;
        v15 = v58;
        v13 = pszPath;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        &v55,
        L"DiscoverHostingAppPath failed for executable path: '%s'",
        v15);
      if ( (v14 & 2) != 0 )
      {
        v14 &= ~2u;
        v16 = v58 - 12;
        if ( _InterlockedDecrement((volatile signed __int32 *)v58 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 8LL))(*(_QWORD *)v16);
        }
      }
      if ( (v14 & 1) != 0 && _InterlockedDecrement((volatile signed __int32 *)v13 - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v13 - 3) + 8LL))(*((_QWORD *)v13 - 3));
      }
      v17 = v55;
      CLogger::LogError(v55, CanonicalName, 0);
      if ( _InterlockedDecrement((volatile signed __int32 *)v17 - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v17 - 3) + 8LL))(*((_QWORD *)v17 - 3));
      }
      _mm_lfence();
      return (unsigned int)CanonicalName;
    }
  }
  v55 = (unsigned __int16 *)(ATL::CSimpleStringT<unsigned short,0>::CloneData(*v4 - 12) + 24);
  CanonicalName = GetCanonicalName(&v55);
  v7 = v55;
  if ( CanonicalName >= 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &pszPath,
      v55);
    ATL::CSimpleStringT<unsigned short,0>::operator=(v4, &pszPath);
    v19 = pszPath - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v19 + 8LL))(*(_QWORD *)v19);
    }
    IsDirectoryW = PathIsDirectoryW(*v4);
    v21 = *v4;
    if ( IsDirectoryW )
    {
      if ( !v21 )
      {
        CanonicalName = -2147024809;
        goto LABEL_61;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v58,
        &WindowName);
      ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 400, &v58);
      v22 = v58 - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)v58 - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v22 + 8LL))(*(_QWORD *)v22);
      }
      pszPath = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &pszPath,
        v21);
      if ( !PathIsDirectoryW(pszPath) )
      {
        v23 = v21;
        CanonicalName = -2147024809;
        v24 = L"AppId path is not a directory";
        goto LABEL_59;
      }
      ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
        &pszPath,
        L"master.pkgdef");
      if ( !PathFileExistsW(pszPath) )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v58,
          v21);
        ATL::CSimpleStringT<unsigned short,0>::operator=(&pszPath, &v58);
        v27 = v58 - 12;
        if ( _InterlockedDecrement((volatile signed __int32 *)v58 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 8LL))(*(_QWORD *)v27);
        }
        ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
          &pszPath,
          L"devenv.pkgdef");
        if ( !PathFileExistsW(pszPath) )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v58,
            v21);
          ATL::CSimpleStringT<unsigned short,0>::operator=(&pszPath, &v58);
          v28 = v58 - 12;
          if ( _InterlockedDecrement((volatile signed __int32 *)v58 - 2) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v28 + 8LL))(*(_QWORD *)v28);
          }
          ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
            &pszPath,
            L"Common7\\IDE");
          ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
            &pszPath,
            L"master.pkgdef");
          if ( !PathFileExistsW(pszPath) )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v58,
              v21);
            ATL::CSimpleStringT<unsigned short,0>::operator=(&pszPath, &v58);
            v29 = v58 - 12;
            if ( _InterlockedDecrement((volatile signed __int32 *)v58 - 2) <= 0 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v29 + 8LL))(*(_QWORD *)v29);
            }
            ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
              &pszPath,
              L"Common7\\IDE");
            ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
              &pszPath,
              L"devenv.pkgdef");
            if ( !PathFileExistsW(pszPath) )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                &v58,
                v21);
              ATL::CSimpleStringT<unsigned short,0>::operator=(&pszPath, &v58);
              v30 = v58 - 12;
              if ( _InterlockedDecrement((volatile signed __int32 *)v58 - 2) <= 0 )
              {
                _mm_lfence();
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v30 + 8LL))(*(_QWORD *)v30);
              }
              ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
                &pszPath,
                L"Common7\\IDE");
              ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
                &pszPath,
                L"Ssms.pkgdef");
              if ( !PathFileExistsW(pszPath) )
              {
                v23 = v21;
                CanonicalName = -2147287038;
                v24 = L"Could not locate master pkgdef file in directory";
LABEL_59:
                CLogger::LogError(v24, CanonicalName, v23);
                v31 = pszPath - 12;
                if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
                {
                  _mm_lfence();
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 8LL))(*(_QWORD *)v31);
                }
LABEL_61:
                v32 = ATL::CAtlStringMgr::GetInstance();
                if ( v32 )
                {
                  _mm_lfence();
                  v56 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v32 + 24LL))(v32)
                                           + 24);
                  if ( *v4 )
                  {
                    v33 = (const WCHAR *)(ATL::CSimpleStringT<unsigned short,0>::CloneData(*v4 - 12) + 24);
                    pszPath = v33;
                    v34 = 16;
                    v35 = v33;
                  }
                  else
                  {
                    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                      &v58,
                      L"NULL");
                    v34 = 32;
                    v35 = v58;
                    v33 = pszPath;
                  }
                  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
                    &v56,
                    L"LocateMasterPkgDefInDirectory failed for app executable path '%s'",
                    v35);
                  if ( (v34 & 0x20) != 0 )
                  {
                    v34 &= ~0x20u;
                    v36 = v58 - 12;
                    if ( _InterlockedDecrement((volatile signed __int32 *)v58 - 2) <= 0 )
                    {
                      _mm_lfence();
                      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v36 + 8LL))(*(_QWORD *)v36);
                    }
                  }
                  if ( (v34 & 0x10) != 0 && _InterlockedDecrement((volatile signed __int32 *)v33 - 2) <= 0 )
                  {
                    _mm_lfence();
                    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v33 - 3) + 8LL))(*((_QWORD *)v33 - 3));
                  }
                  goto LABEL_104;
                }
LABEL_119:
                ATL::AtlThrowImpl(-2147467259);
              }
            }
          }
        }
      }
      ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 400, &pszPath);
      v25 = pszPath - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v25 + 8LL))(*(_QWORD *)v25);
      }
      v26 = (char *)this + 400;
LABEL_110:
      CanonicalName = 0;
      ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 80, v26);
      ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RemoveFileSpec((char *)this + 80);
      if ( (*((_DWORD *)this + 15) & 0x2020) != 0
        || *((_DWORD *)this + 17) == -1
        || *(_DWORD *)(*((_QWORD *)this + 15) - 16LL) )
      {
        v54 = Microsoft::VisualStudio::PkgDef::CPkgDefManagement::ScanMasterPkgDefForInitializationFields(this);
        CanonicalName = v54;
        if ( v54 >= 0 )
        {
          if ( *((_DWORD *)this + 17) == -1 )
            *((_DWORD *)this + 17) = 1;
        }
        else
        {
          _mm_lfence();
          CLogger::LogError(L"ScanMasterPkgDefForInitializationFields failed", v54, 0);
        }
      }
      goto LABEL_117;
    }
    if ( !v21 )
    {
      CanonicalName = -2147024809;
      goto LABEL_94;
    }
    pszPath = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &pszPath,
      v21);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v58,
      &WindowName);
    ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 400, &v58);
    v37 = v58 - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)v58 - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v37 + 8LL))(*(_QWORD *)v37);
    }
    if ( PathFileExistsW(pszPath) )
    {
      Extension = (wchar_t **)ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::GetExtension(
                                &pszPath,
                                &v58);
      v40 = Extension;
      v41 = *((int *)*Extension - 4);
      if ( (int)v41 < 0 )
        goto LABEL_120;
      _mm_lfence();
      if ( ((1 - *((_DWORD *)*Extension - 2)) | (*((_DWORD *)*Extension - 3) - (int)v41)) < 0 )
      {
        _mm_lfence();
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(Extension, (unsigned int)v41);
      }
      _wcsupr_s(*v40, (int)v41 + 1);
      if ( (int)v41 > *((_DWORD *)*v40 - 3) )
LABEL_120:
        ATL::AtlThrowImpl(-2147024809);
      *((_DWORD *)*v40 - 4) = v41;
      (*v40)[v41] = 0;
      v42 = wcscmp_0(*v40, L".EXE");
      v43 = v58 - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)v58 - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v43 + 8LL))(*(_QWORD *)v43);
      }
      if ( !v42 )
      {
        v58 = (LPCWSTR)(ATL::CSimpleStringT<unsigned short,0>::CloneData(pszPath - 12) + 24);
        ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RenameExtension(
          &v58,
          L".PkgDef");
        v44 = v58;
        if ( !PathFileExistsW(v58) )
        {
          ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RemoveFileSpec(&v58);
          ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
            &v58,
            L"master.pkgdef");
          v44 = v58;
        }
        if ( PathFileExistsW(v44) )
        {
          v26 = (char *)this + 400;
          ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 400, &v58);
          if ( _InterlockedDecrement((volatile signed __int32 *)v44 - 2) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v44 - 3) + 8LL))(*((_QWORD *)v44 - 3));
          }
          v53 = pszPath - 12;
          if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v53 + 8LL))(*(_QWORD *)v53);
          }
          goto LABEL_110;
        }
        v45 = v21;
        CanonicalName = -2147287038;
        CLogger::LogError(L"Could not locate master pkgdef file for AppId", -2147287038, v45);
        if ( _InterlockedDecrement((volatile signed __int32 *)v44 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v44 - 3) + 8LL))(*((_QWORD *)v44 - 3));
        }
        goto LABEL_92;
      }
      CanonicalName = -2147024809;
      v38 = L"Executable is not '.EXE'";
    }
    else
    {
      CanonicalName = -2147287038;
      v38 = L"Could not locate executable";
    }
    CLogger::LogError(v38, CanonicalName, pszPath);
LABEL_92:
    v46 = pszPath - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v46 + 8LL))(*(_QWORD *)v46);
    }
LABEL_94:
    v47 = ATL::CAtlStringMgr::GetInstance();
    if ( v47 )
    {
      _mm_lfence();
      v56 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v47 + 24LL))(v47)
                               + 24);
      if ( *v4 )
      {
        v48 = (const WCHAR *)(ATL::CSimpleStringT<unsigned short,0>::CloneData(*v4 - 12) + 24);
        pszPath = v48;
        v49 = 64;
        v50 = v48;
      }
      else
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v58,
          L"NULL");
        v49 = 0x80;
        v50 = v58;
        v48 = pszPath;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        &v56,
        L"LocateMasterPkgDefFromExe failed for app executable path '%s'",
        v50);
      if ( v49 < 0 )
      {
        v49 &= ~0x80u;
        v51 = v58 - 12;
        if ( _InterlockedDecrement((volatile signed __int32 *)v58 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v51 + 8LL))(*(_QWORD *)v51);
        }
      }
      if ( (v49 & 0x40) != 0 && _InterlockedDecrement((volatile signed __int32 *)v48 - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v48 - 3) + 8LL))(*((_QWORD *)v48 - 3));
      }
      goto LABEL_104;
    }
    goto LABEL_119;
  }
  v8 = ATL::CAtlStringMgr::GetInstance();
  if ( !v8 )
    goto LABEL_119;
  _mm_lfence();
  v56 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v8 + 24LL))(v8) + 24);
  if ( *v4 )
  {
    v9 = (const WCHAR *)(ATL::CSimpleStringT<unsigned short,0>::CloneData(*v4 - 12) + 24);
    pszPath = v9;
    v10 = 4;
    v11 = v9;
  }
  else
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v58,
      L"NULL");
    v10 = 8;
    v11 = v58;
    v9 = pszPath;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &v56,
    L"GetCanonicalName failed for application executable path '%s'",
    v11);
  if ( (v10 & 8) != 0 )
  {
    v10 &= ~8u;
    v18 = v58 - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)v58 - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 8LL))(*(_QWORD *)v18);
    }
  }
  if ( (v10 & 4) != 0 && _InterlockedDecrement((volatile signed __int32 *)v9 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v9 - 3) + 8LL))(*((_QWORD *)v9 - 3));
  }
LABEL_104:
  v52 = v56;
  CLogger::LogError(v56, CanonicalName, 0);
  if ( _InterlockedDecrement((volatile signed __int32 *)v52 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v52 - 3) + 8LL))(*((_QWORD *)v52 - 3));
  }
LABEL_117:
  if ( _InterlockedDecrement((volatile signed __int32 *)v7 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
  }
  return (unsigned int)CanonicalName;
}

```

## disassembly

```asm
0x14001d8a0  mov     [rsp-38h+arg_8], rbx
0x14001d8a5  push    rbp
0x14001d8a6  push    rsi
0x14001d8a7  push    rdi
0x14001d8a8  push    r12
0x14001d8aa  push    r13
0x14001d8ac  push    r14
0x14001d8ae  push    r15
0x14001d8b0  mov     rbp, rsp
0x14001d8b3  sub     rsp, 30h
0x14001d8b7  mov     r15, rcx
0x14001d8ba  xor     r13d, r13d
0x14001d8bd  mov     [rbp+arg_0], r13d
0x14001d8c1  cmp     [rcx+10h], r13
0x14001d8c5  jz      short loc_14001D8F4
0x14001d8c7  xor     r8d, r8d; unsigned __int16 *
0x14001d8ca  mov     ebx, 8000FFFFh
0x14001d8cf  mov     edx, ebx; int
0x14001d8d1  lea     rcx, aPkgdefmanageme_8; "PkgDefManagement already initialized"
0x14001d8d8  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x14001d8dd  mov     eax, ebx
0x14001d8df  mov     rbx, [rsp+30h+arg_8]
0x14001d8e4  add     rsp, 30h
0x14001d8e8  pop     r15
0x14001d8ea  pop     r14
0x14001d8ec  pop     r13
0x14001d8ee  pop     r12
0x14001d8f0  pop     rdi
0x14001d8f1  pop     rsi
0x14001d8f2  pop     rbp
0x14001d8f3  retn
0x14001d8f4  lea     r12, [rcx+58h]
0x14001d8f8  or      esi, 0FFFFFFFFh
0x14001d8fb  test    rdx, rdx
0x14001d8fe  jz      loc_14001D9B7
0x14001d904  lea     rcx, [rbp+pszPath]
0x14001d908  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001d90d  nop
0x14001d90e  lea     rdx, [rbp+pszPath]
0x14001d912  mov     rcx, r12
0x14001d915  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001d91a  nop
0x14001d91b  mov     rdx, [rbp+pszPath]
0x14001d91f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001d923  mov     eax, esi
0x14001d925  lock xadd [rdx+10h], eax
0x14001d92a  add     eax, esi
0x14001d92c  test    eax, eax
0x14001d92e  jg      short loc_14001D93C
0x14001d930  lfence
0x14001d933  mov     rcx, [rdx]
0x14001d936  mov     rax, [rcx]
0x14001d939  call    qword ptr [rax+8]
0x14001d93c  mov     rcx, [r12]
0x14001d940  sub     rcx, 18h
0x14001d944  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001d949  add     rax, 18h
0x14001d94d  mov     [rbp+var_10], rax
0x14001d951  lea     rcx, [rbp+var_10]
0x14001d955  call    ?GetCanonicalName@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetCanonicalName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14001d95a  mov     r14d, eax
0x14001d95d  mov     rdi, [rbp+var_10]
0x14001d961  test    eax, eax
0x14001d963  jns     loc_14001DB72
0x14001d969  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14001d96e  mov     rcx, rax
0x14001d971  test    rax, rax
0x14001d974  jz      loc_14001E35E
0x14001d97a  lfence
0x14001d97d  mov     rax, [rax]
0x14001d980  call    qword ptr [rax+18h]
0x14001d983  add     rax, 18h
0x14001d987  mov     [rbp+var_8], rax
0x14001d98b  mov     rcx, [r12]
0x14001d98f  test    rcx, rcx
0x14001d992  jz      loc_14001DAD3
0x14001d998  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14001d99c  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001d9a1  lea     rbx, [rax+18h]
0x14001d9a5  mov     [rbp+pszPath], rbx
0x14001d9a9  mov     r15d, 4
0x14001d9af  mov     r8, rbx
0x14001d9b2  jmp     loc_14001DAF2
0x14001d9b7  mov     rcx, r12
0x14001d9ba  call    ?DiscoverHostingAppPath@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; DiscoverHostingAppPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14001d9bf  mov     r14d, eax
0x14001d9c2  test    eax, eax
0x14001d9c4  jns     loc_14001D93C
0x14001d9ca  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14001d9cf  mov     rcx, rax
0x14001d9d2  test    rax, rax
0x14001d9d5  jz      loc_14001E37B
0x14001d9db  lfence
0x14001d9de  mov     rax, [rax]
0x14001d9e1  call    qword ptr [rax+18h]
0x14001d9e4  add     rax, 18h
0x14001d9e8  mov     [rbp+var_10], rax
0x14001d9ec  cmp     [r12], r13
0x14001d9f0  jz      short loc_14001DA14
0x14001d9f2  lfence
0x14001d9f5  mov     rcx, [r12]
0x14001d9f9  sub     rcx, 18h
0x14001d9fd  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001da02  lea     rbx, [rax+18h]
0x14001da06  mov     [rbp+pszPath], rbx
0x14001da0a  mov     edi, 1
0x14001da0f  mov     r8, rbx
0x14001da12  jmp     short loc_14001DA31
0x14001da14  lea     rdx, aNull_0; "NULL"
0x14001da1b  lea     rcx, [rbp+arg_18]
0x14001da1f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001da24  mov     edi, 2
0x14001da29  mov     r8, [rbp+arg_18]
0x14001da2d  mov     rbx, [rbp+pszPath]
0x14001da31  mov     [rbp+arg_0], edi
0x14001da34  lea     rdx, aDiscoverhostin; "DiscoverHostingAppPath failed for execu"...
0x14001da3b  lea     rcx, [rbp+var_10]
0x14001da3f  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14001da44  or      esi, 0FFFFFFFFh
0x14001da47  test    dil, 2
0x14001da4b  jz      short loc_14001DA75
0x14001da4d  and     edi, 0FFFFFFFDh
0x14001da50  mov     [rbp+arg_0], edi
0x14001da53  mov     rdx, [rbp+arg_18]
0x14001da57  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001da5b  mov     eax, esi
0x14001da5d  lock xadd [rdx+10h], eax
0x14001da62  add     eax, esi
0x14001da64  test    eax, eax
0x14001da66  jg      short loc_14001DA75
0x14001da68  lfence
0x14001da6b  mov     rcx, [rdx]
0x14001da6e  mov     rax, [rcx]
0x14001da71  call    qword ptr [rax+8]
0x14001da74  nop
0x14001da75  test    dil, 1
0x14001da79  jz      short loc_14001DA98
0x14001da7b  lea     rdx, [rbx-18h]
0x14001da7f  mov     eax, esi
0x14001da81  lock xadd [rdx+10h], eax
0x14001da86  add     eax, esi
0x14001da88  test    eax, eax
0x14001da8a  jg      short loc_14001DA98
0x14001da8c  lfence
0x14001da8f  mov     rcx, [rdx]
0x14001da92  mov     rax, [rcx]
0x14001da95  call    qword ptr [rax+8]
0x14001da98  xor     r8d, r8d; unsigned __int16 *
0x14001da9b  mov     edx, r14d; int
0x14001da9e  mov     rbx, [rbp+var_10]
0x14001daa2  mov     rcx, rbx; unsigned __int16 *
0x14001daa5  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x14001daaa  nop
0x14001daab  lea     rdx, [rbx-18h]
0x14001daaf  mov     eax, esi
0x14001dab1  lock xadd [rdx+10h], eax
0x14001dab6  add     eax, esi
0x14001dab8  test    eax, eax
0x14001daba  jg      short loc_14001DAC8
0x14001dabc  lfence
0x14001dabf  mov     rcx, [rdx]
0x14001dac2  mov     rax, [rcx]
0x14001dac5  call    qword ptr [rax+8]
0x14001dac8  lfence
0x14001dacb  mov     eax, r14d
0x14001dace  jmp     loc_14001D8DF
0x14001dad3  lea     rdx, aNull_0; "NULL"
0x14001dada  lea     rcx, [rbp+arg_18]
0x14001dade  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001dae3  nop
0x14001dae4  mov     r15d, 8
0x14001daea  mov     r8, [rbp+arg_18]
0x14001daee  mov     rbx, [rbp+pszPath]
0x14001daf2  mov     [rbp+arg_0], r15d
0x14001daf6  lea     rdx, aGetcanonicalna; "GetCanonicalName failed for application"...
0x14001dafd  lea     rcx, [rbp+var_8]
0x14001db01  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14001db06  nop
0x14001db07  test    r15b, 8
0x14001db0b  jz      short loc_14001DB37
0x14001db0d  and     r15d, 0FFFFFFF7h
0x14001db11  mov     [rbp+arg_0], r15d
0x14001db15  mov     rdx, [rbp+arg_18]
0x14001db19  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001db1d  mov     eax, esi
0x14001db1f  lock xadd [rdx+10h], eax
0x14001db24  add     eax, esi
0x14001db26  test    eax, eax
0x14001db28  jg      short loc_14001DB37
0x14001db2a  lfence
0x14001db2d  mov     rcx, [rdx]
0x14001db30  mov     rax, [rcx]
0x14001db33  call    qword ptr [rax+8]
0x14001db36  nop
0x14001db37  test    r15b, 4
0x14001db3b  jz      short loc_14001DB5A
0x14001db3d  lea     rdx, [rbx-18h]
0x14001db41  mov     eax, esi
0x14001db43  lock xadd [rdx+10h], eax
0x14001db48  add     eax, esi
0x14001db4a  test    eax, eax
0x14001db4c  jg      short loc_14001DB5A
0x14001db4e  lfence
0x14001db51  mov     rcx, [rdx]
0x14001db54  mov     rax, [rcx]
0x14001db57  call    qword ptr [rax+8]
0x14001db5a  xor     r8d, r8d; unsigned __int16 *
0x14001db5d  mov     edx, r14d; int
0x14001db60  mov     rbx, [rbp+var_8]
0x14001db64  mov     rcx, rbx; unsigned __int16 *
0x14001db67  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x14001db6c  nop
0x14001db6d  jmp     loc_14001E259
0x14001db72  mov     rdx, rdi
0x14001db75  lea     rcx, [rbp+pszPath]
0x14001db79  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001db7e  nop
0x14001db7f  lea     rdx, [rbp+pszPath]
0x14001db83  mov     rcx, r12
0x14001db86  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001db8b  nop
0x14001db8c  mov     rdx, [rbp+pszPath]
0x14001db90  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001db94  mov     eax, esi
0x14001db96  lock xadd [rdx+10h], eax
0x14001db9b  add     eax, esi
0x14001db9d  test    eax, eax
0x14001db9f  jg      short loc_14001DBAD
0x14001dba1  lfence
0x14001dba4  mov     rcx, [rdx]
0x14001dba7  mov     rax, [rcx]
0x14001dbaa  call    qword ptr [rax+8]
0x14001dbad  mov     rcx, [r12]; pszPath
0x14001dbb1  call    cs:__imp_PathIsDirectoryW
0x14001dbb7  lea     rbx, [r15+190h]
0x14001dbbe  mov     r14, [r12]
0x14001dbc2  test    eax, eax
0x14001dbc4  jz      loc_14001DF71
0x14001dbca  test    r14, r14
0x14001dbcd  jnz     short loc_14001DBDA
0x14001dbcf  mov     r14d, 80070057h
0x14001dbd5  jmp     loc_14001DE8D
0x14001dbda  lea     rdx, WindowName
0x14001dbe1  lea     rcx, [rbp+arg_18]
0x14001dbe5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001dbea  nop
0x14001dbeb  lea     rdx, [rbp+arg_18]
0x14001dbef  mov     rcx, rbx
0x14001dbf2  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001dbf7  nop
0x14001dbf8  mov     rdx, [rbp+arg_18]
0x14001dbfc  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001dc00  mov     eax, esi
0x14001dc02  lock xadd [rdx+10h], eax
0x14001dc07  add     eax, esi
0x14001dc09  test    eax, eax
0x14001dc0b  jg      short loc_14001DC19
0x14001dc0d  lfence
0x14001dc10  mov     rcx, [rdx]
0x14001dc13  mov     rax, [rcx]
0x14001dc16  call    qword ptr [rax+8]
0x14001dc19  mov     [rbp+pszPath], r13
0x14001dc1d  mov     rdx, r14
0x14001dc20  lea     rcx, [rbp+pszPath]
0x14001dc24  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001dc29  nop
0x14001dc2a  nop     word ptr [rax+rax+00h]
0x14001dc30  mov     rcx, [rbp+pszPath]; pszPath
0x14001dc34  call    cs:__imp_PathIsDirectoryW
0x14001dc3a  test    eax, eax
0x14001dc3c  jnz     short loc_14001DC53
0x14001dc3e  mov     r8, r14
0x14001dc41  mov     r14d, 80070057h
0x14001dc47  lea     rcx, aAppidPathIsNot; "AppId path is not a directory"
0x14001dc4e  jmp     loc_14001DE63
0x14001dc53  lea     rdx, aMasterPkgdef; "master.pkgdef"
0x14001dc5a  lea     rcx, [rbp+pszPath]
0x14001dc5e  call    ?Append@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Append(ushort const *)
0x14001dc63  mov     rcx, [rbp+pszPath]; pszPath
0x14001dc67  call    cs:__imp_PathFileExistsW
0x14001dc6d  test    eax, eax
0x14001dc6f  jz      short loc_14001DCAB
0x14001dc71  lea     rdx, [rbp+pszPath]
0x14001dc75  mov     rcx, rbx
0x14001dc78  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001dc7d  nop
0x14001dc7e  mov     rdx, [rbp+pszPath]
0x14001dc82  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001dc86  mov     eax, esi
0x14001dc88  lock xadd [rdx+10h], eax
0x14001dc8d  add     eax, esi
0x14001dc8f  test    eax, eax
0x14001dc91  jg      short loc_14001DC9F
0x14001dc93  lfence
0x14001dc96  mov     rcx, [rdx]
0x14001dc99  mov     rax, [rcx]
0x14001dc9c  call    qword ptr [rax+8]
0x14001dc9f  lea     r12, [r15+190h]
0x14001dca6  jmp     loc_14001E2D2
0x14001dcab  mov     rdx, r14
  ... truncated ...
```
