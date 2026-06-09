# CCbsSession::PrepareForPostponedReserveExecution(void)

- ea: `0x1800caa88`
- end: `0x1800cb9ad`
- name: `?PrepareForPostponedReserveExecution@CCbsSession@@QEAAJXZ`
- size: `3877`
- prototype: `__int64 __fastcall(CCbsSession *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, installer_update`

## callers

- `0x180172330`

## callees

- `0x180011a14`
- `0x180013250`
- `0x180015420`
- `0x180023ca8`
- `0x1800261e0`
- `0x18002a2bc`
- `0x180048fc0`
- `0x18004e388`
- `0x180057c28`
- `0x180059a00`
- `0x18005aa38`
- `0x180093c4c`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a108c`
- `0x1800a658c`
- `0x1800caa88`
- `0x1800e4f40`
- `0x1800eb920`
- `0x18010ddd8`
- `0x180158a44`
- `0x1801c10d0`
- `0x1801cf788`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800cadc6`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800cadc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cae25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800caf07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb1c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb2d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cae25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800caf07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb1c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb2d9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800cae15`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800caef3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800cae15`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800caef3`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800cae86`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800caf76`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800cae86`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800caf76`

## string_xrefs

- `0x1800caf2a`: `Failed to copy cab into sandbox. Source: {} Target: {}`
- `0x1800cae52`: `Failed to copy metadata container into sandbox. Source: {} Target: {}`
- `0x1800cb1ea`: `Failed to move metadata container into sandbox. Source: {} Target: {}`
- `0x1800cb2f8`: `Failed to move cab into sandbox. Source: {} Target: {}`
- `0x1800caaff`: `Failed to get servicing directory sandboxes path`
- `0x1800cabc3`: `Failed to remove directory {}`
- `0x1800cb5e5`: `Failed to remove postponed package from package tracker`
- `0x1800cb07e`: `Failed to move directory. Source: {} Target: {}`
- `0x1800cb3db`: `Failed to move directory. Source: {} Target: {}`
- `0x1800cb463`: `Failed to move directory. Source: {} Target: {}`
- `0x1800cb4e0`: `Failed to move directory. Source: {} Target: {}`
- `0x1800cb568`: `Failed to move directory. Source: {} Target: {}`
- `0x1800cb894`: `Failed to move contents of local file system source directory. Source: {} Target: {}`
- `0x1800cb8f9`: `Failed to move contents of local file system source directory. Source: {} Target: {}`
- `0x1800cb7f0`: `Moving source directory top level contents {} to {}`
- `0x1800cb842`: `Moving source directory contents recursively {} to {}`
- `0x1800cac3b`: `Failed creating {} directory.`
- `0x1800cb655`: `Failed creating {} directory.`

## pseudocode

```c
__int64 __fastcall CCbsSession::PrepareForPostponedReserveExecution(CCbsSession *this)
{
  __int64 v1; // rsi
  int ServicingDirectory; // eax
  unsigned int v4; // ebx
  int v5; // edx
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  int v8; // eax
  wchar_t *v9; // rdi
  int v10; // eax
  int v11; // edx
  int Directory; // eax
  int v13; // edx
  int v14; // eax
  int v15; // edx
  CCbsPackage ***v16; // r13
  LPCWSTR *v17; // rax
  CCbsPackage **v18; // r12
  int v19; // eax
  const wchar_t *v20; // rdx
  CCbsPackage ****v21; // rbx
  int v22; // r14d
  const WCHAR *v23; // rcx
  wchar_t *v24; // rax
  int v25; // eax
  bool v26; // al
  LPCWSTR v27; // r14
  signed int LastError; // ebx
  int v29; // edx
  unsigned int v30; // eax
  int v31; // eax
  bool v32; // al
  LPCWSTR v33; // rbx
  const WCHAR *v34; // rcx
  signed int v35; // esi
  int v36; // edx
  unsigned int v37; // eax
  BOOL v38; // r13d
  int v39; // esi
  int v40; // eax
  CCbsPackage *v41; // rax
  int v42; // edx
  __int64 v43; // rdx
  __int64 v44; // rdx
  unsigned __int64 v45; // r9
  int v46; // edx
  unsigned int v47; // eax
  signed int v48; // esi
  int v49; // edx
  unsigned int v50; // eax
  __int64 v51; // rdx
  int v52; // edx
  int v53; // edx
  CCbsPackage *v54; // rax
  int v55; // edx
  int v56; // edx
  int v57; // edx
  unsigned __int64 v58; // r9
  __int64 v59; // rdx
  int v60; // edx
  BOOL IsOfflineUnitTestMode; // edi
  CCbsSession *v62; // rcx
  int LocalFileSystemSources; // eax
  int v64; // edx
  int v65; // edx
  __int64 v66; // rbx
  BOOL v67; // r15d
  _QWORD *v68; // rdi
  _QWORD *v69; // r12
  int v70; // edx
  int v71; // edx
  __int64 v72; // rdx
  int v73; // edx
  unsigned int v75; // [rsp+20h] [rbp-A9h]
  int v76; // [rsp+20h] [rbp-A9h]
  unsigned int v77[2]; // [rsp+30h] [rbp-99h] BYREF
  int v78[2]; // [rsp+38h] [rbp-91h] BYREF
  LPCWSTR *v79; // [rsp+40h] [rbp-89h] BYREF
  wchar_t *v80; // [rsp+48h] [rbp-81h] BYREF
  __int64 v81; // [rsp+50h] [rbp-79h] BYREF
  __int64 v82; // [rsp+58h] [rbp-71h] BYREF
  int v83[2]; // [rsp+60h] [rbp-69h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+68h] [rbp-61h] BYREF
  CCbsPackage ***v85; // [rsp+70h] [rbp-59h] BYREF
  CCbsPackage ****v86; // [rsp+78h] [rbp-51h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v88[24]; // [rsp+90h] [rbp-39h] BYREF
  __int64 v89; // [rsp+A8h] [rbp-21h]
  _QWORD *v90; // [rsp+B8h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  *((_DWORD *)this + 552) |= 0x20000u;
  v1 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  ServicingDirectory = CCbsSession::GetServicingDirectory(this, L"Sandboxes\\", &v80);
  v4 = ServicingDirectory;
  if ( ServicingDirectory < 0 )
  {
    LODWORD(v85) = ServicingDirectory;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Failed to get servicing directory sandboxes path");
      lpExistingFileName = (LPCWSTR)&v85;
      LOBYTE(v5) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v5,
        3,
        (unsigned int)": {}",
        (__int64)&lpExistingFileName);
    }
    v6 = v4;
    v7 = 309;
    goto LABEL_8;
  }
  v8 = SczAllocConcatSz(&v80, *((_QWORD *)this + 80));
  v4 = v8;
  if ( v8 < 0 )
  {
    v7 = 311;
LABEL_7:
    v6 = (unsigned int)v8;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
      (const char *)v6,
      v75);
    goto LABEL_152;
  }
  v8 = SczEnsureBackslashTerminated(&v80);
  v4 = v8;
  if ( v8 < 0 )
  {
    v7 = 313;
    goto LABEL_7;
  }
  v9 = v80;
  v10 = CCbsSession::RemoveDirectoryViaCbsTemp(this, v80);
  v4 = v10;
  if ( v10 < 0 )
  {
    LODWORD(v85) = v10;
    if ( LogAdapter::g_Logger )
    {
      lpExistingFileName = v9;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to remove directory {}",
        (__int64)&lpExistingFileName);
      v86 = &v85;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)&v86);
    }
    v6 = v4;
    v7 = 316;
    goto LABEL_8;
  }
  Directory = RecursivelyCreateDirectory(v9, 0);
  v4 = Directory;
  if ( Directory < 0 )
  {
    LODWORD(v85) = Directory;
    if ( LogAdapter::g_Logger )
    {
      lpExistingFileName = v9;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed creating {} directory.",
        (__int64)&lpExistingFileName);
      v86 = &v85;
      LOBYTE(v13) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v13,
        3,
        (unsigned int)": {}",
        (__int64)&v86);
    }
    v6 = v4;
    v7 = 319;
    goto LABEL_8;
  }
  v14 = CCbsSession::TagEmptyDirectory(this, v9);
  v4 = v14;
  if ( v14 < 0 )
  {
    LODWORD(v85) = v14;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to put servicing sandbox in reserve");
      lpExistingFileName = (LPCWSTR)&v85;
      LOBYTE(v15) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v15,
        3,
        (unsigned int)": {}",
        (__int64)&lpExistingFileName);
    }
    v6 = v4;
    v7 = 322;
    goto LABEL_8;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::GetImpl'::`2'::impl) )
    Windows::AutoGenericHandleBase<IMultiSourceUpdateContainer *,0,Windows::AutoReleasePtr<IMultiSourceUpdateContainer>>::Close((char *)this + 2368);
  v16 = (CCbsPackage ***)*((_QWORD *)this + 102);
  v17 = (LPCWSTR *)&v16[*((_QWORD *)this + 100)];
  v79 = v17;
  while ( 1 )
  {
    v85 = v16;
    if ( v16 == (CCbsPackage ***)v17 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::GetImpl'::`2'::impl)
        && *((_BYTE *)this + 2254) )
      {
        CCbsStringArray::CCbsStringArray((CCbsStringArray *)v88);
        IsOfflineUnitTestMode = CCbsSession::IsOfflineUnitTestMode(this);
        LocalFileSystemSources = CCbsSession::GetLocalFileSystemSources(v62, (struct CCbsStringArray *)v88, 0, 1, 0);
        v4 = LocalFileSystemSources;
        if ( LocalFileSystemSources < 0 )
        {
          LODWORD(v85) = LocalFileSystemSources;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get local file system sources");
            *(_QWORD *)v78 = &v85;
            LOBYTE(v65) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v65,
              3,
              (unsigned int)": {}",
              (__int64)v78);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1CB,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
            (const char *)v4,
            v76);
          CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v88);
          goto LABEL_152;
        }
        if ( v89 )
        {
          v66 = v82;
          v67 = IsOfflineUnitTestMode;
          v68 = v90;
          v69 = &v90[v89];
          while ( 1 )
          {
            if ( v68 == v69 )
              goto LABEL_150;
            *(_QWORD *)v77 = v66;
            if ( LogAdapter::g_Logger )
            {
              LOBYTE(v64) = 1;
              LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                (_DWORD)LogAdapter::g_Logger,
                v64,
                1,
                (unsigned int)"Moving source directory top level contents {} to {}",
                (__int64)v68,
                (__int64)v77);
            }
            v22 = CbsMoveDirectoryContents((v67 + 2) | 4u, *v68, v66);
            if ( v22 < 0 )
              break;
            *(_QWORD *)v77 = v1;
            if ( LogAdapter::g_Logger )
            {
              LOBYTE(v70) = 1;
              LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                (_DWORD)LogAdapter::g_Logger,
                v70,
                1,
                (unsigned int)"Moving source directory contents recursively {} to {}",
                (__int64)v68,
                (__int64)v77);
            }
            v22 = CbsMoveDirectoryContents((unsigned int)(v67 + 2), *v68, v1);
            if ( v22 < 0 )
            {
              LODWORD(lpNewFileName[0]) = v22;
              if ( LogAdapter::g_Logger )
              {
                *(_QWORD *)v78 = v1;
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"Failed to move contents of local file system source directory. Source: {} Target: {}",
                  (__int64)v68,
                  (__int64)v78);
                v79 = lpNewFileName;
                LOBYTE(v71) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v71,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v79);
              }
              v72 = 480;
