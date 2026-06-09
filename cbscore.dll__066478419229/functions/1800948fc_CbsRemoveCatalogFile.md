# CbsRemoveCatalogFile

- ea: `0x1800948fc`
- end: `0x180094d2f`
- name: `CbsRemoveCatalogFile`
- size: `1075`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, installer_update`

## callers

- `0x180093fbc`
- `0x1800ca250`
- `0x1801ebfe4`

## callees

- `0x180013250`
- `0x180015420`
- `0x180016d40`
- `0x18005ec58`
- `0x180093c4c`
- `0x1800948fc`
- `0x180094d38`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad504`
- `0x1800eb920`
- `0x1801ecec8`
- `0x1801ecf04`
- `0x1801ecf94`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094c7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094c7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094a92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094bb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094a92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094bb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094c8a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180094a82`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180094a82`

## string_xrefs

- `0x18009497b`: `onecore\base\cbs\core\cbscataloginstallation.cpp`
- `0x180094a49`: `onecore\base\cbs\core\cbscataloginstallation.cpp`
- `0x180094b4c`: `onecore\base\cbs\core\cbscataloginstallation.cpp`
- `0x180094d07`: `onecore\base\cbs\core\cbscataloginstallation.cpp`
- `0x180094ca9`: `Failed call to CryptCATAdminRemoveCatalog.`
- `0x180094ae9`: `Failed to remove catalog {} from offline image path {}`
- `0x180094a5e`: `System32\CatRoot\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\`
- `0x180094aaa`: `Catalog to be removed does not exist in catroot.`

## pseudocode

```c
__int64 __fastcall CbsRemoveCatalogFile(__int64 a1, const wchar_t *a2, char a3)
{
  unsigned int v4; // ebx
  int v5; // edx
  __int64 v7; // r9
  int WindowsDirectory; // eax
  int v9; // edx
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  int v12; // eax
  LPCWSTR v13; // rbx
  DWORD v14; // eax
  int v15; // esi
  int v16; // edx
  unsigned int v17; // eax
  void **InitPointer; // rax
  unsigned int v19; // r8d
  signed int LastError; // ebx
  int v21; // edx
  unsigned int v22; // eax
  __int64 v23; // rdx
  int v24; // edx
  unsigned int v25; // eax
  unsigned int v26; // [rsp+20h] [rbp-50h]
  int v27[2]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v28[2]; // [rsp+38h] [rbp-38h] BYREF
  const wchar_t *v29; // [rsp+40h] [rbp-30h] BYREF
  int v30; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-20h] BYREF
  struct _GUID v32; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v29 = a2;
  if ( !a2 )
  {
    v4 = -2147024809;
    v30 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No catalog name specified");
      *(_QWORD *)v27 = &v30;
      LOBYTE(v5) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v5,
        3,
        (unsigned int)": {}",
        (__int64)v27);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\base\\cbs\\core\\cbscataloginstallation.cpp",
      (const char *)0x80070057LL,
      v26);
    return v4;
  }
  LOBYTE(a1) = a1 != 0;
  lpFileName = 0;
  if ( !(unsigned __int8)WillUninstallCatalogQuickly(a1) )
  {
    v32.Data1 = -145692989;
    *(_DWORD *)&v32.Data2 = 298924270;
    *(_DWORD *)v32.Data4 = -1073683067;
    *(_DWORD *)&v32.Data4[4] = -292175281;
    InitPointer = (void **)Windows::AutoGenericHandleBase_void___0_Windows::AutoGenericHandle_void___0__CloseWithCryptCATAdminReleaseContext___::GetInitPointer(&lpFileName);
    if ( (unsigned int)CbsDelayloadCryptCATAdminAcquireContext(InitPointer, &v32, v19) )
    {
      if ( vpfnCryptCATAdminRemoveCatalog )
      {
        if ( vpfnCryptCATAdminRemoveCatalog((void *)lpFileName, v29, 0) )
          goto LABEL_43;
      }
      else
      {
        SetLastError(0x7Fu);
      }
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed call to CryptCATAdminRemoveCatalog.");
        if ( LastError > 0 )
          v25 = (unsigned __int16)LastError | 0x80070000;
        else
          v25 = LastError;
        v30 = v25;
        LOBYTE(v24) = 1;
        *(_QWORD *)v28 = &v30;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v24,
          3,
          (unsigned int)": {0}",
          (__int64)v28);
      }
      if ( LastError )
      {
        v23 = 272;
LABEL_54:
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v23,
               (unsigned int)"onecore\\base\\cbs\\core\\cbscataloginstallation.cpp",
               (const char *)(unsigned int)LastError,
               v26);
        if ( lpFileName )
          CloseWithCryptCATAdminReleaseContext();
        return v4;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed call to CryptCATAdminAcquireContext.");
        if ( LastError > 0 )
          v22 = (unsigned __int16)LastError | 0x80070000;
        else
          v22 = LastError;
        v30 = v22;
        LOBYTE(v21) = 1;
        *(_QWORD *)v28 = &v30;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v21,
          3,
          (unsigned int)": {0}",
          (__int64)v28);
      }
      if ( LastError )
      {
        v23 = 266;
        goto LABEL_54;
      }
    }
