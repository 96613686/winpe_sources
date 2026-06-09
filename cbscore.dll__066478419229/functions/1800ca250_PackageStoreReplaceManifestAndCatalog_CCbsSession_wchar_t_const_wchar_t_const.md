# PackageStoreReplaceManifestAndCatalog(CCbsSession *,wchar_t const *,wchar_t const *)

- ea: `0x1800ca250`
- end: `0x1800caa80`
- name: `?PackageStoreReplaceManifestAndCatalog@@YAJPEAVCCbsSession@@PEB_W1@Z`
- size: `2096`
- prototype: `__int64 __fastcall(struct CCbsSession *this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180190a08`

## callees

- `0x180010f54`
- `0x180011094`
- `0x180013250`
- `0x1800261e0`
- `0x180028e24`
- `0x180042448`
- `0x18004b1b8`
- `0x18005aa38`
- `0x180093c4c`
- `0x180094320`
- `0x1800948fc`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800ca250`
- `0x1800eb920`
- `0x1801c1498`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca5ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca6c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca5ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca6c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca964`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800ca597`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800ca698`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800ca938`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800ca597`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800ca698`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800ca938`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ca57e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ca67f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ca91f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ca57e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ca67f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ca91f`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800ca5b6`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800ca6b1`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800ca950`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800ca5b6`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800ca6b1`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800ca950`

## string_xrefs

- `0x1800ca5fd`: `Failed to move package manifest '{}' to store: {}`
- `0x1800ca98b`: `Failed to move package session source '{}' to target: {}`
- `0x1800ca6ec`: `Failed to move package catalog '{}' to store: {}`
- `0x1800ca40c`: `Failed to get package store directory.`
- `0x1800ca7b5`: `Failed to get offline windows directory.`
- `0x1800ca3a4`: `No source path specified`

## pseudocode

```c
__int64 __fastcall PackageStoreReplaceManifestAndCatalog(
        struct CCbsSession *this,
        const wchar_t *a2,
        const wchar_t *a3)
{
  wchar_t *v6; // rsi
  unsigned int v7; // r15d
  int v8; // edx
  __int64 v9; // rdx
  int v10; // edx
  int v11; // edx
  int PackageStoreDirectory; // eax
  int v13; // edx
  unsigned __int64 v14; // r9
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  wchar_t *v19; // r14
  int v20; // eax
  int v21; // eax
  int v22; // eax
  const WCHAR *v23; // rbx
  LPCWSTR v24; // rdi
  signed int LastError; // esi
  int v26; // edx
  unsigned int v27; // eax
  __int64 v28; // rdx
  const WCHAR *v29; // rbx
  LPCWSTR v30; // rdi
  int v31; // edx
  unsigned int v32; // eax
  int v33; // eax
  CCbsSession *v34; // rcx
  __int64 v35; // r8
  int OfflineWindowsDirectory; // eax
  int v37; // edx
  __int64 v38; // rdi
  int v39; // eax
  int v40; // edx
  int v41; // eax
  int v42; // edx
  const WCHAR *v43; // rdi
  const WCHAR *v44; // rbx
  int v45; // edx
  unsigned int v46; // eax
  unsigned int v48; // [rsp+20h] [rbp-79h]
  int v49[2]; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v50[2]; // [rsp+38h] [rbp-61h] BYREF
  int *v51; // [rsp+40h] [rbp-59h] BYREF
  wchar_t *v52; // [rsp+48h] [rbp-51h] BYREF
  wchar_t *v53; // [rsp+50h] [rbp-49h] BYREF
  __int64 v54; // [rsp+58h] [rbp-41h] BYREF
  LPCWSTR v55; // [rsp+60h] [rbp-39h] BYREF
  LPCWSTR lpNewFileName; // [rsp+68h] [rbp-31h] BYREF
  LPCWSTR lpFileName; // [rsp+70h] [rbp-29h] BYREF
  LPCWSTR v58; // [rsp+78h] [rbp-21h] BYREF
  LPCWSTR v59; // [rsp+80h] [rbp-19h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+88h] [rbp-11h] BYREF
  _BYTE v61[24]; // [rsp+90h] [rbp-9h] BYREF
  int v62; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v52 = 0;
  lpExistingFileName = 0;
  v59 = 0;
  v58 = 0;
  lpFileName = 0;
  lpNewFileName = 0;
  v6 = 0;
  v55 = 0;
  v54 = 0;
  v53 = 0;
  MonitoredCritSecLocker::MonitoredCritSecLocker(
    (MonitoredCritSecLocker *)v61,
    (struct AutoMonitoredCritSec *)&vPackageStoreLock,
    1);
  if ( this )
  {
    if ( !a2 )
    {
      v7 = -2147024809;
      v62 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No package identity specified");
        *(_QWORD *)v49 = &v62;
        LOBYTE(v10) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v10,
          3,
          (unsigned int)": {}",
          (__int64)v49);
      }
      v9 = 8631;
      goto LABEL_17;
    }
    if ( !a3 )
    {
      v7 = -2147024809;
      v62 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No source path specified");
        *(_QWORD *)v49 = &v62;
        LOBYTE(v11) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v11,
          3,
          (unsigned int)": {}",
          (__int64)v49);
      }
      v9 = 8632;
      goto LABEL_17;
    }
    PackageStoreDirectory = CCbsSession::GetPackageStoreDirectory(this, &v52);
    v7 = PackageStoreDirectory;
    if ( PackageStoreDirectory < 0 )
    {
      v62 = PackageStoreDirectory;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get package store directory.");
        *(_QWORD *)v49 = &v62;
        LOBYTE(v13) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v13,
          3,
          (unsigned int)": {}",
          (__int64)v49);
      }
      v9 = 8638;
      goto LABEL_17;
    }
    v15 = SczEnsureBackslashTerminated(&v52);
    v7 = v15;
    if ( v15 < 0 )
    {
      v14 = (unsigned int)v15;
      v9 = 8640;
      goto LABEL_18;
    }
    v16 = SczAllocFormatted(&lpExistingFileName, L"%ws%ws.mum", a3, a2);
    v7 = v16;
    if ( v16 < 0 )
    {
      v14 = (unsigned int)v16;
      v9 = 8642;
      goto LABEL_18;
    }
    v17 = SczAllocFormatted(&v59, L"%ws%ws.cat", a3, a2);
    v7 = v17;
    if ( v17 < 0 )
    {
      v14 = (unsigned int)v17;
      v9 = 8644;
      goto LABEL_18;
    }
    v18 = SczAllocFormatted(&v58, L"%ws%ws.ses", a3, a2);
    v7 = v18;
    if ( v18 < 0 )
    {
      v14 = (unsigned int)v18;
      v9 = 8646;
      goto LABEL_18;
    }
    v19 = v52;
    v20 = SczAllocFormatted(&lpFileName, L"%ws%ws.mum", v52, a2);
    v7 = v20;
    if ( v20 < 0 )
    {
      v14 = (unsigned int)v20;
      v9 = 8648;
      goto LABEL_18;
    }
    v21 = SczAllocFormatted(&lpNewFileName, L"%ws%ws.cat", v19, a2);
    v7 = v21;
    if ( v21 < 0 )
    {
      v14 = (unsigned int)v21;
      v9 = 8650;
      goto LABEL_18;
    }
    v22 = SczAllocFormatted(&v55, L"%ws%ws.ses", v19, a2);
    v7 = v22;
    if ( v22 < 0 )
    {
      v14 = (unsigned int)v22;
      v9 = 8652;
      goto LABEL_18;
    }
    v23 = lpFileName;
    if ( GetFileAttributesW(lpFileName) != -1 )
      SetFileAttributesW(v23, 0x80u);
    v24 = lpExistingFileName;
    if ( MoveFileExW(lpExistingFileName, v23, 1u) )
    {
      v29 = lpNewFileName;
      if ( GetFileAttributesW(lpNewFileName) != -1 )
        SetFileAttributesW(v29, 0x80u);
      v30 = v59;
      if ( MoveFileExW(v59, v29, 1u) )
      {
        v33 = SczAllocFormatted(&v54, L"%s.cat", a2);
        v7 = v33;
        if ( v33 < 0 )
        {
          v14 = (unsigned int)v33;
          v9 = 8673;
          goto LABEL_18;
        }
        if ( (unsigned int)CCbsSession::IsOffline(this) )
        {
          OfflineWindowsDirectory = CCbsSession::GetOfflineWindowsDirectory(v34, &v53);
          v7 = OfflineWindowsDirectory;
          if ( OfflineWindowsDirectory < 0 )
          {
            v62 = OfflineWindowsDirectory;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed to get offline windows directory.");
              *(_QWORD *)v50 = &v62;
              LOBYTE(v37) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v37,
                3,
                (unsigned int)": {}",
                (__int64)v50);
            }
            v9 = 8678;
            goto LABEL_17;
          }
          v6 = v53;
        }
        v38 = v54;
        LOBYTE(v35) = 1;
        v39 = CbsRemoveCatalogFile(v6, v54, v35);
        v7 = v39;
        if ( v39 < 0 )
        {
          v62 = v39;
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v50 = v38;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to revoke package catalog '{}' from catroot",
              (__int64)v50);
            v51 = &v62;
            LOBYTE(v40) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v40,
              3,
              (unsigned int)": {}",
              (__int64)&v51);
          }
          v9 = 8684;
          goto LABEL_17;
        }
        v41 = CbsInstallCatalogFile(v6, v29, v38);
        v7 = v41;
        if ( v41 < 0 )
        {
          v62 = v41;
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v50 = v38;
            v51 = (int *)v19;
            LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to publish package catalog '{}{}' to catroot",
              (__int64)&v51,
              (__int64)v50);
            *(_QWORD *)v49 = &v62;
            LOBYTE(v42) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v42,
              3,
              (unsigned int)": {}",
              (__int64)v49);
          }
          v9 = 8687;
          goto LABEL_17;
        }
        v43 = v58;
        if ( (unsigned int)DoesFileExist(v58, 0) )
        {
          v44 = v55;
          if ( GetFileAttributesW(v55) != -1 )
            SetFileAttributesW(v44, 0x80u);
          if ( !MoveFileExW(v43, v44, 1u) )
          {
            LastError = GetLastError();
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v50 = v44;
              v51 = (int *)v43;
              LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to move package session source '{}' to target: {}",
                (__int64)&v51,
                (__int64)v50);
              if ( LastError > 0 )
                v46 = (unsigned __int16)LastError | 0x80070000;
              else
                v46 = LastError;
              v62 = v46;
              LOBYTE(v45) = 1;
              *(_QWORD *)v49 = &v62;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v45,
                3,
                (unsigned int)": {0}",
                (__int64)v49);
            }
            if ( LastError )
            {
              v28 = 8697;
              goto LABEL_43;
            }
          }
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v50 = v29;
          v51 = (int *)v30;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to move package catalog '{}' to store: {}",
            (__int64)&v51,
            (__int64)v50);
          if ( LastError > 0 )
            v32 = (unsigned __int16)LastError | 0x80070000;
          else
            v32 = LastError;
          v62 = v32;
          LOBYTE(v31) = 1;
          *(_QWORD *)v49 = &v62;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v31,
            3,
            (unsigned int)": {0}",
            (__int64)v49);
        }
        if ( LastError )
        {
          v28 = 8668;
          goto LABEL_43;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v49 = v23;
        v51 = (int *)v24;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to move package manifest '{}' to store: {}",
          (__int64)&v51,
          (__int64)v49);
        if ( LastError > 0 )
          v27 = (unsigned __int16)LastError | 0x80070000;
        else
          v27 = LastError;
        v62 = v27;
        LOBYTE(v26) = 1;
        *(_QWORD *)v50 = &v62;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v26,
          3,
          (unsigned int)": {0}",
          (__int64)v50);
      }
      if ( LastError )
      {
        v28 = 8660;
LABEL_43:
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v28,
               (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
               (const char *)(unsigned int)LastError,
               v48);
        goto LABEL_82;
      }
    }
    v7 = 0;
    goto LABEL_82;
  }
  v7 = -2147024809;
  v62 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No session specified");
    *(_QWORD *)v49 = &v62;
    LOBYTE(v8) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v8,
      3,
      (unsigned int)": {}",
      (__int64)v49);
  }
  v9 = 8630;
