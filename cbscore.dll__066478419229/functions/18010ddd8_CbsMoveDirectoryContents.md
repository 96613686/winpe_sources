# CbsMoveDirectoryContents

- ea: `0x18010ddd8`
- end: `0x18010e70e`
- name: `CbsMoveDirectoryContents`
- size: `2358`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update`

## callers

- `0x1800caa88`
- `0x18010ddd8`

## callees

- `0x180013250`
- `0x180015420`
- `0x18002e224`
- `0x18002e280`
- `0x18004e554`
- `0x180055fc8`
- `0x180059a00`
- `0x18005aa38`
- `0x180093c4c`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a658c`
- `0x1800be15c`
- `0x1800d0588`
- `0x1800eb920`
- `0x1800ec920`
- `0x1800fe364`
- `0x18010d444`
- `0x18010d5c4`
- `0x18010ddd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010e17d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010e21c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010e4a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010e53c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010e5d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010e17d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010e21c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010e4a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010e53c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010e5d8`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18010e333`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18010e333`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18010e006`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18010e006`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18010e2f2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18010e2f2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18010e1ef`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18010e1ef`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x18010e2b8`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x18010e2b8`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x18010e169`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x18010e277`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x18010e169`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x18010e277`

## string_xrefs

- `0x18010e1aa`: `Failed to copy file. Source: {} Target: {}`
- `0x18010e247`: `Unable to move file or directory; falling back to hardlink and delete-on-close. Source: {} Target: {}`
- `0x18010e36c`: `Failed to copy directory. Source: {} Target: {}`
- `0x18010e4ca`: `Failed to copy directory. Source: {} Target: {}`
- `0x18010e556`: `Failed to open file for delete-on-close`
- `0x18010e448`: `Failed to move directory contents. Source: {} Target: {}`
- `0x18010e616`: `Failed creating hardlink. Source: {} Target: {}`

## pseudocode