LABEL_43:
    if ( lpFileName )
      CloseWithCryptCATAdminReleaseContext();
    return 0;
  }
  *(_QWORD *)v27 = 0;
  if ( !v7 )
  {
    WindowsDirectory = PathGetWindowsDirectory((LPWSTR *)v27, 0);
    v4 = WindowsDirectory;
    if ( WindowsDirectory < 0 )
    {
      v30 = WindowsDirectory;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get online Windir");
        *(_QWORD *)&v32.Data1 = &v30;
        LOBYTE(v9) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v9,
          3,
          (unsigned int)": {}",
          (__int64)&v32);
      }
      v10 = v4;
      v11 = 234;
      goto LABEL_16;
    }
    v7 = *(_QWORD *)v27;
  }
  v12 = SczAllocFromSz(&lpFileName, v7);
  v4 = v12;
  if ( v12 < 0 )
  {
    v11 = 242;
LABEL_15:
    v10 = (unsigned int)v12;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\cbs\\core\\cbscataloginstallation.cpp",
      (const char *)v10,
      v26);
LABEL_32:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v27);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
    return v4;
  }
  v12 = SczAllocConcat2Sz(&lpFileName, L"System32\\CatRoot\\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\\", v29);
  v4 = v12;
  if ( v12 < 0 )
  {
    v11 = 244;
    goto LABEL_15;
  }
  v13 = lpFileName;
  if ( !DeleteFileW(lpFileName) )
  {
    v14 = GetLastError();
    v15 = v14;
    if ( !a3 || v14 != 2 )
    {
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)&v32.Data1 = v13;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to remove catalog {} from offline image path {}",
          (__int64)&v29,
          (__int64)&v32);
        if ( v15 > 0 )
          v17 = (unsigned __int16)v15 | 0x80070000;
        else
          v17 = v15;
        v30 = v17;
        LOBYTE(v16) = 1;
        *(_QWORD *)v28 = &v30;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v16,
          3,
          (unsigned int)": {0}",
          (__int64)v28);
      }
      if ( v15 )
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xFF,
               (unsigned int)"onecore\\base\\cbs\\core\\cbscataloginstallation.cpp",
               (const char *)(unsigned int)v15,
               v26);
      else
        v4 = 0;
      goto LABEL_32;
    }
    LogAdapter::TraceAtLevel<>(1, "Catalog to be removed does not exist in catroot.");
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v27);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  return 0;
}

