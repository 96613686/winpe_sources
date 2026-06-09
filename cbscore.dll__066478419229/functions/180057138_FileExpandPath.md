# FileExpandPath

- ea: `0x180057138`
- end: `0x1800576c4`
- name: `FileExpandPath`
- size: `1420`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1800f2908`

## callees

- `0x180013250`
- `0x180033d50`
- `0x180057138`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb500`
- `0x1800eb920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800572a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005738f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800574bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800572a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005738f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800574bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057594`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180057293`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005737b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180057293`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005737b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800574a7`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180057580`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800574a7`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180057580`

## string_xrefs

- `0x1800571f9`: `No full path result specified`
- `0x180057196`: `No relative path specified`
- `0x180057630`: `Failed to allocate buffer for full path.`
- `0x180057433`: `Failed to allocate buffer for expanded path.`
- `0x1800574ec`: `Failed to get full path for string: {}`
- `0x1800575c3`: `Failed to get full path for string: {}`

## pseudocode

```c
__int64 __fastcall FileExpandPath(const WCHAR *a1, const struct std::nothrow_t *a2)
{
  unsigned int v3; // edi
  int v4; // edx
  __int64 v5; // rdx
  int v6; // edx
  unsigned __int64 v7; // r9
  int v8; // eax
  const WCHAR *v9; // rbx
  DWORD v10; // eax
  DWORD v11; // esi
  signed int LastError; // edi
  int v13; // edx
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r9
  int v17; // eax
  DWORD v18; // eax
  int v19; // edx
  unsigned int v20; // eax
  int v21; // edx
  int v22; // eax
  LPWSTR v23; // rdi
  DWORD FullPathNameW; // eax
  DWORD v25; // esi
  int v26; // edx
  unsigned int v27; // eax
  int v28; // eax
  DWORD v29; // eax
  int v30; // edx
  unsigned int v31; // eax
  int v32; // edx
  unsigned int v34; // [rsp+20h] [rbp-50h]
  unsigned int v35[2]; // [rsp+30h] [rbp-40h] BYREF
  LPWSTR lpBuffer; // [rsp+38h] [rbp-38h] BYREF
  LPWSTR lpDst; // [rsp+40h] [rbp-30h] BYREF
  int *v38; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR lpSrc; // [rsp+50h] [rbp-20h] BYREF
  LPWSTR FilePart; // [rsp+58h] [rbp-18h] BYREF
  int v41; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  lpSrc = a1;
  lpDst = 0;
  lpBuffer = 0;
  FilePart = 0;
  if ( a1 )
  {
    if ( !a2 )
    {
      v3 = -2147467261;
      v41 = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No full path result specified");
        *(_QWORD *)v35 = &v41;
        LOBYTE(v6) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v6,
          3,
          (unsigned int)": {}",
          (__int64)v35);
      }
      v5 = 252;
      goto LABEL_9;
    }
    if ( *(_QWORD *)a2 )
    {
      operator delete((void *)(*(_QWORD *)a2 - 8LL), a2);
      *(_QWORD *)a2 = 0;
    }
    v8 = SczAlloc(&lpDst, 260);
    v3 = v8;
    if ( v8 < 0 )
    {
      v7 = (unsigned int)v8;
      v5 = 259;
      goto LABEL_10;
    }
    v9 = lpDst;
    v10 = ExpandEnvironmentStringsW(lpSrc, lpDst, 0x104u);
    v11 = v10;
    if ( !v10 )
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
          v14 = (unsigned __int16)LastError | 0x80070000;
        else
          v14 = LastError;
        v41 = v14;
        LOBYTE(v13) = 1;
        *(_QWORD *)v35 = &v41;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v13,
          3,
          (unsigned int)": {0}",
          (__int64)v35);
      }
      if ( LastError )
      {
        v15 = 264;
LABEL_23:
        v16 = (unsigned int)LastError;
LABEL_24:
        v3 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v15,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
               (const char *)v16,
               v34);
        goto LABEL_67;
      }
      goto LABEL_66;
    }
    if ( v10 > 0x104 )
    {
      v17 = SczAlloc(&lpDst, v10);
      v3 = v17;
      if ( v17 < 0 )
      {
        v7 = (unsigned int)v17;
        v5 = 269;
        goto LABEL_10;
      }
      v9 = lpDst;
      v18 = ExpandEnvironmentStringsW(lpSrc, lpDst, v11);
      if ( !v18 )
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
            v20 = (unsigned __int16)LastError | 0x80070000;
          else
            v20 = LastError;
          v41 = v20;
          LOBYTE(v19) = 1;
          *(_QWORD *)v35 = &v41;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v19,
            3,
            (unsigned int)": {0}",
            (__int64)v35);
        }
        if ( LastError )
        {
          v15 = 274;
          goto LABEL_23;
        }
        goto LABEL_66;
      }
      if ( v11 < v18 )
      {
        v3 = -2147024774;
        v41 = -2147024774;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to allocate buffer for expanded path.");
          *(_QWORD *)v35 = &v41;
          LOBYTE(v21) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v21,
            3,
            (unsigned int)": {}",
            (__int64)v35);
        }
        v5 = 278;
        goto LABEL_9;
      }
    }
    v22 = SczAlloc(&lpBuffer, 260);
    v3 = v22;
    if ( v22 < 0 )
    {
      v7 = (unsigned int)v22;
      v5 = 286;
      goto LABEL_10;
    }
    v23 = lpBuffer;
    FullPathNameW = GetFullPathNameW(v9, 0x104u, lpBuffer, &FilePart);
    v25 = FullPathNameW;
    if ( FullPathNameW )
    {
      if ( FullPathNameW > 0x104 )
      {
        v28 = SczAlloc(&lpBuffer, FullPathNameW);
        v3 = v28;
        if ( v28 < 0 )
        {
          v7 = (unsigned int)v28;
          v5 = 296;
          goto LABEL_10;
        }
        v23 = lpBuffer;
        v29 = GetFullPathNameW(v9, v25, lpBuffer, &FilePart);
        if ( !v29 )
        {
          LastError = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            v38 = (int *)v9;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to get full path for string: {}",
              (__int64)&v38);
            if ( LastError > 0 )
              v31 = (unsigned __int16)LastError | 0x80070000;
            else
              v31 = LastError;
            v41 = v31;
            LOBYTE(v30) = 1;
            *(_QWORD *)v35 = &v41;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v30,
              3,
              (unsigned int)": {0}",
              (__int64)v35);
          }
          if ( LastError )
          {
            v15 = 301;
            goto LABEL_23;
          }
          goto LABEL_66;
        }
        if ( v25 < v29 )
        {
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate buffer for full path.");
            v38 = &v41;
            LOBYTE(v32) = 1;
            v41 = -2147024774;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v32,
              3,
              (unsigned int)": {0}",
              (__int64)&v38);
          }
          v16 = 122;
          v15 = 305;
          goto LABEL_24;
        }
      }
      lpBuffer = 0;
      *(_QWORD *)a2 = v23;
      goto LABEL_66;
    }
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      *(_QWORD *)v35 = v9;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to get full path for string: {}",
        (__int64)v35);
      if ( LastError > 0 )
        v27 = (unsigned __int16)LastError | 0x80070000;
      else
        v27 = LastError;
      v41 = v27;
      LOBYTE(v26) = 1;
      v38 = &v41;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v26,
        3,
        (unsigned int)": {0}",
        (__int64)&v38);
    }
    if ( LastError )
    {
      v15 = 291;
      goto LABEL_23;
    }
LABEL_66:
    v3 = 0;
    goto LABEL_67;
  }
  v3 = -2147024809;
  v41 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No relative path specified");
    *(_QWORD *)v35 = &v41;
    LOBYTE(v4) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v4,
      3,
      (unsigned int)": {}",
      (__int64)v35);
  }
  v5 = 251;
LABEL_9:
  v7 = v3;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
    (const char *)v7,
    v34);
LABEL_67:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
  return v3;
}

```

