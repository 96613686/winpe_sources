# PathExpand

- ea: `0x140015a08`
- end: `0x14001631f`
- name: `PathExpand`
- size: `2327`
- prototype: `__int64 __fastcall(LPWSTR *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, installer_update`

## callers

- `0x14000d9d0`

## callees

- `0x140001fcc`
- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006984`
- `0x140006c50`
- `0x14000726c`
- `0x14000952c`
- `0x14000955c`
- `0x140010b3c`
- `0x140011884`
- `0x140011e8c`
- `0x140015a08`
- `0x1400165f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015b93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015fc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400160f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015b93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015fc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400160f6`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140015fb7`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1400160e8`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140015fb7`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1400160e8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140015b83`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140015cfa`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140015b83`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140015cfa`

## string_xrefs

- `0x140015a36`: `%windir%\servicing\trustedinstaller.exe`
- `0x140015a75`: `No full path result specified`
- `0x140015ab8`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140015b08`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140015b4c`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140015c0b`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140015c7c`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140015cc0`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140015d82`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140015e28`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140015e80`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140015ec8`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140015f35`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140015f7b`: `onecore\base\cbs\util\cbspath.cpp`
- `0x14001603d`: `onecore\base\cbs\util\cbspath.cpp`
- `0x1400160ac`: `onecore\base\cbs\util\cbspath.cpp`
- `0x14001616e`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140016213`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140016259`: `onecore\base\cbs\util\cbspath.cpp`
- `0x1400162f4`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140015de4`: `Failed to allocate buffer for expanded path.`
- `0x140015fe2`: `Failed to get full path for string: {}`
- `0x140016113`: `Failed to get full path for string: {}`
- `0x1400161cf`: `Failed to allocate buffer for full path.`

## pseudocode

