# CbsCatalogInstallationApiLoad

- ea: `0x18009753c`
- end: `0x180097bc9`
- name: `CbsCatalogInstallationApiLoad`
- size: `1677`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800f3f0c`

## callees

- `0x180013250`
- `0x180033d50`
- `0x180059a00`
- `0x18005aa38`
- `0x180095e34`
- `0x18009753c`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1801ece94`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097850`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800978fc`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800979ab`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097a5a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097b09`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097850`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800978fc`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800979ab`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097a5a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180097b09`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180097570`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180097570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009761e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800976f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800977c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009786c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800979c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097a76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097b25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009761e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800976f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800977c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009786c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800979c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097a76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097b25`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18009760a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800976e8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18009760a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800976e8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800977b3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800977b3`

## string_xrefs

- `0x180097697`: `onecore\base\cbs\core\cbscataloginstallation.cpp`
- `0x1800976ce`: `onecore\base\cbs\core\cbscataloginstallation.cpp`
- `0x18009763d`: `Failed to get system directory`
- `0x180097717`: `Failed to get system directory`
- `0x1800977e3`: `Wintrust catalog support is not present; skipping synchronous catalog installation (possibly expected)`
- `0x180097b44`: `Failed to get proc address for CryptCATAdminRemoveCatalog`
- `0x1800975a7`: `Failed to load wintrust.dll (possibly expected)`
- `0x180097b02`: `CryptCATAdminRemoveCatalog`
- `0x180097569`: `wintrust.dll`
- `0x18009778f`: `cryptcatsvc.dll`

## pseudocode

```c
__int64 CbsCatalogInstallationApiLoad()
{
  signed int LastError; // edi
  int v2; // edx
  unsigned int v3; // eax
  __int64 v4; // rdx
  UINT SystemDirectoryW; // eax
  int v6; // edx
  unsigned int v7; // eax
  const char *v8; // r8
  unsigned int v9; // ebx
  UINT v10; // edi
  int v11; // eax
  __int64 v12; // rdx
  int v13; // edx
  unsigned int v14; // eax
  int v15; // edx
  unsigned int v16; // eax
  int v17; // edx
  unsigned int v18; // eax
  int v19; // edx
  unsigned int v20; // eax
  int v21; // edx
  unsigned int v22; // eax
  int v23; // edx
  unsigned int v24; // eax
  int v25; // edx
  unsigned int v26; // eax
  unsigned int v27; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  char v29; // [rsp+50h] [rbp+20h] BYREF
  unsigned int v30; // [rsp+58h] [rbp+28h] BYREF
  LPWSTR lpBuffer; // [rsp+60h] [rbp+30h] BYREF
  unsigned int *v32; // [rsp+68h] [rbp+38h] BYREF

  if ( hLibModule )
    return 0;
  v29 = 1;
  lpBuffer = 0;
  hLibModule = LoadLibraryExW(L"wintrust.dll", 0, 0);
  if ( hLibModule )
  {
    SystemDirectoryW = GetSystemDirectoryW(0, 0);
    if ( !SystemDirectoryW )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get system directory");
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        else
          v7 = LastError;
        v30 = v7;
        LOBYTE(v6) = 1;
        v32 = &v30;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v6,
          3,
          (unsigned int)": {0}",
          (__int64)&v32);
      }
      if ( LastError )
      {
        v4 = 44;
        goto LABEL_19;
      }
