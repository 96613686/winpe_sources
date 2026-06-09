# CbsInstallCatalogFile

- ea: `0x180094320`
- end: `0x1800948f6`
- name: `CbsInstallCatalogFile`
- size: `1494`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x1800ca250`
- `0x1800cbe5c`

## callees

- `0x180013250`
- `0x180016d40`
- `0x180059a00`
- `0x18005ec58`
- `0x180093a4c`
- `0x180093a70`
- `0x180094320`
- `0x180094d38`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800b2fbc`
- `0x1800c0054`
- `0x1800eb920`
- `0x1801ecec8`
- `0x1801ecf04`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094571`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009462c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094571`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009462c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800947a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800947e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800947a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800947e0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800947cc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800947cc`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18009473f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18009473f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180094767`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180094767`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180094726`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180094726`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180094798`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180094798`

## string_xrefs

- `0x1800943a8`: `onecore\base\cbs\core\cbscataloginstallation.cpp`
- `0x180094510`: `onecore\base\cbs\core\cbscataloginstallation.cpp`
- `0x1800946f5`: `onecore\base\cbs\core\cbscataloginstallation.cpp`
- `0x180094890`: `onecore\base\cbs\core\cbscataloginstallation.cpp`
- `0x180094814`: `Failed to {} catalog {} to offline image path {}`
- `0x1800947fe`: `hardlink`
- `0x180094753`: `File already exists when adding the catalog: {}`
- `0x18009477f`: `Catalog [{}] exists in catroot and cannot be deleted.`
- `0x1800946d3`: `System32\CatRoot\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\`

## pseudocode

```c
__int64 __fastcall CbsInstallCatalogFile(__int64 a1, const WCHAR *a2, wchar_t *a3)
{
  unsigned int v4; // ebx
  int v5; // edx
  __int64 v6; // rdx
  int v8; // edx
  void **InitPointer; // rax
  unsigned int v10; // r8d
  signed int v11; // ebx
  int v12; // edx
  unsigned int v13; // eax
  __int64 v14; // rdx
  void *v15; // rax
  int v16; // edx
  unsigned int v17; // eax
  int WindowsDirectory; // eax
  int v19; // edx
  unsigned __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // eax
  const WCHAR *v23; // rbx
  BOOL HardLinkW; // edi
  DWORD LastError; // eax
  DWORD v26; // r14d
  signed int v27; // edi
  const wchar_t *v28; // rdx
  int v29; // edx
  unsigned int v30; // eax
  unsigned int v31; // [rsp+20h] [rbp-29h]
  unsigned int v32[2]; // [rsp+40h] [rbp-9h] BYREF
  int *v33; // [rsp+48h] [rbp-1h] BYREF
  wchar_t *v34; // [rsp+50h] [rbp+7h] BYREF
  void **p_lpFileName; // [rsp+58h] [rbp+Fh]
  LPCWSTR lpExistingFileName; // [rsp+60h] [rbp+17h] BYREF
  int v37; // [rsp+68h] [rbp+1Fh] BYREF
  LPCWSTR lpFileName; // [rsp+70h] [rbp+27h] BYREF
  struct _GUID v39; // [rsp+78h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  lpExistingFileName = a2;
  if ( !a2 )
  {
    v4 = -2147024809;
    v37 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No catalog location specified.");
      *(_QWORD *)v32 = &v37;
      LOBYTE(v5) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v5,
        3,
        (unsigned int)": {}",
        (__int64)v32);
    }
    v6 = 120;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\core\\cbscataloginstallation.cpp",
      (const char *)0x80070057LL,
      v31);
    return v4;
  }
  if ( !a3 )
  {
    v4 = -2147024809;
    v37 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No new catalog name specified.");
      *(_QWORD *)v32 = &v37;
      LOBYTE(v8) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v8,
        3,
        (unsigned int)": {}",
        (__int64)v32);
    }
    v6 = 121;
    goto LABEL_5;
  }
  if ( a1
    || !vpfnCryptCATAdminAcquireContext
    || !vpfnCryptCATAdminAddCatalog
    || !vpfnCryptCATAdminReleaseCatalogContext
    || !vpfnCryptCATAdminReleaseContext )
  {
    lpFileName = 0;
    *(_QWORD *)v32 = 0;
    if ( !a1 )
    {
      WindowsDirectory = PathGetWindowsDirectory(v32, 0);
      v4 = WindowsDirectory;
      if ( WindowsDirectory < 0 )
      {
        v37 = WindowsDirectory;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get online Windir");
          v33 = &v37;
          LOBYTE(v19) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v19,
            3,
            (unsigned int)": {}",
            (__int64)&v33);
        }
        v20 = v4;
        v21 = 158;
        goto LABEL_51;
      }
      a1 = *(_QWORD *)v32;
    }
    v22 = SczAllocConcat2Sz(&lpFileName, a1, L"System32\\CatRoot\\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\\");
    v4 = v22;
    if ( v22 >= 0 )
    {
      v22 = SczAllocConcatSz(&lpFileName, a3);
      v4 = v22;
      if ( v22 >= 0 )
      {
        v23 = lpFileName;
        if ( GetFileAttributesW(lpFileName) != -1 )
        {
          SetFileAttributesW(v23, 0x80u);
          v33 = (int *)v23;
          LogAdapter::TraceAtLevel<wchar_t const *>(1, "File already exists when adding the catalog: {}", &v33);
          if ( !DeleteFileW(v23) )
          {
            v33 = (int *)v23;
            LogAdapter::TraceAtLevelLastError<wchar_t const *>(
              3,
              "Catalog [{}] exists in catroot and cannot be deleted.",
              &v33);
          }
        }
        HardLinkW = CreateHardLinkW(v23, lpExistingFileName, 0);
        LastError = GetLastError();
        v26 = LastError;
        if ( HardLinkW || LastError == 1 && CopyFileW(lpExistingFileName, v23, 0) )
        {
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v32);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
          return 0;
        }
        v27 = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          v33 = (int *)v23;
          v28 = L"copy";
          if ( v26 != 1 )
            v28 = L"hardlink";
          v34 = (wchar_t *)v28;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to {} catalog {} to offline image path {}",
            (__int64)&v34,
            (__int64)&lpExistingFileName,
            (__int64)&v33);
          if ( v27 > 0 )
            v30 = (unsigned __int16)v27 | 0x80070000;
          else
            v30 = v27;
          v37 = v30;
          LOBYTE(v29) = 1;
          *(_QWORD *)&v39.Data1 = &v37;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v29,
            3,
            (unsigned int)": {0}",
            (__int64)&v39);
        }
        if ( v27 )
          v4 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0xC0,
                 (unsigned int)"onecore\\base\\cbs\\core\\cbscataloginstallation.cpp",
                 (const char *)(unsigned int)v27,
                 v31);
        else
          v4 = 0;