LABEL_149:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v72,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
                (const char *)(unsigned int)v22,
                v76);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v88);
              goto LABEL_121;
            }
            ++v68;
          }
          LODWORD(v86) = v22;
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v78 = v1;
            LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to move contents of local file system source directory. Source: {} Target: {}",
              (__int64)v68,
              (__int64)v78);
            *(_QWORD *)v83 = &v86;
            LOBYTE(v73) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v73,
              3,
              (unsigned int)": {}",
              (__int64)v83);
          }
          v72 = 474;
          goto LABEL_149;
        }
LABEL_150:
        CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v88);
      }
LABEL_151:
      v4 = 0;
      goto LABEL_152;
    }
    v18 = *v16;
    v86 = 0;
    v19 = SczAllocConcatSz(&v86, v9);
    v4 = v19;
    if ( v19 < 0 )
    {
      v59 = 335;
LABEL_124:
      v58 = (unsigned int)v19;
      goto LABEL_125;
    }
    v20 = &qword_1802EB518;
    if ( *((_QWORD *)*v18 + 15) )
      v20 = (const wchar_t *)*((_QWORD *)*v18 + 15);
    v19 = SczAllocConcatSz(&v86, v20);
    v4 = v19;
    if ( v19 < 0 )
    {
      v59 = 337;
      goto LABEL_124;
    }
    v21 = v86;
    v22 = RecursivelyCreateDirectory(v86, 0);
    if ( v22 < 0 )
      break;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::GetImpl'::`2'::impl) )
    {
      v23 = (const WCHAR *)*((_QWORD *)*v18 + 139);
      lpExistingFileName = v23;
      if ( v23 )
      {
        v24 = wcsrchr(v23, 0x2Eu);
        lpNewFileName[0] = 0;
        v25 = SczAllocFormatted(lpNewFileName, L"%ws\\metadatacontainer%ws", v21, v24);
        v22 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x15D,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
            (const char *)(unsigned int)v25,
            v75);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(lpNewFileName);
          goto LABEL_120;
        }
        v26 = CCbsSession::IsOfflineUnitTestMode(this);
        v27 = lpNewFileName[0];
        if ( v26 )
        {
          if ( !CopyFileW(lpExistingFileName, lpNewFileName[0], 0) )
          {
            LastError = GetLastError();
            if ( LogAdapter::g_Logger )
            {
              v79 = (LPCWSTR *)v27;
              LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to copy metadata container into sandbox. Source: {} Target: {}",
                (__int64)&lpExistingFileName,
                (__int64)&v79);
              if ( LastError > 0 )
                v30 = (unsigned __int16)LastError | 0x80070000;
              else
                v30 = LastError;
              LODWORD(v85) = v30;
              LOBYTE(v29) = 1;
              *(_QWORD *)v77 = &v85;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v29,
                3,
                (unsigned int)": {0}",
                (__int64)v77);
            }
            if ( LastError )
            {
              v44 = 355;
LABEL_74:
              v45 = (unsigned int)LastError;
LABEL_75:
              v4 = wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)v44,
                     (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
                     (const char *)v45,
                     v75);