```c
__int64 __fastcall PathExpand(LPWSTR *a1)
{
  unsigned int v2; // edi
  __int64 v3; // rdx
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // rdi
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  LPWSTR v10; // rbx
  DWORD v11; // eax
  unsigned int v12; // ecx
  signed int v13; // edi
  __int64 v14; // rdx
  DWORD v15; // eax
  unsigned __int64 v16; // r14
  int v17; // eax
  int v18; // eax
  DWORD v19; // eax
  signed int LastError; // edi
  __int64 v21; // rdx
  DWORD v22; // eax
  __int64 v23; // rdx
  unsigned int v24; // eax
  int v25; // eax
  const WCHAR *v26; // rax
  int v27; // eax
  DWORD v28; // edi
  int v29; // eax
  LPWSTR v30; // rbx
  DWORD FullPathNameW; // eax
  signed int v32; // edi
  __int64 v33; // rdx
  DWORD v34; // eax
  DWORD v35; // edi
  int v36; // eax
  signed int v37; // edi
  __int64 v38; // rdx
  DWORD v39; // eax
  __int64 v40; // rdx
  int v41; // eax
  int v42; // eax
  LPWSTR lpBuffer; // [rsp+30h] [rbp-29h] BYREF
  LPWSTR lpDst; // [rsp+38h] [rbp-21h] BYREF
  unsigned int v45[2]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v46; // [rsp+48h] [rbp-11h]
  LPWSTR FilePart; // [rsp+50h] [rbp-9h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-1h] BYREF
  LPCWSTR lpSrc[2]; // [rsp+60h] [rbp+7h] BYREF
  DWORD nSize; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v46 = -2;
  lpSrc[0] = L"%windir%\\servicing\\trustedinstaller.exe";
  lpDst = 0;
  nSize = 0;
  lpBuffer = 0;
  if ( !a1 )
  {
    v2 = -2147467261;
    nSize = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No full path result specified");
      FilePart = (LPWSTR)&nSize;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v3,
        3,
        (__int64)": {}",
        (__int64)&FilePart);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
      (const char *)0x80004003LL);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
    return v2;
  }
  v5 = 64;
  v6 = 64;
  lpFileName = (LPCWSTR)64;
  v7 = SczAlloc(&lpDst, 64);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
      (const char *)(unsigned int)v7);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
    return v8;
  }
  v9 = ULongLongToULong(0x40u, &nSize);
  v8 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33,
      (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
      (const char *)(unsigned int)v9);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
    return v8;
  }
  v10 = lpDst;
  v11 = ExpandEnvironmentStringsW(lpSrc[0], lpDst, nSize);
  v12 = v11;
  if ( v11 )
  {
    v16 = v11;
    if ( v11 > 0x40uLL )
    {
      v6 = v11;
      lpFileName = (LPCWSTR)v11;
      v17 = SczAlloc(&lpDst, v11);
      v8 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B,
          (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
          (const char *)(unsigned int)v17);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
        return v8;
      }
      v18 = ULongLongToULong(v16, &nSize);
      v8 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3C,
          (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
          (const char *)(unsigned int)v18);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
        return v8;
      }
      v10 = lpDst;
      v19 = ExpandEnvironmentStringsW(lpSrc[0], lpDst, nSize);
      v12 = v19;
      if ( !v19 )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to expand environment variables in string: {}",
            (__int64)lpSrc);
          if ( LastError > 0 )
            v22 = (unsigned __int16)LastError | 0x80070000;
          else
            v22 = LastError;
          nSize = v22;
          FilePart = (LPWSTR)&nSize;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v21,
            3,
            (__int64)": {0}",
            (__int64)&FilePart);
        }
        if ( LastError )
        {
          v8 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x3F,
                 (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
                 (const char *)(unsigned int)LastError);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
          return v8;
        }
        goto LABEL_89;
      }
      if ( v16 < v19 )
      {
        v2 = -2147024774;
        nSize = -2147024774;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate buffer for expanded path.");
          FilePart = (LPWSTR)&nSize;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v23,
            3,
            (__int64)": {}",
            (__int64)&FilePart);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x43,
          (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
          (const char *)0x8007007ALL);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
        return v2;
      }
    }
    if ( v12 > 0x104 )
    {
      v24 = PathPrefix(&lpDst);
      v8 = 0;
      if ( v24 != -2147024809 )
        v8 = v24;
      if ( (v8 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4F,
          (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
          (const char *)v8);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
        return v8;
      }
      v10 = lpDst;
      v25 = SczSize(lpDst, &lpFileName);
      v2 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x51,
          (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
          (const char *)(unsigned int)v25);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
        return v2;
      }
      v6 = (unsigned __int64)lpFileName;
    }
    FilePart = 0;
    v26 = lpSrc[0];
    if ( v10 )
      v26 = v10;
    lpFileName = v26;
    if ( v6 > 0x40 )
      v5 = v6;
    nSize = 0;
    v27 = ULongLongToULong(v5, &nSize);
    v8 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F,
        (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
        (const char *)(unsigned int)v27);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
      return v8;
    }
    v28 = nSize;
    v29 = SczAlloc(&lpBuffer, nSize);
    v8 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x60,
        (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
        (const char *)(unsigned int)v29);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
      return v8;
    }
    v30 = lpBuffer;
    FullPathNameW = GetFullPathNameW(lpFileName, v28, lpBuffer, &FilePart);
    if ( FullPathNameW )
    {
      if ( v28 < FullPathNameW )
      {
        v35 = FullPathNameW;
        if ( FullPathNameW >= 0x104 )
          v35 = FullPathNameW + 7;
        v36 = SczAlloc(&lpBuffer, v35);
        v8 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x68,
            (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
            (const char *)(unsigned int)v36);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
          return v8;
        }
        v30 = lpBuffer;
        FullPathNameW = GetFullPathNameW(lpFileName, v35, lpBuffer, &FilePart);
        if ( !FullPathNameW )
        {
          v37 = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to get full path for string: {}",
              (__int64)&lpFileName);
            if ( v37 > 0 )
              v39 = (unsigned __int16)v37 | 0x80070000;
            else
              v39 = v37;
            nSize = v39;
            *(_QWORD *)v45 = &nSize;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              v38,
              3,
              (__int64)": {0}",
              (__int64)v45);
          }
          if ( v37 )
          {
            v8 = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0x6B,
                   (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
                   (const char *)(unsigned int)v37);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
            return v8;
          }
          goto LABEL_89;
        }
        if ( v35 < FullPathNameW )
        {
          v2 = -2147024774;
          nSize = -2147024774;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate buffer for full path.");
            *(_QWORD *)v45 = &nSize;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              v40,
              3,
              (__int64)": {}",
              (__int64)v45);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6F,
            (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
            (const char *)0x8007007ALL);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
          return v2;
        }
      }
      if ( FullPathNameW > 0x104 )
      {
        v41 = PathPrefix(&lpBuffer);
        v8 = v41;
        if ( v41 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x75,
            (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
            (const char *)(unsigned int)v41);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
          return v8;
        }
        v30 = lpBuffer;
      }
      if ( v30 )
      {
        if ( *a1 )
          operator delete(*a1 - 4);
        lpBuffer = 0;
        *a1 = v30;
      }
      else
      {
        v42 = SczAllocFromSz(a1, lpSrc[0]);
        v8 = v42;
        if ( v42 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x84,
            (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
            (const char *)(unsigned int)v42);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
          return v8;
        }
      }
      goto LABEL_89;
    }
    v32 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to get full path for string: {}",
        (__int64)&lpFileName);
      if ( v32 > 0 )
        v34 = (unsigned __int16)v32 | 0x80070000;
      else
        v34 = v32;
      nSize = v34;
      *(_QWORD *)v45 = &nSize;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v33,
        3,
        (__int64)": {0}",
        (__int64)v45);
    }
    if ( v32 )
    {
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x63,
             (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
             (const char *)(unsigned int)v32);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
      return v8;
    }
  }
  else
  {
    v13 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to expand environment variables in string: {}",
        (__int64)lpSrc);
      if ( v13 > 0 )
        v15 = (unsigned __int16)v13 | 0x80070000;
      else
        v15 = v13;
      nSize = v15;
      FilePart = (LPWSTR)&nSize;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v14,
        3,
        (__int64)": {0}",
        (__int64)&FilePart);
    }
    if ( v13 )
    {
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x36,
             (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
             (const char *)(unsigned int)v13);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
      return v8;
    }
  }
LABEL_89:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
  return 0;
}

```

