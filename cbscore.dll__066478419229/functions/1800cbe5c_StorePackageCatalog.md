# StorePackageCatalog

- ea: `0x1800cbe5c`
- end: `0x1800cc400`
- name: `StorePackageCatalog`
- size: `1444`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000b5fc`

## callees

- `0x180013250`
- `0x180016d40`
- `0x1800603c8`
- `0x180093c4c`
- `0x180094320`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800c82d8`
- `0x1800cbe5c`
- `0x1800eb920`
- `0x180106a0c`
- `0x1801dd9ac`
- `0x1801e95a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc2a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc2a7`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800cc183`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800cc183`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800cc146`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800cc146`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800cc268`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800cc268`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800cc242`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800cc242`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x1800cc293`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x1800cc293`

## string_xrefs

- `0x1800cc2ce`: `Failed to copy package catalog '{}' to store: {}`
- `0x1800cc379`: `Failed to set security info on '{}'`
- `0x1800cbfec`: `Failed to install catalog file {} for package`
- `0x1800cc052`: `Failed to install catalog file {} for package`
- `0x1800cc0f3`: `Failed to remove catalog file {} from drainlist`
- `0x1800cbeb4`: `No package store directory specified`
- `0x1800cc1ad`: `File already exists when adding the catalog: {}`
- `0x1800cc1db`: `Failed to delete existing package catalog '{}'`

## pseudocode