LABEL_76:
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(lpNewFileName);
LABEL_126:
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v86);
              goto LABEL_152;
            }
            goto LABEL_84;
          }
        }
        else if ( !MoveFileExW(lpExistingFileName, lpNewFileName[0], 8u) )
        {
          LastError = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v77 = v27;
            LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to move metadata container into sandbox. Source: {} Target: {}",
              (__int64)&lpExistingFileName,
              (__int64)v77);
            if ( LastError > 0 )
              v47 = (unsigned __int16)LastError | 0x80070000;
            else
              v47 = LastError;
            LODWORD(v85) = v47;
            LOBYTE(v46) = 1;
            v79 = (LPCWSTR *)&v85;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v46,
              3,
              (unsigned int)": {0}",
              (__int64)&v79);
          }
          if ( LastError )
          {
            v44 = 362;
            goto LABEL_74;
          }
          goto LABEL_84;
        }
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(lpNewFileName);
      }
    }
    if ( *((_DWORD *)v18 + 2) )
    {
      if ( *((_DWORD *)v18 + 2) == 1 )
      {
        v38 = CCbsSession::IsOfflineUnitTestMode(this);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::GetImpl'::`2'::impl) )
        {
          if ( *((_BYTE *)this + 2254) && CCbsPackage::IsLCUPackage(*v18) )
          {
            if ( v1 )
            {
              v39 = SczAllocFromSz(&v82, v1);
              if ( v39 < 0 )
              {
                v51 = 400;
LABEL_99:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v51,
                  (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
                  (const char *)(unsigned int)v39,
                  v75);
                Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v86);
                v4 = v39;
                goto LABEL_152;
              }
            }
            v39 = SczAllocFromSz(&v81, v21);
            if ( v39 < 0 )
            {
              v51 = 403;
              goto LABEL_99;
            }
            v39 = CbsMoveDirectoryContents(v38, v18[3], v21);
            if ( v39 < 0 )
            {
              LODWORD(v85) = v39;
              if ( LogAdapter::g_Logger )
              {
                *(_QWORD *)v77 = v18[3];
                *(_QWORD *)v78 = v21;
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"Failed to move directory. Source: {} Target: {}",
                  (__int64)v77,
                  (__int64)v78);
                v79 = (LPCWSTR *)&v85;
                LOBYTE(v52) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v52,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v79);
              }
              v51 = 408;
              goto LABEL_99;
            }
            v1 = v81;
          }
          else
          {
            v22 = CbsMoveDirectoryContents(v38, v18[3], v21);
            if ( v22 < 0 )
            {
              LODWORD(v85) = v22;
              if ( LogAdapter::g_Logger )
              {
                *(_QWORD *)v77 = v18[3];
                *(_QWORD *)v78 = v21;
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"Failed to move directory. Source: {} Target: {}",
                  (__int64)v77,
                  (__int64)v78);
                v79 = (LPCWSTR *)&v85;
                LOBYTE(v53) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v53,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v79);
              }
              v43 = 415;
              goto LABEL_119;
            }
            v40 = CbsMoveDirectoryContents(v38, *((_QWORD *)*v18 + 138), v21);
            v22 = v40;
            if ( v40 < 0 )
            {
              LODWORD(v85) = v40;
              if ( LogAdapter::g_Logger )
              {
                v41 = *v18;
                *(_QWORD *)v78 = v21;
                *(_QWORD *)v77 = *((_QWORD *)v41 + 138);
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"Failed to move directory. Source: {} Target: {}",
                  (__int64)v77,
                  (__int64)v78);
                v79 = (LPCWSTR *)&v85;
                LOBYTE(v42) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v42,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v79);
              }
              v43 = 421;
              goto LABEL_119;
            }
          }
        }
        else
        {
          v22 = CbsMoveDirectoryContents(v38, v18[3], v21);
          if ( v22 < 0 )
          {
            LODWORD(v85) = v22;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v77 = v18[3];
              *(_QWORD *)v78 = v21;
              LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to move directory. Source: {} Target: {}",
                (__int64)v77,
                (__int64)v78);
              v79 = (LPCWSTR *)&v85;
              LOBYTE(v56) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v56,
                3,
                (unsigned int)": {}",
                (__int64)&v79);
            }
            v43 = 429;
            goto LABEL_119;
          }
          v22 = CbsMoveDirectoryContents(v38, *((_QWORD *)*v18 + 138), v21);
          if ( v22 < 0 )
          {
            LODWORD(v85) = v22;
            if ( LogAdapter::g_Logger )
            {
              v54 = *v18;
              *(_QWORD *)v78 = v21;
              *(_QWORD *)v77 = *((_QWORD *)v54 + 138);
              LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to move directory. Source: {} Target: {}",
                (__int64)v77,
                (__int64)v78);
              v79 = (LPCWSTR *)&v85;
              LOBYTE(v55) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v55,
                3,
                (unsigned int)": {}",
                (__int64)&v79);
            }
            v43 = 435;
            goto LABEL_119;
          }
        }
        v16 = v85;
      }
    }
    else
    {
      lpNewFileName[0] = 0;
      v31 = SczAllocFormatted(lpNewFileName, L"%ws\\package.cab", v21);
      v4 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x172,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
          (const char *)(unsigned int)v31,
          v75);
        goto LABEL_76;
      }
      v32 = CCbsSession::IsOfflineUnitTestMode(this);
      v33 = lpNewFileName[0];
      v34 = (const WCHAR *)v18[5];
      if ( v32 )
      {
        if ( !CopyFileW(v34, lpNewFileName[0], 0) )
        {
          v35 = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            v79 = (LPCWSTR *)v18[5];
            *(_QWORD *)v77 = v33;
            LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to copy cab into sandbox. Source: {} Target: {}",
              (__int64)&v79,
              (__int64)v77);
            if ( v35 > 0 )
              v37 = (unsigned __int16)v35 | 0x80070000;
            else
              v37 = v35;
            LODWORD(v85) = v37;
            LOBYTE(v36) = 1;
            *(_QWORD *)v78 = &v85;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v36,
              3,
              (unsigned int)": {0}",
              (__int64)v78);
          }
          if ( v35 )
          {
            v45 = (unsigned int)v35;
            v44 = 377;
            goto LABEL_75;
          }
          goto LABEL_84;
        }
      }
      else if ( !MoveFileExW(v34, lpNewFileName[0], 8u) )
      {
        v48 = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v77 = v18[5];
          *(_QWORD *)v78 = v33;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to move cab into sandbox. Source: {} Target: {}",
            (__int64)v77,
            (__int64)v78);
          if ( v48 > 0 )
            v50 = (unsigned __int16)v48 | 0x80070000;
          else
            v50 = v48;
          LODWORD(v85) = v50;
          LOBYTE(v49) = 1;
          v79 = (LPCWSTR *)&v85;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v49,
            3,
            (unsigned int)": {0}",
            (__int64)&v79);
        }
        if ( v48 )
        {
          v45 = (unsigned int)v48;
          v44 = 382;
          goto LABEL_75;
        }