## disassembly

```asm
0x140015a08  push    rbp
0x140015a0a  push    rbx
0x140015a0b  push    rsi
0x140015a0c  push    rdi
0x140015a0d  push    r14
0x140015a0f  push    r15
0x140015a11  lea     rbp, [rsp-2Fh]
0x140015a16  sub     rsp, 88h
0x140015a1d  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x140015a25  mov     rax, cs:__security_cookie
0x140015a2c  xor     rax, rsp
0x140015a2f  mov     [rbp+57h+var_38], rax
0x140015a33  mov     r15, rcx
0x140015a36  lea     rax, aWindirServicin; "%windir%\\servicing\\trustedinstaller.e"...
0x140015a3d  mov     [rbp+57h+lpSrc], rax
0x140015a41  mov     [rbp+57h+lpDst], 0
0x140015a49  mov     [rbp+57h+nSize], 0
0x140015a50  mov     [rbp+57h+lpBuffer], 0
0x140015a58  test    rcx, rcx
0x140015a5b  jnz     loc_140015AE5
0x140015a61  mov     edi, 80004003h
0x140015a66  mov     [rbp+57h+nSize], edi
0x140015a69  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140015a70  test    rcx, rcx
0x140015a73  jz      short loc_140015AB1
0x140015a75  lea     r9, aNoFullPathResu; "No full path result specified"
0x140015a7c  lea     ebx, [r15+3]
0x140015a80  mov     r8d, ebx
0x140015a83  xor     edx, edx
0x140015a85  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140015a8a  lea     rax, [rbp+57h+nSize]
0x140015a8e  mov     [rbp+57h+FilePart], rax
0x140015a92  lea     rax, [rbp+57h+FilePart]
0x140015a96  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x140015a9b  lea     r9, asc_14002D4FC; ": {}"
0x140015aa2  mov     r8d, ebx
0x140015aa5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140015aac  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140015ab1  mov     rcx, [rbp+5Fh]; this
0x140015ab5  mov     r9d, edi; char *
0x140015ab8  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140015abf  mov     edx, 27h ; '''; void *
0x140015ac4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015ac9  nop
0x140015aca  lea     rcx, [rbp+57h+lpBuffer]
0x140015ace  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015ad3  nop
0x140015ad4  lea     rcx, [rbp+57h+lpDst]
0x140015ad8  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015add  nop
0x140015ade  mov     eax, edi
0x140015ae0  jmp     loc_1400162BF
0x140015ae5  mov     esi, 40h ; '@'
0x140015aea  mov     edi, esi
0x140015aec  mov     [rbp+57h+lpFileName], rsi
0x140015af0  mov     edx, esi
0x140015af2  lea     rcx, [rbp+57h+lpDst]
0x140015af6  call    SczAlloc
0x140015afb  mov     ebx, eax
0x140015afd  test    eax, eax
0x140015aff  jns     short loc_140015B33
0x140015b01  mov     rcx, [rbp+5Fh]; this
0x140015b05  mov     r9d, eax; char *
0x140015b08  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140015b0f  lea     edx, [rsi-0Eh]; void *
0x140015b12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015b17  nop
0x140015b18  lea     rcx, [rbp+57h+lpBuffer]
0x140015b1c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015b21  nop
0x140015b22  lea     rcx, [rbp+57h+lpDst]
0x140015b26  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015b2b  nop
0x140015b2c  mov     eax, ebx
0x140015b2e  jmp     loc_1400162BF
0x140015b33  lea     rdx, [rbp+57h+nSize]; unsigned int *
0x140015b37  mov     rcx, rsi; unsigned __int64
0x140015b3a  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140015b3f  mov     ebx, eax
0x140015b41  test    eax, eax
0x140015b43  jns     short loc_140015B74
0x140015b45  mov     rcx, [rbp+5Fh]; this
0x140015b49  mov     r9d, eax; char *
0x140015b4c  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140015b53  mov     edx, 33h ; '3'; void *
0x140015b58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015b5d  nop
0x140015b5e  lea     rcx, [rbp+57h+lpBuffer]
0x140015b62  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015b67  nop
0x140015b68  lea     rcx, [rbp+57h+lpDst]
0x140015b6c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015b71  nop
0x140015b72  jmp     short loc_140015B2C
0x140015b74  mov     r8d, [rbp+57h+nSize]; nSize
0x140015b78  mov     rbx, [rbp+57h+lpDst]
0x140015b7c  mov     rdx, rbx; lpDst
0x140015b7f  mov     rcx, [rbp+57h+lpSrc]; lpSrc
0x140015b83  call    cs:__imp_ExpandEnvironmentStringsW
0x140015b89  mov     ecx, eax
0x140015b8b  test    eax, eax
0x140015b8d  jnz     loc_140015C50
0x140015b93  call    cs:__imp_GetLastError
0x140015b99  mov     edi, eax
0x140015b9b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140015ba2  test    rcx, rcx
0x140015ba5  jz      short loc_140015C00
0x140015ba7  lea     rax, [rbp+57h+lpSrc]
0x140015bab  mov     qword ptr [rsp+0B0h+var_90], rax
0x140015bb0  lea     r9, aFailedToExpand; "Failed to expand environment variables "...
0x140015bb7  mov     ebx, 3
0x140015bbc  mov     r8d, ebx
0x140015bbf  xor     edx, edx
0x140015bc1  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140015bc6  test    edi, edi
0x140015bc8  jg      short loc_140015BCE
0x140015bca  mov     eax, edi
0x140015bcc  jmp     short loc_140015BD6
0x140015bce  movzx   eax, di
0x140015bd1  or      eax, 80070000h
0x140015bd6  mov     [rbp+57h+nSize], eax
0x140015bd9  lea     rax, [rbp+57h+nSize]
0x140015bdd  mov     [rbp+57h+FilePart], rax
0x140015be1  lea     rax, [rbp+57h+FilePart]
0x140015be5  mov     qword ptr [rsp+0B0h+var_90], rax; unsigned int
0x140015bea  lea     r9, a0; ": {0}"
0x140015bf1  mov     r8d, ebx
0x140015bf4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140015bfb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140015c00  test    edi, edi
0x140015c02  jz      short loc_140015C37
0x140015c04  mov     rcx, [rbp+5Fh]; this
0x140015c08  mov     r9d, edi; char *
0x140015c0b  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140015c12  mov     edx, 36h ; '6'; void *
0x140015c17  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140015c1c  mov     ebx, eax
0x140015c1e  lea     rcx, [rbp+57h+lpBuffer]
0x140015c22  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015c27  nop
0x140015c28  lea     rcx, [rbp+57h+lpDst]
0x140015c2c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015c31  nop
0x140015c32  jmp     loc_140015B2C
0x140015c37  lea     rcx, [rbp+57h+lpBuffer]
0x140015c3b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015c40  nop
0x140015c41  lea     rcx, [rbp+57h+lpDst]
0x140015c45  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015c4a  nop
0x140015c4b  jmp     loc_1400162BD
0x140015c50  mov     r14, rcx
0x140015c53  cmp     rcx, rsi
0x140015c56  jbe     loc_140015E53
0x140015c5c  mov     rdi, rcx
0x140015c5f  mov     [rbp+57h+lpFileName], rcx
0x140015c63  mov     rdx, rcx
0x140015c66  lea     rcx, [rbp+57h+lpDst]
0x140015c6a  call    SczAlloc
0x140015c6f  mov     ebx, eax
0x140015c71  test    eax, eax
0x140015c73  jns     short loc_140015CA7
0x140015c75  mov     rcx, [rbp+5Fh]; this
0x140015c79  mov     r9d, eax; char *
0x140015c7c  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140015c83  mov     edx, 3Bh ; ';'; void *
0x140015c88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015c8d  nop
0x140015c8e  lea     rcx, [rbp+57h+lpBuffer]
0x140015c92  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015c97  nop
0x140015c98  lea     rcx, [rbp+57h+lpDst]
0x140015c9c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015ca1  nop
0x140015ca2  jmp     loc_140015B2C
0x140015ca7  lea     rdx, [rbp+57h+nSize]; unsigned int *
0x140015cab  mov     rcx, r14; unsigned __int64
0x140015cae  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140015cb3  mov     ebx, eax
0x140015cb5  test    eax, eax
0x140015cb7  jns     short loc_140015CEB
0x140015cb9  mov     rcx, [rbp+5Fh]; this
0x140015cbd  mov     r9d, eax; char *
0x140015cc0  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140015cc7  mov     edx, 3Ch ; '<'; void *
0x140015ccc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015cd1  nop
0x140015cd2  lea     rcx, [rbp+57h+lpBuffer]
0x140015cd6  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015cdb  nop
0x140015cdc  lea     rcx, [rbp+57h+lpDst]
0x140015ce0  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015ce5  nop
0x140015ce6  jmp     loc_140015B2C
0x140015ceb  mov     r8d, [rbp+57h+nSize]; nSize
0x140015cef  mov     rbx, [rbp+57h+lpDst]
0x140015cf3  mov     rdx, rbx; lpDst
0x140015cf6  mov     rcx, [rbp+57h+lpSrc]; lpSrc
0x140015cfa  call    cs:__imp_ExpandEnvironmentStringsW
0x140015d00  mov     ecx, eax
0x140015d02  test    eax, eax
0x140015d04  jnz     loc_140015DC7
0x140015d0a  call    cs:__imp_GetLastError
0x140015d10  mov     edi, eax
0x140015d12  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140015d19  test    rcx, rcx
0x140015d1c  jz      short loc_140015D77
0x140015d1e  lea     rax, [rbp+57h+lpSrc]
0x140015d22  mov     qword ptr [rsp+0B0h+var_90], rax
0x140015d27  lea     r9, aFailedToExpand; "Failed to expand environment variables "...
0x140015d2e  mov     ebx, 3
0x140015d33  mov     r8d, ebx
0x140015d36  xor     edx, edx
0x140015d38  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140015d3d  test    edi, edi
0x140015d3f  jg      short loc_140015D45
0x140015d41  mov     eax, edi
0x140015d43  jmp     short loc_140015D4D
0x140015d45  movzx   eax, di
0x140015d48  or      eax, 80070000h
0x140015d4d  mov     [rbp+57h+nSize], eax
0x140015d50  lea     rax, [rbp+57h+nSize]
0x140015d54  mov     [rbp+57h+FilePart], rax
0x140015d58  lea     rax, [rbp+57h+FilePart]
0x140015d5c  mov     qword ptr [rsp+0B0h+var_90], rax; unsigned int
0x140015d61  lea     r9, a0; ": {0}"
0x140015d68  mov     r8d, ebx
0x140015d6b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140015d72  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140015d77  test    edi, edi
0x140015d79  jz      short loc_140015DAE
0x140015d7b  mov     rcx, [rbp+5Fh]; this
0x140015d7f  mov     r9d, edi; char *
0x140015d82  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140015d89  mov     edx, 3Fh ; '?'; void *
0x140015d8e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140015d93  mov     ebx, eax
0x140015d95  lea     rcx, [rbp+57h+lpBuffer]
0x140015d99  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015d9e  nop
0x140015d9f  lea     rcx, [rbp+57h+lpDst]
0x140015da3  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015da8  nop
0x140015da9  jmp     loc_140015B2C
0x140015dae  lea     rcx, [rbp+57h+lpBuffer]
0x140015db2  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015db7  nop
0x140015db8  lea     rcx, [rbp+57h+lpDst]
0x140015dbc  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015dc1  nop
0x140015dc2  jmp     loc_1400162BD
0x140015dc7  cmp     r14, rcx
0x140015dca  jnb     loc_140015E53
0x140015dd0  mov     edi, 8007007Ah
0x140015dd5  mov     [rbp+57h+nSize], edi
0x140015dd8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140015ddf  test    rcx, rcx
0x140015de2  jz      short loc_140015E21
0x140015de4  lea     r9, aFailedToAlloca_1; "Failed to allocate buffer for expanded "...
0x140015deb  mov     ebx, 3
0x140015df0  mov     r8d, ebx
0x140015df3  xor     edx, edx
0x140015df5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140015dfa  lea     rax, [rbp+57h+nSize]
0x140015dfe  mov     [rbp+57h+FilePart], rax
0x140015e02  lea     rax, [rbp+57h+FilePart]
0x140015e06  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x140015e0b  lea     r9, asc_14002D4FC; ": {}"
0x140015e12  mov     r8d, ebx
0x140015e15  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140015e1c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140015e21  mov     rcx, [rbp+5Fh]; this
0x140015e25  mov     r9d, edi; char *
0x140015e28  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140015e2f  mov     edx, 43h ; 'C'; void *
0x140015e34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015e39  nop
0x140015e3a  lea     rcx, [rbp+57h+lpBuffer]
0x140015e3e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015e43  nop
0x140015e44  lea     rcx, [rbp+57h+lpDst]
0x140015e48  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140015e4d  nop
0x140015e4e  jmp     loc_140015ADE
0x140015e53  mov     r14d, 104h
0x140015e59  cmp     ecx, r14d
0x140015e5c  jbe     loc_140015EF7
0x140015e62  lea     rcx, [rbp+57h+lpDst]
0x140015e66  call    PathPrefix
0x140015e6b  xor     ebx, ebx
0x140015e6d  cmp     eax, 80070057h
0x140015e72  cmovnz  ebx, eax
0x140015e75  test    ebx, ebx
0x140015e77  jns     short loc_140015EAB
0x140015e79  mov     rcx, [rbp+5Fh]; this
0x140015e7d  mov     r9d, ebx; char *
0x140015e80  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140015e87  mov     edx, 4Fh ; 'O'; void *
0x140015e8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015e91  nop
  ... truncated ...
```