LABEL_70:
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v32);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
        return v4;
      }
      v21 = 167;
    }
    else
    {
      v21 = 166;
    }
    v20 = (unsigned int)v22;
LABEL_51:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\base\\cbs\\core\\cbscataloginstallation.cpp",
      (const char *)v20,
      v31);
    goto LABEL_70;
  }
  lpFileName = 0;
  v39.Data1 = -145692989;
  *(_DWORD *)&v39.Data2 = 298924270;
  *(_DWORD *)v39.Data4 = -1073683067;
  *(_DWORD *)&v39.Data4[4] = -292175281;
  InitPointer = (void **)Windows::AutoGenericHandleBase_void___0_Windows::AutoGenericHandle_void___0__CloseWithCryptCATAdminReleaseContext___::GetInitPointer(&lpFileName);
  if ( (unsigned int)CbsDelayloadCryptCATAdminAcquireContext(InitPointer, &v39, v10) )
  {
    v34 = 0;
    p_lpFileName = (void **)&lpFileName;
    if ( vpfnCryptCATAdminAddCatalog )
    {
      v15 = vpfnCryptCATAdminAddCatalog((void *)lpFileName, (wchar_t *)lpExistingFileName, a3, 1u);
    }
    else
    {
      SetLastError(0x7Fu);
      v15 = 0;
    }
    Windows::AutoCustomDeleterHandleBase_void___0__CbsInstallCatalogFile_::_39_::_lambda_1__Windows::AutoCustomDeleterHandle_void___0__CbsInstallCatalogFile_::_39_::_lambda_1_____::TakeOwnership(
      &v34,
      v15);
    if ( v34 )
    {
      if ( vpfnCryptCATAdminReleaseCatalogContext )
        vpfnCryptCATAdminReleaseCatalogContext(*p_lpFileName, v34, 0);
      else
        SetLastError(0x7Fu);
    }
    else
    {
      v11 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed call to CryptCATAdminAddCatalog");
        if ( v11 > 0 )
          v17 = (unsigned __int16)v11 | 0x80070000;
        else
          v17 = v11;
        v37 = v17;
        LOBYTE(v16) = 1;
        *(_QWORD *)v32 = &v37;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v16,
          3,
          (unsigned int)": {0}",
          (__int64)v32);
      }
      if ( v11 )
      {
        v14 = 148;
LABEL_24:
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v14,
               (unsigned int)"onecore\\base\\cbs\\core\\cbscataloginstallation.cpp",
               (const char *)(unsigned int)v11,
               v31);
        if ( lpFileName )
          CloseWithCryptCATAdminReleaseContext();
        return v4;
      }
    }
  }
  else
  {
    v11 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed call to CryptCATAdminAcquireContext.");
      if ( v11 > 0 )
        v13 = (unsigned __int16)v11 | 0x80070000;
      else
        v13 = v11;
      v37 = v13;
      LOBYTE(v12) = 1;
      *(_QWORD *)v32 = &v37;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v12,
        3,
        (unsigned int)": {0}",
        (__int64)v32);
    }
    if ( v11 )
    {
      v14 = 141;
      goto LABEL_24;
    }
  }
  if ( lpFileName )
    CloseWithCryptCATAdminReleaseContext();
  return 0;
}

