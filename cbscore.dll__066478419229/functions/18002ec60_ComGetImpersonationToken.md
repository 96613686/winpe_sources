# ComGetImpersonationToken

- ea: `0x18002ec60`
- end: `0x18002ef45`
- name: `ComGetImpersonationToken`
- size: `741`
- prototype: ``
- caller_count: `12`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ed84`
- `0x18002cedc`
- `0x18002e778`
- `0x18005e64c`
- `0x18006a09c`
- `0x1801b337c`
- `0x1801bb214`
- `0x1801dba50`
- `0x1802b4ec4`
- `0x1802b5994`
- `0x1802b66f0`
- `0x1802b79b0`

## callees

- `0x18002ec60`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x180112ca4`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ed5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ed5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee1a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ee06`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ee06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002edeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002edeb`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18002ed07`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18002ed07`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002ed79`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002ed79`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18002ed48`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18002ed48`

## string_xrefs

- `0x18002ecb0`: `No token handle result specified`
- `0x18002ee39`: `Failed to get user security token`
- `0x18002ed9f`: `Failed to impersonate client.`
- `0x18002ee8e`: `onecore\base\cbs\util\cbscom.cpp`
- `0x18002ef15`: `onecore\base\cbs\util\cbscom.cpp`

## pseudocode

