# UnstorePackage

- ea: `0x1800b5f90`
- end: `0x1800b65d3`
- name: `UnstorePackage`
- size: `1603`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180027790`
- `0x18004da0c`

## callees

- `0x180010f54`
- `0x180011094`
- `0x180013018`
- `0x180013250`
- `0x180018a64`
- `0x1800261e0`
- `0x1800576cc`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800b5f90`
- `0x1800b67ec`
- `0x1800b6e34`
- `0x1800b980c`
- `0x1800d6b88`
- `0x1800eb920`
- `0x18010c194`
- `0x18012955c`
- `0x1801e97dc`
- `0x1801ebfe4`
- `0x1801ec2a0`
- `0x1801ecba4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b647f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b64c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b647f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b64c1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800b63b1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800b646a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800b63b1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800b646a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b63c0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b64b1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b63c0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b64b1`

## string_xrefs

- `0x1800b64d5`: `Unable to delete session guide source: {}, continuing...`
- `0x1800b6360`: `Failed to delete from the store package: {}`
- `0x1800b6405`: `Failed to replace extension for session guide source`
- `0x1800b6540`: `Unable to remove package index for package: {}`
- `0x1800b6577`: `Unable to remove package from package index for package: {}`
- `0x1800b606b`: `Failed to remove package dependencies for package: {}`
- `0x1800b60f8`: `Failed to remove update dependencies for package: {}`
- `0x1800b6259`: `Failed to remove catalog for package: {}`
- `0x1800b6170`: `Failed to remove capability dependencies for package: {}`
- `0x1800b61e3`: `Failed to remove component dependencies for package: {}`

## pseudocode