```c
__int64 __fastcall CbsMoveDirectoryContents(unsigned int a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  signed int v6; // r14d
  int v7; // edx
  __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // edx
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // edx
  int v14; // eax
  HANDLE FirstFileW; // rax
  HANDLE v16; // rsi
  int v17; // eax
  const wchar_t *v18; // r8
  LPCWSTR v19; // rbx
  LPCWSTR v20; // rdi
  signed int LastError; // esi
  int v22; // edx
  unsigned int v23; // eax
  const WCHAR *v24; // rdi
  const WCHAR *v25; // rbx
  HANDLE FileW; // rax
  int v27; // edx
  unsigned __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // rdx
  int v31; // edx
  int v32; // edx
  unsigned int v33; // eax
  signed int v34; // ebx
  int v35; // edx
  unsigned int v36; // eax
  signed int v37; // eax
  int v38; // edx
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  unsigned int v41[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpNewFileName; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR v44; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v45[2]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hFindFile; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+78h] [rbp-88h] BYREF
  __int64 v49; // [rsp+80h] [rbp-80h] BYREF
  char v50; // [rsp+88h] [rbp-78h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  v3 = a3;
  v48 = a3;
  lpFileName = 0;
  hFindFile = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v49 = 0;
  v50 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    LODWORD(v48) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No source folder specified");
      *(_QWORD *)v41 = &v48;
      LOBYTE(v7) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v7,
        3,
        (unsigned int)": {}",
        (__int64)v41);
    }
    v8 = 2147942487LL;
    v9 = 875;
    goto LABEL_16;
  }
  if ( !v3 )
  {
    v6 = -2147024809;
    LODWORD(v48) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No target folder specified");
      *(_QWORD *)v41 = &v48;
      LOBYTE(v10) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v10,
        3,
        (unsigned int)": {}",
        (__int64)v41);
    }
    v8 = 2147942487LL;
    v9 = 876;
    goto LABEL_16;
  }
  v11 = RtlSystemUtil::BackupRestorePrivilegeAcquisition::Acquire((RtlSystemUtil::BackupRestorePrivilegeAcquisition *)&v49);
  v12 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v48) = v11;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to acquire backup/restore");
      *(_QWORD *)v41 = &v48;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v13,
        3,
        (unsigned int)": {}",
        (__int64)v41);
    }
    v6 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x36F,
           (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
           (const char *)v12,
           dwCreationDisposition);
    goto LABEL_100;
  }
  v14 = SczAllocFromSz(&lpFileName, a2);
  v6 = v14;
  if ( v14 < 0 )
  {
    v9 = 881;
LABEL_15:
    v8 = (unsigned int)v14;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
      (const char *)v8,
      dwCreationDisposition);
    goto LABEL_100;
  }
  v14 = SczEnsureBackslashTerminated(&lpFileName);
  v6 = v14;
  if ( v14 < 0 )
  {
    v9 = 882;
    goto LABEL_15;
  }
  v14 = SczAllocConcatSz(&lpFileName, L"*.*");
  v6 = v14;
  if ( v14 < 0 )
  {
    v9 = 888;
    goto LABEL_15;
  }
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
    &hFindFile,
    FirstFileW);
  v16 = hFindFile;
  v6 = 0;
  if ( (char *)hFindFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    goto LABEL_100;
  lpExistingFileName = 0;
  lpNewFileName = 0;
  while ( 1 )
  {
    if ( FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2])
      || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::GetImpl'::`2'::impl)
      && (a1 & 4) != 0
      && (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      goto LABEL_57;
    }
    v17 = SczAllocFromSz(&lpExistingFileName, a2);
    v6 = v17;
    if ( v17 < 0 )
    {
      v29 = 919;
      goto LABEL_97;
    }
    v17 = SczEnsureBackslashTerminated(&lpExistingFileName);
    v6 = v17;
    if ( v17 < 0 )
    {
      v29 = 920;
      goto LABEL_97;
    }
    v17 = SczAllocConcatSz(&lpExistingFileName, FindFileData.cFileName);
    v6 = v17;
    if ( v17 < 0 )
    {
      v29 = 921;
      goto LABEL_97;
    }
    v17 = SczAllocFromSz(&lpNewFileName, v3);
    v6 = v17;
    if ( v17 < 0 )
    {
      v29 = 926;
      goto LABEL_97;
    }
    v17 = SczEnsureBackslashTerminated(&lpNewFileName);
    v6 = v17;
    if ( v17 < 0 )
    {
      v29 = 927;
      goto LABEL_97;
    }
    v17 = SczAllocConcatSz(&lpNewFileName, FindFileData.cFileName);
    v6 = v17;
    if ( v17 < 0 )
    {
      v29 = 928;
LABEL_97:
      v28 = (unsigned int)v17;
      goto LABEL_98;
    }
    if ( (a1 & 1) == 0 )
      break;
    v19 = lpNewFileName;
    v20 = lpExistingFileName;
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      v6 = RecursiveCopy(lpExistingFileName, lpNewFileName, v18);
      if ( v6 < 0 )
      {
        LODWORD(v48) = v6;
        if ( LogAdapter::g_Logger )
        {
          v44 = v19;
          *(_QWORD *)v41 = v20;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to copy directory. Source: {} Target: {}",
            (__int64)v41,
            (__int64)&v44);
          *(_QWORD *)v45 = &v48;
          LOBYTE(v27) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v27,
            3,
            (unsigned int)": {}",
            (__int64)v45);
        }
        v28 = (unsigned int)v6;
        v29 = 938;
        goto LABEL_98;
      }
      v6 = 0;
      goto LABEL_56;
    }
    v6 = 0;
    if ( !(unsigned int)PrivCopyFileExW(lpExistingFileName, lpNewFileName, 0, 0, 0, 2416) )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v45 = v19;
        v44 = v20;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to copy file. Source: {} Target: {}",
          (__int64)&v44,
          (__int64)v45);
        if ( LastError > 0 )
          v23 = (unsigned __int16)LastError | 0x80070000;
        else
          v23 = LastError;
        LODWORD(v48) = v23;
        LOBYTE(v22) = 1;
        *(_QWORD *)v41 = &v48;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v22,
          3,
          (unsigned int)": {0}",
          (__int64)v41);
      }
      if ( !LastError )
        goto LABEL_99;
      v30 = 948;
      goto LABEL_66;
    }
LABEL_56:
    v3 = v48;