LABEL_84:
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(lpNewFileName);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v86);
        goto LABEL_151;
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(lpNewFileName);
    }
    v4 = PackageTrackerRemove(*v18);
    if ( (v4 & 0x80000000) != 0 )
    {
      LODWORD(v85) = v4;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to remove postponed package from package tracker");
        *(_QWORD *)v78 = &v85;
        LOBYTE(v57) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v57,
          3,
          (unsigned int)": {}",
          (__int64)v78);
      }
      v58 = v4;
      v59 = 442;
LABEL_125:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v59,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
        (const char *)v58,
        v75);
      goto LABEL_126;
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v86);
    v17 = v79;
    ++v16;
  }
  LODWORD(v85) = v22;
  if ( LogAdapter::g_Logger )
  {
    *(_QWORD *)v78 = v21;
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed creating {} directory.",
      (__int64)v78);
    *(_QWORD *)v77 = &v85;
    LOBYTE(v60) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v60,
      3,
      (unsigned int)": {}",
      (__int64)v77);
  }
  v43 = 340;
LABEL_119:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v43,
    (unsigned int)"onecore\\base\\cbs\\core\\cbssessionstoragereserves.cpp",
    (const char *)(unsigned int)v22,
    v75);
LABEL_120:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v86);
LABEL_121:
  v4 = v22;
