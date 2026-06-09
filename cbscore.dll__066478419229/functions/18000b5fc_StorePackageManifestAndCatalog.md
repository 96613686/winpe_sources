# StorePackageManifestAndCatalog

- ea: `0x18000b5fc`
- end: `0x18000c23f`
- name: `StorePackageManifestAndCatalog`
- size: `3139`
- prototype: ``
- caller_count: `2`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000c7e8`
- `0x180027790`

## callees

- `0x18000b5fc`
- `0x18000c284`
- `0x18000c5e0`
- `0x18000c70c`
- `0x180010b60`
- `0x180010cc0`
- `0x180010f54`
- `0x1800110d0`
- `0x180012fe4`
- `0x180013250`
- `0x180015420`
- `0x180016250`
- `0x180016d40`
- `0x18004b1b8`
- `0x1800576cc`
- `0x1800603c8`
- `0x180073b74`
- `0x180093c4c`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad504`
- `0x1800b980c`
- `0x1800cbe5c`
- `0x1800eb920`
- `0x1801064b0`
- `0x1801a428c`
- `0x1801a43e0`
- `0x1801c1498`
- `0x1801c3524`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c094`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000bf1d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c055`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000bf1d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c055`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000bf06`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c03e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000bf06`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c03e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000bf45`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000c080`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000bf45`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000c080`

## string_xrefs

- `0x18000c0bc`: `Failed to move package manifest '{}' to store: {}`
- `0x18000bf80`: `Failed to move package session guide '{}' to store: {}`
- `0x18000bbc4`: `Failed to get catalog path for package: {}`
- `0x18000ba88`: `Failed to replace extension for session guide source`
- `0x18000be79`: `Failed to install catalog for package: {}`
- `0x18000bc99`: `Failed to parse manifest: {}`
- `0x18000bd30`: `Failed to convert from package assembly to CBSIdentity on manifest: {}`
- `0x18000bf29`: `File already exists when adding the manifest.`
- `0x18000c061`: `File already exists when adding the manifest.`
- `0x18000c167`: `Failed to set security info on '{}'`
- `0x18000b731`: `CIM: Skipping copy of package {}.`
- `0x18000b940`: `Failed to get manifest path for package: {}`
- `0x18000bb2d`: `Failed to replace extension for session guide target`
- `0x18000b7b2`: `Failed to get offline windows directory when trying to store manifest for package: {}`
- `0x18000b881`: `Failed to get package store directory to store manifest for package: {}`

## pseudocode

```c
__int64 __fastcall StorePackageManifestAndCatalog(struct CCbsSession *a1, CCbsPackage **this, void *a3)
{
  int v5; // edx
  int v7; // edx
  CCbsPackage *v8; // r13
  unsigned int v9; // r12d
  int OfflineWindowsDirectory; // eax
  CCbsPackage *v11; // r13
  int v12; // edx
  int PackageStoreDirectory; // eax
  CCbsPackage *v14; // r13
  int v15; // edx
  int ManifestPath; // eax
  CCbsPackage *v17; // r13
  int v18; // edx
  int v19; // eax
  __int64 v20; // rdx
  CCbsPackage *v21; // r13
  const wchar_t *v22; // rdx
  CCbsPackage *v23; // rax
  const WCHAR *v24; // rbx
  wchar_t *v25; // rdi
  void *v26; // r14
  wchar_t *v27; // rsi
  int v28; // eax
  int v29; // edx
  __int64 v30; // rdx
  int v31; // eax
  int v32; // edx
  int CatalogPath; // eax
  struct Windows::Rtl::StopWatch *v34; // r9
  int v35; // edx
  __int64 v36; // rdx
  int v37; // edx
  __int64 v38; // r12
  struct CCbsIdentity **InitPointer; // rax
  int CbsIdentityFromAssemblyIdentity; // eax
  int v41; // edx
  int v42; // edx
  const wchar_t *v43; // r9
  int v44; // eax
  int v45; // edx
  signed int LastError; // edi
  int v47; // edx
  unsigned int v48; // eax
  unsigned __int64 v49; // r9
  __int64 v50; // rdx
  int v51; // eax
  signed int v52; // r14d
  int v53; // edx
  unsigned int v54; // eax
  int v55; // eax
  int v56; // edx
  unsigned int v57; // [rsp+20h] [rbp-E0h]
  CCbsPackage *v58; // [rsp+30h] [rbp-D0h] BYREF
  struct CCbsIdentity *v59; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *v60; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v61; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v62; // [rsp+50h] [rbp-B0h] BYREF
  void *FastCbsIdentityString; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+68h] [rbp-98h] BYREF
  const WCHAR *v66; // [rsp+70h] [rbp-90h] BYREF
  void *v67; // [rsp+78h] [rbp-88h] BYREF
  void *v68; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v69[2]; // [rsp+88h] [rbp-78h] BYREF
  char v70; // [rsp+98h] [rbp-68h]
  _BYTE v71[56]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v72; // [rsp+D8h] [rbp-28h]
  struct CCbsSession *v73; // [rsp+2D0h] [rbp+1D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  FastCbsIdentityString = a3;
  v58 = (CCbsPackage *)this;
  v73 = a1;
  if ( a1 )
  {
    ParsingSession::ParsingSession((ParsingSession *)v71);
    v59 = 0;
    v69[1] = &vPackageStoreLock;
    v70 = 0;
    v69[0] = &PackageTrackerLocker::`vftable';
    MonitoredCritSecLocker::Lock((MonitoredCritSecLocker *)v69);
    if ( (*((_DWORD *)a1 + 173) & 0x80000) != 0 )
    {
      v8 = (CCbsPackage *)&qword_1802EB518;
      if ( this[15] )
        v8 = this[15];
      v58 = v8;
      if ( LogAdapter::g_Logger )
      {
        LOBYTE(v7) = 1;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          v7,
          1,
          (unsigned int)"CIM: Skipping copy of package {}.",
          (__int64)&v58);
      }
      MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v69);
      if ( v59 )
      {
        (*(void (__fastcall **)(struct CCbsIdentity *))(*(_QWORD *)v59 + 16LL))(v59);
        v59 = 0;
      }
      v9 = 0;
      goto LABEL_114;
    }
    v61 = 0;
    OfflineWindowsDirectory = CCbsSession::GetOfflineWindowsDirectory(a1, &v61);
    v9 = OfflineWindowsDirectory;
    if ( OfflineWindowsDirectory < 0 )
    {
      LODWORD(v73) = OfflineWindowsDirectory;
      if ( LogAdapter::g_Logger )
      {
        v11 = (CCbsPackage *)&qword_1802EB518;
        if ( this[15] )
          v11 = this[15];
        v58 = v11;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to get offline windows directory when trying to store manifest for package: {}",
          (__int64)&v58);
        v62 = (wchar_t *)&v73;
        LOBYTE(v12) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v12,
          3,
          (unsigned int)": {}",
          (__int64)&v62);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE4F,
        (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
        (const char *)v9,
        v57);
      goto LABEL_19;
    }
    v60 = 0;
    PackageStoreDirectory = CCbsSession::GetPackageStoreDirectory(a1, &v60);
    v9 = PackageStoreDirectory;
    if ( PackageStoreDirectory < 0 )
    {
      LODWORD(v73) = PackageStoreDirectory;
      if ( LogAdapter::g_Logger )
      {
        v14 = (CCbsPackage *)&qword_1802EB518;
        if ( this[15] )
          v14 = this[15];
        v58 = v14;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to get package store directory to store manifest for package: {}",
          (__int64)&v58);
        v62 = (wchar_t *)&v73;
        LOBYTE(v15) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v15,
          3,
          (unsigned int)": {}",
          (__int64)&v62);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE53,
        (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
        (const char *)v9,
        v57);
      goto LABEL_26;
    }
    lpExistingFileName = 0;
    ManifestPath = CCbsPackage::GetManifestPath((CCbsPackage *)this, a1, (wchar_t **)&lpExistingFileName);
    v9 = ManifestPath;
    if ( ManifestPath < 0 )
    {
      LODWORD(v73) = ManifestPath;
      if ( LogAdapter::g_Logger )
      {
        v17 = (CCbsPackage *)&qword_1802EB518;
        if ( this[15] )
          v17 = this[15];
        v58 = v17;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to get manifest path for package: {}",
          (__int64)&v58);
        v62 = (wchar_t *)&v73;
        LOBYTE(v18) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v18,
          3,
          (unsigned int)": {}",
          (__int64)&v62);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE57,
        (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
        (const char *)v9,
        v57);
      goto LABEL_33;
    }
    lpFileName = 0;
    v19 = SczAllocFromSz(&lpFileName, v60);
    v9 = v19;
    if ( v19 < 0 )
    {
      v20 = 3674;
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
        (const char *)(unsigned int)v19,
        v57);
LABEL_37:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
LABEL_33:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
LABEL_26:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v60);
LABEL_19:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v61);
      MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v69);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v59);
LABEL_114:
      ParsingSession::~ParsingSession((ParsingSession *)v71);
      return v9;
    }
    v21 = (CCbsPackage *)&qword_1802EB518;
    v22 = &qword_1802EB518;
    if ( this[15] )
      v22 = (const wchar_t *)this[15];
    v19 = SczAllocConcat2Sz(&lpFileName, v22, L".mum");
    v9 = v19;
    if ( v19 < 0 )
    {
      v20 = 3676;
      goto LABEL_36;
    }
    v23 = v58;
    v24 = 0;
    v25 = (wchar_t *)lpFileName;
    v26 = 0;
    v67 = 0;
    v27 = (wchar_t *)lpExistingFileName;
    v66 = 0;
    if ( *((_DWORD *)v58 + 221) )
    {
      v28 = FileReplaceExtension((wchar_t *)lpExistingFileName);
      v9 = v28;
      if ( v28 < 0 )
      {
        LODWORD(v73) = v28;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to replace extension for session guide source");
          v58 = (CCbsPackage *)&v73;
          LOBYTE(v29) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v29,
            3,
            (unsigned int)": {}",
            (__int64)&v58);
        }
        v30 = 3683;
LABEL_47:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
          (const char *)v9,
          v57);
LABEL_48:
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v66);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v67);
        goto LABEL_37;
      }
      v31 = FileReplaceExtension(v25);
      v9 = v31;
      if ( v31 < 0 )
      {
        LODWORD(v73) = v31;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to replace extension for session guide target");
          v58 = (CCbsPackage *)&v73;
          LOBYTE(v32) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v32,
            3,
            (unsigned int)": {}",
            (__int64)&v58);
        }
        v30 = 3686;
        goto LABEL_47;
      }
      v26 = v67;
      v24 = v66;
      v23 = v58;
    }
    v62 = 0;
    CatalogPath = CCbsPackage::GetCatalogPath(v23, v73, &v62);
    v9 = CatalogPath;
    if ( CatalogPath < 0 )
    {
      LODWORD(v73) = CatalogPath;
      if ( LogAdapter::g_Logger )
      {
        if ( *((_QWORD *)v58 + 15) )
          v21 = (CCbsPackage *)*((_QWORD *)v58 + 15);
        v58 = v21;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to get catalog path for package: {}",
          (__int64)&v58);
        FastCbsIdentityString = &v73;
        LOBYTE(v35) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v35,
          3,
          (unsigned int)": {}",
          (__int64)&FastCbsIdentityString);
      }
      v36 = 3691;
LABEL_60:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
        (const char *)v9,
        v57);
LABEL_61:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v62);
      goto LABEL_48;
    }
    v9 = ParseCbsPackage(FastCbsIdentityString, v27, (struct ParsingSession *)v71, v34);
    if ( (v9 & 0x80000000) != 0 )
    {
      CCbsSession::MarkPackageStoreCorrupt(v73);
      LODWORD(v73) = v9;
      if ( LogAdapter::g_Logger )
      {
        FastCbsIdentityString = v27;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to parse manifest: {}",
          (__int64)&FastCbsIdentityString);
        v58 = (CCbsPackage *)&v73;
        LOBYTE(v37) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v37,
          3,
          (unsigned int)": {}",
          (__int64)&v58);
      }
      v36 = 3700;
      goto LABEL_60;
    }
    v38 = v72;
    InitPointer = (struct CCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v59);
    CbsIdentityFromAssemblyIdentity = GetCbsIdentityFromAssemblyIdentity(
                                        (const struct IDENTITY_TYPE *)(v38 + 304),
                                        InitPointer,
                                        0);
    v9 = CbsIdentityFromAssemblyIdentity;
    if ( CbsIdentityFromAssemblyIdentity < 0 )
    {
      LODWORD(v73) = CbsIdentityFromAssemblyIdentity;
      if ( LogAdapter::g_Logger )
      {
        FastCbsIdentityString = v27;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to convert from package assembly to CBSIdentity on manifest: {}",
          (__int64)&FastCbsIdentityString);
        v58 = (CCbsPackage *)&v73;
        LOBYTE(v41) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v41,
          3,
          (unsigned int)": {}",
          (__int64)&v58);
      }
      v36 = 3705;
      goto LABEL_60;
    }
    if ( (unsigned int)CCbsIdentity::IsFastEqual(*((CCbsIdentity **)v58 + 14), v59) != 1 )
    {
      v9 = -2146498536;
      LODWORD(v73) = -2146498536;
      if ( LogAdapter::g_Logger )
      {
        FastCbsIdentityString = GetFastCbsIdentityString(v59);
        if ( *((_QWORD *)v58 + 15) )
          v21 = (CCbsPackage *)*((_QWORD *)v58 + 15);
        v68 = v21;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Identity mismatch on storing the package: Specified Identity: {}, actual package Identity: {}",
          (__int64)&v68,
          (__int64)&FastCbsIdentityString);
        v58 = (CCbsPackage *)&v73;
        LOBYTE(v42) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v42,
          3,
          (unsigned int)": {}",
          (__int64)&v58);
      }
      v36 = 3711;
      goto LABEL_60;
    }
    v43 = &qword_1802EB518;
    if ( *((_QWORD *)v58 + 15) )
      v43 = (const wchar_t *)*((_QWORD *)v58 + 15);
    v44 = StorePackageCatalog(v62, v61, v60, v43);
    v9 = v44;
    if ( v44 < 0 )
    {
      LODWORD(v73) = v44;
      if ( LogAdapter::g_Logger )
      {
        if ( *((_QWORD *)v58 + 15) )
          v21 = (CCbsPackage *)*((_QWORD *)v58 + 15);
        v68 = v21;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to install catalog for package: {}",
          (__int64)&v68);
        FastCbsIdentityString = &v73;
        LOBYTE(v45) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v45,
          3,
          (unsigned int)": {}",
          (__int64)&FastCbsIdentityString);
      }
      v36 = 3720;
      goto LABEL_60;
    }
    if ( *((_DWORD *)v58 + 221) && v24 )
    {
      if ( GetFileAttributesW(v24) != -1 )
      {
        SetFileAttributesW(v24, 0x80u);
        LogAdapter::TraceAtLevel<>(1, "File already exists when adding the manifest.");
      }
      if ( !MoveFileExW((LPCWSTR)v26, v24, 1u) )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          v68 = (void *)v24;
          FastCbsIdentityString = v26;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to move package session guide '{}' to store: {}",
            (__int64)&FastCbsIdentityString,
            (__int64)&v68);
          if ( LastError > 0 )
            v48 = (unsigned __int16)LastError | 0x80070000;
          else
            v48 = LastError;
          LODWORD(v73) = v48;
          LOBYTE(v47) = 1;
          v58 = (CCbsPackage *)&v73;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v47,
            3,
            (unsigned int)": {0}",
            (__int64)&v58);
        }
        if ( LastError )
        {
          v49 = (unsigned int)LastError;
          v50 = 3737;
LABEL_96:
          v9 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v50,
                 (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
                 (const char *)v49,
                 v57);
          goto LABEL_61;
        }
        goto LABEL_113;
      }
      v68 = (void *)v24;
      v51 = FlushFileToDisk(v24);
      if ( v51 < 0 )
        LogAdapter::TraceAtLevelHr<long,wchar_t const *>(2, (unsigned int)v51, "Unable to flush {}", &v68);
    }
    if ( GetFileAttributesW(v25) != -1 )
    {
      SetFileAttributesW(v25, 0x80u);
      LogAdapter::TraceAtLevel<>(1, "File already exists when adding the manifest.");
    }
    if ( MoveFileExW(v27, v25, 3u) )
    {
      v55 = SetSecurityInfoFromFileTemplate(v25, v60);
      v9 = v55;
      if ( v55 < 0 )
      {
        LODWORD(v73) = v55;
        if ( LogAdapter::g_Logger )
        {
          v68 = v25;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to set security info on '{}'",
            (__int64)&v68);
          FastCbsIdentityString = &v73;
          LOBYTE(v56) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v56,
            3,
            (unsigned int)": {}",
            (__int64)&FastCbsIdentityString);
        }
        v36 = 3756;
        goto LABEL_60;
      }
    }
    else
    {
      v52 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        v68 = v25;
        FastCbsIdentityString = v27;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to move package manifest '{}' to store: {}",
          (__int64)&FastCbsIdentityString,
          (__int64)&v68);
        if ( v52 > 0 )
          v54 = (unsigned __int16)v52 | 0x80070000;
        else
          v54 = v52;
        LODWORD(v73) = v54;
        LOBYTE(v53) = 1;
        v58 = (CCbsPackage *)&v73;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v53,
          3,
          (unsigned int)": {0}",
          (__int64)&v58);
      }
      if ( v52 )
      {
        v49 = (unsigned int)v52;
        v50 = 3753;
        goto LABEL_96;
      }
    }
LABEL_113:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v62);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v66);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v67);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v60);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v61);
    MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v69);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v59);
    v9 = 0;
    goto LABEL_114;
  }
  LODWORD(v73) = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No session specified");
    v58 = (CCbsPackage *)&v73;
    LOBYTE(v5) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v5,
      3,
      (unsigned int)": {}",
      (__int64)&v58);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE3E,
    (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
    (const char *)0x80070057LL,
    v57);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000b5fc  push    rbp
0x18000b5fe  push    rbx
0x18000b5ff  push    rsi
0x18000b600  push    rdi
0x18000b601  push    r12
0x18000b603  push    r13
0x18000b605  push    r14
0x18000b607  lea     rbp, [rsp-1E0h]
0x18000b60f  sub     rsp, 2E0h
0x18000b616  mov     rax, cs:__security_cookie
0x18000b61d  xor     rax, rsp
0x18000b620  mov     [rbp+210h+var_38], rax
0x18000b627  xor     esi, esi
0x18000b629  mov     [rsp+310h+var_2B8], r8
0x18000b62e  mov     [rsp+310h+var_2E0], rdx
0x18000b633  mov     rbx, rdx
0x18000b636  mov     [rbp+210h+var_40], rcx
0x18000b63d  mov     rdi, rcx
0x18000b640  test    rcx, rcx
0x18000b643  jnz     short loc_18000B6C0
0x18000b645  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b64c  mov     edi, 80070057h
0x18000b651  mov     dword ptr [rbp+210h+var_40], edi
0x18000b657  test    rcx, rcx
0x18000b65a  jz      short loc_18000B69E
0x18000b65c  lea     ebx, [rsi+3]
0x18000b65f  xor     edx, edx
0x18000b661  mov     r8d, ebx
0x18000b664  lea     r9, aNoSessionSpeci_0; "No session specified"
0x18000b66b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18000b670  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b677  lea     rax, [rbp+210h+var_40]
0x18000b67e  mov     [rsp+310h+var_2E0], rax
0x18000b683  lea     r9, asc_1802EE7AC; ": {}"
0x18000b68a  lea     rax, [rsp+310h+var_2E0]
0x18000b68f  mov     r8d, ebx
0x18000b692  mov     dl, 1
0x18000b694  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x18000b699  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000b69e  mov     rcx, [rbp+218h]; this
0x18000b6a5  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000b6ac  mov     r9d, edi; char *
0x18000b6af  mov     edx, 0E3Eh; void *
0x18000b6b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b6b9  mov     eax, edi
0x18000b6bb  jmp     loc_18000C21D
0x18000b6c0  lea     rcx, [rbp+210h+var_270]; this
0x18000b6c4  call    ??0ParsingSession@@QEAA@XZ; ParsingSession::ParsingSession(void)
0x18000b6c9  lea     rax, ?vPackageStoreLock@@3UMonitoredCritSec@@A; MonitoredCritSec vPackageStoreLock
0x18000b6d0  mov     [rsp+310h+var_2D8], rsi
0x18000b6d5  mov     [rbp+210h+var_280], rax
0x18000b6d9  lea     rcx, [rbp+210h+var_288]; this
0x18000b6dd  lea     rax, ??_7PackageTrackerLocker@@6B@; const PackageTrackerLocker::`vftable'
0x18000b6e4  mov     [rbp+210h+var_278], sil
0x18000b6e8  mov     [rbp+210h+var_288], rax
0x18000b6ec  call    ?Lock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Lock(void)
0x18000b6f1  test    dword ptr [rdi+2B4h], 80000h
0x18000b6fb  jz      short loc_18000B769
0x18000b6fd  cmp     [rbx+78h], rsi
0x18000b701  lea     r13, qword_1802EB518
0x18000b708  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b70f  cmovnz  r13, [rbx+78h]
0x18000b714  mov     [rsp+310h+var_2E0], r13
0x18000b719  test    rcx, rcx
0x18000b71c  jz      short loc_18000B73D
0x18000b71e  mov     r8d, 1
0x18000b724  lea     rax, [rsp+310h+var_2E0]
0x18000b729  mov     dl, r8b
0x18000b72c  mov     qword ptr [rsp+310h+var_2F0], rax
0x18000b731  lea     r9, aCimSkippingCop; "CIM: Skipping copy of package {}."
0x18000b738  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18000b73d  lea     rcx, [rbp+210h+var_288]; this
0x18000b741  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x18000b746  mov     rcx, [rsp+310h+var_2D8]
0x18000b74b  test    rcx, rcx
0x18000b74e  jz      short loc_18000B761
0x18000b750  mov     rax, [rcx]
0x18000b753  mov     rax, [rax+10h]
0x18000b757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b75c  mov     [rsp+310h+var_2D8], rsi
0x18000b761  mov     r12d, esi
0x18000b764  jmp     loc_18000C211
0x18000b769  lea     rdx, [rsp+310h+var_2C8]; wchar_t **
0x18000b76e  mov     [rsp+310h+var_2C8], rsi
0x18000b773  mov     rcx, rdi; this
0x18000b776  call    ?GetOfflineWindowsDirectory@CCbsSession@@QEBAJPEAPEA_W@Z; CCbsSession::GetOfflineWindowsDirectory(wchar_t * *)
0x18000b77b  mov     r12d, eax
0x18000b77e  test    eax, eax
0x18000b780  jns     loc_18000B838
0x18000b786  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b78d  mov     dword ptr [rbp+210h+var_40], eax
0x18000b793  test    rcx, rcx
0x18000b796  jz      short loc_18000B7FB
0x18000b798  cmp     [rbx+78h], rsi
0x18000b79c  lea     rax, [rsp+310h+var_2E0]
0x18000b7a1  lea     r13, qword_1802EB518
0x18000b7a8  mov     qword ptr [rsp+310h+var_2F0], rax
0x18000b7ad  cmovnz  r13, [rbx+78h]
0x18000b7b2  lea     r9, aFailedToGetOff_16; "Failed to get offline windows directory"...
0x18000b7b9  mov     ebx, 3
0x18000b7be  mov     [rsp+310h+var_2E0], r13
0x18000b7c3  mov     r8d, ebx
0x18000b7c6  xor     edx, edx
0x18000b7c8  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18000b7cd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b7d4  lea     rax, [rbp+210h+var_40]
0x18000b7db  mov     [rsp+310h+var_2C0], rax
0x18000b7e0  lea     r9, asc_1802EE7AC; ": {}"
0x18000b7e7  lea     rax, [rsp+310h+var_2C0]
0x18000b7ec  mov     r8d, ebx
0x18000b7ef  mov     dl, 1
0x18000b7f1  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x18000b7f6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000b7fb  mov     rcx, [rbp+218h]; this
0x18000b802  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000b809  mov     r9d, r12d; char *
0x18000b80c  mov     edx, 0E4Fh; void *
0x18000b811  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b816  lea     rcx, [rsp+310h+var_2C8]
0x18000b81b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18000b820  lea     rcx, [rbp+210h+var_288]; this
0x18000b824  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x18000b829  lea     rcx, [rsp+310h+var_2D8]
0x18000b82e  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x18000b833  jmp     loc_18000C211
0x18000b838  lea     rdx, [rsp+310h+var_2D0]; wchar_t **
0x18000b83d  mov     [rsp+310h+var_2D0], rsi
0x18000b842  mov     rcx, rdi; this
0x18000b845  call    ?GetPackageStoreDirectory@CCbsSession@@QEAAJPEAPEA_W@Z; CCbsSession::GetPackageStoreDirectory(wchar_t * *)
0x18000b84a  mov     r12d, eax
0x18000b84d  test    eax, eax
0x18000b84f  jns     loc_18000B8F4
0x18000b855  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b85c  mov     dword ptr [rbp+210h+var_40], eax
0x18000b862  test    rcx, rcx
0x18000b865  jz      short loc_18000B8CA
0x18000b867  cmp     [rbx+78h], rsi
0x18000b86b  lea     rax, [rsp+310h+var_2E0]
0x18000b870  lea     r13, qword_1802EB518
0x18000b877  mov     qword ptr [rsp+310h+var_2F0], rax
0x18000b87c  cmovnz  r13, [rbx+78h]
0x18000b881  lea     r9, aFailedToGetPac_40; "Failed to get package store directory t"...
0x18000b888  mov     ebx, 3
0x18000b88d  mov     [rsp+310h+var_2E0], r13
0x18000b892  mov     r8d, ebx
0x18000b895  xor     edx, edx
0x18000b897  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18000b89c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b8a3  lea     rax, [rbp+210h+var_40]
0x18000b8aa  mov     [rsp+310h+var_2C0], rax
0x18000b8af  lea     r9, asc_1802EE7AC; ": {}"
0x18000b8b6  lea     rax, [rsp+310h+var_2C0]
0x18000b8bb  mov     r8d, ebx
0x18000b8be  mov     dl, 1
0x18000b8c0  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x18000b8c5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000b8ca  mov     rcx, [rbp+218h]; this
0x18000b8d1  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000b8d8  mov     r9d, r12d; char *
0x18000b8db  mov     edx, 0E53h; void *
0x18000b8e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8e5  lea     rcx, [rsp+310h+var_2D0]
0x18000b8ea  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18000b8ef  jmp     loc_18000B816
0x18000b8f4  lea     r8, [rsp+310h+lpExistingFileName]; wchar_t **
0x18000b8f9  mov     [rsp+310h+lpExistingFileName], rsi
0x18000b8fe  mov     rdx, rdi; struct CCbsSession *
0x18000b901  mov     rcx, rbx; this
0x18000b904  call    ?GetManifestPath@CCbsPackage@@QEAAJPEAVCCbsSession@@PEAPEA_W@Z; CCbsPackage::GetManifestPath(CCbsSession *,wchar_t * *)
0x18000b909  mov     r12d, eax
0x18000b90c  test    eax, eax
0x18000b90e  jns     loc_18000B9B3
0x18000b914  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b91b  mov     dword ptr [rbp+210h+var_40], eax
0x18000b921  test    rcx, rcx
0x18000b924  jz      short loc_18000B989
0x18000b926  cmp     [rbx+78h], rsi
0x18000b92a  lea     rax, [rsp+310h+var_2E0]
0x18000b92f  lea     r13, qword_1802EB518
0x18000b936  mov     qword ptr [rsp+310h+var_2F0], rax
0x18000b93b  cmovnz  r13, [rbx+78h]
0x18000b940  lea     r9, aFailedToGetMan_0; "Failed to get manifest path for package"...
0x18000b947  mov     ebx, 3
0x18000b94c  mov     [rsp+310h+var_2E0], r13
0x18000b951  mov     r8d, ebx
0x18000b954  xor     edx, edx
0x18000b956  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18000b95b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000b962  lea     rax, [rbp+210h+var_40]
0x18000b969  mov     [rsp+310h+var_2C0], rax
0x18000b96e  lea     r9, asc_1802EE7AC; ": {}"
0x18000b975  lea     rax, [rsp+310h+var_2C0]
0x18000b97a  mov     r8d, ebx
0x18000b97d  mov     dl, 1
0x18000b97f  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x18000b984  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000b989  mov     rcx, [rbp+218h]; this
0x18000b990  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000b997  mov     r9d, r12d; char *
0x18000b99a  mov     edx, 0E57h; void *
0x18000b99f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9a4  lea     rcx, [rsp+310h+lpExistingFileName]
0x18000b9a9  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18000b9ae  jmp     loc_18000B8E5
0x18000b9b3  mov     rdx, [rsp+310h+var_2D0]
0x18000b9b8  lea     rcx, [rsp+310h+lpFileName]
0x18000b9bd  mov     [rsp+310h+lpFileName], rsi
0x18000b9c2  call    SczAllocFromSz
0x18000b9c7  mov     r12d, eax
0x18000b9ca  test    eax, eax
0x18000b9cc  jns     short loc_18000B9F5
0x18000b9ce  mov     edx, 0E5Ah; void *
0x18000b9d3  mov     rcx, [rbp+218h]; this
0x18000b9da  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000b9e1  mov     r9d, eax; char *
0x18000b9e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9e9  lea     rcx, [rsp+310h+lpFileName]
0x18000b9ee  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18000b9f3  jmp     short loc_18000B9A4
0x18000b9f5  cmp     [rbx+78h], rsi
0x18000b9f9  lea     r13, qword_1802EB518
0x18000ba00  mov     rdx, r13
0x18000ba03  lea     r8, aMum_0; ".mum"
0x18000ba0a  cmovnz  rdx, [rbx+78h]
0x18000ba0f  lea     rcx, [rsp+310h+lpFileName]
0x18000ba14  call    SczAllocConcat2Sz
0x18000ba19  mov     r12d, eax
0x18000ba1c  test    eax, eax
0x18000ba1e  jns     short loc_18000BA27
0x18000ba20  mov     edx, 0E5Ch
0x18000ba25  jmp     short loc_18000B9D3
0x18000ba27  mov     rax, [rsp+310h+var_2E0]
0x18000ba2c  mov     rbx, rsi
0x18000ba2f  mov     rdi, [rsp+310h+lpFileName]
0x18000ba34  mov     r14, rsi
0x18000ba37  mov     [rsp+310h+var_298], rsi
0x18000ba3c  mov     rsi, [rsp+310h+lpExistingFileName]
0x18000ba41  mov     [rsp+310h+var_2A0], rbx
0x18000ba46  cmp     [rax+374h], ebx
0x18000ba4c  jz      loc_18000BB85
0x18000ba52  lea     r8, [rsp+310h+var_298]
0x18000ba57  mov     rcx, rsi; wchar_t *
0x18000ba5a  lea     rdx, aSes; "ses"
0x18000ba61  call    FileReplaceExtension
0x18000ba66  mov     r12d, eax
0x18000ba69  test    eax, eax
0x18000ba6b  jns     loc_18000BAFB
0x18000ba71  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000ba78  mov     dword ptr [rbp+210h+var_40], eax
0x18000ba7e  test    rcx, rcx
0x18000ba81  jz      short loc_18000BAC7
0x18000ba83  mov     ebx, 3
0x18000ba88  lea     r9, aFailedToReplac_0; "Failed to replace extension for session"...
0x18000ba8f  mov     r8d, ebx
0x18000ba92  xor     edx, edx
0x18000ba94  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18000ba99  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000baa0  lea     rax, [rbp+210h+var_40]
0x18000baa7  mov     [rsp+310h+var_2E0], rax
0x18000baac  lea     r9, asc_1802EE7AC; ": {}"
0x18000bab3  lea     rax, [rsp+310h+var_2E0]
0x18000bab8  mov     r8d, ebx
0x18000babb  mov     dl, 1
0x18000babd  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x18000bac2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000bac7  mov     edx, 0E63h; void *
0x18000bacc  mov     rcx, [rbp+218h]; this
0x18000bad3  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000bada  mov     r9d, r12d; char *
0x18000badd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bae2  lea     rcx, [rsp+310h+var_2A0]
0x18000bae7  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18000baec  lea     rcx, [rsp+310h+var_298]
0x18000baf1  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18000baf6  jmp     loc_18000B9E9
0x18000bafb  lea     r8, [rsp+310h+var_2A0]
0x18000bb00  mov     rcx, rdi; wchar_t *
0x18000bb03  lea     rdx, aSes; "ses"
0x18000bb0a  call    FileReplaceExtension
0x18000bb0f  mov     r12d, eax
0x18000bb12  test    eax, eax
0x18000bb14  jns     short loc_18000BB76
0x18000bb16  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000bb1d  mov     dword ptr [rbp+210h+var_40], eax
0x18000bb23  test    rcx, rcx
0x18000bb26  jz      short loc_18000BB6C
0x18000bb28  mov     ebx, 3
0x18000bb2d  lea     r9, aFailedToReplac; "Failed to replace extension for session"...
0x18000bb34  mov     r8d, ebx
0x18000bb37  xor     edx, edx
0x18000bb39  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18000bb3e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000bb45  lea     rax, [rbp+210h+var_40]
0x18000bb4c  mov     [rsp+310h+var_2E0], rax
0x18000bb51  lea     r9, asc_1802EE7AC; ": {}"
0x18000bb58  lea     rax, [rsp+310h+var_2E0]
0x18000bb5d  mov     r8d, ebx
0x18000bb60  mov     dl, 1
0x18000bb62  mov     qword ptr [rsp+310h+var_2F0], rax
0x18000bb67  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
  ... truncated ...
```