LABEL_57:
    if ( !FindNextFileW(v16, &FindFileData) )
      goto LABEL_99;
  }
  v24 = lpNewFileName;
  v25 = lpExistingFileName;
  v6 = 0;
  if ( MoveFileExW(lpExistingFileName, lpNewFileName, 8u)
    || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::GetImpl'::`2'::impl)
    && (a1 & 2) != 0
    && GetLastError() == 183 )
  {
    goto LABEL_56;
  }
  *(_QWORD *)v41 = v24;
  v44 = v25;
  LogAdapter::TraceAtLevelLastError<wchar_t *,wchar_t *>(
    2,
    "Unable to move file or directory; falling back to hardlink and delete-on-close. Source: {} Target: {}",
    &v44,
    v41);
  if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
  {
    if ( !(unsigned int)PrivCopyFileExW(v25, v24, 0, 0, 0, 2544) )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v45 = v24;
        v44 = v25;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to copy directory. Source: {} Target: {}",
          (__int64)&v44,
          (__int64)v45);
        if ( LastError > 0 )
          v33 = (unsigned __int16)LastError | 0x80070000;
        else
          v33 = LastError;
        LODWORD(v48) = v33;
        LOBYTE(v32) = 1;
        *(_QWORD *)v41 = &v48;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v32,
          3,
          (unsigned int)": {0}",
          (__int64)v41);
      }
      if ( !LastError )
        goto LABEL_99;
      v30 = 984;
LABEL_66:
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v30,
             (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
             (const char *)(unsigned int)LastError,
             dwCreationDisposition);
      goto LABEL_99;
    }
    if ( (FindFileData.dwFileAttributes & 0x400) == 0 )
    {
      v6 = CbsMoveDirectoryContents(a1, v25, v24);
      if ( v6 < 0 )
      {
        LODWORD(v48) = v6;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v45 = v24;
          v44 = v25;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to move directory contents. Source: {} Target: {}",
            (__int64)&v44,
            (__int64)v45);
          *(_QWORD *)v41 = &v48;
          LOBYTE(v31) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v31,
            3,
            (unsigned int)": {}",
            (__int64)v41);
        }
        v28 = (unsigned int)v6;
        v29 = 994;
        goto LABEL_98;
      }
      v6 = 0;
    }
    goto LABEL_54;
  }
  if ( CreateHardLinkW(v24, v25, 0) )
  {
LABEL_54:
    *(_QWORD *)v41 = 0;
    FileW = CreateFileW(v25, 0x10000u, 7u, 0, 3u, 0x6000000u, 0);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
      v41,
      FileW);
    if ( (unsigned __int64)(*(_QWORD *)v41 - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v34 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to open file for delete-on-close");
        if ( v34 > 0 )
          v36 = (unsigned __int16)v34 | 0x80070000;
        else
          v36 = v34;
        LODWORD(v48) = v36;
        LOBYTE(v35) = 1;
        *(_QWORD *)v45 = &v48;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v35,
          3,
          (unsigned int)": {0}",
          (__int64)v45);
      }
      if ( v34 )
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x3F9,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
               (const char *)(unsigned int)v34,
               dwCreationDisposition);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(v41);
      goto LABEL_99;
    }
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(v41);
    goto LABEL_56;
  }
  v37 = GetLastError();
  v6 = v37;
  if ( v37 > 0 )
    v6 = (unsigned __int16)v37 | 0x80070000;
  LODWORD(v48) = v6;
  if ( LogAdapter::g_Logger )
  {
    *(_QWORD *)v45 = v24;
    v44 = v25;
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed creating hardlink. Source: {} Target: {}",
      (__int64)&v44,
      (__int64)v45);
    *(_QWORD *)v41 = &v48;
    LOBYTE(v38) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v38,
      3,
      (unsigned int)": {}",
      (__int64)v41);
  }
  if ( v6 < 0 )
  {
    v28 = (unsigned int)v6;
    v29 = 1002;
LABEL_98:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
      (const char *)v28,
      dwCreationDisposition);
  }