```

## disassembly

```asm
0x1800948fc  mov     [rsp-18h+arg_10], rbx
0x180094901  push    rbp
0x180094902  push    rsi
0x180094903  push    rdi
0x180094904  mov     rbp, rsp
0x180094907  sub     rsp, 70h
0x18009490b  mov     rax, cs:__security_cookie
0x180094912  xor     rax, rsp
0x180094915  mov     [rbp+var_8], rax
0x180094919  mov     [rbp+var_30], rdx
0x18009491d  mov     dil, r8b
0x180094920  mov     r9, rcx
0x180094923  test    rdx, rdx
0x180094926  jnz     short loc_180094996
0x180094928  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009492f  mov     ebx, 80070057h
0x180094934  mov     [rbp+var_28], ebx
0x180094937  test    rcx, rcx
0x18009493a  jz      short loc_180094977
0x18009493c  lea     edi, [rdx+3]
0x18009493f  mov     r8d, edi
0x180094942  lea     r9, aNoCatalogNameS; "No catalog name specified"
0x180094949  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18009494e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180094955  lea     rax, [rbp+var_28]
0x180094959  mov     qword ptr [rbp+var_40], rax
0x18009495d  lea     r9, asc_1802EE7AC; ": {}"
0x180094964  lea     rax, [rbp+var_40]
0x180094968  mov     r8d, edi
0x18009496b  mov     dl, 1
0x18009496d  mov     qword ptr [rsp+70h+var_50], rax; int
0x180094972  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180094977  mov     rcx, [rbp+18h]; this
0x18009497b  lea     r8, aOnecoreBaseCbs_56; "onecore\\base\\cbs\\core\\cbscatalogins"...
0x180094982  mov     r9d, ebx; char *
0x180094985  mov     edx, 0DCh; void *
0x18009498a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009498f  mov     eax, ebx
0x180094991  jmp     loc_180094C5C
0x180094996  test    r9, r9
0x180094999  setnz   cl
0x18009499c  call    WillUninstallCatalogQuickly
0x1800949a1  mov     [rbp+lpFileName], 0
0x1800949a9  test    al, al
0x1800949ab  jz      loc_180094B7D
0x1800949b1  mov     qword ptr [rbp+var_40], 0
0x1800949b9  test    r9, r9
0x1800949bc  jnz     short loc_180094A2B
0x1800949be  xor     edx, edx
0x1800949c0  lea     rcx, [rbp+var_40]
0x1800949c4  call    PathGetWindowsDirectory
0x1800949c9  mov     ebx, eax
0x1800949cb  test    eax, eax
0x1800949cd  jns     short loc_180094A27
0x1800949cf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800949d6  mov     [rbp+var_28], eax
0x1800949d9  test    rcx, rcx
0x1800949dc  jz      short loc_180094A1D
0x1800949de  mov     edi, 3
0x1800949e3  lea     r9, aFailedToGetOnl; "Failed to get online Windir"
0x1800949ea  mov     r8d, edi
0x1800949ed  xor     edx, edx
0x1800949ef  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800949f4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800949fb  lea     rax, [rbp+var_28]
0x1800949ff  mov     qword ptr [rbp+var_18.Data1], rax
0x180094a03  lea     r9, asc_1802EE7AC; ": {}"
0x180094a0a  lea     rax, [rbp+var_18]
0x180094a0e  mov     r8d, edi
0x180094a11  mov     dl, 1
0x180094a13  mov     qword ptr [rsp+70h+var_50], rax
0x180094a18  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180094a1d  mov     r9d, ebx
0x180094a20  mov     edx, 0EAh
0x180094a25  jmp     short loc_180094A45
0x180094a27  mov     r9, qword ptr [rbp+var_40]
0x180094a2b  mov     rdx, r9
0x180094a2e  lea     rcx, [rbp+lpFileName]
0x180094a32  call    SczAllocFromSz
0x180094a37  mov     ebx, eax
0x180094a39  test    eax, eax
0x180094a3b  jns     short loc_180094A5A
0x180094a3d  mov     edx, 0F2h; void *
0x180094a42  mov     r9d, eax; char *
0x180094a45  mov     rcx, [rbp+18h]; this
0x180094a49  lea     r8, aOnecoreBaseCbs_56; "onecore\\base\\cbs\\core\\cbscatalogins"...
0x180094a50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094a55  jmp     loc_180094B66
0x180094a5a  mov     r8, [rbp+var_30]
0x180094a5e  lea     rdx, aSystem32Catroo; "System32\\CatRoot\\{F750E6C3-38EE-11D1-"...
0x180094a65  lea     rcx, [rbp+lpFileName]
0x180094a69  call    SczAllocConcat2Sz
0x180094a6e  mov     ebx, eax
0x180094a70  test    eax, eax
0x180094a72  jns     short loc_180094A7B
0x180094a74  mov     edx, 0F4h
0x180094a79  jmp     short loc_180094A42
0x180094a7b  mov     rbx, [rbp+lpFileName]
0x180094a7f  mov     rcx, rbx; lpFileName
0x180094a82  call    cs:__imp_DeleteFileW
0x180094a89  nop     dword ptr [rax+rax+00h]
0x180094a8e  test    eax, eax
0x180094a90  jnz     short loc_180094AB9
0x180094a92  call    cs:__imp_GetLastError
0x180094a99  nop     dword ptr [rax+rax+00h]
0x180094a9e  mov     esi, eax
0x180094aa0  test    dil, dil
0x180094aa3  jz      short loc_180094AD0
0x180094aa5  cmp     eax, 2
0x180094aa8  jnz     short loc_180094AD0
0x180094aaa  lea     rdx, aCatalogToBeRem; "Catalog to be removed does not exist in"...
0x180094ab1  lea     ecx, [rax-1]
0x180094ab4  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x180094ab9  lea     rcx, [rbp+var_40]
0x180094abd  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180094ac2  lea     rcx, [rbp+lpFileName]
0x180094ac6  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180094acb  jmp     loc_180094C5A
0x180094ad0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180094ad7  test    rcx, rcx
0x180094ada  jz      short loc_180094B44
0x180094adc  lea     rax, [rbp+var_18]
0x180094ae0  mov     qword ptr [rbp+var_18.Data1], rbx
0x180094ae4  mov     [rsp+70h+var_48], rax
0x180094ae9  lea     r9, aFailedToRemove_24; "Failed to remove catalog {} from offlin"...
0x180094af0  lea     rax, [rbp+var_30]
0x180094af4  mov     edi, 3
0x180094af9  mov     r8d, edi
0x180094afc  mov     qword ptr [rsp+70h+var_50], rax
0x180094b01  xor     edx, edx
0x180094b03  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x180094b08  test    esi, esi
0x180094b0a  jg      short loc_180094B10
0x180094b0c  mov     eax, esi
0x180094b0e  jmp     short loc_180094B18
0x180094b10  movzx   eax, si
0x180094b13  or      eax, 80070000h
0x180094b18  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180094b1f  lea     r9, a0; ": {0}"
0x180094b26  mov     [rbp+var_28], eax
0x180094b29  mov     r8d, edi
0x180094b2c  lea     rax, [rbp+var_28]
0x180094b30  mov     dl, 1
0x180094b32  mov     qword ptr [rbp+var_38], rax
0x180094b36  lea     rax, [rbp+var_38]
0x180094b3a  mov     qword ptr [rsp+70h+var_50], rax; unsigned int
0x180094b3f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180094b44  test    esi, esi
0x180094b46  jz      short loc_180094B64
0x180094b48  mov     rcx, [rbp+18h]; this
0x180094b4c  lea     r8, aOnecoreBaseCbs_56; "onecore\\base\\cbs\\core\\cbscatalogins"...
0x180094b53  mov     r9d, esi; char *
0x180094b56  mov     edx, 0FFh; void *
0x180094b5b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180094b60  mov     ebx, eax
0x180094b62  jmp     short loc_180094B66
0x180094b64  xor     ebx, ebx
0x180094b66  lea     rcx, [rbp+var_40]
0x180094b6a  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180094b6f  lea     rcx, [rbp+lpFileName]
0x180094b73  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180094b78  jmp     loc_18009498F
0x180094b7d  lea     rcx, [rbp+lpFileName]
0x180094b81  mov     [rbp+var_18.Data1], 0F750E6C3h
0x180094b88  mov     dword ptr [rbp+var_18.Data2], 11D138EEh
0x180094b8f  mov     dword ptr [rbp+var_18.Data4], 0C000E585h
0x180094b96  mov     dword ptr [rbp+var_18.Data4+4], 0EE95C24Fh
0x180094b9d  call    Windows__AutoGenericHandleBase_void___0_Windows__AutoGenericHandle_void___0__CloseWithCryptCATAdminReleaseContext_____GetInitPointer
0x180094ba2  mov     rcx, rax; void **
0x180094ba5  lea     rdx, [rbp+var_18]; struct _GUID *
0x180094ba9  call    ?CbsDelayloadCryptCATAdminAcquireContext@@YAHPEAPEAXPEBU_GUID@@K@Z; CbsDelayloadCryptCATAdminAcquireContext(void * *,_GUID const *,ulong)
0x180094bae  test    eax, eax
0x180094bb0  jnz     short loc_180094C2C
0x180094bb2  call    cs:__imp_GetLastError
0x180094bb9  nop     dword ptr [rax+rax+00h]
0x180094bbe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180094bc5  mov     ebx, eax
0x180094bc7  test    rcx, rcx
0x180094bca  jz      short loc_180094C1E
0x180094bcc  mov     edi, 3
0x180094bd1  lea     r9, aFailedCallToCr_0; "Failed call to CryptCATAdminAcquireCont"...
0x180094bd8  mov     r8d, edi
0x180094bdb  xor     edx, edx
0x180094bdd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180094be2  test    ebx, ebx
0x180094be4  jg      short loc_180094BEA
0x180094be6  mov     eax, ebx
0x180094be8  jmp     short loc_180094BF2
0x180094bea  movzx   eax, bx
0x180094bed  or      eax, 80070000h
0x180094bf2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180094bf9  lea     r9, a0; ": {0}"
0x180094c00  mov     [rbp+var_28], eax
0x180094c03  mov     r8d, edi
0x180094c06  lea     rax, [rbp+var_28]
0x180094c0a  mov     dl, 1
0x180094c0c  mov     qword ptr [rbp+var_38], rax
0x180094c10  lea     rax, [rbp+var_38]
0x180094c14  mov     qword ptr [rsp+70h+var_50], rax
0x180094c19  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180094c1e  test    ebx, ebx
0x180094c20  jz      short loc_180094C4C
0x180094c22  mov     edx, 10Ah
0x180094c27  jmp     loc_180094D03
0x180094c2c  mov     rax, cs:?vpfnCryptCATAdminRemoveCatalog@@3P6AHPEAXPEB_WK@ZEA; int (*vpfnCryptCATAdminRemoveCatalog)(void *,wchar_t const *,ulong)
0x180094c33  test    rax, rax
0x180094c36  jz      short loc_180094C79
0x180094c38  mov     rdx, [rbp+var_30]
0x180094c3c  xor     r8d, r8d
0x180094c3f  mov     rcx, [rbp+lpFileName]
0x180094c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094c48  test    eax, eax
0x180094c4a  jz      short loc_180094C8A
0x180094c4c  mov     rcx, [rbp+lpFileName]
0x180094c50  test    rcx, rcx
0x180094c53  jz      short loc_180094C5A
0x180094c55  call    CloseWithCryptCATAdminReleaseContext
0x180094c5a  xor     eax, eax
0x180094c5c  mov     rcx, [rbp+var_8]
0x180094c60  xor     rcx, rsp; StackCookie
0x180094c63  call    __security_check_cookie
0x180094c68  mov     rbx, [rsp+70h+arg_10]
0x180094c70  add     rsp, 70h
0x180094c74  pop     rdi
0x180094c75  pop     rsi
0x180094c76  pop     rbp
0x180094c77  retn
0x180094c79  mov     ecx, 7Fh; dwErrCode
0x180094c7e  call    cs:__imp_SetLastError
0x180094c85  nop     dword ptr [rax+rax+00h]
0x180094c8a  call    cs:__imp_GetLastError
0x180094c91  nop     dword ptr [rax+rax+00h]
0x180094c96  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180094c9d  mov     ebx, eax
0x180094c9f  test    rcx, rcx
0x180094ca2  jz      short loc_180094CF6
0x180094ca4  mov     edi, 3
0x180094ca9  lea     r9, aFailedCallToCr; "Failed call to CryptCATAdminRemoveCatal"...
0x180094cb0  mov     r8d, edi
0x180094cb3  xor     edx, edx
0x180094cb5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180094cba  test    ebx, ebx
0x180094cbc  jg      short loc_180094CC2
0x180094cbe  mov     eax, ebx
0x180094cc0  jmp     short loc_180094CCA
0x180094cc2  movzx   eax, bx
0x180094cc5  or      eax, 80070000h
0x180094cca  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180094cd1  lea     r9, a0; ": {0}"
0x180094cd8  mov     [rbp+var_28], eax
0x180094cdb  mov     r8d, edi
0x180094cde  lea     rax, [rbp+var_28]
0x180094ce2  mov     dl, 1
0x180094ce4  mov     qword ptr [rbp+var_38], rax
0x180094ce8  lea     rax, [rbp+var_38]
0x180094cec  mov     qword ptr [rsp+70h+var_50], rax; unsigned int
0x180094cf1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180094cf6  test    ebx, ebx
0x180094cf8  jz      loc_180094C4C
0x180094cfe  mov     edx, 110h; void *
0x180094d03  mov     rcx, [rbp+18h]; this
0x180094d07  lea     r8, aOnecoreBaseCbs_56; "onecore\\base\\cbs\\core\\cbscatalogins"...
0x180094d0e  mov     r9d, ebx; char *
0x180094d11  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180094d16  mov     rcx, [rbp+lpFileName]
0x180094d1a  mov     ebx, eax
0x180094d1c  test    rcx, rcx
0x180094d1f  jz      loc_18009498F
0x180094d25  call    CloseWithCryptCATAdminReleaseContext
0x180094d2a  jmp     loc_18009498F
```