```

## disassembly

```asm
0x180094320  mov     [rsp-8+arg_18], rbx
0x180094325  push    rbp
0x180094326  push    rdi
0x180094327  push    r14
0x180094329  lea     rbp, [rsp-47h]
0x18009432e  sub     rsp, 90h
0x180094335  mov     rax, cs:__security_cookie
0x18009433c  xor     rax, rsp
0x18009433f  mov     [rbp+57h+var_18], rax
0x180094343  mov     [rbp+57h+lpExistingFileName], rdx
0x180094347  mov     rdi, r8
0x18009434a  test    rdx, rdx
0x18009434d  jnz     short loc_1800943BE
0x18009434f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180094356  mov     ebx, 80070057h
0x18009435b  mov     [rbp+57h+var_38], ebx
0x18009435e  test    rcx, rcx
0x180094361  jz      short loc_18009439F
0x180094363  lea     r9, aNoCatalogLocat; "No catalog location specified."
0x18009436a  lea     r8d, [rdx+3]
0x18009436e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180094373  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009437a  lea     rax, [rbp+57h+var_38]
0x18009437e  mov     qword ptr [rbp+57h+var_60], rax
0x180094382  lea     r9, asc_1802EE7AC; ": {}"
0x180094389  lea     rax, [rbp+57h+var_60]
0x18009438d  mov     r8d, 3
0x180094393  mov     dl, 1
0x180094395  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x18009439a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009439f  mov     edx, 78h ; 'x'; void *
0x1800943a4  mov     rcx, [rbp+5Fh]; this
0x1800943a8  lea     r8, aOnecoreBaseCbs_56; "onecore\\base\\cbs\\core\\cbscatalogins"...
0x1800943af  mov     r9d, ebx; char *
0x1800943b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800943b7  mov     eax, ebx
0x1800943b9  jmp     loc_1800948D5
0x1800943be  test    rdi, rdi
0x1800943c1  jnz     short loc_18009441A
0x1800943c3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800943ca  mov     ebx, 80070057h
0x1800943cf  mov     [rbp+57h+var_38], ebx
0x1800943d2  test    rcx, rcx
0x1800943d5  jz      short loc_180094413
0x1800943d7  lea     r9, aNoNewCatalogNa; "No new catalog name specified."
0x1800943de  xor     edx, edx
0x1800943e0  lea     r8d, [rdi+3]
0x1800943e4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800943e9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800943f0  lea     rax, [rbp+57h+var_38]
0x1800943f4  mov     qword ptr [rbp+57h+var_60], rax
0x1800943f8  lea     r9, asc_1802EE7AC; ": {}"
0x1800943ff  lea     rax, [rbp+57h+var_60]
0x180094403  mov     dl, 1
0x180094405  lea     r8d, [rdi+3]
0x180094409  mov     qword ptr [rsp+0A0h+var_80], rax
0x18009440e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180094413  mov     edx, 79h ; 'y'
0x180094418  jmp     short loc_1800943A4
0x18009441a  test    rcx, rcx
0x18009441d  jnz     loc_18009464F
0x180094423  cmp     cs:?vpfnCryptCATAdminAcquireContext@@3P6AHPEAPEAXPEBU_GUID@@K@ZEA, rcx; int (*vpfnCryptCATAdminAcquireContext)(void * *,_GUID const *,ulong)
0x18009442a  jz      loc_18009464F
0x180094430  cmp     cs:?vpfnCryptCATAdminAddCatalog@@3P6APEAXPEAXPEA_W1K@ZEA, rcx; void * (*vpfnCryptCATAdminAddCatalog)(void *,wchar_t *,wchar_t *,ulong)
0x180094437  jz      loc_18009464F
0x18009443d  cmp     cs:?vpfnCryptCATAdminReleaseCatalogContext@@3P6AHPEAX0K@ZEA, rcx; int (*vpfnCryptCATAdminReleaseCatalogContext)(void *,void *,ulong)
0x180094444  jz      loc_18009464F
0x18009444a  cmp     cs:?vpfnCryptCATAdminReleaseContext@@3P6AHPEAXK@ZEA, rcx; int (*vpfnCryptCATAdminReleaseContext)(void *,ulong)
0x180094451  jz      loc_18009464F
0x180094457  mov     [rbp+57h+lpFileName], rcx
0x18009445b  lea     rcx, [rbp+57h+lpFileName]
0x18009445f  mov     [rbp+57h+var_28.Data1], 0F750E6C3h
0x180094466  mov     dword ptr [rbp+57h+var_28.Data2], 11D138EEh
0x18009446d  mov     dword ptr [rbp+57h+var_28.Data4], 0C000E585h
0x180094474  mov     dword ptr [rbp+57h+var_28.Data4+4], 0EE95C24Fh
0x18009447b  call    Windows__AutoGenericHandleBase_void___0_Windows__AutoGenericHandle_void___0__CloseWithCryptCATAdminReleaseContext_____GetInitPointer
0x180094480  mov     rcx, rax; void **
0x180094483  lea     rdx, [rbp+57h+var_28]; struct _GUID *
0x180094487  call    ?CbsDelayloadCryptCATAdminAcquireContext@@YAHPEAPEAXPEBU_GUID@@K@Z; CbsDelayloadCryptCATAdminAcquireContext(void * *,_GUID const *,ulong)
0x18009448c  test    eax, eax
0x18009448e  jnz     loc_180094538
0x180094494  call    cs:__imp_GetLastError
0x18009449b  nop     dword ptr [rax+rax+00h]
0x1800944a0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800944a7  mov     ebx, eax
0x1800944a9  test    rcx, rcx
0x1800944ac  jz      short loc_1800944FF
0x1800944ae  xor     edx, edx
0x1800944b0  lea     r9, aFailedCallToCr_0; "Failed call to CryptCATAdminAcquireCont"...
0x1800944b7  lea     r8d, [rdx+3]
0x1800944bb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800944c0  test    ebx, ebx
0x1800944c2  jg      short loc_1800944C8
0x1800944c4  mov     eax, ebx
0x1800944c6  jmp     short loc_1800944D0
0x1800944c8  movzx   eax, bx
0x1800944cb  or      eax, 80070000h
0x1800944d0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800944d7  lea     r9, a0; ": {0}"
0x1800944de  mov     [rbp+57h+var_38], eax
0x1800944e1  mov     r8d, 3
0x1800944e7  lea     rax, [rbp+57h+var_38]
0x1800944eb  mov     dl, 1
0x1800944ed  mov     qword ptr [rbp+57h+var_60], rax
0x1800944f1  lea     rax, [rbp+57h+var_60]
0x1800944f5  mov     qword ptr [rsp+0A0h+var_80], rax; unsigned int
0x1800944fa  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800944ff  test    ebx, ebx
0x180094501  jz      loc_180094638
0x180094507  mov     edx, 8Dh; void *
0x18009450c  mov     rcx, [rbp+5Fh]; this
0x180094510  lea     r8, aOnecoreBaseCbs_56; "onecore\\base\\cbs\\core\\cbscatalogins"...
0x180094517  mov     r9d, ebx; char *
0x18009451a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009451f  mov     rcx, [rbp+57h+lpFileName]
0x180094523  mov     ebx, eax
0x180094525  test    rcx, rcx
0x180094528  jz      loc_1800943B7
0x18009452e  call    CloseWithCryptCATAdminReleaseContext
0x180094533  jmp     loc_1800943B7
0x180094538  lea     rax, [rbp+57h+lpFileName]
0x18009453c  mov     [rbp+57h+var_50], 0
0x180094544  mov     [rbp+57h+var_48], rax
0x180094548  mov     ebx, 7Fh
0x18009454d  mov     rax, cs:?vpfnCryptCATAdminAddCatalog@@3P6APEAXPEAXPEA_W1K@ZEA; void * (*vpfnCryptCATAdminAddCatalog)(void *,wchar_t *,wchar_t *,ulong)
0x180094554  test    rax, rax
0x180094557  jz      short loc_18009456F
0x180094559  mov     rdx, [rbp+57h+lpExistingFileName]
0x18009455d  lea     r9d, [rbx-7Eh]
0x180094561  mov     rcx, [rbp+57h+lpFileName]
0x180094565  mov     r8, rdi
0x180094568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009456d  jmp     short loc_18009457F
0x18009456f  mov     ecx, ebx; dwErrCode
0x180094571  call    cs:__imp_SetLastError
0x180094578  nop     dword ptr [rax+rax+00h]
0x18009457d  xor     eax, eax
0x18009457f  mov     rdx, rax
0x180094582  lea     rcx, [rbp+57h+var_50]
0x180094586  call    Windows__AutoCustomDeleterHandleBase_void___0__CbsInstallCatalogFile____39____lambda_1__Windows__AutoCustomDeleterHandle_void___0__CbsInstallCatalogFile____39____lambda_1_______TakeOwnership
0x18009458b  mov     rdx, [rbp+57h+var_50]
0x18009458f  test    rdx, rdx
0x180094592  jnz     short loc_18009460D
0x180094594  call    cs:__imp_GetLastError
0x18009459b  nop     dword ptr [rax+rax+00h]
0x1800945a0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800945a7  mov     ebx, eax
0x1800945a9  test    rcx, rcx
0x1800945ac  jz      short loc_1800945FF
0x1800945ae  xor     edx, edx
0x1800945b0  lea     r9, aFailedCallToCr_1; "Failed call to CryptCATAdminAddCatalog"
0x1800945b7  lea     r8d, [rdx+3]
0x1800945bb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800945c0  test    ebx, ebx
0x1800945c2  jg      short loc_1800945C8
0x1800945c4  mov     eax, ebx
0x1800945c6  jmp     short loc_1800945D0
0x1800945c8  movzx   eax, bx
0x1800945cb  or      eax, 80070000h
0x1800945d0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800945d7  lea     r9, a0; ": {0}"
0x1800945de  mov     [rbp+57h+var_38], eax
0x1800945e1  mov     r8d, 3
0x1800945e7  lea     rax, [rbp+57h+var_38]
0x1800945eb  mov     dl, 1
0x1800945ed  mov     qword ptr [rbp+57h+var_60], rax
0x1800945f1  lea     rax, [rbp+57h+var_60]
0x1800945f5  mov     qword ptr [rsp+0A0h+var_80], rax
0x1800945fa  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800945ff  test    ebx, ebx
0x180094601  jz      short loc_180094638
0x180094603  mov     edx, 94h
0x180094608  jmp     loc_18009450C
0x18009460d  mov     rax, cs:?vpfnCryptCATAdminReleaseCatalogContext@@3P6AHPEAX0K@ZEA; int (*vpfnCryptCATAdminReleaseCatalogContext)(void *,void *,ulong)
0x180094614  test    rax, rax
0x180094617  jz      short loc_18009462A
0x180094619  mov     rcx, [rbp+57h+var_48]
0x18009461d  xor     r8d, r8d
0x180094620  mov     rcx, [rcx]
0x180094623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094628  jmp     short loc_180094638
0x18009462a  mov     ecx, ebx; dwErrCode
0x18009462c  call    cs:__imp_SetLastError
0x180094633  nop     dword ptr [rax+rax+00h]
0x180094638  mov     rcx, [rbp+57h+lpFileName]
0x18009463c  test    rcx, rcx
0x18009463f  jz      loc_1800948D3
0x180094645  call    CloseWithCryptCATAdminReleaseContext
0x18009464a  jmp     loc_1800948D3
0x18009464f  mov     [rbp+57h+lpFileName], 0
0x180094657  mov     qword ptr [rbp+57h+var_60], 0
0x18009465f  test    rcx, rcx
0x180094662  jnz     short loc_1800946D0
0x180094664  xor     edx, edx
0x180094666  lea     rcx, [rbp+57h+var_60]
0x18009466a  call    PathGetWindowsDirectory
0x18009466f  mov     ebx, eax
0x180094671  test    eax, eax
0x180094673  jns     short loc_1800946CC
0x180094675  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009467c  mov     [rbp+57h+var_38], eax
0x18009467f  test    rcx, rcx
0x180094682  jz      short loc_1800946C2
0x180094684  xor     edx, edx
0x180094686  lea     r9, aFailedToGetOnl; "Failed to get online Windir"
0x18009468d  lea     r8d, [rdx+3]
0x180094691  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180094696  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009469d  lea     rax, [rbp+57h+var_38]
0x1800946a1  mov     [rbp+57h+var_58], rax
0x1800946a5  lea     r9, asc_1802EE7AC; ": {}"
0x1800946ac  lea     rax, [rbp+57h+var_58]
0x1800946b0  mov     r8d, 3
0x1800946b6  mov     dl, 1
0x1800946b8  mov     qword ptr [rsp+0A0h+var_80], rax
0x1800946bd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800946c2  mov     r9d, ebx
0x1800946c5  mov     edx, 9Eh
0x1800946ca  jmp     short loc_1800946F1
0x1800946cc  mov     rcx, qword ptr [rbp+57h+var_60]
0x1800946d0  mov     rdx, rcx
0x1800946d3  lea     r8, aSystem32Catroo; "System32\\CatRoot\\{F750E6C3-38EE-11D1-"...
0x1800946da  lea     rcx, [rbp+57h+lpFileName]
0x1800946de  call    SczAllocConcat2Sz
0x1800946e3  mov     ebx, eax
0x1800946e5  test    eax, eax
0x1800946e7  jns     short loc_180094706
0x1800946e9  mov     edx, 0A6h; void *
0x1800946ee  mov     r9d, eax; char *
0x1800946f1  mov     rcx, [rbp+5Fh]; this
0x1800946f5  lea     r8, aOnecoreBaseCbs_56; "onecore\\base\\cbs\\core\\cbscatalogins"...
0x1800946fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094701  jmp     loc_1800948AA
0x180094706  mov     rdx, rdi
0x180094709  lea     rcx, [rbp+57h+lpFileName]
0x18009470d  call    SczAllocConcatSz
0x180094712  mov     ebx, eax
0x180094714  test    eax, eax
0x180094716  jns     short loc_18009471F
0x180094718  mov     edx, 0A7h
0x18009471d  jmp     short loc_1800946EE
0x18009471f  mov     rbx, [rbp+57h+lpFileName]
0x180094723  mov     rcx, rbx; lpFileName
0x180094726  call    cs:__imp_GetFileAttributesW
0x18009472d  nop     dword ptr [rax+rax+00h]
0x180094732  cmp     eax, 0FFFFFFFFh
0x180094735  jz      short loc_18009478E
0x180094737  mov     edx, 80h; dwFileAttributes
0x18009473c  mov     rcx, rbx; lpFileName
0x18009473f  call    cs:__imp_SetFileAttributesW
0x180094746  nop     dword ptr [rax+rax+00h]
0x18009474b  lea     r8, [rbp+57h+var_58]
0x18009474f  mov     [rbp+57h+var_58], rbx
0x180094753  lea     rdx, aFileAlreadyExi_0; "File already exists when adding the cat"...
0x18009475a  mov     ecx, 1
0x18009475f  call    ??$TraceAtLevel@PEB_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEB_W@Z; LogAdapter::TraceAtLevel<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180094764  mov     rcx, rbx; lpFileName
0x180094767  call    cs:__imp_DeleteFileW
0x18009476e  nop     dword ptr [rax+rax+00h]
0x180094773  test    eax, eax
0x180094775  jnz     short loc_18009478E
0x180094777  lea     r8, [rbp+57h+var_58]
0x18009477b  mov     [rbp+57h+var_58], rbx
0x18009477f  lea     rdx, aCatalogExistsI; "Catalog [{}] exists in catroot and cann"...
0x180094786  lea     ecx, [rax+3]
0x180094789  call    ??$TraceAtLevelLastError@PEB_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelLastError<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18009478e  mov     rdx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x180094792  xor     r8d, r8d; lpSecurityAttributes
0x180094795  mov     rcx, rbx; lpFileName
0x180094798  call    cs:__imp_CreateHardLinkW
0x18009479f  nop     dword ptr [rax+rax+00h]
0x1800947a4  mov     edi, eax
0x1800947a6  call    cs:__imp_GetLastError
0x1800947ad  nop     dword ptr [rax+rax+00h]
0x1800947b2  mov     r14d, eax
0x1800947b5  test    edi, edi
0x1800947b7  jnz     loc_1800948C1
0x1800947bd  cmp     eax, 1
0x1800947c0  jnz     short loc_1800947E0
0x1800947c2  mov     rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x1800947c6  xor     r8d, r8d; bFailIfExists
0x1800947c9  mov     rdx, rbx; lpNewFileName
0x1800947cc  call    cs:__imp_CopyFileW
0x1800947d3  nop     dword ptr [rax+rax+00h]
0x1800947d8  test    eax, eax
0x1800947da  jnz     loc_1800948C1
0x1800947e0  call    cs:__imp_GetLastError
0x1800947e7  nop     dword ptr [rax+rax+00h]
0x1800947ec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800947f3  mov     edi, eax
0x1800947f5  test    rcx, rcx
0x1800947f8  jz      loc_180094888
0x1800947fe  lea     rax, aHardlink; "hardlink"
0x180094805  mov     [rbp+57h+var_58], rbx
0x180094809  cmp     r14d, 1
0x18009480d  lea     rdx, aCopy_0; "copy"
0x180094814  lea     r9, aFailedToCatalo; "Failed to {} catalog {} to offline imag"...
0x18009481b  cmovnz  rdx, rax
0x18009481f  lea     rax, [rbp+57h+var_58]
0x180094823  mov     [rsp+0A0h+var_70], rax
  ... truncated ...
```