LABEL_99:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
LABEL_100:
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v49);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18010ddd8  mov     [rsp-8+arg_18], rbx
0x18010dddd  push    rbp
0x18010ddde  push    rsi
0x18010dddf  push    rdi
0x18010dde0  push    r12
0x18010dde2  push    r13
0x18010dde4  push    r14
0x18010dde6  push    r15
0x18010dde8  lea     rbp, [rsp-1F0h]
0x18010ddf0  sub     rsp, 2F0h
0x18010ddf7  mov     rax, cs:__security_cookie
0x18010ddfe  xor     rax, rsp
0x18010de01  mov     [rbp+220h+var_40], rax
0x18010de08  mov     rdi, r8
0x18010de0b  mov     [rsp+320h+var_2A8], r8
0x18010de10  mov     r13, rdx
0x18010de13  mov     r12d, ecx
0x18010de16  xor     esi, esi
0x18010de18  lea     rcx, [rbp+220h+FindFileData]; void *
0x18010de1c  xor     edx, edx; Val
0x18010de1e  mov     [rsp+320h+lpFileName], rsi
0x18010de23  mov     r8d, 250h; Size
0x18010de29  mov     [rsp+320h+hFindFile], rsi
0x18010de2e  call    memset_0
0x18010de33  mov     [rbp+220h+var_2A0], rsi
0x18010de37  mov     [rbp+220h+var_298], sil
0x18010de3b  test    r13, r13
0x18010de3e  jnz     short loc_18010DEA5
0x18010de40  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010de47  mov     r14d, 80070057h
0x18010de4d  mov     dword ptr [rsp+320h+var_2A8], r14d
0x18010de52  test    rcx, rcx
0x18010de55  jz      short loc_18010DE98
0x18010de57  lea     r15d, [rsi+3]
0x18010de5b  xor     edx, edx
0x18010de5d  mov     r8d, r15d
0x18010de60  lea     r9, aNoSourceFolder; "No source folder specified"
0x18010de67  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18010de6c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010de73  lea     rax, [rsp+320h+var_2A8]
0x18010de78  mov     qword ptr [rsp+320h+var_2E0], rax
0x18010de7d  lea     r9, asc_1802EE7AC; ": {}"
0x18010de84  lea     rax, [rsp+320h+var_2E0]
0x18010de89  mov     r8d, r15d
0x18010de8c  mov     dl, 1
0x18010de8e  mov     qword ptr [rsp+320h+dwCreationDisposition], rax
0x18010de93  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010de98  mov     r9d, r14d
0x18010de9b  mov     edx, 36Bh
0x18010dea0  jmp     loc_18010DFAE
0x18010dea5  test    rdi, rdi
0x18010dea8  jnz     short loc_18010DF0F
0x18010deaa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010deb1  mov     r14d, 80070057h
0x18010deb7  mov     dword ptr [rsp+320h+var_2A8], r14d
0x18010debc  test    rcx, rcx
0x18010debf  jz      short loc_18010DF02
0x18010dec1  lea     r15d, [rdi+3]
0x18010dec5  xor     edx, edx
0x18010dec7  mov     r8d, r15d
0x18010deca  lea     r9, aNoTargetFolder; "No target folder specified"
0x18010ded1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18010ded6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010dedd  lea     rax, [rsp+320h+var_2A8]
0x18010dee2  mov     qword ptr [rsp+320h+var_2E0], rax
0x18010dee7  lea     r9, asc_1802EE7AC; ": {}"
0x18010deee  lea     rax, [rsp+320h+var_2E0]
0x18010def3  mov     r8d, r15d
0x18010def6  mov     dl, 1
0x18010def8  mov     qword ptr [rsp+320h+dwCreationDisposition], rax
0x18010defd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010df02  mov     r9d, r14d
0x18010df05  mov     edx, 36Ch
0x18010df0a  jmp     loc_18010DFAE
0x18010df0f  lea     rcx, [rbp+220h+var_2A0]; this
0x18010df13  call    ?Acquire@BackupRestorePrivilegeAcquisition@RtlSystemUtil@@QEAAJXZ; RtlSystemUtil::BackupRestorePrivilegeAcquisition::Acquire(void)
0x18010df18  mov     ebx, eax
0x18010df1a  test    eax, eax
0x18010df1c  jns     short loc_18010DF92
0x18010df1e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010df25  mov     dword ptr [rsp+320h+var_2A8], eax
0x18010df29  test    rcx, rcx
0x18010df2c  jz      short loc_18010DF6F
0x18010df2e  mov     r15d, 3
0x18010df34  lea     r9, aFailedToAcquir; "Failed to acquire backup/restore"
0x18010df3b  mov     r8d, r15d
0x18010df3e  xor     edx, edx
0x18010df40  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18010df45  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010df4c  lea     rax, [rsp+320h+var_2A8]
0x18010df51  mov     qword ptr [rsp+320h+var_2E0], rax
0x18010df56  lea     r9, asc_1802EE7AC; ": {}"
0x18010df5d  lea     rax, [rsp+320h+var_2E0]
0x18010df62  mov     r8d, r15d
0x18010df65  mov     qword ptr [rsp+320h+dwCreationDisposition], rax; int
0x18010df6a  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18010df6f  mov     rcx, [rbp+228h]; this
0x18010df76  lea     r8, aOnecoreBaseCbs_48; "onecore\\base\\cbs\\util\\cbsfile2.cpp"
0x18010df7d  mov     r9d, ebx; char *
0x18010df80  mov     edx, 36Fh; void *
0x18010df85  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18010df8a  mov     r14d, eax
0x18010df8d  jmp     loc_18010E6C3
0x18010df92  mov     rdx, r13
0x18010df95  lea     rcx, [rsp+320h+lpFileName]
0x18010df9a  call    SczAllocFromSz
0x18010df9f  mov     r14d, eax
0x18010dfa2  test    eax, eax
0x18010dfa4  jns     short loc_18010DFC6
0x18010dfa6  mov     edx, 371h; void *
0x18010dfab  mov     r9d, eax; char *
0x18010dfae  mov     rcx, [rbp+228h]; this
0x18010dfb5  lea     r8, aOnecoreBaseCbs_48; "onecore\\base\\cbs\\util\\cbsfile2.cpp"
0x18010dfbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010dfc1  jmp     loc_18010E6C3
0x18010dfc6  lea     rcx, [rsp+320h+lpFileName]
0x18010dfcb  call    SczEnsureBackslashTerminated
0x18010dfd0  mov     r14d, eax
0x18010dfd3  test    eax, eax
0x18010dfd5  jns     short loc_18010DFDE
0x18010dfd7  mov     edx, 372h
0x18010dfdc  jmp     short loc_18010DFAB
0x18010dfde  lea     rdx, asc_1802FA280; "*.*"
0x18010dfe5  lea     rcx, [rsp+320h+lpFileName]
0x18010dfea  call    SczAllocConcatSz
0x18010dfef  mov     r14d, eax
0x18010dff2  test    eax, eax
0x18010dff4  jns     short loc_18010DFFD
0x18010dff6  mov     edx, 378h
0x18010dffb  jmp     short loc_18010DFAB
0x18010dffd  mov     rcx, [rsp+320h+lpFileName]; lpFileName
0x18010e002  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x18010e006  call    cs:__imp_FindFirstFileW
0x18010e00d  nop     dword ptr [rax+rax+00h]
0x18010e012  mov     rdx, rax
0x18010e015  lea     rcx, [rsp+320h+hFindFile]
0x18010e01a  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x18010e01f  mov     rsi, [rsp+320h+hFindFile]
0x18010e024  xor     r14d, r14d
0x18010e027  lea     rax, [rsi-1]
0x18010e02b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010e02f  ja      loc_18010E6C3
0x18010e035  mov     [rsp+320h+lpExistingFileName], r14
0x18010e03a  lea     r15d, [r14+3]
0x18010e03e  mov     [rsp+320h+lpNewFileName], r14
0x18010e043  cmp     [rbp+220h+FindFileData.cFileName], 2Eh ; '.'
0x18010e048  movzx   eax, [rbp+220h+FindFileData.cFileName+2]
0x18010e04c  jnz     short loc_18010E06F
0x18010e04e  test    ax, ax
0x18010e051  jz      loc_18010E32C
0x18010e057  cmp     [rbp+220h+FindFileData.cFileName], 2Eh ; '.'
0x18010e05c  jnz     short loc_18010E06F
0x18010e05e  cmp     ax, 2Eh ; '.'
0x18010e062  jnz     short loc_18010E06F
0x18010e064  cmp     [rbp+220h+FindFileData.cFileName+4], r14w
0x18010e069  jz      loc_18010E32C
0x18010e06f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::GetImpl(void)'::`2'::impl
0x18010e076  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::__private_IsEnabled(void)
0x18010e07b  test    al, al
0x18010e07d  jz      short loc_18010E08F
0x18010e07f  test    r12b, 4
0x18010e083  jz      short loc_18010E08F
0x18010e085  test    byte ptr [rbp+220h+FindFileData.dwFileAttributes], 10h
0x18010e089  jnz     loc_18010E32C
0x18010e08f  mov     rdx, r13
0x18010e092  lea     rcx, [rsp+320h+lpExistingFileName]
0x18010e097  call    SczAllocFromSz
0x18010e09c  mov     r14d, eax
0x18010e09f  test    eax, eax
0x18010e0a1  js      loc_18010E694
0x18010e0a7  lea     rcx, [rsp+320h+lpExistingFileName]
0x18010e0ac  call    SczEnsureBackslashTerminated
0x18010e0b1  mov     r14d, eax
0x18010e0b4  test    eax, eax
0x18010e0b6  js      loc_18010E68D
0x18010e0bc  lea     rdx, [rbp+220h+FindFileData.cFileName]
0x18010e0c0  lea     rcx, [rsp+320h+lpExistingFileName]
0x18010e0c5  call    SczAllocConcatSz
0x18010e0ca  mov     r14d, eax
0x18010e0cd  test    eax, eax
0x18010e0cf  js      loc_18010E686
0x18010e0d5  mov     rdx, rdi
0x18010e0d8  lea     rcx, [rsp+320h+lpNewFileName]
0x18010e0dd  call    SczAllocFromSz
0x18010e0e2  mov     r14d, eax
0x18010e0e5  test    eax, eax
0x18010e0e7  js      loc_18010E67F
0x18010e0ed  lea     rcx, [rsp+320h+lpNewFileName]
0x18010e0f2  call    SczEnsureBackslashTerminated
0x18010e0f7  mov     r14d, eax
0x18010e0fa  test    eax, eax
0x18010e0fc  js      loc_18010E678
0x18010e102  lea     rdx, [rbp+220h+FindFileData.cFileName]
0x18010e106  lea     rcx, [rsp+320h+lpNewFileName]
0x18010e10b  call    SczAllocConcatSz
0x18010e110  mov     r14d, eax
0x18010e113  test    eax, eax
0x18010e115  js      loc_18010E671
0x18010e11b  test    r12b, 1
0x18010e11f  jz      loc_18010E1D9
0x18010e125  test    byte ptr [rbp+220h+FindFileData.dwFileAttributes], 10h
0x18010e129  mov     rbx, [rsp+320h+lpNewFileName]
0x18010e12e  mov     rdi, [rsp+320h+lpExistingFileName]
0x18010e133  mov     rdx, rbx; wchar_t *
0x18010e136  mov     rcx, rdi; wchar_t *
0x18010e139  jz      short loc_18010E153
0x18010e13b  call    ?RecursiveCopy@@YAJPEB_W00@Z; RecursiveCopy(wchar_t const *,wchar_t const *,wchar_t const *)
0x18010e140  mov     r14d, eax
0x18010e143  test    eax, eax
0x18010e145  js      loc_18010E34C
0x18010e14b  xor     r14d, r14d
0x18010e14e  jmp     loc_18010E327
0x18010e153  xor     r14d, r14d
0x18010e156  mov     [rsp+320h+dwFlagsAndAttributes], 970h
0x18010e15e  xor     r9d, r9d
0x18010e161  mov     qword ptr [rsp+320h+dwCreationDisposition], r14
0x18010e166  xor     r8d, r8d
0x18010e169  call    cs:__imp_PrivCopyFileExW
0x18010e170  nop     dword ptr [rax+rax+00h]
0x18010e175  test    eax, eax
0x18010e177  jnz     loc_18010E327
0x18010e17d  call    cs:__imp_GetLastError
0x18010e184  nop     dword ptr [rax+rax+00h]
0x18010e189  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010e190  mov     esi, eax
0x18010e192  test    rcx, rcx
0x18010e195  jz      loc_18010E3FD
0x18010e19b  lea     rax, [rsp+320h+var_2C0]
0x18010e1a0  mov     qword ptr [rsp+320h+var_2C0], rbx
0x18010e1a5  mov     qword ptr [rsp+320h+dwFlagsAndAttributes], rax
0x18010e1aa  lea     r9, aFailedToCopyFi; "Failed to copy file. Source: {} Target:"...
0x18010e1b1  lea     rax, [rsp+320h+var_2C8]
0x18010e1b6  mov     [rsp+320h+var_2C8], rdi
0x18010e1bb  mov     r8d, r15d
0x18010e1be  mov     qword ptr [rsp+320h+dwCreationDisposition], rax
0x18010e1c3  xor     edx, edx
0x18010e1c5  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x18010e1ca  test    esi, esi
0x18010e1cc  jg      loc_18010E3C5
0x18010e1d2  mov     eax, esi
0x18010e1d4  jmp     loc_18010E3CD
0x18010e1d9  mov     rdi, [rsp+320h+lpNewFileName]
0x18010e1de  mov     r8d, 8; dwFlags
0x18010e1e4  mov     rbx, [rsp+320h+lpExistingFileName]
0x18010e1e9  mov     rdx, rdi; lpNewFileName
0x18010e1ec  mov     rcx, rbx; lpExistingFileName
0x18010e1ef  call    cs:__imp_MoveFileExW
0x18010e1f6  nop     dword ptr [rax+rax+00h]
0x18010e1fb  xor     r14d, r14d
0x18010e1fe  test    eax, eax
0x18010e200  jnz     loc_18010E327
0x18010e206  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::GetImpl(void)'::`2'::impl
0x18010e20d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PostponedInstallForRebasedLCUs>::__private_IsEnabled(void)
0x18010e212  test    al, al
0x18010e214  jz      short loc_18010E233
0x18010e216  test    r12b, 2
0x18010e21a  jz      short loc_18010E233
0x18010e21c  call    cs:__imp_GetLastError
0x18010e223  nop     dword ptr [rax+rax+00h]
0x18010e228  cmp     eax, 0B7h
0x18010e22d  jz      loc_18010E327
0x18010e233  lea     r9, [rsp+320h+var_2E0]
0x18010e238  mov     qword ptr [rsp+320h+var_2E0], rdi
0x18010e23d  lea     r8, [rsp+320h+var_2C8]
0x18010e242  mov     [rsp+320h+var_2C8], rbx
0x18010e247  lea     rdx, aUnableToMoveFi_0; "Unable to move file or directory; falli"...
0x18010e24e  mov     ecx, 2
0x18010e253  call    ??$TraceAtLevelLastError@PEA_WPEA_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEA_W2@Z; LogAdapter::TraceAtLevelLastError<wchar_t *,wchar_t *>(LogAdapter::LogLevel,char const * const,wchar_t * const &,wchar_t * const &)
0x18010e258  xor     r8d, r8d; lpSecurityAttributes
0x18010e25b  test    byte ptr [rbp+220h+FindFileData.dwFileAttributes], 10h
0x18010e25f  jz      short loc_18010E2B2
0x18010e261  mov     [rsp+320h+dwFlagsAndAttributes], 9F0h
0x18010e269  xor     r9d, r9d
0x18010e26c  mov     rdx, rdi
0x18010e26f  mov     qword ptr [rsp+320h+dwCreationDisposition], r14; int
0x18010e274  mov     rcx, rbx
0x18010e277  call    cs:__imp_PrivCopyFileExW
0x18010e27e  nop     dword ptr [rax+rax+00h]
0x18010e283  test    eax, eax
0x18010e285  jz      loc_18010E4A1
0x18010e28b  test    [rbp+220h+FindFileData.dwFileAttributes], 400h
0x18010e292  jnz     short loc_18010E2CC
0x18010e294  mov     r8, rdi
0x18010e297  mov     rdx, rbx
0x18010e29a  mov     ecx, r12d
0x18010e29d  call    CbsMoveDirectoryContents
0x18010e2a2  mov     r14d, eax
0x18010e2a5  test    eax, eax
0x18010e2a7  js      loc_18010E428
0x18010e2ad  xor     r14d, r14d
0x18010e2b0  jmp     short loc_18010E2CC
0x18010e2b2  mov     rdx, rbx; lpExistingFileName
0x18010e2b5  mov     rcx, rdi; lpFileName
0x18010e2b8  call    cs:__imp_CreateHardLinkW
0x18010e2bf  nop     dword ptr [rax+rax+00h]
0x18010e2c4  test    eax, eax
0x18010e2c6  jz      loc_18010E5D8
0x18010e2cc  xor     r9d, r9d; lpSecurityAttributes
0x18010e2cf  mov     [rsp+320h+hTemplateFile], r14; hTemplateFile
0x18010e2d4  mov     [rsp+320h+dwFlagsAndAttributes], 6000000h; dwFlagsAndAttributes
  ... truncated ...
```