## disassembly

```asm
0x180057138  mov     [rsp-28h+arg_10], rbx
0x18005713d  push    rbp
0x18005713e  push    rsi
0x18005713f  push    rdi
0x180057140  push    r12
0x180057142  push    r14
0x180057144  mov     rbp, rsp
0x180057147  sub     rsp, 70h
0x18005714b  mov     rax, cs:__security_cookie
0x180057152  xor     rax, rsp
0x180057155  mov     [rbp+var_8], rax
0x180057159  mov     [rbp+lpSrc], rcx
0x18005715d  mov     r14, rdx
0x180057160  mov     [rbp+lpDst], 0
0x180057168  mov     [rbp+lpBuffer], 0
0x180057170  mov     [rbp+FilePart], 0
0x180057178  test    rcx, rcx
0x18005717b  jnz     short loc_1800571D7
0x18005717d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180057184  mov     edi, 80070057h
0x180057189  mov     [rbp+var_10], edi
0x18005718c  test    rcx, rcx
0x18005718f  jz      short loc_1800571D0
0x180057191  mov     ebx, 3
0x180057196  lea     r9, aNoRelativePath; "No relative path specified"
0x18005719d  mov     r8d, ebx
0x1800571a0  xor     edx, edx
0x1800571a2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800571a7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800571ae  lea     rax, [rbp+var_10]
0x1800571b2  mov     qword ptr [rbp+var_40], rax
0x1800571b6  lea     r9, asc_1802EE7AC; ": {}"
0x1800571bd  lea     rax, [rbp+var_40]
0x1800571c1  mov     r8d, ebx
0x1800571c4  mov     dl, 1
0x1800571c6  mov     qword ptr [rsp+70h+var_50], rax
0x1800571cb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800571d0  mov     edx, 0FBh
0x1800571d5  jmp     short loc_180057233
0x1800571d7  test    r14, r14
0x1800571da  jnz     short loc_18005724B
0x1800571dc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800571e3  mov     edi, 80004003h
0x1800571e8  mov     [rbp+var_10], edi
0x1800571eb  test    rcx, rcx
0x1800571ee  jz      short loc_18005722E
0x1800571f0  lea     ebx, [r14+3]
0x1800571f4  xor     edx, edx
0x1800571f6  mov     r8d, ebx
0x1800571f9  lea     r9, aNoFullPathResu; "No full path result specified"
0x180057200  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180057205  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005720c  lea     rax, [rbp+var_10]
0x180057210  mov     qword ptr [rbp+var_40], rax
0x180057214  lea     r9, asc_1802EE7AC; ": {}"
0x18005721b  lea     rax, [rbp+var_40]
0x18005721f  mov     r8d, ebx
0x180057222  mov     dl, 1
0x180057224  mov     qword ptr [rsp+70h+var_50], rax; int
0x180057229  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005722e  mov     edx, 0FCh; void *
0x180057233  mov     r9d, edi; char *
0x180057236  mov     rcx, [rbp+28h]; this
0x18005723a  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180057241  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057246  jmp     loc_18005768F
0x18005724b  mov     rcx, [rdx]
0x18005724e  test    rcx, rcx
0x180057251  jz      short loc_180057263
0x180057253  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x180057257  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005725c  mov     qword ptr [r14], 0
0x180057263  mov     r12d, 104h
0x180057269  lea     rcx, [rbp+lpDst]
0x18005726d  mov     edx, r12d
0x180057270  call    SczAlloc
0x180057275  mov     edi, eax
0x180057277  test    eax, eax
0x180057279  jns     short loc_180057285
0x18005727b  mov     r9d, eax
0x18005727e  lea     edx, [r12-1]
0x180057283  jmp     short loc_180057236
0x180057285  mov     rbx, [rbp+lpDst]
0x180057289  mov     r8d, r12d; nSize
0x18005728c  mov     rcx, [rbp+lpSrc]; lpSrc
0x180057290  mov     rdx, rbx; lpDst
0x180057293  call    cs:__imp_ExpandEnvironmentStringsW
0x18005729a  nop     dword ptr [rax+rax+00h]
0x18005729f  mov     esi, eax
0x1800572a1  test    eax, eax
0x1800572a3  jnz     loc_180057345
0x1800572a9  call    cs:__imp_GetLastError
0x1800572b0  nop     dword ptr [rax+rax+00h]
0x1800572b5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800572bc  mov     edi, eax
0x1800572be  test    rcx, rcx
0x1800572c1  jz      short loc_18005731E
0x1800572c3  lea     rax, [rbp+lpSrc]
0x1800572c7  mov     ebx, 3
0x1800572cc  mov     r8d, ebx
0x1800572cf  mov     qword ptr [rsp+70h+var_50], rax
0x1800572d4  lea     r9, aFailedToExpand_0; "Failed to expand environment variables "...
0x1800572db  xor     edx, edx
0x1800572dd  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800572e2  test    edi, edi
0x1800572e4  jg      short loc_1800572EA
0x1800572e6  mov     eax, edi
0x1800572e8  jmp     short loc_1800572F2
0x1800572ea  movzx   eax, di
0x1800572ed  or      eax, 80070000h
0x1800572f2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800572f9  lea     r9, a0; ": {0}"
0x180057300  mov     [rbp+var_10], eax
0x180057303  mov     r8d, ebx
0x180057306  lea     rax, [rbp+var_10]
0x18005730a  mov     dl, 1
0x18005730c  mov     qword ptr [rbp+var_40], rax
0x180057310  lea     rax, [rbp+var_40]
0x180057314  mov     qword ptr [rsp+70h+var_50], rax; unsigned int
0x180057319  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005731e  test    edi, edi
0x180057320  jz      loc_18005768D
0x180057326  mov     edx, 108h; void *
0x18005732b  mov     r9d, edi; char *
0x18005732e  mov     rcx, [rbp+28h]; this
0x180057332  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180057339  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005733e  mov     edi, eax
0x180057340  jmp     loc_18005768F
0x180057345  cmp     esi, r12d
0x180057348  jbe     loc_180057477
0x18005734e  mov     rdx, rsi
0x180057351  lea     rcx, [rbp+lpDst]
0x180057355  call    SczAlloc
0x18005735a  mov     edi, eax
0x18005735c  test    eax, eax
0x18005735e  jns     short loc_18005736D
0x180057360  mov     r9d, eax
0x180057363  mov     edx, 10Dh
0x180057368  jmp     loc_180057236
0x18005736d  mov     rbx, [rbp+lpDst]
0x180057371  mov     r8d, esi; nSize
0x180057374  mov     rcx, [rbp+lpSrc]; lpSrc
0x180057378  mov     rdx, rbx; lpDst
0x18005737b  call    cs:__imp_ExpandEnvironmentStringsW
0x180057382  nop     dword ptr [rax+rax+00h]
0x180057387  test    eax, eax
0x180057389  jnz     loc_180057416
0x18005738f  call    cs:__imp_GetLastError
0x180057396  nop     dword ptr [rax+rax+00h]
0x18005739b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800573a2  mov     edi, eax
0x1800573a4  test    rcx, rcx
0x1800573a7  jz      short loc_180057404
0x1800573a9  lea     rax, [rbp+lpSrc]
0x1800573ad  mov     ebx, 3
0x1800573b2  mov     r8d, ebx
0x1800573b5  mov     qword ptr [rsp+70h+var_50], rax
0x1800573ba  lea     r9, aFailedToExpand_0; "Failed to expand environment variables "...
0x1800573c1  xor     edx, edx
0x1800573c3  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800573c8  test    edi, edi
0x1800573ca  jg      short loc_1800573D0
0x1800573cc  mov     eax, edi
0x1800573ce  jmp     short loc_1800573D8
0x1800573d0  movzx   eax, di
0x1800573d3  or      eax, 80070000h
0x1800573d8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800573df  lea     r9, a0; ": {0}"
0x1800573e6  mov     [rbp+var_10], eax
0x1800573e9  mov     r8d, ebx
0x1800573ec  lea     rax, [rbp+var_10]
0x1800573f0  mov     dl, 1
0x1800573f2  mov     qword ptr [rbp+var_40], rax
0x1800573f6  lea     rax, [rbp+var_40]
0x1800573fa  mov     qword ptr [rsp+70h+var_50], rax
0x1800573ff  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180057404  test    edi, edi
0x180057406  jz      loc_18005768D
0x18005740c  mov     edx, 112h
0x180057411  jmp     loc_18005732B
0x180057416  cmp     esi, eax
0x180057418  jnb     short loc_180057477
0x18005741a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180057421  mov     edi, 8007007Ah
0x180057426  mov     [rbp+var_10], edi
0x180057429  test    rcx, rcx
0x18005742c  jz      short loc_18005746D
0x18005742e  mov     ebx, 3
0x180057433  lea     r9, aFailedToAlloca_50; "Failed to allocate buffer for expanded "...
0x18005743a  mov     r8d, ebx
0x18005743d  xor     edx, edx
0x18005743f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180057444  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005744b  lea     rax, [rbp+var_10]
0x18005744f  mov     qword ptr [rbp+var_40], rax
0x180057453  lea     r9, asc_1802EE7AC; ": {}"
0x18005745a  lea     rax, [rbp+var_40]
0x18005745e  mov     r8d, ebx
0x180057461  mov     dl, 1
0x180057463  mov     qword ptr [rsp+70h+var_50], rax
0x180057468  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005746d  mov     edx, 116h
0x180057472  jmp     loc_180057233
0x180057477  mov     rdx, r12
0x18005747a  lea     rcx, [rbp+lpBuffer]
0x18005747e  call    SczAlloc
0x180057483  mov     edi, eax
0x180057485  test    eax, eax
0x180057487  jns     short loc_180057496
0x180057489  mov     r9d, eax
0x18005748c  mov     edx, 11Eh
0x180057491  jmp     loc_180057236
0x180057496  mov     rdi, [rbp+lpBuffer]
0x18005749a  lea     r9, [rbp+FilePart]; lpFilePart
0x18005749e  mov     r8, rdi; lpBuffer
0x1800574a1  mov     edx, r12d; nBufferLength
0x1800574a4  mov     rcx, rbx; lpFileName
0x1800574a7  call    cs:__imp_GetFullPathNameW
0x1800574ae  nop     dword ptr [rax+rax+00h]
0x1800574b3  mov     esi, eax
0x1800574b5  test    eax, eax
0x1800574b7  jnz     loc_180057548
0x1800574bd  call    cs:__imp_GetLastError
0x1800574c4  nop     dword ptr [rax+rax+00h]
0x1800574c9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800574d0  mov     edi, eax
0x1800574d2  test    rcx, rcx
0x1800574d5  jz      short loc_180057536
0x1800574d7  mov     qword ptr [rbp+var_40], rbx
0x1800574db  lea     rax, [rbp+var_40]
0x1800574df  mov     ebx, 3
0x1800574e4  mov     qword ptr [rsp+70h+var_50], rax
0x1800574e9  mov     r8d, ebx
0x1800574ec  lea     r9, aFailedToGetFul; "Failed to get full path for string: {}"
0x1800574f3  xor     edx, edx
0x1800574f5  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800574fa  test    edi, edi
0x1800574fc  jg      short loc_180057502
0x1800574fe  mov     eax, edi
0x180057500  jmp     short loc_18005750A
0x180057502  movzx   eax, di
0x180057505  or      eax, 80070000h
0x18005750a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180057511  lea     r9, a0; ": {0}"
0x180057518  mov     [rbp+var_10], eax
0x18005751b  mov     r8d, ebx
0x18005751e  lea     rax, [rbp+var_10]
0x180057522  mov     dl, 1
0x180057524  mov     [rbp+var_28], rax
0x180057528  lea     rax, [rbp+var_28]
0x18005752c  mov     qword ptr [rsp+70h+var_50], rax
0x180057531  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180057536  test    edi, edi
0x180057538  jz      loc_18005768D
0x18005753e  mov     edx, 123h
0x180057543  jmp     loc_18005732B
0x180057548  cmp     esi, r12d
0x18005754b  jbe     loc_180057682
0x180057551  mov     rdx, rsi
0x180057554  lea     rcx, [rbp+lpBuffer]
0x180057558  call    SczAlloc
0x18005755d  mov     edi, eax
0x18005755f  test    eax, eax
0x180057561  jns     short loc_180057570
0x180057563  mov     r9d, eax
0x180057566  mov     edx, 128h
0x18005756b  jmp     loc_180057236
0x180057570  mov     rdi, [rbp+lpBuffer]
0x180057574  lea     r9, [rbp+FilePart]; lpFilePart
0x180057578  mov     r8, rdi; lpBuffer
0x18005757b  mov     edx, esi; nBufferLength
0x18005757d  mov     rcx, rbx; lpFileName
0x180057580  call    cs:__imp_GetFullPathNameW
0x180057587  nop     dword ptr [rax+rax+00h]
0x18005758c  test    eax, eax
0x18005758e  jnz     loc_18005761B
0x180057594  call    cs:__imp_GetLastError
0x18005759b  nop     dword ptr [rax+rax+00h]
0x1800575a0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800575a7  mov     edi, eax
0x1800575a9  test    rcx, rcx
0x1800575ac  jz      short loc_18005760D
0x1800575ae  mov     [rbp+var_28], rbx
0x1800575b2  lea     rax, [rbp+var_28]
0x1800575b6  mov     ebx, 3
0x1800575bb  mov     qword ptr [rsp+70h+var_50], rax
0x1800575c0  mov     r8d, ebx
0x1800575c3  lea     r9, aFailedToGetFul; "Failed to get full path for string: {}"
0x1800575ca  xor     edx, edx
0x1800575cc  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800575d1  test    edi, edi
0x1800575d3  jg      short loc_1800575D9
0x1800575d5  mov     eax, edi
0x1800575d7  jmp     short loc_1800575E1
0x1800575d9  movzx   eax, di
0x1800575dc  or      eax, 80070000h
0x1800575e1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800575e8  lea     r9, a0; ": {0}"
0x1800575ef  mov     [rbp+var_10], eax
  ... truncated ...
```