```c
__int64 __fastcall UnstorePackage(__int64 a1, __int64 a2, CCbsStoreObject *a3, wchar_t *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int v10; // esi
  int v11; // edx
  __int64 v12; // rdx
  int v13; // eax
  int v14; // edx
  int v15; // eax
  int v16; // edx
  int v17; // eax
  int v18; // edx
  int v19; // eax
  int v20; // edx
  int VersionLessIdentity; // eax
  int v22; // edx
  __int64 v23; // rdx
  int v24; // eax
  int v25; // edx
  WCHAR *v26; // rbx
  int v27; // eax
  int v28; // edx
  DWORD LastError; // eax
  DWORD v30; // eax
  int v31; // eax
  int v32; // eax
  int v34; // [rsp+20h] [rbp-69h]
  LPCWSTR v35; // [rsp+30h] [rbp-59h] BYREF
  wchar_t *v36; // [rsp+38h] [rbp-51h] BYREF
  int v37[2]; // [rsp+40h] [rbp-49h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-41h] BYREF
  _BYTE v39[24]; // [rsp+50h] [rbp-39h] BYREF
  wchar_t *v40; // [rsp+68h] [rbp-21h] BYREF
  int v41; // [rsp+70h] [rbp-19h] BYREF
  __int64 v42; // [rsp+78h] [rbp-11h] BYREF
  int v43; // [rsp+80h] [rbp-9h]
  __int128 v44; // [rsp+88h] [rbp-1h]
  __int64 v45; // [rsp+98h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v40 = a4;
  lpFileName = 0;
  v42 = 0;
  v43 = 0;
  v45 = 0;
  v44 = 0;
  MonitoredCritSecLocker::MonitoredCritSecLocker(
    (MonitoredCritSecLocker *)v39,
    (struct AutoMonitoredCritSec *)&vPackageStoreLock,
    1);
  v7 = SczAllocFormatted(&lpFileName, L"%ws%ws.mum", a2, v40);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC44,
      (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
      (const char *)(unsigned int)v7,
      v34);
    goto LABEL_50;
  }
  v9 = UnstorePackageIndicesFrom(a3, 6, v40);
  v10 = v9;
  if ( v9 < 0 )
  {
    v41 = v9;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to remove package dependencies for package: {}",
        (__int64)&v40);
      v35 = (LPCWSTR)&v41;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)&v35);
    }
    v12 = 3146;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
      (const char *)v10,
      v34);
LABEL_8:
    v8 = v10;
    goto LABEL_50;
  }
  v13 = UnstorePackageIndicesFrom(a3, 7, v40);
  v10 = v13;
  if ( v13 < 0 )
  {
    v41 = v13;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to remove update dependencies for package: {}",
        (__int64)&v40);
      v35 = (LPCWSTR)&v41;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {}",
        (__int64)&v35);
    }
    v12 = 3149;
    goto LABEL_7;
  }
  v15 = UnstorePackageIndicesFrom(a3, 13, v40);
  v10 = v15;
  if ( v15 < 0 )
  {
    v41 = v15;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to remove capability dependencies for package: {}",
        (__int64)&v40);
      v35 = (LPCWSTR)&v41;
      LOBYTE(v16) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v16,
        3,
        (unsigned int)": {}",
        (__int64)&v35);
    }
    v12 = 3152;
    goto LABEL_7;
  }
  v17 = UnstoreComponentDependencies(a3, v40);
  v10 = v17;
  if ( v17 < 0 )
  {
    v41 = v17;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to remove component dependencies for package: {}",
        (__int64)&v40);
      v35 = (LPCWSTR)&v41;
      LOBYTE(v18) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v18,
        3,
        (unsigned int)": {}",
        (__int64)&v35);
    }
    v12 = 3155;
    goto LABEL_7;
  }
  v19 = UnstorePackageCatalog(a1, a2, v40);
  v10 = v19;
  if ( v19 < 0 )
  {
    v41 = v19;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to remove catalog for package: {}",
        (__int64)&v40);
      v35 = (LPCWSTR)&v41;
      LOBYTE(v20) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v20,
        3,
        (unsigned int)": {}",
        (__int64)&v35);
    }
    v12 = 3161;
    goto LABEL_7;
  }
  v36 = 0;
  VersionLessIdentity = GetVersionLessIdentity(v40, &v36);
  v10 = VersionLessIdentity;
  if ( VersionLessIdentity < 0 )
  {
    v41 = VersionLessIdentity;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to get versionless identity on package: {}",
        (__int64)&v40);
      v35 = (LPCWSTR)&v41;
      LOBYTE(v22) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v22,
        3,
        (unsigned int)": {}",
        (__int64)&v35);
    }
    v23 = 3168;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
      (const char *)v10,
      v34);
LABEL_30:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v36);
    goto LABEL_8;
  }
  v24 = CCbsStoreObject::Delete(a3);
  v10 = v24;
  if ( v24 < 0 )
  {
    v41 = v24;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to delete from the store package: {}",
        (__int64)&v40);
      v35 = (LPCWSTR)&v41;
      LOBYTE(v25) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v25,
        3,
        (unsigned int)": {}",
        (__int64)&v35);
    }
    v23 = 3173;
    goto LABEL_29;
  }
  v26 = (WCHAR *)lpFileName;
  SetFileAttributesW(lpFileName, 0x80u);
  DeleteFileW(v26);
  v35 = 0;
  v27 = FileReplaceExtension(v26);
  v10 = v27;
  if ( v27 < 0 )
  {
    v41 = v27;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Failed to replace extension for session guide source");
      *(_QWORD *)v37 = &v41;
      LOBYTE(v28) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v28,
        3,
        (unsigned int)": {}",
        (__int64)v37);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC6F,
      (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
      (const char *)v10,
      v34);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v35);
    goto LABEL_30;
  }
  if ( !SetFileAttributesW(v35, 0x80u) )
  {
    LastError = GetLastError();
    if ( (LastError & 0xFFFFFFFD) != 0 )
    {
      *(_QWORD *)v37 = v35;
      LogAdapter::TraceAtLevelWin32<unsigned long,wchar_t *>(
        2,
        LastError,
        "Unable to set file attribute to normal for session guide source: {}, continuing...",
        v37);
      *(_QWORD *)v37 = v35;
      if ( !DeleteFileW(v35) )
      {
        v30 = GetLastError();
        LogAdapter::TraceAtLevelWin32<unsigned long,wchar_t *>(
          2,
          v30,
          "Unable to delete session guide source: {}, continuing...",
          v37);
      }
    }
  }
  RemovePackageFromSpecialIndex(a3, L"System", v40);
  RemovePackageFromSpecialIndex(a3, L"Product", v40);
  v31 = CCbsStoreObject::Open(a3, v36, 3);
  if ( v31 < 0 )
  {
    LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
      2,
      (unsigned int)v31,
      "Unable to remove package from package index for package: {}",
      &v40);
  }
  else
  {
    v32 = CCbsStoreObject::DeleteValue((CCbsStoreObject *)&v42, v40, 1);
    if ( v32 < 0 )
      LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
        2,
        (unsigned int)v32,
        "Unable to remove package index for package: {}",
        &v40);
    if ( (unsigned int)CCbsStoreObject::EnumNumericValue((CCbsStoreObject *)&v42, 0, 0, 0) == -2147024637 )
      CCbsStoreObject::Delete((CCbsStoreObject *)&v42);
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v35);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v36);
  v8 = 0;
LABEL_50:
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v39);
  CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v42);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  return v8;
}

```