```c
__int64 __fastcall StorePackageCatalog(const WCHAR *a1, __int64 a2, const WCHAR *a3, __int64 a4)
{
  unsigned int v6; // edi
  int v7; // edx
  __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // edx
  int v11; // eax
  wchar_t *v12; // rbx
  int v13; // eax
  int v14; // edx
  int v15; // eax
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // eax
  int v20; // edx
  __int64 v21; // rdx
  __int64 v22; // rcx
  signed int LastError; // edi
  int v24; // edx
  unsigned int v25; // eax
  int v26; // eax
  int v27; // edx
  unsigned int v29; // [rsp+20h] [rbp-50h]
  _BYTE v30[8]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v31[2]; // [rsp+38h] [rbp-38h] BYREF
  LPCWSTR v32; // [rsp+40h] [rbp-30h] BYREF
  PCNZWCH lpString1; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+50h] [rbp-20h] BYREF
  int v35; // [rsp+58h] [rbp-18h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  lpExistingFileName = a1;
  lpString1 = 0;
  lpFileName = 0;
  if ( !a3 )
  {
    v6 = -2147024809;
    v35 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No package store directory specified");
      *(_QWORD *)v31 = &v35;
      LOBYTE(v7) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v7,
        3,
        (unsigned int)": {}",
        (__int64)v31);
    }
    v8 = 2147942487LL;
    v9 = 4686;
    goto LABEL_12;
  }
  if ( !a4 )
  {
    v6 = -2147024809;
    v35 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No package identity specified");
      *(_QWORD *)v31 = &v35;
      LOBYTE(v10) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v10,
        3,
        (unsigned int)": {}",
        (__int64)v31);
    }
    v8 = 2147942487LL;
    v9 = 4687;
    goto LABEL_12;
  }
  v11 = SczAllocConcat2Sz(&lpString1, a4, L".cat");
  v6 = v11;
  if ( v11 >= 0 )
  {
    v12 = (wchar_t *)lpString1;
    v11 = SczAllocConcat2Sz(&lpFileName, a3, lpString1);
    v6 = v11;
    if ( v11 < 0 )
    {
      v9 = 4695;
      goto LABEL_11;
    }
    if ( lpExistingFileName )
    {
      v13 = CbsInstallCatalogFile(a2, lpExistingFileName, v12);
      v6 = v13;
      if ( v13 < 0 )
      {
        v35 = v13;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to install catalog file {} for package",
            (__int64)&lpExistingFileName);
          *(_QWORD *)v31 = &v35;
          LOBYTE(v14) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v14,
            3,
            (unsigned int)": {}",
            (__int64)v31);
        }
        v8 = v6;
        v9 = 4700;
        goto LABEL_12;
      }
    }
    else
    {
      v15 = CbsInstallCatalogFile(a2, lpFileName, v12);
      v6 = v15;
      if ( v15 < 0 )
      {
        v35 = v15;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v31 = lpFileName;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to install catalog file {} for package",
            (__int64)v31);
          v32 = (LPCWSTR)&v35;
          LOBYTE(v16) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v16,
            3,
            (unsigned int)": {}",
            (__int64)&v32);
        }
        v8 = v6;
        v9 = 4705;
        goto LABEL_12;
      }
    }
    if ( !a2 )
    {
      v6 = RemoveCatalogFileFromDrainlistOnline(v12);
      if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147024894 )
      {
        v35 = v6;
        if ( LogAdapter::g_Logger )
        {
          v32 = v12;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to remove catalog file {} from drainlist",
            (__int64)&v32);
          *(_QWORD *)v31 = &v35;
          LOBYTE(v17) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v17,
            3,
            (unsigned int)": {}",
            (__int64)v31);
        }
        v8 = v6;
        v9 = 4715;
        goto LABEL_12;
      }
    }
    if ( lpExistingFileName )
    {
      if ( GetFileAttributesW(lpFileName) != -1 )
      {
        v30[0] = 0;
        if ( (int)IsFileBackedByCim(lpFileName, v30) >= 0 && v30[0] )
          goto LABEL_53;
        SetFileAttributesW(lpFileName, 0x80u);
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v18) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v18,
            1,
            (unsigned int)"File already exists when adding the catalog: {}",
            (__int64)&lpFileName);
        }
        v19 = CbsSetAttrAndDeleteFile(lpFileName);
        v6 = v19;
        if ( v19 < 0 )
        {
          v35 = v19;
          if ( LogAdapter::g_Logger )
          {
            v32 = lpFileName;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to delete existing package catalog '{}'",
              (__int64)&v32);
            *(_QWORD *)v31 = &v35;
            LOBYTE(v20) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v20,
              3,
              (unsigned int)": {}",
              (__int64)v31);
          }
          v8 = v6;
          v9 = 4740;
          goto LABEL_12;
        }
      }
      if ( MoveFileExW(lpExistingFileName, lpFileName, 8u)
        || (LogAdapter::TraceAtLevelLastError<wchar_t const *,AutoScz>(v22, v21, &lpExistingFileName, &lpFileName),
            Sleep(0x3E8u),
            (unsigned int)PrivCopyFileExW(lpExistingFileName, lpFileName, 0, 0, 0, 256)) )
      {
        v26 = SetSecurityInfoFromFileTemplate(lpFileName, a3);
        v6 = v26;
        if ( v26 < 0 )
        {
          v35 = v26;
          if ( LogAdapter::g_Logger )
          {
            v32 = lpFileName;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to set security info on '{}'",
              (__int64)&v32);
            *(_QWORD *)v31 = &v35;
            LOBYTE(v27) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v27,
              3,
              (unsigned int)": {}",
              (__int64)v31);
          }
          v8 = v6;
          v9 = 4758;
          goto LABEL_12;
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          v32 = lpFileName;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to copy package catalog '{}' to store: {}",
            (__int64)&lpExistingFileName,
            (__int64)&v32);
          if ( LastError > 0 )
            v25 = (unsigned __int16)LastError | 0x80070000;
          else
            v25 = LastError;
          v35 = v25;
          LOBYTE(v24) = 1;
          *(_QWORD *)v31 = &v35;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v24,
            3,
            (unsigned int)": {0}",
            (__int64)v31);
        }
        if ( LastError )
        {
          v6 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x1292,
                 (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
                 (const char *)(unsigned int)LastError,
                 v29);
          goto LABEL_54;
        }
      }
    }
LABEL_53:
    v6 = 0;
    goto LABEL_54;
  }
  v9 = 4693;
LABEL_11:
  v8 = (unsigned int)v11;
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
    (const char *)v8,
    v29);
LABEL_54:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpString1);
  return v6;
}

```

## disassembly