LABEL_152:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v81);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v82);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v80);
  return v4;
}

```

## disassembly

```asm
0x1800caa88  push    rbp
0x1800caa8a  push    rbx
0x1800caa8b  push    rsi
0x1800caa8c  push    rdi
0x1800caa8d  push    r12
0x1800caa8f  push    r13
0x1800caa91  push    r14
0x1800caa93  push    r15
0x1800caa95  lea     rbp, [rsp-1Fh]
0x1800caa9a  sub     rsp, 0E8h
0x1800caaa1  mov     rax, cs:__security_cookie
0x1800caaa8  xor     rax, rsp
0x1800caaab  mov     [rbp+57h+var_50], rax
0x1800caaaf  bts     dword ptr [rcx+8A0h], 11h
0x1800caab7  lea     r8, [rsp+120h+var_D8]; wchar_t **
0x1800caabc  xor     esi, esi
0x1800caabe  mov     [rsp+120h+var_D8], 0
0x1800caac7  lea     rdx, aSandboxes; "Sandboxes\\"
0x1800caace  mov     [rbp+57h+var_D0], rsi
0x1800caad2  mov     r15, rcx
0x1800caad5  mov     [rbp+57h+var_C8], 0
0x1800caadd  call    ?GetServicingDirectory@CCbsSession@@QEAAJPEB_WPEAPEA_W@Z; CCbsSession::GetServicingDirectory(wchar_t const *,wchar_t * *)
0x1800caae2  mov     ebx, eax
0x1800caae4  test    eax, eax
0x1800caae6  jns     short loc_1800CAB3E
0x1800caae8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800caaef  mov     dword ptr [rbp+57h+var_B0], eax
0x1800caaf2  test    rcx, rcx
0x1800caaf5  jz      short loc_1800CAB34
0x1800caaf7  lea     edi, [rsi+3]
0x1800caafa  xor     edx, edx
0x1800caafc  mov     r8d, edi
0x1800caaff  lea     r9, aFailedToGetSer_4; "Failed to get servicing directory sandb"...
0x1800cab06  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cab0b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cab12  lea     rax, [rbp+57h+var_B0]
0x1800cab16  mov     [rbp+57h+lpExistingFileName], rax
0x1800cab1a  lea     r9, asc_1802EE7AC; ": {}"
0x1800cab21  lea     rax, [rbp+57h+lpExistingFileName]
0x1800cab25  mov     r8d, edi
0x1800cab28  mov     dl, 1
0x1800cab2a  mov     qword ptr [rsp+120h+var_100], rax
0x1800cab2f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cab34  mov     r9d, ebx
0x1800cab37  mov     edx, 135h
0x1800cab3c  jmp     short loc_1800CAB5D
0x1800cab3e  mov     rdx, [r15+280h]
0x1800cab45  lea     rcx, [rsp+120h+var_D8]
0x1800cab4a  call    SczAllocConcatSz
0x1800cab4f  mov     ebx, eax
0x1800cab51  test    eax, eax
0x1800cab53  jns     short loc_1800CAB72
0x1800cab55  mov     edx, 137h; void *
0x1800cab5a  mov     r9d, eax; char *
0x1800cab5d  mov     rcx, [rbp+5Fh]; this
0x1800cab61  lea     r8, aOnecoreBaseCbs_83; "onecore\\base\\cbs\\core\\cbssessionsto"...
0x1800cab68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cab6d  jmp     loc_1800CB96E
0x1800cab72  lea     rcx, [rsp+120h+var_D8]
0x1800cab77  call    SczEnsureBackslashTerminated
0x1800cab7c  mov     ebx, eax
0x1800cab7e  test    eax, eax
0x1800cab80  jns     short loc_1800CAB89
0x1800cab82  mov     edx, 139h
0x1800cab87  jmp     short loc_1800CAB5A
0x1800cab89  mov     rdi, [rsp+120h+var_D8]
0x1800cab8e  mov     rcx, r15; this
0x1800cab91  mov     rdx, rdi; wchar_t *
0x1800cab94  call    ?RemoveDirectoryViaCbsTemp@CCbsSession@@QEAAJQEB_W@Z; CCbsSession::RemoveDirectoryViaCbsTemp(wchar_t const * const)
0x1800cab99  mov     ebx, eax
0x1800cab9b  test    eax, eax
0x1800cab9d  jns     short loc_1800CAC07
0x1800cab9f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800caba6  mov     dword ptr [rbp+57h+var_B0], eax
0x1800caba9  test    rcx, rcx
0x1800cabac  jz      short loc_1800CABFA
0x1800cabae  mov     [rbp+57h+lpExistingFileName], rdi
0x1800cabb2  lea     rax, [rbp+57h+lpExistingFileName]
0x1800cabb6  mov     edi, 3
0x1800cabbb  mov     qword ptr [rsp+120h+var_100], rax
0x1800cabc0  mov     r8d, edi
0x1800cabc3  lea     r9, aFailedToRemove_0; "Failed to remove directory {}"
0x1800cabca  xor     edx, edx
0x1800cabcc  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800cabd1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cabd8  lea     rax, [rbp+57h+var_B0]
0x1800cabdc  mov     [rbp+57h+var_A8], rax
0x1800cabe0  lea     r9, asc_1802EE7AC; ": {}"
0x1800cabe7  lea     rax, [rbp+57h+var_A8]
0x1800cabeb  mov     r8d, edi
0x1800cabee  mov     dl, 1
0x1800cabf0  mov     qword ptr [rsp+120h+var_100], rax
0x1800cabf5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cabfa  mov     r9d, ebx
0x1800cabfd  mov     edx, 13Ch
0x1800cac02  jmp     loc_1800CAB5D
0x1800cac07  xor     edx, edx
0x1800cac09  mov     rcx, rdi
0x1800cac0c  call    RecursivelyCreateDirectory
0x1800cac11  mov     ebx, eax
0x1800cac13  test    eax, eax
0x1800cac15  jns     short loc_1800CAC7F
0x1800cac17  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cac1e  mov     dword ptr [rbp+57h+var_B0], eax
0x1800cac21  test    rcx, rcx
0x1800cac24  jz      short loc_1800CAC72
0x1800cac26  mov     [rbp+57h+lpExistingFileName], rdi
0x1800cac2a  lea     rax, [rbp+57h+lpExistingFileName]
0x1800cac2e  mov     edi, 3
0x1800cac33  mov     qword ptr [rsp+120h+var_100], rax
0x1800cac38  mov     r8d, edi
0x1800cac3b  lea     r9, aFailedCreating; "Failed creating {} directory."
0x1800cac42  xor     edx, edx
0x1800cac44  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800cac49  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cac50  lea     rax, [rbp+57h+var_B0]
0x1800cac54  mov     [rbp+57h+var_A8], rax
0x1800cac58  lea     r9, asc_1802EE7AC; ": {}"
0x1800cac5f  lea     rax, [rbp+57h+var_A8]
0x1800cac63  mov     r8d, edi
0x1800cac66  mov     dl, 1
0x1800cac68  mov     qword ptr [rsp+120h+var_100], rax
0x1800cac6d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cac72  mov     r9d, ebx
0x1800cac75  mov     edx, 13Fh
0x1800cac7a  jmp     loc_1800CAB5D
0x1800cac7f  mov     rdx, rdi
0x1800cac82  mov     rcx, r15
0x1800cac85  call    ?TagEmptyDirectory@CCbsSession@@QEAAJPEB_WW4ScenarioId@IUpdateReserveManager@@@Z; CCbsSession::TagEmptyDirectory(wchar_t const *,IUpdateReserveManager::ScenarioId)
0x1800cac8a  mov     ebx, eax
0x1800cac8c  test    eax, eax
0x1800cac8e  jns     short loc_1800CACEB
0x1800cac90  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cac97  mov     dword ptr [rbp+57h+var_B0], eax
0x1800cac9a  test    rcx, rcx
0x1800cac9d  jz      short loc_1800CACDE
0x1800cac9f  mov     edi, 3
0x1800caca4  lea     r9, aFailedToPutSer; "Failed to put servicing sandbox in rese"...
0x1800cacab  mov     r8d, edi
0x1800cacae  xor     edx, edx
0x1800cacb0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cacb5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cacbc  lea     rax, [rbp+57h+var_B0]
0x1800cacc0  mov     [rbp+57h+lpExistingFileName], rax
0x1800cacc4  lea     r9, asc_1802EE7AC; ": {}"
0x1800caccb  lea     rax, [rbp+57h+lpExistingFileName]
0x1800caccf  mov     r8d, edi
0x1800cacd2  mov     dl, 1
0x1800cacd4  mov     qword ptr [rsp+120h+var_100], rax
0x1800cacd9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cacde  mov     r9d, ebx
0x1800cace1  mov     edx, 142h
0x1800cace6  jmp     loc_1800CAB5D
0x1800caceb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::GetImpl(void)'::`2'::impl
0x1800cacf2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::__private_IsEnabled(void)
0x1800cacf7  test    al, al
0x1800cacf9  jz      short loc_1800CAD07
0x1800cacfb  lea     rcx, [r15+940h]
0x1800cad02  call    ?Close@?$AutoGenericHandleBase@PEAVIMultiSourceUpdateContainer@@$0A@V?$AutoReleasePtr@VIMultiSourceUpdateContainer@@@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<IMultiSourceUpdateContainer *,0,Windows::AutoReleasePtr<IMultiSourceUpdateContainer>>::Close(void)
0x1800cad07  mov     rax, [r15+320h]
0x1800cad0e  mov     r13, [r15+330h]
0x1800cad15  lea     rax, ds:0[rax*8]
0x1800cad1d  add     rax, r13
0x1800cad20  mov     [rsp+120h+var_E0], rax
0x1800cad25  mov     [rbp+57h+var_B0], r13
0x1800cad29  cmp     r13, rax
0x1800cad2c  jz      loc_1800CB6E4
0x1800cad32  mov     r12, [r13+0]
0x1800cad36  lea     rcx, [rbp+57h+var_A8]
0x1800cad3a  mov     rdx, rdi
0x1800cad3d  mov     [rbp+57h+var_A8], 0
0x1800cad45  call    SczAllocConcatSz
0x1800cad4a  mov     ebx, eax
0x1800cad4c  test    eax, eax
0x1800cad4e  js      loc_1800CB6BE
0x1800cad54  mov     rax, [r12]
0x1800cad58  lea     rdx, qword_1802EB518
0x1800cad5f  lea     rcx, [rbp+57h+var_A8]
0x1800cad63  cmp     qword ptr [rax+78h], 0
0x1800cad68  cmovnz  rdx, [rax+78h]
0x1800cad6d  call    SczAllocConcatSz
0x1800cad72  mov     ebx, eax
0x1800cad74  test    eax, eax
0x1800cad76  js      loc_1800CB6B7
0x1800cad7c  mov     rbx, [rbp+57h+var_A8]
0x1800cad80  xor     edx, edx
0x1800cad82  mov     rcx, rbx
0x1800cad85  call    RecursivelyCreateDirectory
0x1800cad8a  mov     r14d, eax
0x1800cad8d  test    eax, eax
0x1800cad8f  js      loc_1800CB62E
0x1800cad95  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::GetImpl(void)'::`2'::impl
0x1800cad9c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::__private_IsEnabled(void)
0x1800cada1  test    al, al
0x1800cada3  jz      loc_1800CAEA3
0x1800cada9  mov     rax, [r12]
0x1800cadad  mov     rcx, [rax+458h]; Str
0x1800cadb4  mov     [rbp+57h+lpExistingFileName], rcx
0x1800cadb8  test    rcx, rcx
0x1800cadbb  jz      loc_1800CAEA3
0x1800cadc1  mov     edx, 2Eh ; '.'; Ch
0x1800cadc6  call    cs:__imp_wcsrchr
0x1800cadcd  nop     dword ptr [rax+rax+00h]
0x1800cadd2  mov     r8, rbx
0x1800cadd5  mov     [rbp+57h+lpNewFileName], 0
0x1800caddd  mov     r9, rax
0x1800cade0  lea     rdx, aWsMetadatacont_0; "%ws\\metadatacontainer%ws"
0x1800cade7  lea     rcx, [rbp+57h+lpNewFileName]
0x1800cadeb  call    SczAllocFormatted
0x1800cadf0  mov     r14d, eax
0x1800cadf3  test    eax, eax
0x1800cadf5  js      loc_1800CB26C
0x1800cadfb  mov     rcx, r15; this
0x1800cadfe  call    ?IsOfflineUnitTestMode@CCbsSession@@QEBA_NXZ; CCbsSession::IsOfflineUnitTestMode(void)
0x1800cae03  mov     r14, [rbp+57h+lpNewFileName]
0x1800cae07  mov     rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x1800cae0b  mov     rdx, r14; lpNewFileName
0x1800cae0e  test    al, al
0x1800cae10  jz      short loc_1800CAE80
0x1800cae12  xor     r8d, r8d; bFailIfExists
0x1800cae15  call    cs:__imp_CopyFileW
0x1800cae1c  nop     dword ptr [rax+rax+00h]
0x1800cae21  test    eax, eax
0x1800cae23  jnz     short loc_1800CAE9A
0x1800cae25  call    cs:__imp_GetLastError
0x1800cae2c  nop     dword ptr [rax+rax+00h]
0x1800cae31  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cae38  mov     ebx, eax
0x1800cae3a  test    rcx, rcx
0x1800cae3d  jz      loc_1800CB191
0x1800cae43  lea     rax, [rsp+120h+var_E0]
0x1800cae48  mov     [rsp+120h+var_E0], r14
0x1800cae4d  mov     [rsp+120h+var_F8], rax
0x1800cae52  lea     r9, aFailedToCopyMe; "Failed to copy metadata container into "...
0x1800cae59  lea     rax, [rbp+57h+lpExistingFileName]
0x1800cae5d  mov     edi, 3
0x1800cae62  mov     r8d, edi
0x1800cae65  mov     qword ptr [rsp+120h+var_100], rax
0x1800cae6a  xor     edx, edx
0x1800cae6c  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1800cae71  test    ebx, ebx
0x1800cae73  jg      loc_1800CB15B
0x1800cae79  mov     eax, ebx
0x1800cae7b  jmp     loc_1800CB163
0x1800cae80  mov     r8d, 8; dwFlags
0x1800cae86  call    cs:__imp_MoveFileExW
0x1800cae8d  nop     dword ptr [rax+rax+00h]
0x1800cae92  test    eax, eax
0x1800cae94  jz      loc_1800CB1C1
0x1800cae9a  lea     rcx, [rbp+57h+lpNewFileName]
0x1800cae9e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800caea3  cmp     dword ptr [r12+8], 0
0x1800caea9  jnz     loc_1800CAF98
0x1800caeaf  mov     r8, rbx
0x1800caeb2  mov     [rbp+57h+lpNewFileName], 0
0x1800caeba  lea     rdx, aWsPackageCab; "%ws\\package.cab"
0x1800caec1  lea     rcx, [rbp+57h+lpNewFileName]
0x1800caec5  call    SczAllocFormatted
0x1800caeca  mov     ebx, eax
0x1800caecc  test    eax, eax
0x1800caece  js      loc_1800CB382
0x1800caed4  mov     rcx, r15; this
0x1800caed7  call    ?IsOfflineUnitTestMode@CCbsSession@@QEBA_NXZ; CCbsSession::IsOfflineUnitTestMode(void)
0x1800caedc  mov     rbx, [rbp+57h+lpNewFileName]
0x1800caee0  mov     rcx, [r12+28h]; lpExistingFileName
0x1800caee5  mov     rdx, rbx; lpNewFileName
0x1800caee8  test    al, al
0x1800caeea  jz      loc_1800CAF70
0x1800caef0  xor     r8d, r8d; bFailIfExists
0x1800caef3  call    cs:__imp_CopyFileW
0x1800caefa  nop     dword ptr [rax+rax+00h]
0x1800caeff  test    eax, eax
0x1800caf01  jnz     loc_1800CAF8A
0x1800caf07  call    cs:__imp_GetLastError
0x1800caf0e  nop     dword ptr [rax+rax+00h]
0x1800caf13  mov     esi, eax
0x1800caf15  mov     rax, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800caf1c  test    rax, rax
0x1800caf1f  jz      loc_1800CB2C8
0x1800caf25  mov     rcx, [r12+28h]
0x1800caf2a  lea     r9, aFailedToCopyCa; "Failed to copy cab into sandbox. Source"...
0x1800caf31  mov     [rsp+120h+var_E0], rcx
0x1800caf36  mov     edi, 3
0x1800caf3b  lea     rcx, [rsp+120h+var_F0]
0x1800caf40  mov     qword ptr [rsp+120h+var_F0], rbx
0x1800caf45  mov     [rsp+120h+var_F8], rcx
0x1800caf4a  mov     r8d, edi
0x1800caf4d  lea     rcx, [rsp+120h+var_E0]
0x1800caf52  xor     edx, edx
0x1800caf54  mov     qword ptr [rsp+120h+var_100], rcx
0x1800caf59  mov     rcx, rax
0x1800caf5c  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1800caf61  test    esi, esi
0x1800caf63  jg      loc_1800CB292
0x1800caf69  mov     eax, esi
0x1800caf6b  jmp     loc_1800CB29A
0x1800caf70  mov     r8d, 8; dwFlags
0x1800caf76  call    cs:__imp_MoveFileExW
0x1800caf7d  nop     dword ptr [rax+rax+00h]
0x1800caf82  test    eax, eax
  ... truncated ...
```