LABEL_17:
  v14 = v7;
LABEL_18:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
    (const char *)v14,
    v48);
LABEL_82:
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v61);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v53);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v54);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v55);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v58);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v59);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v52);
  return v7;
}

```

## disassembly

```asm
0x1800ca250  mov     [rsp-8+arg_18], rbx
0x1800ca255  push    rbp
0x1800ca256  push    rsi
0x1800ca257  push    rdi
0x1800ca258  push    r12
0x1800ca25a  push    r13
0x1800ca25c  push    r14
0x1800ca25e  push    r15
0x1800ca260  lea     rbp, [rsp-27h]
0x1800ca265  sub     rsp, 0C0h
0x1800ca26c  mov     rax, cs:__security_cookie
0x1800ca273  xor     rax, rsp
0x1800ca276  mov     [rbp+57h+var_40], rax
0x1800ca27a  xor     edi, edi
0x1800ca27c  mov     rbx, r8
0x1800ca27f  mov     r12, rdx
0x1800ca282  mov     [rbp+57h+var_A8], rdi
0x1800ca286  mov     r13, rcx
0x1800ca289  mov     [rbp+57h+lpExistingFileName], rdi
0x1800ca28d  mov     r8b, 1; bool
0x1800ca290  mov     [rbp+57h+var_70], rdi
0x1800ca294  lea     rdx, ?vPackageStoreLock@@3UMonitoredCritSec@@A; struct AutoMonitoredCritSec *
0x1800ca29b  mov     [rbp+57h+var_78], rdi
0x1800ca29f  lea     rcx, [rbp+57h+var_60]; this
0x1800ca2a3  mov     [rbp+57h+lpFileName], rdi
0x1800ca2a7  mov     [rbp+57h+lpNewFileName], rdi
0x1800ca2ab  mov     esi, edi
0x1800ca2ad  mov     [rbp+57h+var_90], rdi
0x1800ca2b1  mov     [rbp+57h+var_98], rdi
0x1800ca2b5  mov     [rbp+57h+var_A0], rdi
0x1800ca2b9  call    ??0MonitoredCritSecLocker@@QEAA@AEAVAutoMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(AutoMonitoredCritSec &,bool)
0x1800ca2be  test    r13, r13
0x1800ca2c1  jnz     short loc_1800CA320
0x1800ca2c3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ca2ca  mov     r15d, 80070057h
0x1800ca2d0  mov     [rbp+57h+var_48], r15d
0x1800ca2d4  test    rcx, rcx
0x1800ca2d7  jz      short loc_1800CA316
0x1800ca2d9  lea     ebx, [rdi+3]
0x1800ca2dc  xor     edx, edx
0x1800ca2de  mov     r8d, ebx
0x1800ca2e1  lea     r9, aNoSessionSpeci_0; "No session specified"
0x1800ca2e8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800ca2ed  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ca2f4  lea     rax, [rbp+57h+var_48]
0x1800ca2f8  mov     qword ptr [rbp+57h+var_C0], rax
0x1800ca2fc  lea     r9, asc_1802EE7AC; ": {}"
0x1800ca303  lea     rax, [rbp+57h+var_C0]
0x1800ca307  mov     r8d, ebx
0x1800ca30a  mov     dl, 1
0x1800ca30c  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1800ca311  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ca316  mov     edx, 21B6h
0x1800ca31b  jmp     loc_1800CA44B
0x1800ca320  test    r12, r12
0x1800ca323  jnz     short loc_1800CA384
0x1800ca325  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ca32c  mov     r15d, 80070057h
0x1800ca332  mov     [rbp+57h+var_48], r15d
0x1800ca336  test    rcx, rcx
0x1800ca339  jz      short loc_1800CA37A
0x1800ca33b  lea     ebx, [r12+3]
0x1800ca340  xor     edx, edx
0x1800ca342  mov     r8d, ebx
0x1800ca345  lea     r9, aNoPackageIdent_0; "No package identity specified"
0x1800ca34c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800ca351  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ca358  lea     rax, [rbp+57h+var_48]
0x1800ca35c  mov     qword ptr [rbp+57h+var_C0], rax
0x1800ca360  lea     r9, asc_1802EE7AC; ": {}"
0x1800ca367  lea     rax, [rbp+57h+var_C0]
0x1800ca36b  mov     r8d, ebx
0x1800ca36e  mov     dl, 1
0x1800ca370  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1800ca375  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ca37a  mov     edx, 21B7h
0x1800ca37f  jmp     loc_1800CA44B
0x1800ca384  test    rbx, rbx
0x1800ca387  jnz     short loc_1800CA3E5
0x1800ca389  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ca390  mov     r15d, 80070057h
0x1800ca396  mov     [rbp+57h+var_48], r15d
0x1800ca39a  test    rcx, rcx
0x1800ca39d  jz      short loc_1800CA3DE
0x1800ca39f  mov     ebx, 3
0x1800ca3a4  lea     r9, aNoSourcePathSp; "No source path specified"
0x1800ca3ab  mov     r8d, ebx
0x1800ca3ae  xor     edx, edx
0x1800ca3b0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800ca3b5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ca3bc  lea     rax, [rbp+57h+var_48]
0x1800ca3c0  mov     qword ptr [rbp+57h+var_C0], rax
0x1800ca3c4  lea     r9, asc_1802EE7AC; ": {}"
0x1800ca3cb  lea     rax, [rbp+57h+var_C0]
0x1800ca3cf  mov     r8d, ebx
0x1800ca3d2  mov     dl, 1
0x1800ca3d4  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1800ca3d9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ca3de  mov     edx, 21B8h
0x1800ca3e3  jmp     short loc_1800CA44B
0x1800ca3e5  lea     rdx, [rbp+57h+var_A8]; wchar_t **
0x1800ca3e9  mov     rcx, r13; this
0x1800ca3ec  call    ?GetPackageStoreDirectory@CCbsSession@@QEAAJPEAPEA_W@Z; CCbsSession::GetPackageStoreDirectory(wchar_t * *)
0x1800ca3f1  mov     r15d, eax
0x1800ca3f4  test    eax, eax
0x1800ca3f6  jns     short loc_1800CA463
0x1800ca3f8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ca3ff  mov     [rbp+57h+var_48], eax
0x1800ca402  test    rcx, rcx
0x1800ca405  jz      short loc_1800CA446
0x1800ca407  mov     ebx, 3
0x1800ca40c  lea     r9, aFailedToGetPac_19; "Failed to get package store directory."
0x1800ca413  mov     r8d, ebx
0x1800ca416  xor     edx, edx
0x1800ca418  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800ca41d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ca424  lea     rax, [rbp+57h+var_48]
0x1800ca428  mov     qword ptr [rbp+57h+var_C0], rax
0x1800ca42c  lea     r9, asc_1802EE7AC; ": {}"
0x1800ca433  lea     rax, [rbp+57h+var_C0]
0x1800ca437  mov     r8d, ebx
0x1800ca43a  mov     dl, 1
0x1800ca43c  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x1800ca441  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ca446  mov     edx, 21BEh; void *
0x1800ca44b  mov     r9d, r15d; char *
0x1800ca44e  mov     rcx, [rbp+5Fh]; this
0x1800ca452  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x1800ca459  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca45e  jmp     loc_1800CA9FB
0x1800ca463  lea     rcx, [rbp+57h+var_A8]
0x1800ca467  call    SczEnsureBackslashTerminated
0x1800ca46c  mov     r15d, eax
0x1800ca46f  test    eax, eax
0x1800ca471  jns     short loc_1800CA47D
0x1800ca473  mov     r9d, eax
0x1800ca476  mov     edx, 21C0h
0x1800ca47b  jmp     short loc_1800CA44E
0x1800ca47d  mov     r9, r12
0x1800ca480  lea     rdx, aWsWsMum; "%ws%ws.mum"
0x1800ca487  mov     r8, rbx
0x1800ca48a  lea     rcx, [rbp+57h+lpExistingFileName]
0x1800ca48e  call    SczAllocFormatted
0x1800ca493  mov     r15d, eax
0x1800ca496  test    eax, eax
0x1800ca498  jns     short loc_1800CA4A4
0x1800ca49a  mov     r9d, eax
0x1800ca49d  mov     edx, 21C2h
0x1800ca4a2  jmp     short loc_1800CA44E
0x1800ca4a4  mov     r9, r12
0x1800ca4a7  lea     rdx, aWsWsCat; "%ws%ws.cat"
0x1800ca4ae  mov     r8, rbx
0x1800ca4b1  lea     rcx, [rbp+57h+var_70]
0x1800ca4b5  call    SczAllocFormatted
0x1800ca4ba  mov     r15d, eax
0x1800ca4bd  test    eax, eax
0x1800ca4bf  jns     short loc_1800CA4CB
0x1800ca4c1  mov     r9d, eax
0x1800ca4c4  mov     edx, 21C4h
0x1800ca4c9  jmp     short loc_1800CA44E
0x1800ca4cb  mov     r9, r12
0x1800ca4ce  lea     rdx, aWsWsSes; "%ws%ws.ses"
0x1800ca4d5  mov     r8, rbx
0x1800ca4d8  lea     rcx, [rbp+57h+var_78]
0x1800ca4dc  call    SczAllocFormatted
0x1800ca4e1  mov     r15d, eax
0x1800ca4e4  test    eax, eax
0x1800ca4e6  jns     short loc_1800CA4F5
0x1800ca4e8  mov     r9d, eax
0x1800ca4eb  mov     edx, 21C6h
0x1800ca4f0  jmp     loc_1800CA44E
0x1800ca4f5  mov     r14, [rbp+57h+var_A8]
0x1800ca4f9  lea     rdx, aWsWsMum; "%ws%ws.mum"
0x1800ca500  mov     r8, r14
0x1800ca503  lea     rcx, [rbp+57h+lpFileName]
0x1800ca507  mov     r9, r12
0x1800ca50a  call    SczAllocFormatted
0x1800ca50f  mov     r15d, eax
0x1800ca512  test    eax, eax
0x1800ca514  jns     short loc_1800CA523
0x1800ca516  mov     r9d, eax
0x1800ca519  mov     edx, 21C8h
0x1800ca51e  jmp     loc_1800CA44E
0x1800ca523  mov     r9, r12
0x1800ca526  lea     rdx, aWsWsCat; "%ws%ws.cat"
0x1800ca52d  mov     r8, r14
0x1800ca530  lea     rcx, [rbp+57h+lpNewFileName]
0x1800ca534  call    SczAllocFormatted
0x1800ca539  mov     r15d, eax
0x1800ca53c  test    eax, eax
0x1800ca53e  jns     short loc_1800CA54D
0x1800ca540  mov     r9d, eax
0x1800ca543  mov     edx, 21CAh
0x1800ca548  jmp     loc_1800CA44E
0x1800ca54d  mov     r9, r12
0x1800ca550  lea     rdx, aWsWsSes; "%ws%ws.ses"
0x1800ca557  mov     r8, r14
0x1800ca55a  lea     rcx, [rbp+57h+var_90]
0x1800ca55e  call    SczAllocFormatted
0x1800ca563  mov     r15d, eax
0x1800ca566  test    eax, eax
0x1800ca568  jns     short loc_1800CA577
0x1800ca56a  mov     r9d, eax
0x1800ca56d  mov     edx, 21CCh
0x1800ca572  jmp     loc_1800CA44E
0x1800ca577  mov     rbx, [rbp+57h+lpFileName]
0x1800ca57b  mov     rcx, rbx; lpFileName
0x1800ca57e  call    cs:__imp_GetFileAttributesW
0x1800ca585  nop     dword ptr [rax+rax+00h]
0x1800ca58a  cmp     eax, 0FFFFFFFFh
0x1800ca58d  jz      short loc_1800CA5A3
0x1800ca58f  mov     edx, 80h; dwFileAttributes
0x1800ca594  mov     rcx, rbx; lpFileName
0x1800ca597  call    cs:__imp_SetFileAttributesW
0x1800ca59e  nop     dword ptr [rax+rax+00h]
0x1800ca5a3  mov     rdi, [rbp+57h+lpExistingFileName]
0x1800ca5a7  mov     r15d, 1
0x1800ca5ad  mov     r8d, r15d; dwFlags
0x1800ca5b0  mov     rcx, rdi; lpExistingFileName
0x1800ca5b3  mov     rdx, rbx; lpNewFileName
0x1800ca5b6  call    cs:__imp_MoveFileExW
0x1800ca5bd  nop     dword ptr [rax+rax+00h]
0x1800ca5c2  test    eax, eax
0x1800ca5c4  jnz     loc_1800CA678
0x1800ca5ca  call    cs:__imp_GetLastError
0x1800ca5d1  nop     dword ptr [rax+rax+00h]
0x1800ca5d6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ca5dd  mov     esi, eax
0x1800ca5df  test    rcx, rcx
0x1800ca5e2  jz      short loc_1800CA650
0x1800ca5e4  lea     rax, [rbp+57h+var_C0]
0x1800ca5e8  mov     qword ptr [rbp+57h+var_C0], rbx
0x1800ca5ec  mov     [rsp+0F0h+var_C8], rax
0x1800ca5f1  lea     ebx, [r15+2]
0x1800ca5f5  lea     rax, [rbp+57h+var_B0]
0x1800ca5f9  mov     [rbp+57h+var_B0], rdi
0x1800ca5fd  lea     r9, aFailedToMovePa; "Failed to move package manifest '{}' to"...
0x1800ca604  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1800ca609  mov     r8d, ebx
0x1800ca60c  xor     edx, edx
0x1800ca60e  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1800ca613  test    esi, esi
0x1800ca615  jg      short loc_1800CA61B
0x1800ca617  mov     eax, esi
0x1800ca619  jmp     short loc_1800CA623
0x1800ca61b  movzx   eax, si
0x1800ca61e  or      eax, 80070000h
0x1800ca623  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ca62a  lea     r9, a0; ": {0}"
0x1800ca631  mov     [rbp+57h+var_48], eax
0x1800ca634  mov     r8d, ebx
0x1800ca637  lea     rax, [rbp+57h+var_48]
0x1800ca63b  mov     dl, r15b
0x1800ca63e  mov     qword ptr [rbp+57h+var_B8], rax
0x1800ca642  lea     rax, [rbp+57h+var_B8]
0x1800ca646  mov     qword ptr [rsp+0F0h+var_D0], rax; unsigned int
0x1800ca64b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ca650  test    esi, esi
0x1800ca652  jz      loc_1800CA9F8
0x1800ca658  mov     edx, 21D4h; void *
0x1800ca65d  mov     rcx, [rbp+5Fh]; this
0x1800ca661  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x1800ca668  mov     r9d, esi; char *
0x1800ca66b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ca670  mov     r15d, eax
0x1800ca673  jmp     loc_1800CA9FB
0x1800ca678  mov     rbx, [rbp+57h+lpNewFileName]
0x1800ca67c  mov     rcx, rbx; lpFileName
0x1800ca67f  call    cs:__imp_GetFileAttributesW
0x1800ca686  nop     dword ptr [rax+rax+00h]
0x1800ca68b  cmp     eax, 0FFFFFFFFh
0x1800ca68e  jz      short loc_1800CA6A4
0x1800ca690  mov     edx, 80h; dwFileAttributes
0x1800ca695  mov     rcx, rbx; lpFileName
0x1800ca698  call    cs:__imp_SetFileAttributesW
0x1800ca69f  nop     dword ptr [rax+rax+00h]
0x1800ca6a4  mov     rdi, [rbp+57h+var_70]
0x1800ca6a8  mov     r8d, r15d; dwFlags
0x1800ca6ab  mov     rcx, rdi; lpExistingFileName
0x1800ca6ae  mov     rdx, rbx; lpNewFileName
0x1800ca6b1  call    cs:__imp_MoveFileExW
0x1800ca6b8  nop     dword ptr [rax+rax+00h]
0x1800ca6bd  test    eax, eax
0x1800ca6bf  jnz     loc_1800CA75E
0x1800ca6c5  call    cs:__imp_GetLastError
0x1800ca6cc  nop     dword ptr [rax+rax+00h]
0x1800ca6d1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ca6d8  mov     esi, eax
0x1800ca6da  test    rcx, rcx
0x1800ca6dd  jz      short loc_1800CA74C
0x1800ca6df  lea     rax, [rbp+57h+var_B8]
0x1800ca6e3  mov     qword ptr [rbp+57h+var_B8], rbx
0x1800ca6e7  mov     [rsp+0F0h+var_C8], rax
0x1800ca6ec  lea     r9, aFailedToMovePa_0; "Failed to move package catalog '{}' to "...
0x1800ca6f3  lea     rax, [rbp+57h+var_B0]
0x1800ca6f7  mov     [rbp+57h+var_B0], rdi
0x1800ca6fb  mov     ebx, 3
0x1800ca700  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1800ca705  mov     r8d, ebx
0x1800ca708  xor     edx, edx
  ... truncated ...
```