LABEL_85:
      v9 = 0;
      goto LABEL_86;
    }
    v10 = SystemDirectoryW + 17;
    v11 = SczAlloc(&lpBuffer, SystemDirectoryW + 17);
    v9 = v11;
    if ( v11 >= 0 )
    {
      if ( !GetSystemDirectoryW(lpBuffer, v10) )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get system directory");
          if ( LastError > 0 )
            v14 = (unsigned __int16)LastError | 0x80070000;
          else
            v14 = LastError;
          v30 = v14;
          LOBYTE(v13) = 1;
          v32 = &v30;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v13,
            3,
            (unsigned int)": {0}",
            (__int64)&v32);
        }
        if ( LastError )
        {
          v4 = 50;
          goto LABEL_19;
        }
        goto LABEL_85;
      }
      v11 = SczEnsureBackslashTerminated(&lpBuffer);
      v9 = v11;
      if ( v11 >= 0 )
      {
        v11 = SczAllocConcatSz(&lpBuffer, L"cryptcatsvc.dll");
        v9 = v11;
        if ( v11 >= 0 )
        {
          if ( GetFileAttributesW(lpBuffer) == -1 )
          {
            LastError = GetLastError();
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Wintrust catalog support is not present; skipping synchronous catalog installation (possibly expected)");
              if ( LastError > 0 )
                v16 = (unsigned __int16)LastError | 0x80070000;
              else
                v16 = LastError;
              v30 = v16;
              LOBYTE(v15) = 1;
              v32 = &v30;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v15,
                3,
                (unsigned int)": {0}",
                (__int64)&v32);
            }
            if ( LastError )
            {
              v4 = 55;
              goto LABEL_19;
            }
          }
          else
          {
            vpfnCryptCATAdminAcquireContext = (int (*)(void **, const struct _GUID *, unsigned int))GetProcAddress(hLibModule, "CryptCATAdminAcquireContext");
            if ( vpfnCryptCATAdminAcquireContext )
            {
              vpfnCryptCATAdminAddCatalog = (void *(*)(void *, wchar_t *, wchar_t *, unsigned int))GetProcAddress(
                                                                                                     hLibModule,
                                                                                                     "CryptCATAdminAddCatalog");
              if ( vpfnCryptCATAdminAddCatalog )
              {
                vpfnCryptCATAdminReleaseCatalogContext = (int (*)(void *, void *, unsigned int))GetProcAddress(
                                                                                                  hLibModule,
                                                                                                  "CryptCATAdminReleaseCatalogContext");
                if ( vpfnCryptCATAdminReleaseCatalogContext )
                {
                  vpfnCryptCATAdminReleaseContext = (int (*)(void *, unsigned int))GetProcAddress(
                                                                                     hLibModule,
                                                                                     "CryptCATAdminReleaseContext");
                  if ( vpfnCryptCATAdminReleaseContext )
                  {
                    vpfnCryptCATAdminRemoveCatalog = (int (*)(void *, const wchar_t *, unsigned int))GetProcAddress(hLibModule, "CryptCATAdminRemoveCatalog");
                    if ( vpfnCryptCATAdminRemoveCatalog )
                    {
                      v29 = 0;
                    }
                    else
                    {
                      LastError = GetLastError();
                      if ( LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<>(
                          LogAdapter::g_Logger,
                          0,
                          3,
                          "Failed to get proc address for CryptCATAdminRemoveCatalog");
                        if ( LastError > 0 )
                          v26 = (unsigned __int16)LastError | 0x80070000;
                        else
                          v26 = LastError;
                        v30 = v26;
                        LOBYTE(v25) = 1;
                        v32 = &v30;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          (_DWORD)LogAdapter::g_Logger,
                          v25,
                          3,
                          (unsigned int)": {0}",
                          (__int64)&v32);
                      }
                      if ( LastError )
                      {
                        v8 = "onecore\\base\\cbs\\core\\cryptcatdelayload.fnlist";
                        v4 = 20;
                        goto LABEL_20;
                      }
                    }
                  }
                  else
                  {
                    LastError = GetLastError();
                    if ( LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<>(
                        LogAdapter::g_Logger,
                        0,
                        3,
                        "Failed to get proc address for CryptCATAdminReleaseContext");
                      if ( LastError > 0 )
                        v24 = (unsigned __int16)LastError | 0x80070000;
                      else
                        v24 = LastError;
                      v30 = v24;
                      LOBYTE(v23) = 1;
                      v32 = &v30;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        (_DWORD)LogAdapter::g_Logger,
                        v23,
                        3,
                        (unsigned int)": {0}",
                        (__int64)&v32);
                    }
                    if ( LastError )
                    {
                      v8 = "onecore\\base\\cbs\\core\\cryptcatdelayload.fnlist";
                      v4 = 15;
                      goto LABEL_20;
                    }
                  }
                }
                else
                {
                  LastError = GetLastError();
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed to get proc address for CryptCATAdminReleaseCatalogContext");
                    if ( LastError > 0 )
                      v22 = (unsigned __int16)LastError | 0x80070000;
                    else
                      v22 = LastError;
                    v30 = v22;
                    LOBYTE(v21) = 1;
                    v32 = &v30;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v21,
                      3,
                      (unsigned int)": {0}",
                      (__int64)&v32);
                  }
                  if ( LastError )
                  {
                    v8 = "onecore\\base\\cbs\\core\\cryptcatdelayload.fnlist";
                    v4 = 12;
                    goto LABEL_20;
                  }
                }
              }
              else
              {
                LastError = GetLastError();
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to get proc address for CryptCATAdminAddCatalog");
                  if ( LastError > 0 )
                    v20 = (unsigned __int16)LastError | 0x80070000;
                  else
                    v20 = LastError;
                  v30 = v20;
                  LOBYTE(v19) = 1;
                  v32 = &v30;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v19,
                    3,
                    (unsigned int)": {0}",
                    (__int64)&v32);
                }
                if ( LastError )
                {
                  v8 = "onecore\\base\\cbs\\core\\cryptcatdelayload.fnlist";
                  v4 = 8;
                  goto LABEL_20;
                }
              }
            }
            else
            {
              LastError = GetLastError();
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to get proc address for CryptCATAdminAcquireContext");
                if ( LastError > 0 )
                  v18 = (unsigned __int16)LastError | 0x80070000;
                else
                  v18 = LastError;
                v30 = v18;
                LOBYTE(v17) = 1;
                v32 = &v30;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v17,
                  3,
                  (unsigned int)": {0}",
                  (__int64)&v32);
              }
              if ( LastError )
              {
                v8 = "onecore\\base\\cbs\\core\\cryptcatdelayload.fnlist";
                v4 = 3;
                goto LABEL_20;
              }
            }
          }
          goto LABEL_85;
        }
        v12 = 52;
      }
      else
      {
        v12 = 51;
      }
    }
    else
    {
      v12 = 48;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\cbs\\core\\cbscataloginstallation.cpp",
      (const char *)(unsigned int)v11,
      v27);
    goto LABEL_86;
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to load wintrust.dll (possibly expected)");
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    else
      v3 = LastError;
    v30 = v3;
    LOBYTE(v2) = 1;
    v32 = &v30;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v2,
      3,
      (unsigned int)": {0}",
      (__int64)&v32);
  }
  if ( !LastError )
    goto LABEL_85;
  v4 = 37;