```asm
0x1800cbe5c  push    rbp
0x1800cbe5e  push    rbx
0x1800cbe5f  push    rsi
0x1800cbe60  push    rdi
0x1800cbe61  push    r14
0x1800cbe63  mov     rbp, rsp
0x1800cbe66  sub     rsp, 70h
0x1800cbe6a  mov     rax, cs:__security_cookie
0x1800cbe71  xor     rax, rsp
0x1800cbe74  mov     [rbp+var_8], rax
0x1800cbe78  mov     [rbp+lpExistingFileName], rcx
0x1800cbe7c  mov     r14, r8
0x1800cbe7f  mov     [rbp+lpString1], 0
0x1800cbe87  mov     rsi, rdx
0x1800cbe8a  mov     [rbp+lpFileName], 0
0x1800cbe92  test    r8, r8
0x1800cbe95  jnz     short loc_1800CBEF6
0x1800cbe97  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cbe9e  mov     edi, 80070057h
0x1800cbea3  mov     [rbp+var_18], edi
0x1800cbea6  test    rcx, rcx
0x1800cbea9  jz      short loc_1800CBEE9
0x1800cbeab  lea     ebx, [r8+3]
0x1800cbeaf  xor     edx, edx
0x1800cbeb1  mov     r8d, ebx
0x1800cbeb4  lea     r9, aNoPackageStore_0; "No package store directory specified"
0x1800cbebb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cbec0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cbec7  lea     rax, [rbp+var_18]
0x1800cbecb  mov     qword ptr [rbp+var_38], rax
0x1800cbecf  lea     r9, asc_1802EE7AC; ": {}"
0x1800cbed6  lea     rax, [rbp+var_38]
0x1800cbeda  mov     r8d, ebx
0x1800cbedd  mov     dl, 1
0x1800cbedf  mov     qword ptr [rsp+70h+var_50], rax
0x1800cbee4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cbee9  mov     r9d, edi
0x1800cbeec  mov     edx, 124Eh
0x1800cbef1  jmp     loc_1800CBF79
0x1800cbef6  test    r9, r9
0x1800cbef9  jnz     short loc_1800CBF58
0x1800cbefb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cbf02  mov     edi, 80070057h
0x1800cbf07  mov     [rbp+var_18], edi
0x1800cbf0a  test    rcx, rcx
0x1800cbf0d  jz      short loc_1800CBF4E
0x1800cbf0f  mov     ebx, 3
0x1800cbf14  lea     r9, aNoPackageIdent_0; "No package identity specified"
0x1800cbf1b  mov     r8d, ebx
0x1800cbf1e  xor     edx, edx
0x1800cbf20  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cbf25  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cbf2c  lea     rax, [rbp+var_18]
0x1800cbf30  mov     qword ptr [rbp+var_38], rax
0x1800cbf34  lea     r9, asc_1802EE7AC; ": {}"
0x1800cbf3b  lea     rax, [rbp+var_38]
0x1800cbf3f  mov     r8d, ebx
0x1800cbf42  mov     dl, 1
0x1800cbf44  mov     qword ptr [rsp+70h+var_50], rax
0x1800cbf49  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cbf4e  mov     r9d, edi
0x1800cbf51  mov     edx, 124Fh
0x1800cbf56  jmp     short loc_1800CBF79
0x1800cbf58  lea     r8, aCat_0; ".cat"
0x1800cbf5f  mov     rdx, r9
0x1800cbf62  lea     rcx, [rbp+lpString1]
0x1800cbf66  call    SczAllocConcat2Sz
0x1800cbf6b  mov     edi, eax
0x1800cbf6d  test    eax, eax
0x1800cbf6f  jns     short loc_1800CBF8E
0x1800cbf71  mov     edx, 1255h; void *
0x1800cbf76  mov     r9d, eax; char *
0x1800cbf79  mov     rcx, [rbp+28h]; this
0x1800cbf7d  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x1800cbf84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cbf89  jmp     loc_1800CC3D4
0x1800cbf8e  mov     rbx, [rbp+lpString1]
0x1800cbf92  lea     rcx, [rbp+lpFileName]
0x1800cbf96  mov     r8, rbx
0x1800cbf99  mov     rdx, r14
0x1800cbf9c  call    SczAllocConcat2Sz
0x1800cbfa1  mov     edi, eax
0x1800cbfa3  test    eax, eax
0x1800cbfa5  jns     short loc_1800CBFAE
0x1800cbfa7  mov     edx, 1257h
0x1800cbfac  jmp     short loc_1800CBF76
0x1800cbfae  mov     rdx, [rbp+lpExistingFileName]
0x1800cbfb2  mov     r8, rbx
0x1800cbfb5  mov     rcx, rsi
0x1800cbfb8  test    rdx, rdx
0x1800cbfbb  jz      short loc_1800CC030
0x1800cbfbd  call    CbsInstallCatalogFile
0x1800cbfc2  mov     edi, eax
0x1800cbfc4  test    eax, eax
0x1800cbfc6  jns     loc_1800CC0AB
0x1800cbfcc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cbfd3  mov     [rbp+var_18], eax
0x1800cbfd6  test    rcx, rcx
0x1800cbfd9  jz      short loc_1800CC023
0x1800cbfdb  lea     rax, [rbp+lpExistingFileName]
0x1800cbfdf  mov     ebx, 3
0x1800cbfe4  mov     r8d, ebx
0x1800cbfe7  mov     qword ptr [rsp+70h+var_50], rax
0x1800cbfec  lea     r9, aFailedToInstal_2; "Failed to install catalog file {} for p"...
0x1800cbff3  xor     edx, edx
0x1800cbff5  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800cbffa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc001  lea     rax, [rbp+var_18]
0x1800cc005  mov     qword ptr [rbp+var_38], rax
0x1800cc009  lea     r9, asc_1802EE7AC; ": {}"
0x1800cc010  lea     rax, [rbp+var_38]
0x1800cc014  mov     r8d, ebx
0x1800cc017  mov     dl, 1
0x1800cc019  mov     qword ptr [rsp+70h+var_50], rax
0x1800cc01e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cc023  mov     r9d, edi
0x1800cc026  mov     edx, 125Ch
0x1800cc02b  jmp     loc_1800CBF79
0x1800cc030  mov     rdx, [rbp+lpFileName]
0x1800cc034  call    CbsInstallCatalogFile
0x1800cc039  mov     edi, eax
0x1800cc03b  test    eax, eax
0x1800cc03d  jns     short loc_1800CC0AB
0x1800cc03f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc046  mov     [rbp+var_18], eax
0x1800cc049  test    rcx, rcx
0x1800cc04c  jz      short loc_1800CC09E
0x1800cc04e  mov     rax, [rbp+lpFileName]
0x1800cc052  lea     r9, aFailedToInstal_2; "Failed to install catalog file {} for p"...
0x1800cc059  mov     qword ptr [rbp+var_38], rax
0x1800cc05d  mov     ebx, 3
0x1800cc062  lea     rax, [rbp+var_38]
0x1800cc066  mov     r8d, ebx
0x1800cc069  xor     edx, edx
0x1800cc06b  mov     qword ptr [rsp+70h+var_50], rax
0x1800cc070  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800cc075  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc07c  lea     rax, [rbp+var_18]
0x1800cc080  mov     [rbp+var_30], rax
0x1800cc084  lea     r9, asc_1802EE7AC; ": {}"
0x1800cc08b  lea     rax, [rbp+var_30]
0x1800cc08f  mov     r8d, ebx
0x1800cc092  mov     dl, 1
0x1800cc094  mov     qword ptr [rsp+70h+var_50], rax
0x1800cc099  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cc09e  mov     r9d, edi
0x1800cc0a1  mov     edx, 1261h
0x1800cc0a6  jmp     loc_1800CBF79
0x1800cc0ab  test    rsi, rsi
0x1800cc0ae  jnz     loc_1800CC137
0x1800cc0b4  mov     rcx, rbx; lpString1
0x1800cc0b7  call    ?RemoveCatalogFileFromDrainlistOnline@@YAJPEA_W@Z; RemoveCatalogFileFromDrainlistOnline(wchar_t *)
0x1800cc0bc  mov     ecx, 80000000h
0x1800cc0c1  mov     edi, eax
0x1800cc0c3  add     eax, ecx
0x1800cc0c5  test    ecx, eax
0x1800cc0c7  jnz     short loc_1800CC137
0x1800cc0c9  cmp     edi, 80070002h
0x1800cc0cf  jz      short loc_1800CC137
0x1800cc0d1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc0d8  mov     [rbp+var_18], edi
0x1800cc0db  test    rcx, rcx
0x1800cc0de  jz      short loc_1800CC12A
0x1800cc0e0  mov     [rbp+var_30], rbx
0x1800cc0e4  lea     rax, [rbp+var_30]
0x1800cc0e8  lea     ebx, [rsi+3]
0x1800cc0eb  mov     qword ptr [rsp+70h+var_50], rax
0x1800cc0f0  mov     r8d, ebx
0x1800cc0f3  lea     r9, aFailedToRemove_11; "Failed to remove catalog file {} from d"...
0x1800cc0fa  xor     edx, edx
0x1800cc0fc  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800cc101  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc108  lea     rax, [rbp+var_18]
0x1800cc10c  mov     qword ptr [rbp+var_38], rax
0x1800cc110  lea     r9, asc_1802EE7AC; ": {}"
0x1800cc117  lea     rax, [rbp+var_38]
0x1800cc11b  mov     r8d, ebx
0x1800cc11e  mov     dl, 1
0x1800cc120  mov     qword ptr [rsp+70h+var_50], rax
0x1800cc125  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cc12a  mov     r9d, edi
0x1800cc12d  mov     edx, 126Bh
0x1800cc132  jmp     loc_1800CBF79
0x1800cc137  cmp     [rbp+lpExistingFileName], 0
0x1800cc13c  jz      loc_1800CC3D2
0x1800cc142  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800cc146  call    cs:__imp_GetFileAttributesW
0x1800cc14d  nop     dword ptr [rax+rax+00h]
0x1800cc152  cmp     eax, 0FFFFFFFFh
0x1800cc155  jz      loc_1800CC234
0x1800cc15b  mov     rcx, [rbp+lpFileName]
0x1800cc15f  lea     rdx, [rbp+var_40]
0x1800cc163  mov     [rbp+var_40], 0
0x1800cc167  call    IsFileBackedByCim
0x1800cc16c  test    eax, eax
0x1800cc16e  js      short loc_1800CC17A
0x1800cc170  cmp     [rbp+var_40], 0
0x1800cc174  jnz     loc_1800CC3D2
0x1800cc17a  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800cc17e  mov     edx, 80h; dwFileAttributes
0x1800cc183  call    cs:__imp_SetFileAttributesW
0x1800cc18a  nop     dword ptr [rax+rax+00h]
0x1800cc18f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc196  test    rcx, rcx
0x1800cc199  jz      short loc_1800CC1B9
0x1800cc19b  mov     r8d, 1
0x1800cc1a1  lea     rax, [rbp+lpFileName]
0x1800cc1a5  mov     dl, r8b
0x1800cc1a8  mov     qword ptr [rsp+70h+var_50], rax
0x1800cc1ad  lea     r9, aFileAlreadyExi_0; "File already exists when adding the cat"...
0x1800cc1b4  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800cc1b9  mov     rcx, [rbp+lpFileName]; lpExistingFileName
0x1800cc1bd  call    CbsSetAttrAndDeleteFile
0x1800cc1c2  mov     edi, eax
0x1800cc1c4  test    eax, eax
0x1800cc1c6  jns     short loc_1800CC234
0x1800cc1c8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc1cf  mov     [rbp+var_18], eax
0x1800cc1d2  test    rcx, rcx
0x1800cc1d5  jz      short loc_1800CC227
0x1800cc1d7  mov     rax, [rbp+lpFileName]
0x1800cc1db  lea     r9, aFailedToDelete_4; "Failed to delete existing package catal"...
0x1800cc1e2  mov     [rbp+var_30], rax
0x1800cc1e6  mov     ebx, 3
0x1800cc1eb  lea     rax, [rbp+var_30]
0x1800cc1ef  mov     r8d, ebx
0x1800cc1f2  xor     edx, edx
0x1800cc1f4  mov     qword ptr [rsp+70h+var_50], rax
0x1800cc1f9  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800cc1fe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc205  lea     rax, [rbp+var_18]
0x1800cc209  mov     qword ptr [rbp+var_38], rax
0x1800cc20d  lea     r9, asc_1802EE7AC; ": {}"
0x1800cc214  lea     rax, [rbp+var_38]
0x1800cc218  mov     r8d, ebx
0x1800cc21b  mov     dl, 1
0x1800cc21d  mov     qword ptr [rsp+70h+var_50], rax
0x1800cc222  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cc227  mov     r9d, edi
0x1800cc22a  mov     edx, 1284h
0x1800cc22f  jmp     loc_1800CBF79
0x1800cc234  mov     rdx, [rbp+lpFileName]; lpNewFileName
0x1800cc238  mov     r8d, 8; dwFlags
0x1800cc23e  mov     rcx, [rbp+lpExistingFileName]; lpExistingFileName
0x1800cc242  call    cs:__imp_MoveFileExW
0x1800cc249  nop     dword ptr [rax+rax+00h]
0x1800cc24e  test    eax, eax
0x1800cc250  jnz     loc_1800CC354
0x1800cc256  lea     r9, [rbp+lpFileName]
0x1800cc25a  lea     r8, [rbp+lpExistingFileName]
0x1800cc25e  call    ??$TraceAtLevelLastError@PEB_WVAutoScz@@@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEB_WAEBVAutoScz@@@Z; LogAdapter::TraceAtLevelLastError<wchar_t const *,AutoScz>(LogAdapter::LogLevel,char const * const,wchar_t const * const &,AutoScz const &)
0x1800cc263  mov     ecx, 3E8h; dwMilliseconds
0x1800cc268  call    cs:__imp_Sleep
0x1800cc26f  nop     dword ptr [rax+rax+00h]
0x1800cc274  mov     rdx, [rbp+lpFileName]
0x1800cc278  xor     r9d, r9d
0x1800cc27b  mov     rcx, [rbp+lpExistingFileName]
0x1800cc27f  xor     r8d, r8d
0x1800cc282  mov     dword ptr [rsp+70h+var_48], 100h
0x1800cc28a  mov     qword ptr [rsp+70h+var_50], 0
0x1800cc293  call    cs:__imp_PrivCopyFileExW
0x1800cc29a  nop     dword ptr [rax+rax+00h]
0x1800cc29f  test    eax, eax
0x1800cc2a1  jnz     loc_1800CC354
0x1800cc2a7  call    cs:__imp_GetLastError
0x1800cc2ae  nop     dword ptr [rax+rax+00h]
0x1800cc2b3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc2ba  mov     edi, eax
0x1800cc2bc  test    rcx, rcx
0x1800cc2bf  jz      short loc_1800CC32D
0x1800cc2c1  mov     rdx, [rbp+lpFileName]
0x1800cc2c5  lea     rax, [rbp+var_30]
0x1800cc2c9  mov     [rsp+70h+var_48], rax
0x1800cc2ce  lea     r9, aFailedToCopyPa_0; "Failed to copy package catalog '{}' to "...
0x1800cc2d5  lea     rax, [rbp+lpExistingFileName]
0x1800cc2d9  mov     [rbp+var_30], rdx
0x1800cc2dd  mov     ebx, 3
0x1800cc2e2  mov     qword ptr [rsp+70h+var_50], rax
0x1800cc2e7  mov     r8d, ebx
0x1800cc2ea  xor     edx, edx
0x1800cc2ec  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1800cc2f1  test    edi, edi
0x1800cc2f3  jg      short loc_1800CC2F9
0x1800cc2f5  mov     eax, edi
0x1800cc2f7  jmp     short loc_1800CC301
0x1800cc2f9  movzx   eax, di
0x1800cc2fc  or      eax, 80070000h
0x1800cc301  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cc308  lea     r9, a0; ": {0}"
0x1800cc30f  mov     [rbp+var_18], eax
0x1800cc312  mov     r8d, ebx
0x1800cc315  lea     rax, [rbp+var_18]
0x1800cc319  mov     dl, 1
0x1800cc31b  mov     qword ptr [rbp+var_38], rax
0x1800cc31f  lea     rax, [rbp+var_38]
0x1800cc323  mov     qword ptr [rsp+70h+var_50], rax; unsigned int
0x1800cc328  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cc32d  test    edi, edi
0x1800cc32f  jz      loc_1800CC3D2
0x1800cc335  mov     rcx, [rbp+28h]; this
  ... truncated ...
```
