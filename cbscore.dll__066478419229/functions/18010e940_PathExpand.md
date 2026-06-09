# PathExpand

- ea: `0x18010e940`
- end: `0x18010f053`
- name: `PathExpand`
- size: `1811`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x1800d3070`
- `0x1802ae0e0`
- `0x1802ae4f0`

## callees

- `0x180013250`
- `0x180015420`
- `0x180033d50`
- `0x18004a658`
- `0x18005ad5c`
- `0x18005eef0`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb500`
- `0x1800eb920`
- `0x18010e940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010eb1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010ec2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010edf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010eecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010eb1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010ec2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010edf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010eecc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010eb04`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010ec16`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010eb04`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010ec16`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18010eddc`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18010eeb8`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18010eddc`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18010eeb8`

## string_xrefs

- `0x18010e99e`: `No full path result specified`
- `0x18010e9f9`: `No relative path specified`
- `0x18010ef70`: `Failed to allocate buffer for full path.`
- `0x18010ecd1`: `Failed to allocate buffer for expanded path.`
- `0x18010ee1b`: `Failed to get full path for string: {}`
- `0x18010eef7`: `Failed to get full path for string: {}`
- `0x18010ea3a`: `onecore\base\cbs\util\cbspath.cpp`
- `0x18010eba0`: `onecore\base\cbs\util\cbspath.cpp`
- `0x18010ea6a`: `Invalid relative path specified`

## pseudocode

```c
__int64 __fastcall PathExpand(LPWSTR *a1, const WCHAR *a2)
{
  unsigned int v3; // edi
  int v4; // edx
  __int64 v5; // rdx
  int v6; // edx
  unsigned __int64 v7; // r9
  int v8; // edx
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // rsi
  int v11; // eax
  int v12; // eax
  LPWSTR v13; // rbx
  DWORD v14; // eax
  unsigned int v15; // ecx
  signed int LastError; // edi
  int v17; // edx
  DWORD v18; // eax
  __int64 v19; // rdx
  unsigned __int64 v20; // r15
  int v21; // eax
  int v22; // eax
  DWORD v23; // eax
  int v24; // edx
  DWORD v25; // eax
  int v26; // edx
  int v27; // eax
  int v28; // ecx
  int v29; // eax
  const WCHAR *v30; // rax
  int v31; // eax
  DWORD v32; // esi
  int v33; // eax
  LPWSTR v34; // rbx
  DWORD FullPathNameW; // eax
  const struct std::nothrow_t *v36; // rdx
  int v37; // edx
  DWORD v38; // eax
  DWORD v39; // esi
  int v40; // eax
  int v41; // edx
  DWORD v42; // eax
  int v43; // edx
  int v44; // eax
  int v46; // eax
  unsigned int v47; // [rsp+20h] [rbp-50h]
  LPWSTR lpBuffer; // [rsp+30h] [rbp-40h] BYREF
  LPWSTR lpDst; // [rsp+38h] [rbp-38h] BYREF
  DWORD *p_nSize; // [rsp+40h] [rbp-30h] BYREF
  LPWSTR FilePart; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-20h] BYREF
  LPCWSTR lpSrc; // [rsp+58h] [rbp-18h] BYREF
  DWORD nSize; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  lpSrc = a2;
  lpDst = 0;
  nSize = 0;
  lpBuffer = 0;
  if ( !a1 )
  {
    v3 = -2147467261;
    nSize = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No full path result specified");
      FilePart = (LPWSTR)&nSize;
      LOBYTE(v4) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v4,
        3,
        (unsigned int)": {}",
        (__int64)&FilePart);
    }
    v5 = 39;
    goto LABEL_9;
  }
  if ( !a2 )
  {
    v3 = -2147024809;
    nSize = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No relative path specified");
      FilePart = (LPWSTR)&nSize;
      LOBYTE(v6) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v6,
        3,
        (unsigned int)": {}",
        (__int64)&FilePart);
    }
    v5 = 40;
    goto LABEL_9;
  }
  if ( !*a2 )
  {
    v3 = -2147024809;
    nSize = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid relative path specified");
      FilePart = (LPWSTR)&nSize;
      LOBYTE(v8) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v8,
        3,
        (unsigned int)": {}",
        (__int64)&FilePart);
    }
    v5 = 41;
    goto LABEL_9;
  }
  v9 = 64;
  lpFileName = (LPCWSTR)64;
  v10 = 64;
  v11 = SczAlloc(&lpDst, 64);
  v3 = v11;
  if ( v11 < 0 )
  {
    v7 = (unsigned int)v11;
    v5 = 50;
    goto LABEL_10;
  }
  v12 = ULongLongToULong(0x40u, &nSize);
  v3 = v12;
  if ( v12 < 0 )
  {
    v7 = (unsigned int)v12;
    v5 = 51;
    goto LABEL_10;
  }
  v13 = lpDst;
  v14 = ExpandEnvironmentStringsW(lpSrc, lpDst, nSize);
  v15 = v14;
  if ( !v14 )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to expand environment variables in string: {}",
        (__int64)&lpSrc);
      if ( LastError > 0 )
        v18 = (unsigned __int16)LastError | 0x80070000;
      else
        v18 = LastError;
      nSize = v18;
      LOBYTE(v17) = 1;
      FilePart = (LPWSTR)&nSize;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v17,
        3,
        (unsigned int)": {0}",
        (__int64)&FilePart);
    }
    if ( LastError )
    {
      v19 = 54;
LABEL_27:
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v19,
             (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
             (const char *)(unsigned int)LastError,
             v47);
      goto LABEL_95;
    }
    goto LABEL_94;
  }
  v20 = v14;
  if ( v14 > 0x40uLL )
  {
    v10 = v14;
    lpFileName = (LPCWSTR)v14;
    v21 = SczAlloc(&lpDst, v14);
    v3 = v21;
    if ( v21 < 0 )
    {
      v7 = (unsigned int)v21;
      v5 = 59;
      goto LABEL_10;
    }
    v22 = ULongLongToULong(v20, &nSize);
    v3 = v22;
    if ( v22 < 0 )
    {
      v7 = (unsigned int)v22;
      v5 = 60;
      goto LABEL_10;
    }
    v13 = lpDst;
    v23 = ExpandEnvironmentStringsW(lpSrc, lpDst, nSize);
    v15 = v23;
    if ( !v23 )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to expand environment variables in string: {}",
          (__int64)&lpSrc);
        if ( LastError > 0 )
          v25 = (unsigned __int16)LastError | 0x80070000;
        else
          v25 = LastError;
        nSize = v25;
        LOBYTE(v24) = 1;
        FilePart = (LPWSTR)&nSize;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v24,
          3,
          (unsigned int)": {0}",
          (__int64)&FilePart);
      }
      if ( LastError )
      {
        v19 = 63;
        goto LABEL_27;
      }
      goto LABEL_94;
    }
    if ( v20 < v23 )
    {
      v3 = -2147024774;
      nSize = -2147024774;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate buffer for expanded path.");
        FilePart = (LPWSTR)&nSize;
        LOBYTE(v26) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v26,
          3,
          (unsigned int)": {}",
          (__int64)&FilePart);
      }
      v5 = 67;
      goto LABEL_9;
    }
  }
  if ( v15 <= 0x104 )
  {
LABEL_53:
    v30 = lpSrc;
    FilePart = 0;
    nSize = 0;
    if ( v13 )
      v30 = v13;
    lpFileName = v30;
    if ( v10 > 0x40 )
      v9 = v10;
    v31 = ULongLongToULong(v9, &nSize);
    v3 = v31;
    if ( v31 < 0 )
    {
      v7 = (unsigned int)v31;
      v5 = 95;
      goto LABEL_10;
    }
    v32 = nSize;
    v33 = SczAlloc(&lpBuffer, nSize);
    v3 = v33;
    if ( v33 < 0 )
    {
      v7 = (unsigned int)v33;
      v5 = 96;
      goto LABEL_10;
    }
    v34 = lpBuffer;
    FullPathNameW = GetFullPathNameW(lpFileName, v32, lpBuffer, &FilePart);
    if ( FullPathNameW )
    {
      if ( v32 < FullPathNameW )
      {
        v39 = FullPathNameW;
        if ( FullPathNameW >= 0x104 )
          v39 = FullPathNameW + 7;
        v40 = SczAlloc(&lpBuffer, v39);
        v3 = v40;
        if ( v40 < 0 )
        {
          v7 = (unsigned int)v40;
          v5 = 104;
          goto LABEL_10;
        }
        v34 = lpBuffer;
        FullPathNameW = GetFullPathNameW(lpFileName, v39, lpBuffer, &FilePart);
        if ( !FullPathNameW )
        {
          LastError = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to get full path for string: {}",
              (__int64)&lpFileName);
            if ( LastError > 0 )
              v42 = (unsigned __int16)LastError | 0x80070000;
            else
              v42 = LastError;
            nSize = v42;
            LOBYTE(v41) = 1;
            p_nSize = &nSize;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v41,
              3,
              (unsigned int)": {0}",
              (__int64)&p_nSize);
          }
          if ( LastError )
          {
            v19 = 107;
            goto LABEL_27;
          }
          goto LABEL_94;
        }
        if ( v39 < FullPathNameW )
        {
          v3 = -2147024774;
          nSize = -2147024774;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate buffer for full path.");
            p_nSize = &nSize;
            LOBYTE(v43) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v43,
              3,
              (unsigned int)": {}",
              (__int64)&p_nSize);
          }
          v5 = 111;
          goto LABEL_9;
        }
      }
      if ( FullPathNameW > 0x104 )
      {
        v44 = PathPrefix(&lpBuffer);
        v3 = v44;
        if ( v44 < 0 )
        {
          v7 = (unsigned int)v44;
          v5 = 117;
          goto LABEL_10;
        }
        v34 = lpBuffer;
      }
      if ( v34 )
      {
        if ( *a1 )
          operator delete(*a1 - 4, v36);
        lpBuffer = 0;
        *a1 = v34;
      }
      else
      {
        v46 = SczAllocFromSz(a1, lpSrc);
        v3 = v46;
        if ( v46 < 0 )
        {
          v7 = (unsigned int)v46;
          v5 = 132;
          goto LABEL_10;
        }
      }
      goto LABEL_94;
    }
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to get full path for string: {}",
        (__int64)&lpFileName);
      if ( LastError > 0 )
        v38 = (unsigned __int16)LastError | 0x80070000;
      else
        v38 = LastError;
      nSize = v38;
      LOBYTE(v37) = 1;
      p_nSize = &nSize;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v37,
        3,
        (unsigned int)": {0}",
        (__int64)&p_nSize);
    }
    if ( LastError )
    {
      v19 = 99;
      goto LABEL_27;
    }