```c
__int64 __fastcall ComGetImpersonationToken(void **a1)
{
  int v2; // ebx
  int v3; // edx
  __int64 v4; // rdx
  signed int LastError; // eax
  int v6; // edx
  HANDLE CurrentThread; // rax
  signed int v8; // ebx
  int v9; // edx
  unsigned int v10; // eax
  int v11; // edx
  unsigned int v13; // [rsp+20h] [rbp-40h]
  int v14[2]; // [rsp+30h] [rbp-30h] BYREF
  char v15; // [rsp+38h] [rbp-28h]
  void *ppInterface; // [rsp+40h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-18h] BYREF
  int v18; // [rsp+50h] [rbp-10h] BYREF
  int v19; // [rsp+54h] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  TokenHandle = 0;
  v19 = 0;
  if ( !a1 )
  {
    v2 = -2147467261;
    v18 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No token handle result specified");
      ppInterface = &v18;
      LOBYTE(v3) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v3,
        3,
        (unsigned int)": {}",
        (__int64)&ppInterface);
    }
    v4 = 9;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\cbs\\util\\cbscom.cpp",
      (const char *)(unsigned int)v2,
      v13);
    return (unsigned int)v2;
  }
  ppInterface = 0;
  v2 = CoGetCallContext(&GUID_0000013e_0000_0000_c000_000000000046, &ppInterface);
  if ( v2 == -2147417833 )
  {
    v19 = 1;
  }
  else
  {
    if ( v2 < 0 )
    {
      v18 = v2;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to check RPC context.");
        *(_QWORD *)v14 = &v18;
        LOBYTE(v11) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v11,
          3,
          (unsigned int)": {}",
          (__int64)v14);
      }
      v4 = 29;
      goto LABEL_31;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
    if ( !v19 )
    {
      v2 = CoImpersonateClient();
      goto LABEL_13;
    }
  }
  if ( ImpersonateSelf(SecurityImpersonation) )
    goto LABEL_17;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
LABEL_13:
  if ( v2 < 0 )
  {
    v18 = v2;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to impersonate client.");
      ppInterface = &v18;
      LOBYTE(v6) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v6,
        3,
        (unsigned int)": {}",
        (__int64)&ppInterface);
    }
    v4 = 42;
    goto LABEL_31;
  }
LABEL_17:
  *(_QWORD *)v14 = &v19;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 0, &TokenHandle) )
  {
    *a1 = TokenHandle;
LABEL_26:
    v2 = 0;
    goto LABEL_27;
  }
  v8 = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get user security token");
    if ( v8 > 0 )
      v10 = (unsigned __int16)v8 | 0x80070000;
    else
      v10 = v8;
    v18 = v10;
    LOBYTE(v9) = 1;
    ppInterface = &v18;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v9,
      3,
      (unsigned int)": {0}",
      (__int64)&ppInterface);
  }
  if ( !v8 )
    goto LABEL_26;
  v2 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x40,
         (unsigned int)"onecore\\base\\cbs\\util\\cbscom.cpp",
         (const char *)(unsigned int)v8,
         v13);
LABEL_27:
  v15 = 0;
  ComGetImpersonationToken_::_2_::_lambda_1_::operator()(v14);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002ec60  mov     [rsp-8+arg_8], rbx
0x18002ec65  mov     [rsp-8+arg_10], rdi
0x18002ec6a  push    rbp
0x18002ec6b  mov     rbp, rsp
0x18002ec6e  sub     rsp, 60h
0x18002ec72  mov     rax, cs:__security_cookie
0x18002ec79  xor     rax, rsp
0x18002ec7c  mov     [rbp+var_8], rax
0x18002ec80  mov     [rbp+TokenHandle], 0
0x18002ec88  mov     rdi, rcx
0x18002ec8b  mov     [rbp+var_C], 0
0x18002ec92  test    rcx, rcx
0x18002ec95  jnz     short loc_18002ECF4
0x18002ec97  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18002ec9e  mov     ebx, 80004003h
0x18002eca3  mov     [rbp+var_10], ebx
0x18002eca6  test    rcx, rcx
0x18002eca9  jz      short loc_18002ECEA
0x18002ecab  mov     edi, 3
0x18002ecb0  lea     r9, aNoTokenHandleR; "No token handle result specified"
0x18002ecb7  mov     r8d, edi
0x18002ecba  xor     edx, edx
0x18002ecbc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18002ecc1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18002ecc8  lea     rax, [rbp+var_10]
0x18002eccc  mov     [rbp+ppInterface], rax
0x18002ecd0  lea     r9, asc_1802EE7AC; ": {}"
0x18002ecd7  lea     rax, [rbp+ppInterface]
0x18002ecdb  mov     r8d, edi
0x18002ecde  mov     dl, 1
0x18002ece0  mov     qword ptr [rsp+60h+var_40], rax
0x18002ece5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18002ecea  mov     edx, 9
0x18002ecef  jmp     loc_18002EF11
0x18002ecf4  lea     rdx, [rbp+ppInterface]; ppInterface
0x18002ecf8  mov     [rbp+ppInterface], 0
0x18002ed00  lea     rcx, _GUID_0000013e_0000_0000_c000_000000000046; riid
0x18002ed07  call    cs:__imp_CoGetCallContext
0x18002ed0e  nop     dword ptr [rax+rax+00h]
0x18002ed13  mov     ebx, eax
0x18002ed15  cmp     eax, 80010117h
0x18002ed1a  jnz     short loc_18002ED25
0x18002ed1c  mov     [rbp+var_C], 1
0x18002ed23  jmp     short loc_18002ED43
0x18002ed25  test    ebx, ebx
0x18002ed27  js      loc_18002EEBE
0x18002ed2d  mov     rcx, [rbp+ppInterface]
0x18002ed31  mov     rax, [rcx]
0x18002ed34  mov     rax, [rax+10h]
0x18002ed38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed3d  cmp     [rbp+var_C], 0
0x18002ed41  jz      short loc_18002ED79
0x18002ed43  mov     ecx, 2; ImpersonationLevel
0x18002ed48  call    cs:__imp_ImpersonateSelf
0x18002ed4f  nop     dword ptr [rax+rax+00h]
0x18002ed54  test    eax, eax
0x18002ed56  jnz     loc_18002EDE3
0x18002ed5c  call    cs:__imp_GetLastError
0x18002ed63  nop     dword ptr [rax+rax+00h]
0x18002ed68  mov     ebx, eax
0x18002ed6a  test    eax, eax
0x18002ed6c  jle     short loc_18002ED87
0x18002ed6e  movzx   ebx, ax
0x18002ed71  or      ebx, 80070000h
0x18002ed77  jmp     short loc_18002ED87
0x18002ed79  call    cs:__imp_CoImpersonateClient
0x18002ed80  nop     dword ptr [rax+rax+00h]
0x18002ed85  mov     ebx, eax
0x18002ed87  test    ebx, ebx
0x18002ed89  jns     short loc_18002EDE3
0x18002ed8b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18002ed92  mov     [rbp+var_10], ebx
0x18002ed95  test    rcx, rcx
0x18002ed98  jz      short loc_18002EDD9
0x18002ed9a  mov     edi, 3
0x18002ed9f  lea     r9, aFailedToImpers; "Failed to impersonate client."
0x18002eda6  mov     r8d, edi
0x18002eda9  xor     edx, edx
0x18002edab  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18002edb0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18002edb7  lea     rax, [rbp+var_10]
0x18002edbb  mov     [rbp+ppInterface], rax
0x18002edbf  lea     r9, asc_1802EE7AC; ": {}"
0x18002edc6  lea     rax, [rbp+ppInterface]
0x18002edca  mov     r8d, edi
0x18002edcd  mov     dl, 1
0x18002edcf  mov     qword ptr [rsp+60h+var_40], rax
0x18002edd4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18002edd9  mov     edx, 2Ah ; '*'
0x18002edde  jmp     loc_18002EF11
0x18002ede3  lea     rax, [rbp+var_C]
0x18002ede7  mov     qword ptr [rbp+var_30], rax
0x18002edeb  call    cs:__imp_GetCurrentThread
0x18002edf2  nop     dword ptr [rax+rax+00h]
0x18002edf7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002edfb  xor     r8d, r8d; OpenAsSelf
0x18002edfe  mov     rcx, rax; ThreadHandle
0x18002ee01  mov     edx, 0F01FFh; DesiredAccess
0x18002ee06  call    cs:__imp_OpenThreadToken
0x18002ee0d  nop     dword ptr [rax+rax+00h]
0x18002ee12  test    eax, eax
0x18002ee14  jnz     loc_18002EEA6
0x18002ee1a  call    cs:__imp_GetLastError
0x18002ee21  nop     dword ptr [rax+rax+00h]
0x18002ee26  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18002ee2d  mov     ebx, eax
0x18002ee2f  test    rcx, rcx
0x18002ee32  jz      short loc_18002EE86
0x18002ee34  mov     edi, 3
0x18002ee39  lea     r9, aFailedToGetUse_6; "Failed to get user security token"
0x18002ee40  mov     r8d, edi
0x18002ee43  xor     edx, edx
0x18002ee45  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18002ee4a  test    ebx, ebx
0x18002ee4c  jg      short loc_18002EE52
0x18002ee4e  mov     eax, ebx
0x18002ee50  jmp     short loc_18002EE5A
0x18002ee52  movzx   eax, bx
0x18002ee55  or      eax, 80070000h
0x18002ee5a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18002ee61  lea     r9, a0; ": {0}"
0x18002ee68  mov     [rbp+var_10], eax
0x18002ee6b  mov     r8d, edi
0x18002ee6e  lea     rax, [rbp+var_10]
0x18002ee72  mov     dl, 1
0x18002ee74  mov     [rbp+ppInterface], rax
0x18002ee78  lea     rax, [rbp+ppInterface]
0x18002ee7c  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x18002ee81  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18002ee86  test    ebx, ebx
0x18002ee88  jz      short loc_18002EEAD
0x18002ee8a  mov     rcx, [rbp+8]; this
0x18002ee8e  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbscom.cpp"
0x18002ee95  mov     r9d, ebx; char *
0x18002ee98  mov     edx, 40h ; '@'; void *
0x18002ee9d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002eea2  mov     ebx, eax
0x18002eea4  jmp     short loc_18002EEAF
0x18002eea6  mov     rax, [rbp+TokenHandle]
0x18002eeaa  mov     [rdi], rax
0x18002eead  xor     ebx, ebx
0x18002eeaf  lea     rcx, [rbp+var_30]
0x18002eeb3  mov     [rbp+var_28], 0
0x18002eeb7  call    _ComGetImpersonationToken____2____lambda_1___operator__
0x18002eebc  jmp     short loc_18002EF24
0x18002eebe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18002eec5  mov     [rbp+var_10], ebx
0x18002eec8  test    rcx, rcx
0x18002eecb  jz      short loc_18002EF0C
0x18002eecd  mov     edi, 3
0x18002eed2  lea     r9, aFailedToCheckR_0; "Failed to check RPC context."
0x18002eed9  mov     r8d, edi
0x18002eedc  xor     edx, edx
0x18002eede  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18002eee3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18002eeea  lea     rax, [rbp+var_10]
0x18002eeee  mov     qword ptr [rbp+var_30], rax
0x18002eef2  lea     r9, asc_1802EE7AC; ": {}"
0x18002eef9  lea     rax, [rbp+var_30]
0x18002eefd  mov     r8d, edi
0x18002ef00  mov     dl, 1
0x18002ef02  mov     qword ptr [rsp+60h+var_40], rax; int
0x18002ef07  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18002ef0c  mov     edx, 1Dh; void *
0x18002ef11  mov     rcx, [rbp+8]; this
0x18002ef15  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbscom.cpp"
0x18002ef1c  mov     r9d, ebx; char *
0x18002ef1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ef24  mov     eax, ebx
0x18002ef26  mov     rcx, [rbp+var_8]
0x18002ef2a  xor     rcx, rsp; StackCookie
0x18002ef2d  call    __security_check_cookie
0x18002ef32  lea     r11, [rsp+60h+var_s0]
0x18002ef37  mov     rbx, [r11+18h]
0x18002ef3b  mov     rdi, [r11+20h]
0x18002ef3f  mov     rsp, r11
0x18002ef42  pop     rbp
0x18002ef43  retn
```