## disassembly

```asm
0x1800b5f90  push    rbp
0x1800b5f92  push    rbx
0x1800b5f93  push    rsi
0x1800b5f94  push    rdi
0x1800b5f95  push    r14
0x1800b5f97  push    r15
0x1800b5f99  lea     rbp, [rsp-2Fh]
0x1800b5f9e  sub     rsp, 0B8h
0x1800b5fa5  mov     rax, cs:__security_cookie
0x1800b5fac  xor     rax, rsp
0x1800b5faf  mov     [rbp+57h+var_40], rax
0x1800b5fb3  mov     rdi, r8
0x1800b5fb6  mov     [rbp+57h+var_78], r9
0x1800b5fba  mov     r14, rdx
0x1800b5fbd  mov     [rbp+57h+lpFileName], 0
0x1800b5fc5  mov     r15, rcx
0x1800b5fc8  mov     [rbp+57h+var_68], 0
0x1800b5fd0  xorps   xmm0, xmm0
0x1800b5fd3  mov     [rbp+57h+var_60], 0
0x1800b5fda  mov     r8b, 1; bool
0x1800b5fdd  mov     [rbp+57h+var_48], 0
0x1800b5fe5  lea     rdx, ?vPackageStoreLock@@3UMonitoredCritSec@@A; struct AutoMonitoredCritSec *
0x1800b5fec  lea     rcx, [rbp+57h+var_90]; this
0x1800b5ff0  movdqu  [rbp+57h+var_58], xmm0
0x1800b5ff5  call    ??0MonitoredCritSecLocker@@QEAA@AEAVAutoMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(AutoMonitoredCritSec &,bool)
0x1800b5ffa  mov     r9, [rbp+57h+var_78]
0x1800b5ffe  lea     rdx, aWsWsMum; "%ws%ws.mum"
0x1800b6005  mov     r8, r14
0x1800b6008  lea     rcx, [rbp+57h+lpFileName]
0x1800b600c  call    SczAllocFormatted
0x1800b6011  mov     ebx, eax
0x1800b6013  test    eax, eax
0x1800b6015  jns     short loc_1800B6034
0x1800b6017  mov     rcx, [rbp+5Fh]; this
0x1800b601b  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x1800b6022  mov     r9d, eax; char *
0x1800b6025  mov     edx, 0C44h; void *
0x1800b602a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b602f  jmp     loc_1800B6599
0x1800b6034  mov     r8, [rbp+57h+var_78]
0x1800b6038  mov     edx, 6
0x1800b603d  mov     rcx, rdi
0x1800b6040  call    UnstorePackageIndicesFrom
0x1800b6045  mov     esi, eax
0x1800b6047  test    eax, eax
0x1800b6049  jns     short loc_1800B60C1
0x1800b604b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b6052  mov     [rbp+57h+var_70], eax
0x1800b6055  test    rcx, rcx
0x1800b6058  jz      short loc_1800B60A2
0x1800b605a  lea     rax, [rbp+57h+var_78]
0x1800b605e  mov     ebx, 3
0x1800b6063  mov     r8d, ebx
0x1800b6066  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b606b  lea     r9, aFailedToRemove_12; "Failed to remove package dependencies f"...
0x1800b6072  xor     edx, edx
0x1800b6074  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b6079  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b6080  lea     rax, [rbp+57h+var_70]
0x1800b6084  mov     [rbp+57h+var_B0], rax
0x1800b6088  lea     r9, asc_1802EE7AC; ": {}"
0x1800b608f  lea     rax, [rbp+57h+var_B0]
0x1800b6093  mov     r8d, ebx
0x1800b6096  mov     dl, 1
0x1800b6098  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800b609d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b60a2  mov     edx, 0C4Ah; void *
0x1800b60a7  mov     rcx, [rbp+5Fh]; this
0x1800b60ab  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x1800b60b2  mov     r9d, esi; char *
0x1800b60b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b60ba  mov     ebx, esi
0x1800b60bc  jmp     loc_1800B6599
0x1800b60c1  mov     r8, [rbp+57h+var_78]
0x1800b60c5  mov     edx, 7
0x1800b60ca  mov     rcx, rdi
0x1800b60cd  call    UnstorePackageIndicesFrom
0x1800b60d2  mov     esi, eax
0x1800b60d4  test    eax, eax
0x1800b60d6  jns     short loc_1800B6139
0x1800b60d8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b60df  mov     [rbp+57h+var_70], eax
0x1800b60e2  test    rcx, rcx
0x1800b60e5  jz      short loc_1800B612F
0x1800b60e7  lea     rax, [rbp+57h+var_78]
0x1800b60eb  mov     ebx, 3
0x1800b60f0  mov     r8d, ebx
0x1800b60f3  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b60f8  lea     r9, aFailedToRemove_17; "Failed to remove update dependencies fo"...
0x1800b60ff  xor     edx, edx
0x1800b6101  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b6106  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b610d  lea     rax, [rbp+57h+var_70]
0x1800b6111  mov     [rbp+57h+var_B0], rax
0x1800b6115  lea     r9, asc_1802EE7AC; ": {}"
0x1800b611c  lea     rax, [rbp+57h+var_B0]
0x1800b6120  mov     r8d, ebx
0x1800b6123  mov     dl, 1
0x1800b6125  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b612a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b612f  mov     edx, 0C4Dh
0x1800b6134  jmp     loc_1800B60A7
0x1800b6139  mov     r8, [rbp+57h+var_78]
0x1800b613d  mov     edx, 0Dh
0x1800b6142  mov     rcx, rdi
0x1800b6145  call    UnstorePackageIndicesFrom
0x1800b614a  mov     esi, eax
0x1800b614c  test    eax, eax
0x1800b614e  jns     short loc_1800B61B1
0x1800b6150  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b6157  mov     [rbp+57h+var_70], eax
0x1800b615a  test    rcx, rcx
0x1800b615d  jz      short loc_1800B61A7
0x1800b615f  lea     rax, [rbp+57h+var_78]
0x1800b6163  mov     ebx, 3
0x1800b6168  mov     r8d, ebx
0x1800b616b  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b6170  lea     r9, aFailedToRemove_3; "Failed to remove capability dependencie"...
0x1800b6177  xor     edx, edx
0x1800b6179  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b617e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b6185  lea     rax, [rbp+57h+var_70]
0x1800b6189  mov     [rbp+57h+var_B0], rax
0x1800b618d  lea     r9, asc_1802EE7AC; ": {}"
0x1800b6194  lea     rax, [rbp+57h+var_B0]
0x1800b6198  mov     r8d, ebx
0x1800b619b  mov     dl, 1
0x1800b619d  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b61a2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b61a7  mov     edx, 0C50h
0x1800b61ac  jmp     loc_1800B60A7
0x1800b61b1  mov     rdx, [rbp+57h+var_78]
0x1800b61b5  mov     rcx, rdi
0x1800b61b8  call    UnstoreComponentDependencies
0x1800b61bd  mov     esi, eax
0x1800b61bf  test    eax, eax
0x1800b61c1  jns     short loc_1800B6224
0x1800b61c3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b61ca  mov     [rbp+57h+var_70], eax
0x1800b61cd  test    rcx, rcx
0x1800b61d0  jz      short loc_1800B621A
0x1800b61d2  lea     rax, [rbp+57h+var_78]
0x1800b61d6  mov     ebx, 3
0x1800b61db  mov     r8d, ebx
0x1800b61de  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b61e3  lea     r9, aFailedToRemove_23; "Failed to remove component dependencies"...
0x1800b61ea  xor     edx, edx
0x1800b61ec  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b61f1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b61f8  lea     rax, [rbp+57h+var_70]
0x1800b61fc  mov     [rbp+57h+var_B0], rax
0x1800b6200  lea     r9, asc_1802EE7AC; ": {}"
0x1800b6207  lea     rax, [rbp+57h+var_B0]
0x1800b620b  mov     r8d, ebx
0x1800b620e  mov     dl, 1
0x1800b6210  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b6215  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b621a  mov     edx, 0C53h
0x1800b621f  jmp     loc_1800B60A7
0x1800b6224  mov     r8, [rbp+57h+var_78]
0x1800b6228  mov     rdx, r14
0x1800b622b  mov     rcx, r15
0x1800b622e  call    UnstorePackageCatalog
0x1800b6233  mov     esi, eax
0x1800b6235  test    eax, eax
0x1800b6237  jns     short loc_1800B629A
0x1800b6239  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b6240  mov     [rbp+57h+var_70], eax
0x1800b6243  test    rcx, rcx
0x1800b6246  jz      short loc_1800B6290
0x1800b6248  lea     rax, [rbp+57h+var_78]
0x1800b624c  mov     ebx, 3
0x1800b6251  mov     r8d, ebx
0x1800b6254  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b6259  lea     r9, aFailedToRemove_22; "Failed to remove catalog for package: {"...
0x1800b6260  xor     edx, edx
0x1800b6262  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b6267  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b626e  lea     rax, [rbp+57h+var_70]
0x1800b6272  mov     [rbp+57h+var_B0], rax
0x1800b6276  lea     r9, asc_1802EE7AC; ": {}"
0x1800b627d  lea     rax, [rbp+57h+var_B0]
0x1800b6281  mov     r8d, ebx
0x1800b6284  mov     dl, 1
0x1800b6286  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b628b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b6290  mov     edx, 0C59h
0x1800b6295  jmp     loc_1800B60A7
0x1800b629a  mov     rcx, [rbp+57h+var_78]; wchar_t *
0x1800b629e  lea     rdx, [rbp+57h+var_A8]; wchar_t **
0x1800b62a2  mov     [rbp+57h+var_A8], 0
0x1800b62aa  call    ?GetVersionLessIdentity@@YAJPEB_WPEAPEA_W@Z; GetVersionLessIdentity(wchar_t const *,wchar_t * *)
0x1800b62af  mov     esi, eax
0x1800b62b1  test    eax, eax
0x1800b62b3  jns     short loc_1800B6332
0x1800b62b5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b62bc  mov     [rbp+57h+var_70], eax
0x1800b62bf  test    rcx, rcx
0x1800b62c2  jz      short loc_1800B630C
0x1800b62c4  lea     rax, [rbp+57h+var_78]
0x1800b62c8  mov     ebx, 3
0x1800b62cd  mov     r8d, ebx
0x1800b62d0  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b62d5  lea     r9, aFailedToGetVer_11; "Failed to get versionless identity on p"...
0x1800b62dc  xor     edx, edx
0x1800b62de  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b62e3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b62ea  lea     rax, [rbp+57h+var_70]
0x1800b62ee  mov     [rbp+57h+var_B0], rax
0x1800b62f2  lea     r9, asc_1802EE7AC; ": {}"
0x1800b62f9  lea     rax, [rbp+57h+var_B0]
0x1800b62fd  mov     r8d, ebx
0x1800b6300  mov     dl, 1
0x1800b6302  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800b6307  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b630c  mov     edx, 0C60h; void *
0x1800b6311  mov     rcx, [rbp+5Fh]; this
0x1800b6315  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x1800b631c  mov     r9d, esi; char *
0x1800b631f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6324  lea     rcx, [rbp+57h+var_A8]
0x1800b6328  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800b632d  jmp     loc_1800B60BA
0x1800b6332  mov     rcx, rdi; this
0x1800b6335  call    ?Delete@CCbsStoreObject@@QEAAJXZ; CCbsStoreObject::Delete(void)
0x1800b633a  mov     esi, eax
0x1800b633c  test    eax, eax
0x1800b633e  jns     short loc_1800B63A1
0x1800b6340  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b6347  mov     [rbp+57h+var_70], eax
0x1800b634a  test    rcx, rcx
0x1800b634d  jz      short loc_1800B6397
0x1800b634f  lea     rax, [rbp+57h+var_78]
0x1800b6353  mov     ebx, 3
0x1800b6358  mov     r8d, ebx
0x1800b635b  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b6360  lea     r9, aFailedToDelete_19; "Failed to delete from the store package"...
0x1800b6367  xor     edx, edx
0x1800b6369  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b636e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b6375  lea     rax, [rbp+57h+var_70]
0x1800b6379  mov     [rbp+57h+var_B0], rax
0x1800b637d  lea     r9, asc_1802EE7AC; ": {}"
0x1800b6384  lea     rax, [rbp+57h+var_B0]
0x1800b6388  mov     r8d, ebx
0x1800b638b  mov     dl, 1
0x1800b638d  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b6392  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b6397  mov     edx, 0C65h
0x1800b639c  jmp     loc_1800B6311
0x1800b63a1  mov     rbx, [rbp+57h+lpFileName]
0x1800b63a5  mov     r14d, 80h
0x1800b63ab  mov     edx, r14d; dwFileAttributes
0x1800b63ae  mov     rcx, rbx; lpFileName
0x1800b63b1  call    cs:__imp_SetFileAttributesW
0x1800b63b8  nop     dword ptr [rax+rax+00h]
0x1800b63bd  mov     rcx, rbx; lpFileName
0x1800b63c0  call    cs:__imp_DeleteFileW
0x1800b63c7  nop     dword ptr [rax+rax+00h]
0x1800b63cc  lea     r8, [rbp+57h+var_B0]
0x1800b63d0  mov     [rbp+57h+var_B0], 0
0x1800b63d8  lea     rdx, aSes; "ses"
0x1800b63df  mov     rcx, rbx; wchar_t *
0x1800b63e2  call    FileReplaceExtension
0x1800b63e7  mov     esi, eax
0x1800b63e9  test    eax, eax
0x1800b63eb  jns     short loc_1800B6460
0x1800b63ed  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b63f4  mov     [rbp+57h+var_70], eax
0x1800b63f7  test    rcx, rcx
0x1800b63fa  jz      short loc_1800B643A
0x1800b63fc  lea     ebx, [r14-7Dh]
0x1800b6400  xor     edx, edx
0x1800b6402  mov     r8d, ebx
0x1800b6405  lea     r9, aFailedToReplac_0; "Failed to replace extension for session"...
0x1800b640c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800b6411  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b6418  lea     rax, [rbp+57h+var_70]
0x1800b641c  mov     qword ptr [rbp+57h+var_A0], rax
0x1800b6420  lea     r9, asc_1802EE7AC; ": {}"
0x1800b6427  lea     rax, [rbp+57h+var_A0]
0x1800b642b  mov     r8d, ebx
0x1800b642e  mov     dl, 1
0x1800b6430  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800b6435  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b643a  mov     rcx, [rbp+5Fh]; this
0x1800b643e  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x1800b6445  mov     r9d, esi; char *
0x1800b6448  mov     edx, 0C6Fh; void *
0x1800b644d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6452  lea     rcx, [rbp+57h+var_B0]
0x1800b6456  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800b645b  jmp     loc_1800B6324
0x1800b6460  mov     rbx, [rbp+57h+var_B0]
0x1800b6464  mov     edx, r14d; dwFileAttributes
0x1800b6467  mov     rcx, rbx; lpFileName
0x1800b646a  call    cs:__imp_SetFileAttributesW
0x1800b6471  nop     dword ptr [rax+rax+00h]
0x1800b6476  mov     esi, 2
0x1800b647b  test    eax, eax
  ... truncated ...
```