LABEL_19:
  v8 = "onecore\\base\\cbs\\core\\cbscataloginstallation.cpp";
LABEL_20:
  v9 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v4,
         (unsigned int)v8,
         (const char *)(unsigned int)LastError,
         v27);
LABEL_86:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
  Windows::Detail::OnBlockExitImpl__CbsCatalogInstallationApiLoad_::_2_::_lambda_1___::_OnBlockExitImpl__CbsCatalogInstallationApiLoad_::_2_::_lambda_1___(&v29);
  return v9;
}

```

## disassembly

```asm
0x18009753c  push    rbp
0x18009753e  push    rbx
0x18009753f  push    rdi
0x180097540  mov     rbp, rsp
0x180097543  sub     rsp, 30h
0x180097547  cmp     cs:hLibModule, 0
0x18009754f  jz      short loc_180097558
0x180097551  xor     eax, eax
0x180097553  jmp     loc_180097BC0
0x180097558  xor     r8d, r8d; dwFlags
0x18009755b  mov     [rbp+arg_0], 1
0x18009755f  xor     edx, edx; hFile
0x180097561  mov     [rbp+lpBuffer], 0
0x180097569  lea     rcx, aWintrustDll_0; "wintrust.dll"
0x180097570  call    cs:__imp_LoadLibraryExW
0x180097577  nop     dword ptr [rax+rax+00h]
0x18009757c  mov     cs:hLibModule, rax
0x180097583  test    rax, rax
0x180097586  jnz     short loc_180097606
0x180097588  call    cs:__imp_GetLastError
0x18009758f  nop     dword ptr [rax+rax+00h]
0x180097594  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009759b  mov     edi, eax
0x18009759d  test    rcx, rcx
0x1800975a0  jz      short loc_1800975F4
0x1800975a2  mov     ebx, 3
0x1800975a7  lea     r9, aFailedToLoadWi_0; "Failed to load wintrust.dll (possibly e"...
0x1800975ae  mov     r8d, ebx
0x1800975b1  xor     edx, edx
0x1800975b3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800975b8  test    edi, edi
0x1800975ba  jg      short loc_1800975C0
0x1800975bc  mov     eax, edi
0x1800975be  jmp     short loc_1800975C8
0x1800975c0  movzx   eax, di
0x1800975c3  or      eax, 80070000h
0x1800975c8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800975cf  lea     r9, a0; ": {0}"
0x1800975d6  mov     [rbp+arg_8], eax
0x1800975d9  mov     r8d, ebx
0x1800975dc  lea     rax, [rbp+arg_8]
0x1800975e0  mov     dl, 1
0x1800975e2  mov     [rbp+arg_18], rax
0x1800975e6  lea     rax, [rbp+arg_18]
0x1800975ea  mov     qword ptr [rsp+30h+var_10], rax
0x1800975ef  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800975f4  test    edi, edi
0x1800975f6  jz      loc_180097BAA
0x1800975fc  mov     edx, 25h ; '%'
0x180097601  jmp     loc_180097697
0x180097606  xor     edx, edx; uSize
0x180097608  xor     ecx, ecx; lpBuffer
0x18009760a  call    cs:__imp_GetSystemDirectoryW
0x180097611  nop     dword ptr [rax+rax+00h]
0x180097616  test    eax, eax
0x180097618  jnz     loc_1800976B1
0x18009761e  call    cs:__imp_GetLastError
0x180097625  nop     dword ptr [rax+rax+00h]
0x18009762a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180097631  mov     edi, eax
0x180097633  test    rcx, rcx
0x180097636  jz      short loc_18009768A
0x180097638  mov     ebx, 3
0x18009763d  lea     r9, aFailedToGetSys_4; "Failed to get system directory"
0x180097644  mov     r8d, ebx
0x180097647  xor     edx, edx
0x180097649  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18009764e  test    edi, edi
0x180097650  jg      short loc_180097656
0x180097652  mov     eax, edi
0x180097654  jmp     short loc_18009765E
0x180097656  movzx   eax, di
0x180097659  or      eax, 80070000h
0x18009765e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180097665  lea     r9, a0; ": {0}"
0x18009766c  mov     [rbp+arg_8], eax
0x18009766f  mov     r8d, ebx
0x180097672  lea     rax, [rbp+arg_8]
0x180097676  mov     dl, 1
0x180097678  mov     [rbp+arg_18], rax
0x18009767c  lea     rax, [rbp+arg_18]
0x180097680  mov     qword ptr [rsp+30h+var_10], rax; unsigned int
0x180097685  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009768a  test    edi, edi
0x18009768c  jz      loc_180097BAA
0x180097692  mov     edx, 2Ch ; ','; void *
0x180097697  lea     r8, aOnecoreBaseCbs_56; "onecore\\base\\cbs\\core\\cbscatalogins"...
0x18009769e  mov     rcx, [rbp+18h]; this
0x1800976a2  mov     r9d, edi; char *
0x1800976a5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800976aa  mov     ebx, eax
0x1800976ac  jmp     loc_180097BAC
0x1800976b1  lea     edi, [rax+11h]
0x1800976b4  mov     edx, edi
0x1800976b6  lea     rcx, [rbp+lpBuffer]
0x1800976ba  call    SczAlloc
0x1800976bf  mov     ebx, eax
0x1800976c1  test    eax, eax
0x1800976c3  jns     short loc_1800976E2
0x1800976c5  mov     edx, 30h ; '0'; void *
0x1800976ca  mov     rcx, [rbp+18h]; this
0x1800976ce  lea     r8, aOnecoreBaseCbs_56; "onecore\\base\\cbs\\core\\cbscatalogins"...
0x1800976d5  mov     r9d, eax; char *
0x1800976d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800976dd  jmp     loc_180097BAC
0x1800976e2  mov     rcx, [rbp+lpBuffer]; lpBuffer
0x1800976e6  mov     edx, edi; uSize
0x1800976e8  call    cs:__imp_GetSystemDirectoryW
0x1800976ef  nop     dword ptr [rax+rax+00h]
0x1800976f4  test    eax, eax
0x1800976f6  jnz     short loc_180097776
0x1800976f8  call    cs:__imp_GetLastError
0x1800976ff  nop     dword ptr [rax+rax+00h]
0x180097704  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009770b  mov     edi, eax
0x18009770d  test    rcx, rcx
0x180097710  jz      short loc_180097764
0x180097712  mov     ebx, 3
0x180097717  lea     r9, aFailedToGetSys_4; "Failed to get system directory"
0x18009771e  mov     r8d, ebx
0x180097721  xor     edx, edx
0x180097723  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180097728  test    edi, edi
0x18009772a  jg      short loc_180097730
0x18009772c  mov     eax, edi
0x18009772e  jmp     short loc_180097738
0x180097730  movzx   eax, di
0x180097733  or      eax, 80070000h
0x180097738  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009773f  lea     r9, a0; ": {0}"
0x180097746  mov     [rbp+arg_8], eax
0x180097749  mov     r8d, ebx
0x18009774c  lea     rax, [rbp+arg_8]
0x180097750  mov     dl, 1
0x180097752  mov     [rbp+arg_18], rax
0x180097756  lea     rax, [rbp+arg_18]
0x18009775a  mov     qword ptr [rsp+30h+var_10], rax
0x18009775f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180097764  test    edi, edi
0x180097766  jz      loc_180097BAA
0x18009776c  mov     edx, 32h ; '2'
0x180097771  jmp     loc_180097697
0x180097776  lea     rcx, [rbp+lpBuffer]
0x18009777a  call    SczEnsureBackslashTerminated
0x18009777f  mov     ebx, eax
0x180097781  test    eax, eax
0x180097783  jns     short loc_18009778F
0x180097785  mov     edx, 33h ; '3'
0x18009778a  jmp     loc_1800976CA
0x18009778f  lea     rdx, aCryptcatsvcDll; "cryptcatsvc.dll"
0x180097796  lea     rcx, [rbp+lpBuffer]
0x18009779a  call    SczAllocConcatSz
0x18009779f  mov     ebx, eax
0x1800977a1  test    eax, eax
0x1800977a3  jns     short loc_1800977AF
0x1800977a5  mov     edx, 34h ; '4'
0x1800977aa  jmp     loc_1800976CA
0x1800977af  mov     rcx, [rbp+lpBuffer]; lpFileName
0x1800977b3  call    cs:__imp_GetFileAttributesW
0x1800977ba  nop     dword ptr [rax+rax+00h]
0x1800977bf  cmp     eax, 0FFFFFFFFh
0x1800977c2  jnz     short loc_180097842
0x1800977c4  call    cs:__imp_GetLastError
0x1800977cb  nop     dword ptr [rax+rax+00h]
0x1800977d0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800977d7  mov     edi, eax
0x1800977d9  test    rcx, rcx
0x1800977dc  jz      short loc_180097830
0x1800977de  mov     ebx, 3
0x1800977e3  lea     r9, aWintrustCatalo; "Wintrust catalog support is not present"...
0x1800977ea  mov     r8d, ebx
0x1800977ed  xor     edx, edx
0x1800977ef  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800977f4  test    edi, edi
0x1800977f6  jg      short loc_1800977FC
0x1800977f8  mov     eax, edi
0x1800977fa  jmp     short loc_180097804
0x1800977fc  movzx   eax, di
0x1800977ff  or      eax, 80070000h
0x180097804  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009780b  lea     r9, a0; ": {0}"
0x180097812  mov     [rbp+arg_8], eax
0x180097815  mov     r8d, ebx
0x180097818  lea     rax, [rbp+arg_8]
0x18009781c  mov     dl, 1
0x18009781e  mov     [rbp+arg_18], rax
0x180097822  lea     rax, [rbp+arg_18]
0x180097826  mov     qword ptr [rsp+30h+var_10], rax
0x18009782b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180097830  test    edi, edi
0x180097832  jz      loc_180097BAA
0x180097838  mov     edx, 37h ; '7'
0x18009783d  jmp     loc_180097697
0x180097842  mov     rcx, cs:hLibModule; hModule
0x180097849  lea     rdx, aCryptcatadmina_0; "CryptCATAdminAcquireContext"
0x180097850  call    cs:__imp_GetProcAddress
0x180097857  nop     dword ptr [rax+rax+00h]
0x18009785c  mov     cs:?vpfnCryptCATAdminAcquireContext@@3P6AHPEAPEAXPEBU_GUID@@K@ZEA, rax; int (*vpfnCryptCATAdminAcquireContext)(void * *,_GUID const *,ulong)
0x180097863  test    rax, rax
0x180097866  jnz     loc_1800978EE
0x18009786c  call    cs:__imp_GetLastError
0x180097873  nop     dword ptr [rax+rax+00h]
0x180097878  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009787f  mov     ebx, 3
0x180097884  mov     edi, eax
0x180097886  test    rcx, rcx
0x180097889  jz      short loc_1800978D8
0x18009788b  lea     r9, aFailedToGetPro_36; "Failed to get proc address for CryptCAT"...
0x180097892  mov     r8d, ebx
0x180097895  xor     edx, edx
0x180097897  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18009789c  test    edi, edi
0x18009789e  jg      short loc_1800978A4
0x1800978a0  mov     eax, edi
0x1800978a2  jmp     short loc_1800978AC
0x1800978a4  movzx   eax, di
0x1800978a7  or      eax, 80070000h
0x1800978ac  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800978b3  lea     r9, a0; ": {0}"
0x1800978ba  mov     [rbp+arg_8], eax
0x1800978bd  mov     r8d, ebx
0x1800978c0  lea     rax, [rbp+arg_8]
0x1800978c4  mov     dl, 1
0x1800978c6  mov     [rbp+arg_18], rax
0x1800978ca  lea     rax, [rbp+arg_18]
0x1800978ce  mov     qword ptr [rsp+30h+var_10], rax
0x1800978d3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800978d8  test    edi, edi
0x1800978da  jz      loc_180097BAA
0x1800978e0  lea     r8, aOnecoreBaseCbs_94; "onecore\\base\\cbs\\core\\cryptcatdelay"...
0x1800978e7  mov     edx, ebx
0x1800978e9  jmp     loc_18009769E
0x1800978ee  mov     rcx, cs:hLibModule; hModule
0x1800978f5  lea     rdx, aCryptcatadmina; "CryptCATAdminAddCatalog"
0x1800978fc  call    cs:__imp_GetProcAddress
0x180097903  nop     dword ptr [rax+rax+00h]
0x180097908  mov     cs:?vpfnCryptCATAdminAddCatalog@@3P6APEAXPEAXPEA_W1K@ZEA, rax; void * (*vpfnCryptCATAdminAddCatalog)(void *,wchar_t *,wchar_t *,ulong)
0x18009790f  test    rax, rax
0x180097912  jnz     loc_18009799D
0x180097918  call    cs:__imp_GetLastError
0x18009791f  nop     dword ptr [rax+rax+00h]
0x180097924  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009792b  mov     edi, eax
0x18009792d  test    rcx, rcx
0x180097930  jz      short loc_180097984
0x180097932  mov     ebx, 3
0x180097937  lea     r9, aFailedToGetPro_25; "Failed to get proc address for CryptCAT"...
0x18009793e  mov     r8d, ebx
0x180097941  xor     edx, edx
0x180097943  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180097948  test    edi, edi
0x18009794a  jg      short loc_180097950
0x18009794c  mov     eax, edi
0x18009794e  jmp     short loc_180097958
0x180097950  movzx   eax, di
0x180097953  or      eax, 80070000h
0x180097958  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009795f  lea     r9, a0; ": {0}"
0x180097966  mov     [rbp+arg_8], eax
0x180097969  mov     r8d, ebx
0x18009796c  lea     rax, [rbp+arg_8]
0x180097970  mov     dl, 1
0x180097972  mov     [rbp+arg_18], rax
0x180097976  lea     rax, [rbp+arg_18]
0x18009797a  mov     qword ptr [rsp+30h+var_10], rax
0x18009797f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180097984  test    edi, edi
0x180097986  jz      loc_180097BAA
0x18009798c  lea     r8, aOnecoreBaseCbs_94; "onecore\\base\\cbs\\core\\cryptcatdelay"...
0x180097993  mov     edx, 8
0x180097998  jmp     loc_18009769E
0x18009799d  mov     rcx, cs:hLibModule; hModule
0x1800979a4  lea     rdx, aCryptcatadminr_1; "CryptCATAdminReleaseCatalogContext"
0x1800979ab  call    cs:__imp_GetProcAddress
0x1800979b2  nop     dword ptr [rax+rax+00h]
0x1800979b7  mov     cs:?vpfnCryptCATAdminReleaseCatalogContext@@3P6AHPEAX0K@ZEA, rax; int (*vpfnCryptCATAdminReleaseCatalogContext)(void *,void *,ulong)
0x1800979be  test    rax, rax
0x1800979c1  jnz     loc_180097A4C
0x1800979c7  call    cs:__imp_GetLastError
0x1800979ce  nop     dword ptr [rax+rax+00h]
0x1800979d3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800979da  mov     edi, eax
0x1800979dc  test    rcx, rcx
0x1800979df  jz      short loc_180097A33
0x1800979e1  mov     ebx, 3
0x1800979e6  lea     r9, aFailedToGetPro_9; "Failed to get proc address for CryptCAT"...
0x1800979ed  mov     r8d, ebx
0x1800979f0  xor     edx, edx
0x1800979f2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800979f7  test    edi, edi
0x1800979f9  jg      short loc_1800979FF
0x1800979fb  mov     eax, edi
0x1800979fd  jmp     short loc_180097A07
0x1800979ff  movzx   eax, di
0x180097a02  or      eax, 80070000h
0x180097a07  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180097a0e  lea     r9, a0; ": {0}"
0x180097a15  mov     [rbp+arg_8], eax
0x180097a18  mov     r8d, ebx
0x180097a1b  lea     rax, [rbp+arg_8]
  ... truncated ...
```