LABEL_94:
    v3 = 0;
    goto LABEL_95;
  }
  v27 = PathPrefix(&lpDst);
  v28 = 0;
  if ( v27 != -2147024809 )
    v28 = v27;
  v3 = v28;
  if ( v28 >= 0 )
  {
    v13 = lpDst;
    v29 = SczSize(lpDst, &lpFileName);
    v3 = v29;
    if ( v29 < 0 )
    {
      v7 = (unsigned int)v29;
      v5 = 81;
      goto LABEL_10;
    }
    v10 = (unsigned __int64)lpFileName;
    goto LABEL_53;
  }
  v5 = 79;
LABEL_9:
  v7 = v3;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
    (const char *)v7,
    v47);
LABEL_95:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
  return v3;
}

```

## disassembly

```asm
0x18010e940  mov     [rsp-38h+arg_10], rbx
0x18010e945  push    rbp
0x18010e946  push    rsi
0x18010e947  push    rdi
0x18010e948  push    r12
0x18010e94a  push    r13
0x18010e94c  push    r14
0x18010e94e  push    r15
0x18010e950  mov     rbp, rsp
0x18010e953  sub     rsp, 70h
0x18010e957  mov     rax, cs:__security_cookie
0x18010e95e  xor     rax, rsp
0x18010e961  mov     [rbp+var_8], rax
0x18010e965  xor     r13d, r13d
0x18010e968  mov     [rbp+lpSrc], rdx
0x18010e96c  mov     [rbp+lpDst], r13
0x18010e970  mov     r12, rcx
0x18010e973  mov     [rbp+nSize], r13d
0x18010e977  mov     [rbp+lpBuffer], r13
0x18010e97b  test    rcx, rcx
0x18010e97e  jnz     short loc_18010E9DA
0x18010e980  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010e987  mov     edi, 80004003h
0x18010e98c  mov     [rbp+nSize], edi
0x18010e98f  test    rcx, rcx
0x18010e992  jz      short loc_18010E9D3
0x18010e994  lea     ebx, [r12+3]
0x18010e999  xor     edx, edx
0x18010e99b  mov     r8d, ebx
0x18010e99e  lea     r9, aNoFullPathResu; "No full path result specified"
0x18010e9a5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18010e9aa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010e9b1  lea     rax, [rbp+nSize]
0x18010e9b5  mov     [rbp+FilePart], rax
0x18010e9b9  lea     r9, asc_1802EE7AC; ": {}"
0x18010e9c0  lea     rax, [rbp+FilePart]
0x18010e9c4  mov     r8d, ebx
0x18010e9c7  mov     dl, 1
0x18010e9c9  mov     qword ptr [rsp+70h+var_50], rax
0x18010e9ce  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010e9d3  mov     edx, 27h ; '''
0x18010e9d8  jmp     short loc_18010EA33
0x18010e9da  test    rdx, rdx
0x18010e9dd  jnz     short loc_18010EA4B
0x18010e9df  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010e9e6  mov     edi, 80070057h
0x18010e9eb  mov     [rbp+nSize], edi
0x18010e9ee  test    rcx, rcx
0x18010e9f1  jz      short loc_18010EA2E
0x18010e9f3  lea     ebx, [rdx+3]
0x18010e9f6  mov     r8d, ebx
0x18010e9f9  lea     r9, aNoRelativePath; "No relative path specified"
0x18010ea00  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18010ea05  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ea0c  lea     rax, [rbp+nSize]
0x18010ea10  mov     [rbp+FilePart], rax
0x18010ea14  lea     r9, asc_1802EE7AC; ": {}"
0x18010ea1b  lea     rax, [rbp+FilePart]
0x18010ea1f  mov     r8d, ebx
0x18010ea22  mov     dl, 1
0x18010ea24  mov     qword ptr [rsp+70h+var_50], rax; int
0x18010ea29  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010ea2e  mov     edx, 28h ; '('; void *
0x18010ea33  mov     r9d, edi; char *
0x18010ea36  mov     rcx, [rbp+38h]; this
0x18010ea3a  lea     r8, aOnecoreBaseCbs_120; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x18010ea41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ea46  jmp     loc_18010EFFB
0x18010ea4b  cmp     [rdx], r13w
0x18010ea4f  jnz     short loc_18010EAAB
0x18010ea51  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ea58  mov     edi, 80070057h
0x18010ea5d  mov     [rbp+nSize], edi
0x18010ea60  test    rcx, rcx
0x18010ea63  jz      short loc_18010EAA4
0x18010ea65  mov     ebx, 3
0x18010ea6a  lea     r9, aInvalidRelativ; "Invalid relative path specified"
0x18010ea71  mov     r8d, ebx
0x18010ea74  xor     edx, edx
0x18010ea76  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18010ea7b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ea82  lea     rax, [rbp+nSize]
0x18010ea86  mov     [rbp+FilePart], rax
0x18010ea8a  lea     r9, asc_1802EE7AC; ": {}"
0x18010ea91  lea     rax, [rbp+FilePart]
0x18010ea95  mov     r8d, ebx
0x18010ea98  mov     dl, 1
0x18010ea9a  mov     qword ptr [rsp+70h+var_50], rax
0x18010ea9f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010eaa4  mov     edx, 29h ; ')'
0x18010eaa9  jmp     short loc_18010EA33
0x18010eaab  mov     r14d, 40h ; '@'
0x18010eab1  lea     rcx, [rbp+lpDst]
0x18010eab5  mov     edx, r14d
0x18010eab8  mov     [rbp+lpFileName], r14
0x18010eabc  mov     esi, r14d
0x18010eabf  call    SczAlloc
0x18010eac4  mov     edi, eax
0x18010eac6  test    eax, eax
0x18010eac8  jns     short loc_18010EAD6
0x18010eaca  mov     r9d, eax
0x18010eacd  lea     edx, [r14-0Eh]
0x18010ead1  jmp     loc_18010EA36
0x18010ead6  lea     rdx, [rbp+nSize]; unsigned int *
0x18010eada  mov     rcx, r14; unsigned __int64
0x18010eadd  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18010eae2  mov     edi, eax
0x18010eae4  test    eax, eax
0x18010eae6  jns     short loc_18010EAF5
0x18010eae8  mov     r9d, eax
0x18010eaeb  mov     edx, 33h ; '3'
0x18010eaf0  jmp     loc_18010EA36
0x18010eaf5  mov     rbx, [rbp+lpDst]
0x18010eaf9  mov     r8d, [rbp+nSize]; nSize
0x18010eafd  mov     rdx, rbx; lpDst
0x18010eb00  mov     rcx, [rbp+lpSrc]; lpSrc
0x18010eb04  call    cs:__imp_ExpandEnvironmentStringsW
0x18010eb0b  nop     dword ptr [rax+rax+00h]
0x18010eb10  mov     ecx, eax
0x18010eb12  test    eax, eax
0x18010eb14  jnz     loc_18010EBB6
0x18010eb1a  call    cs:__imp_GetLastError
0x18010eb21  nop     dword ptr [rax+rax+00h]
0x18010eb26  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010eb2d  mov     edi, eax
0x18010eb2f  test    rcx, rcx
0x18010eb32  jz      short loc_18010EB8F
0x18010eb34  lea     rax, [rbp+lpSrc]
0x18010eb38  mov     ebx, 3
0x18010eb3d  mov     r8d, ebx
0x18010eb40  mov     qword ptr [rsp+70h+var_50], rax
0x18010eb45  lea     r9, aFailedToExpand_0; "Failed to expand environment variables "...
0x18010eb4c  xor     edx, edx
0x18010eb4e  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18010eb53  test    edi, edi
0x18010eb55  jg      short loc_18010EB5B
0x18010eb57  mov     eax, edi
0x18010eb59  jmp     short loc_18010EB63
0x18010eb5b  movzx   eax, di
0x18010eb5e  or      eax, 80070000h
0x18010eb63  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010eb6a  lea     r9, a0; ": {0}"
0x18010eb71  mov     [rbp+nSize], eax
0x18010eb74  mov     r8d, ebx
0x18010eb77  lea     rax, [rbp+nSize]
0x18010eb7b  mov     dl, 1
0x18010eb7d  mov     [rbp+FilePart], rax
0x18010eb81  lea     rax, [rbp+FilePart]
0x18010eb85  mov     qword ptr [rsp+70h+var_50], rax; unsigned int
0x18010eb8a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010eb8f  test    edi, edi
0x18010eb91  jz      loc_18010EFF8
0x18010eb97  mov     edx, 36h ; '6'; void *
0x18010eb9c  mov     rcx, [rbp+38h]; this
0x18010eba0  lea     r8, aOnecoreBaseCbs_120; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x18010eba7  mov     r9d, edi; char *
0x18010ebaa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010ebaf  mov     edi, eax
0x18010ebb1  jmp     loc_18010EFFB
0x18010ebb6  mov     r15, rcx
0x18010ebb9  cmp     rcx, r14
0x18010ebbc  jbe     loc_18010ED15
0x18010ebc2  mov     rsi, rcx
0x18010ebc5  mov     [rbp+lpFileName], rcx
0x18010ebc9  mov     rdx, rcx
0x18010ebcc  lea     rcx, [rbp+lpDst]
0x18010ebd0  call    SczAlloc
0x18010ebd5  mov     edi, eax
0x18010ebd7  test    eax, eax
0x18010ebd9  jns     short loc_18010EBE8
0x18010ebdb  mov     r9d, eax
0x18010ebde  mov     edx, 3Bh ; ';'
0x18010ebe3  jmp     loc_18010EA36
0x18010ebe8  lea     rdx, [rbp+nSize]; unsigned int *
0x18010ebec  mov     rcx, r15; unsigned __int64
0x18010ebef  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18010ebf4  mov     edi, eax
0x18010ebf6  test    eax, eax
0x18010ebf8  jns     short loc_18010EC07
0x18010ebfa  mov     r9d, eax
0x18010ebfd  mov     edx, 3Ch ; '<'
0x18010ec02  jmp     loc_18010EA36
0x18010ec07  mov     rbx, [rbp+lpDst]
0x18010ec0b  mov     r8d, [rbp+nSize]; nSize
0x18010ec0f  mov     rdx, rbx; lpDst
0x18010ec12  mov     rcx, [rbp+lpSrc]; lpSrc
0x18010ec16  call    cs:__imp_ExpandEnvironmentStringsW
0x18010ec1d  nop     dword ptr [rax+rax+00h]
0x18010ec22  mov     ecx, eax
0x18010ec24  test    eax, eax
0x18010ec26  jnz     loc_18010ECB3
0x18010ec2c  call    cs:__imp_GetLastError
0x18010ec33  nop     dword ptr [rax+rax+00h]
0x18010ec38  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ec3f  mov     edi, eax
0x18010ec41  test    rcx, rcx
0x18010ec44  jz      short loc_18010ECA1
0x18010ec46  lea     rax, [rbp+lpSrc]
0x18010ec4a  mov     ebx, 3
0x18010ec4f  mov     r8d, ebx
0x18010ec52  mov     qword ptr [rsp+70h+var_50], rax
0x18010ec57  lea     r9, aFailedToExpand_0; "Failed to expand environment variables "...
0x18010ec5e  xor     edx, edx
0x18010ec60  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18010ec65  test    edi, edi
0x18010ec67  jg      short loc_18010EC6D
0x18010ec69  mov     eax, edi
0x18010ec6b  jmp     short loc_18010EC75
0x18010ec6d  movzx   eax, di
0x18010ec70  or      eax, 80070000h
0x18010ec75  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ec7c  lea     r9, a0; ": {0}"
0x18010ec83  mov     [rbp+nSize], eax
0x18010ec86  mov     r8d, ebx
0x18010ec89  lea     rax, [rbp+nSize]
0x18010ec8d  mov     dl, 1
0x18010ec8f  mov     [rbp+FilePart], rax
0x18010ec93  lea     rax, [rbp+FilePart]
0x18010ec97  mov     qword ptr [rsp+70h+var_50], rax
0x18010ec9c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010eca1  test    edi, edi
0x18010eca3  jz      loc_18010EFF8
0x18010eca9  mov     edx, 3Fh ; '?'
0x18010ecae  jmp     loc_18010EB9C
0x18010ecb3  cmp     r15, rcx
0x18010ecb6  jnb     short loc_18010ED15
0x18010ecb8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ecbf  mov     edi, 8007007Ah
0x18010ecc4  mov     [rbp+nSize], edi
0x18010ecc7  test    rcx, rcx
0x18010ecca  jz      short loc_18010ED0B
0x18010eccc  mov     ebx, 3
0x18010ecd1  lea     r9, aFailedToAlloca_50; "Failed to allocate buffer for expanded "...
0x18010ecd8  mov     r8d, ebx
0x18010ecdb  xor     edx, edx
0x18010ecdd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18010ece2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ece9  lea     rax, [rbp+nSize]
0x18010eced  mov     [rbp+FilePart], rax
0x18010ecf1  lea     r9, asc_1802EE7AC; ": {}"
0x18010ecf8  lea     rax, [rbp+FilePart]
0x18010ecfc  mov     r8d, ebx
0x18010ecff  mov     dl, 1
0x18010ed01  mov     qword ptr [rsp+70h+var_50], rax
0x18010ed06  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010ed0b  mov     edx, 43h ; 'C'
0x18010ed10  jmp     loc_18010EA33
0x18010ed15  mov     r15d, 104h
0x18010ed1b  cmp     ecx, r15d
0x18010ed1e  jbe     short loc_18010ED6D
0x18010ed20  lea     rcx, [rbp+lpDst]
0x18010ed24  call    PathPrefix
0x18010ed29  mov     edi, 80070057h
0x18010ed2e  mov     ecx, r13d
0x18010ed31  cmp     eax, edi
0x18010ed33  cmovnz  ecx, eax
0x18010ed36  mov     edi, ecx
0x18010ed38  test    ecx, ecx
0x18010ed3a  jns     short loc_18010ED46
0x18010ed3c  mov     edx, 4Fh ; 'O'
0x18010ed41  jmp     loc_18010EA33
0x18010ed46  mov     rbx, [rbp+lpDst]
0x18010ed4a  lea     rdx, [rbp+lpFileName]
0x18010ed4e  mov     rcx, rbx
0x18010ed51  call    SczSize
0x18010ed56  mov     edi, eax
0x18010ed58  test    eax, eax
0x18010ed5a  jns     short loc_18010ED69
0x18010ed5c  mov     r9d, eax
0x18010ed5f  mov     edx, 51h ; 'Q'
0x18010ed64  jmp     loc_18010EA36
0x18010ed69  mov     rsi, [rbp+lpFileName]
0x18010ed6d  mov     rax, [rbp+lpSrc]
0x18010ed71  lea     rdx, [rbp+nSize]; unsigned int *
0x18010ed75  test    rbx, rbx
0x18010ed78  mov     [rbp+FilePart], r13
0x18010ed7c  mov     [rbp+nSize], r13d
0x18010ed80  cmovnz  rax, rbx
0x18010ed84  cmp     rsi, r14
0x18010ed87  mov     [rbp+lpFileName], rax
0x18010ed8b  cmova   r14, rsi
0x18010ed8f  mov     rcx, r14; unsigned __int64
0x18010ed92  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18010ed97  mov     edi, eax
0x18010ed99  test    eax, eax
0x18010ed9b  jns     short loc_18010EDAA
0x18010ed9d  mov     r9d, eax
0x18010eda0  mov     edx, 5Fh ; '_'
0x18010eda5  jmp     loc_18010EA36
0x18010edaa  mov     esi, [rbp+nSize]
0x18010edad  lea     rcx, [rbp+lpBuffer]
0x18010edb1  mov     edx, esi
0x18010edb3  call    SczAlloc
0x18010edb8  mov     edi, eax
0x18010edba  test    eax, eax
0x18010edbc  jns     short loc_18010EDCB
0x18010edbe  mov     r9d, eax
0x18010edc1  mov     edx, 60h ; '`'
0x18010edc6  jmp     loc_18010EA36
0x18010edcb  mov     rbx, [rbp+lpBuffer]
  ... truncated ...
```
