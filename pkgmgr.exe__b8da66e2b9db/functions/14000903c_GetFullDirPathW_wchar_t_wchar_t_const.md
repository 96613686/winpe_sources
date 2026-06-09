# GetFullDirPathW(wchar_t * *,wchar_t const *)

- ea: `0x14000903c`
- end: `0x1400092f5`
- name: `?GetFullDirPathW@@YAJPEAPEA_WPEB_W@Z`
- size: `697`
- prototype: `__int64 __fastcall(wchar_t **, const wchar_t *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x140007524`
- `0x1400089c0`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006984`
- `0x140006c50`
- `0x14000726c`
- `0x140008de8`
- `0x14000903c`
- `0x14000952c`
- `0x140010b3c`
- `0x140011884`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400091c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400091c1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14000911e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14000911e`

## string_xrefs

- `0x14000926b`: `Failed allocating buffer for path expansion`
- `0x1400091d5`: `Failed getting the full path name`
- `0x140009165`: `Failed allocating memory for full directory path {}`

## pseudocode

```c
__int64 __fastcall GetFullDirPathW(wchar_t **a1, const wchar_t *a2)
{
  int v3; // eax
  int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  DWORD i; // edi
  LPWSTR v8; // rbx
  DWORD FullPathNameW; // eax
  int v10; // eax
  unsigned int v11; // esi
  __int64 v12; // rdx
  signed int LastError; // ebx
  __int64 v14; // rdx
  unsigned int v15; // eax
  __int64 v17; // rdx
  unsigned int v18; // [rsp+20h] [rbp-60h]
  LPCWSTR lpFileName; // [rsp+30h] [rbp-50h] BYREF
  LPWSTR lpBuffer; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v21[2]; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v22[2]; // [rsp+48h] [rbp-38h] BYREF
  const wchar_t *v23; // [rsp+58h] [rbp-28h] BYREF
  LPWSTR FilePart; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v25; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v22[1] = -2;
  v23 = a2;
  lpBuffer = 0;
  FilePart = 0;
  lpFileName = 0;
  v3 = ExpandStringFromSz((wchar_t **)&lpFileName, a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    for ( i = 260; ; i = FullPathNameW )
    {
      v4 = SczAlloc(&lpBuffer, i);
      if ( v4 < 0 )
        break;
      v8 = lpBuffer;
      FullPathNameW = GetFullPathNameW(lpFileName, i, lpBuffer, &FilePart);
      if ( !FullPathNameW )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting the full path name");
          if ( LastError > 0 )
            v15 = (unsigned __int16)LastError | 0x80070000;
          else
            v15 = LastError;
          v25 = v15;
          *(_QWORD *)v21 = &v25;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v14,
            3,
            (__int64)": {0}",
            (__int64)v21);
        }
        if ( LastError )
        {
          v4 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x53,
                 (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\util.cpp",
                 (const char *)(unsigned int)LastError,
                 v18);
          goto LABEL_26;
        }
        goto LABEL_21;
      }
      if ( FullPathNameW <= i )
      {
        v10 = SczAllocFromSz(a1, v8);
        v11 = v10;
        if ( v10 < 0 )
        {
          v25 = v10;
          if ( LogAdapter::g_Logger )
          {
            v22[0] = v8;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed allocating memory for full directory path {}",
              (__int64)v22);
            *(_QWORD *)v21 = &v25;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              v12,
              3,
              (__int64)": {}",
              (__int64)v21);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5D,
            (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\util.cpp",
            (const char *)v11,
            v18);
          v4 = v11;
          goto LABEL_26;
        }
LABEL_21:
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
        return 0;
      }
    }
    v25 = v4;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed allocating buffer for path expansion");
      *(_QWORD *)v21 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v17,
        3,
        (__int64)": {}",
        (__int64)v21);
    }
    v6 = 75;
  }
  else
  {
    v25 = v3;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed expanding string: {}",
        (__int64)&v23);
      v22[0] = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v22);
    }
    v6 = 68;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\util.cpp",
    (const char *)(unsigned int)v4,
    v18);
LABEL_26:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000903c  mov     rax, rsp
0x14000903f  push    rbp
0x140009040  push    rsi
0x140009041  push    rdi
0x140009042  mov     rbp, rsp
0x140009045  sub     rsp, 80h
0x14000904c  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x140009054  mov     [rax+18h], rbx
0x140009058  mov     rax, cs:__security_cookie
0x14000905f  xor     rax, rsp
0x140009062  mov     [rbp+var_10], rax
0x140009066  mov     rsi, rcx
0x140009069  mov     [rbp+var_28], rdx
0x14000906d  mov     [rbp+lpBuffer], 0
0x140009075  mov     [rbp+FilePart], 0
0x14000907d  mov     [rbp+lpFileName], 0
0x140009085  lea     rcx, [rbp+lpFileName]; wchar_t **
0x140009089  call    ?ExpandStringFromSz@@YAJPEAPEA_WPEB_W@Z; ExpandStringFromSz(wchar_t * *,wchar_t const *)
0x14000908e  mov     ebx, eax
0x140009090  test    eax, eax
0x140009092  jns     short loc_1400090F3
0x140009094  mov     [rbp+var_18], eax
0x140009097  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000909e  test    rcx, rcx
0x1400090a1  jz      short loc_1400090E9
0x1400090a3  lea     rax, [rbp+var_28]
0x1400090a7  mov     qword ptr [rsp+80h+var_60], rax
0x1400090ac  lea     r9, aFailedExpandin; "Failed expanding string: {}"
0x1400090b3  mov     edi, 3
0x1400090b8  mov     r8d, edi
0x1400090bb  xor     edx, edx
0x1400090bd  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1400090c2  lea     rax, [rbp+var_18]
0x1400090c6  mov     [rbp+var_38], rax
0x1400090ca  lea     rax, [rbp+var_38]
0x1400090ce  mov     qword ptr [rsp+80h+var_60], rax
0x1400090d3  lea     r9, asc_14002D4FC; ": {}"
0x1400090da  mov     r8d, edi
0x1400090dd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400090e4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400090e9  mov     edx, 44h ; 'D'
0x1400090ee  jmp     loc_1400092AD
0x1400090f3  mov     edi, 104h
0x1400090f8  mov     edx, edi
0x1400090fa  lea     rcx, [rbp+lpBuffer]
0x1400090fe  call    SczAlloc
0x140009103  mov     ebx, eax
0x140009105  test    eax, eax
0x140009107  js      loc_14000925C
0x14000910d  lea     r9, [rbp+FilePart]; lpFilePart
0x140009111  mov     rbx, [rbp+lpBuffer]
0x140009115  mov     r8, rbx; lpBuffer
0x140009118  mov     edx, edi; nBufferLength
0x14000911a  mov     rcx, [rbp+lpFileName]; lpFileName
0x14000911e  call    cs:__imp_GetFullPathNameW
0x140009124  test    eax, eax
0x140009126  jz      loc_1400091C1
0x14000912c  cmp     eax, edi
0x14000912e  jbe     short loc_140009134
0x140009130  mov     edi, eax
0x140009132  jmp     short loc_1400090F8
0x140009134  mov     rdx, rbx
0x140009137  mov     rcx, rsi
0x14000913a  call    SczAllocFromSz
0x14000913f  mov     esi, eax
0x140009141  test    eax, eax
0x140009143  jns     loc_140009245
0x140009149  mov     [rbp+var_18], eax
0x14000914c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009153  test    rcx, rcx
0x140009156  jz      short loc_1400091A2
0x140009158  mov     [rbp+var_38], rbx
0x14000915c  lea     rax, [rbp+var_38]
0x140009160  mov     qword ptr [rsp+80h+var_60], rax
0x140009165  lea     r9, aFailedAllocati_3; "Failed allocating memory for full direc"...
0x14000916c  mov     edi, 3
0x140009171  mov     r8d, edi
0x140009174  xor     edx, edx
0x140009176  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14000917b  lea     rax, [rbp+var_18]
0x14000917f  mov     qword ptr [rbp+var_40], rax
0x140009183  lea     rax, [rbp+var_40]
0x140009187  mov     qword ptr [rsp+80h+var_60], rax; int
0x14000918c  lea     r9, asc_14002D4FC; ": {}"
0x140009193  mov     r8d, edi
0x140009196  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000919d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400091a2  mov     rcx, [rbp+18h]; this
0x1400091a6  mov     r9d, esi; char *
0x1400091a9  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\pkgmgrshim\\util.cp"...
0x1400091b0  mov     edx, 5Dh ; ']'; void *
0x1400091b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400091ba  mov     ebx, esi
0x1400091bc  jmp     loc_1400092C1
0x1400091c1  call    cs:__imp_GetLastError
0x1400091c7  mov     ebx, eax
0x1400091c9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400091d0  test    rcx, rcx
0x1400091d3  jz      short loc_140009225
0x1400091d5  lea     r9, aFailedGettingT; "Failed getting the full path name"
0x1400091dc  mov     edi, 3
0x1400091e1  mov     r8d, edi
0x1400091e4  xor     edx, edx
0x1400091e6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400091eb  test    ebx, ebx
0x1400091ed  jg      short loc_1400091F3
0x1400091ef  mov     eax, ebx
0x1400091f1  jmp     short loc_1400091FB
0x1400091f3  movzx   eax, bx
0x1400091f6  or      eax, 80070000h
0x1400091fb  mov     [rbp+var_18], eax
0x1400091fe  lea     rax, [rbp+var_18]
0x140009202  mov     qword ptr [rbp+var_40], rax
0x140009206  lea     rax, [rbp+var_40]
0x14000920a  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x14000920f  lea     r9, a0; ": {0}"
0x140009216  mov     r8d, edi
0x140009219  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009220  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140009225  test    ebx, ebx
0x140009227  jz      short loc_140009245
0x140009229  mov     rcx, [rbp+18h]; this
0x14000922d  mov     r9d, ebx; char *
0x140009230  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\pkgmgrshim\\util.cp"...
0x140009237  mov     edx, 53h ; 'S'; void *
0x14000923c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140009241  mov     ebx, eax
0x140009243  jmp     short loc_1400092C1
0x140009245  lea     rcx, [rbp+lpFileName]
0x140009249  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000924e  nop
0x14000924f  lea     rcx, [rbp+lpBuffer]
0x140009253  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140009258  xor     eax, eax
0x14000925a  jmp     short loc_1400092D6
0x14000925c  mov     [rbp+var_18], ebx
0x14000925f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009266  test    rcx, rcx
0x140009269  jz      short loc_1400092A8
0x14000926b  lea     r9, aFailedAllocati_1; "Failed allocating buffer for path expan"...
0x140009272  mov     edi, 3
0x140009277  mov     r8d, edi
0x14000927a  xor     edx, edx
0x14000927c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140009281  lea     rax, [rbp+var_18]
0x140009285  mov     qword ptr [rbp+var_40], rax
0x140009289  lea     rax, [rbp+var_40]
0x14000928d  mov     qword ptr [rsp+80h+var_60], rax; int
0x140009292  lea     r9, asc_14002D4FC; ": {}"
0x140009299  mov     r8d, edi
0x14000929c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400092a3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400092a8  mov     edx, 4Bh ; 'K'; void *
0x1400092ad  mov     r9d, ebx; char *
0x1400092b0  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\pkgmgrshim\\util.cp"...
0x1400092b7  mov     rcx, [rbp+18h]; this
0x1400092bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400092c0  nop
0x1400092c1  lea     rcx, [rbp+lpFileName]
0x1400092c5  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400092ca  nop
0x1400092cb  lea     rcx, [rbp+lpBuffer]
0x1400092cf  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400092d4  mov     eax, ebx
0x1400092d6  mov     rcx, [rbp+var_10]
0x1400092da  xor     rcx, rsp; StackCookie
0x1400092dd  call    __security_check_cookie
0x1400092e2  mov     rbx, [rsp+80h+arg_10]
0x1400092ea  add     rsp, 80h
0x1400092f1  pop     rdi
0x1400092f2  pop     rsi
0x1400092f3  pop     rbp
0x1400092f4  retn
```
