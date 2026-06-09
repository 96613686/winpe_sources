# ImpersonateLoggedOnUserUsingUMgr

- ea: `0x140011cd0`
- end: `0x140012117`
- name: `ImpersonateLoggedOnUserUsingUMgr`
- size: `1095`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400119f0`

## callees

- `0x140001008`
- `0x140001840`
- `0x140001bb4`
- `0x140002e50`
- `0x140002eb8`
- `0x140011580`
- `0x140011cd0`
- `0x140019610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012019`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400120c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400120c7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140012009`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140012009`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1400120e3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1400120e3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x140011f4f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x140011f4f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x140011e0b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x140011e0b`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x140011d77`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x140011d77`

## string_xrefs

- `0x140011d53`: `Attempting to impersonate with UMgr`
- `0x140011de3`: `Attempt to find active user with UMgr`
- `0x14001206a`: `User context token is invalid.`
- `0x140011f73`: `UMgrQueryUserToken failed.`
- `0x140011fcd`: `Got user token.`
- `0x140012042`: `ImpersonateLoggedOnUser failed`

## pseudocode

```c
__int64 __fastcall ImpersonateLoggedOnUserUsingUMgr(WCHAR **a1)
{
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  signed int v9; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  signed int UserToken; // ebx
  unsigned int v14; // r14d
  const char *v15; // rax
  __int16 *v16; // rdx
  __int64 v17; // r14
  signed int LastError; // eax
  const char *v19; // [rsp+30h] [rbp-59h] BYREF
  const char *v20; // [rsp+38h] [rbp-51h] BYREF
  unsigned int v21; // [rsp+40h] [rbp-49h] BYREF
  int v22; // [rsp+44h] [rbp-45h] BYREF
  __int64 v23; // [rsp+48h] [rbp-41h] BYREF
  __int64 v24; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v25[32]; // [rsp+60h] [rbp-29h] BYREF
  const char *v26; // [rsp+80h] [rbp-9h]
  __int64 v27; // [rsp+88h] [rbp-1h]
  const char **v28; // [rsp+90h] [rbp+7h]
  __int64 v29; // [rsp+98h] [rbp+Fh]
  const char **v30; // [rsp+A0h] [rbp+17h]
  __int64 v31; // [rsp+A8h] [rbp+1Fh]
  const char **v32; // [rsp+B0h] [rbp+27h]
  __int64 v33; // [rsp+B8h] [rbp+2Fh]

  v22 = 0;
  v21 = 0;
  v24 = 0;
  if ( !a1 )
    return 2147942487LL;
  *a1 = (WCHAR *)-1LL;
  if ( !(unsigned __int8)IsUMgrEnumerateSessionUsersPresent()
    || !(unsigned __int8)IsUMgrEnumerateSessionUsersPresent()
    || !(unsigned __int8)IsQueryActiveSessionPresent() )
  {
    UserToken = -2147024846;
    if ( (unsigned int)dword_140028000 <= 5 )
      goto LABEL_44;
    LODWORD(v19) = -2147024846;
    v15 = "UMgr not available";
    v16 = (__int16 *)byte_140023211;
    goto LABEL_43;
  }
  if ( (unsigned int)dword_140028000 > 5 )
  {
    v19 = "Attempting to impersonate with UMgr";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v3,
      (unsigned int)byte_140023163,
      v4,
      v5,
      (__int64)&v19);
  }
  if ( (unsigned int)QueryActiveSession(&v22) )
  {
    if ( (unsigned int)dword_140028000 > 5 )
    {
      v19 = "Attempt to find active user with UMgr";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v6,
        (unsigned int)&byte_140023307,
        v7,
        v8,
        (__int64)&v19);
    }
    UserToken = UMgrEnumerateSessionUsers(&v21, &v24);
    if ( UserToken >= 0 && v21 && v24 )
    {
      v14 = 0;
      while ( 1 )
      {
        if ( (unsigned int)dword_140028000 > 5 )
        {
          LODWORD(v23) = UserToken;
          v32 = (const char **)&v23;
          LODWORD(v20) = v14;
          v30 = &v20;
          LODWORD(v19) = v14;
          v28 = &v19;
          v33 = 4;
          v26 = "Session info.";
          v31 = 4;
          v29 = 4;
          v27 = 14;
          tlgWriteTransfer_EventWriteTransfer(&dword_140028000, byte_140023325, 0, 0, 6, v25);
        }
        v3 = 2 * v14;
        if ( *(_DWORD *)(v24 + 16LL * v14 + 8) == v22 )
          break;
        if ( ++v14 >= v21 )
          goto LABEL_23;
      }
      v17 = *(_QWORD *)(v24 + 16LL * v14);
      if ( (unsigned int)dword_140028000 > 5 )
      {
        LODWORD(v19) = UserToken;
        v20 = "Found user context for active session.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v3,
          (unsigned int)&byte_1400231A7,
          v4,
          v5,
          (__int64)&v20,
          (__int64)&v19);
      }
      if ( !v17 )
      {
LABEL_23:
        if ( (unsigned int)dword_140028000 <= 5 )
          goto LABEL_44;
        LODWORD(v19) = UserToken;
        v15 = "Failed to find the session context for the active session";
        v16 = &word_140023536;
        goto LABEL_43;
      }
      UserToken = UMgrQueryUserToken(v17, a1);
      if ( UserToken >= 0 )
      {
        if ( (unsigned int)dword_140028000 > 5 )
        {
          v20 = (const char *)*a1;
          LODWORD(v19) = UserToken;
          v32 = &v19;
          v23 = v17;
          v30 = &v20;
          v33 = 4;
          v28 = (const char **)&v23;
          v26 = "Got user token.";
          v31 = 8;
          v29 = 8;
          v27 = 16;
          tlgWriteTransfer_EventWriteTransfer(&dword_140028000, &byte_140023237, 0, 0, 6, v25);
        }
        if ( ImpersonateLoggedOnUser(*a1) )
        {
          DumpSIDString(*a1);
          goto LABEL_46;
        }
        LastError = GetLastError();
        UserToken = LastError;
        if ( LastError > 0 )
          UserToken = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)dword_140028000 > 5 )
        {
          LODWORD(v19) = UserToken;
          v15 = "ImpersonateLoggedOnUser failed";
          v16 = (__int16 *)&dword_1400234C4;
          goto LABEL_43;
        }
        goto LABEL_44;
      }
      if ( (unsigned int)dword_140028000 <= 5 )
        goto LABEL_44;
      LODWORD(v19) = UserToken;
      v15 = "UMgrQueryUserToken failed.";
      v16 = word_140023452;
    }
    else
    {
      if ( (unsigned int)dword_140028000 <= 5 )
        goto LABEL_44;
      LODWORD(v19) = UserToken;
      v15 = "User context token is invalid.";
      v16 = (__int16 *)qword_140023278;
    }
LABEL_43:
    v20 = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v3,
      (_DWORD)v16,
      v4,
      v5,
      (__int64)&v20,
      (__int64)&v19);
    goto LABEL_44;
  }
  v9 = GetLastError();
  UserToken = v9;
  if ( v9 > 0 )
    UserToken = (unsigned __int16)v9 | 0x80070000;
  if ( (unsigned int)dword_140028000 > 5 )
  {
    LODWORD(v23) = UserToken;
    v19 = "QueryActiveSession failed.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v10,
      (unsigned int)qword_1400233E0,
      v11,
      v12,
      (__int64)&v19,
      (__int64)&v23);
  }
LABEL_44:
  if ( (unsigned __int64)*a1 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(*a1);
    *a1 = (WCHAR *)-1LL;
  }
LABEL_46:
  if ( v24 )
    UMgrFreeSessionUsers();
  return (unsigned int)UserToken;
}

```

## disassembly

```asm
0x140011cd0  mov     [rsp-8+arg_8], rbx
0x140011cd5  mov     [rsp-8+arg_10], rsi
0x140011cda  push    rbp
0x140011cdb  push    r14
0x140011cdd  push    r15
0x140011cdf  lea     rbp, [rsp-47h]
0x140011ce4  sub     rsp, 0D0h
0x140011ceb  mov     rax, cs:__security_cookie
0x140011cf2  xor     rax, rsp
0x140011cf5  mov     [rbp+57h+var_20], rax
0x140011cf9  xor     r15d, r15d
0x140011cfc  mov     rsi, rcx
0x140011cff  mov     [rbp+57h+var_9C], r15d
0x140011d03  mov     [rbp+57h+var_A0], r15d
0x140011d07  mov     [rbp+57h+var_90], r15
0x140011d0b  test    rcx, rcx
0x140011d0e  jnz     short loc_140011D1A
0x140011d10  mov     eax, 80070057h
0x140011d15  jmp     loc_1400120F1
0x140011d1a  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x140011d21  call    IsUMgrEnumerateSessionUsersPresent
0x140011d26  test    al, al
0x140011d28  jz      loc_14001207A
0x140011d2e  call    IsUMgrEnumerateSessionUsersPresent
0x140011d33  test    al, al
0x140011d35  jz      loc_14001207A
0x140011d3b  call    IsQueryActiveSessionPresent
0x140011d40  test    al, al
0x140011d42  jz      loc_14001207A
0x140011d48  mov     eax, cs:dword_140028000
0x140011d4e  cmp     eax, 5
0x140011d51  jbe     short loc_140011D73
0x140011d53  lea     rax, aAttemptingToIm_0; "Attempting to impersonate with UMgr"
0x140011d5a  mov     [rbp+57h+var_B0], rax
0x140011d5e  lea     rdx, byte_140023163
0x140011d65  lea     rax, [rbp+57h+var_B0]
0x140011d69  mov     [rsp+0E0h+var_C0], rax
0x140011d6e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140011d73  lea     rcx, [rbp+57h+var_9C]
0x140011d77  call    cs:__imp_QueryActiveSession
0x140011d7e  nop     dword ptr [rax+rax+00h]
0x140011d83  test    eax, eax
0x140011d85  jnz     short loc_140011DD8
0x140011d87  call    cs:__imp_GetLastError
0x140011d8e  nop     dword ptr [rax+rax+00h]
0x140011d93  mov     ebx, eax
0x140011d95  test    eax, eax
0x140011d97  jle     short loc_140011DA2
0x140011d99  movzx   ebx, ax
0x140011d9c  or      ebx, 80070000h
0x140011da2  mov     eax, cs:dword_140028000
0x140011da8  cmp     eax, 5
0x140011dab  jbe     loc_1400120BA
0x140011db1  lea     rax, aQueryactiveses_0; "QueryActiveSession failed."
0x140011db8  mov     dword ptr [rbp+57h+var_98], ebx
0x140011dbb  mov     [rbp+57h+var_B0], rax
0x140011dbf  lea     rdx, qword_1400233E0
0x140011dc6  lea     rax, [rbp+57h+var_98]
0x140011dca  mov     [rsp+0E0h+var_B8], rax
0x140011dcf  lea     rax, [rbp+57h+var_B0]
0x140011dd3  jmp     loc_1400120B0
0x140011dd8  mov     eax, cs:dword_140028000
0x140011dde  cmp     eax, 5
0x140011de1  jbe     short loc_140011E03
0x140011de3  lea     rax, aAttemptToFindA; "Attempt to find active user with UMgr"
0x140011dea  mov     [rbp+57h+var_B0], rax
0x140011dee  lea     rdx, byte_140023307
0x140011df5  lea     rax, [rbp+57h+var_B0]
0x140011df9  mov     [rsp+0E0h+var_C0], rax
0x140011dfe  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140011e03  lea     rdx, [rbp+57h+var_90]
0x140011e07  lea     rcx, [rbp+57h+var_A0]
0x140011e0b  call    cs:__imp_UMgrEnumerateSessionUsers
0x140011e12  nop     dword ptr [rax+rax+00h]
0x140011e17  mov     ebx, eax
0x140011e19  test    eax, eax
0x140011e1b  js      loc_14001205C
0x140011e21  mov     eax, [rbp+57h+var_A0]
0x140011e24  test    eax, eax
0x140011e26  jz      loc_14001205C
0x140011e2c  cmp     [rbp+57h+var_90], r15
0x140011e30  jz      loc_14001205C
0x140011e36  mov     r14d, r15d
0x140011e39  test    eax, eax
0x140011e3b  jz      loc_140011EE4
0x140011e41  mov     eax, cs:dword_140028000
0x140011e47  cmp     eax, 5
0x140011e4a  jbe     short loc_140011EC4
0x140011e4c  lea     rax, [rbp+57h+var_98]
0x140011e50  mov     dword ptr [rbp+57h+var_98], ebx
0x140011e53  mov     [rbp+57h+var_30], rax
0x140011e57  lea     rdx, byte_140023325
0x140011e5e  lea     rax, [rbp+57h+var_A8]
0x140011e62  mov     dword ptr [rbp+57h+var_A8], r14d
0x140011e66  mov     [rbp+57h+var_40], rax
0x140011e6a  lea     rcx, dword_140028000
0x140011e71  lea     rax, [rbp+57h+var_B0]
0x140011e75  mov     dword ptr [rbp+57h+var_B0], r14d
0x140011e79  mov     [rbp+57h+var_50], rax
0x140011e7d  xor     r9d, r9d
0x140011e80  lea     rax, aSessionInfo; "Session info."
0x140011e87  mov     [rbp+57h+var_28], 4
0x140011e8f  mov     [rbp+57h+var_60], rax
0x140011e93  xor     r8d, r8d
0x140011e96  lea     rax, [rbp+57h+var_80]
0x140011e9a  mov     [rbp+57h+var_38], 4
0x140011ea2  mov     [rsp+0E0h+var_B8], rax
0x140011ea7  mov     dword ptr [rsp+0E0h+var_C0], 6
0x140011eaf  mov     [rbp+57h+var_48], 4
0x140011eb7  mov     [rbp+57h+var_58], 0Eh
0x140011ebf  call    _tlgWriteTransfer_EventWriteTransfer
0x140011ec4  mov     rdx, [rbp+57h+var_90]
0x140011ec8  mov     eax, [rbp+57h+var_9C]
0x140011ecb  mov     ecx, r14d
0x140011ece  add     rcx, rcx
0x140011ed1  cmp     [rdx+rcx*8+8], eax
0x140011ed5  jz      short loc_140011F09
0x140011ed7  inc     r14d
0x140011eda  cmp     r14d, [rbp+57h+var_A0]
0x140011ede  jb      loc_140011E41
0x140011ee4  mov     eax, cs:dword_140028000
0x140011eea  cmp     eax, 5
0x140011eed  jbe     loc_1400120BA
0x140011ef3  mov     dword ptr [rbp+57h+var_B0], ebx
0x140011ef6  lea     rax, aFailedToFindTh; "Failed to find the session context for "...
0x140011efd  lea     rdx, word_140023536
0x140011f04  jmp     loc_14001209F
0x140011f09  mov     eax, cs:dword_140028000
0x140011f0f  mov     r14, [rdx+rcx*8]
0x140011f13  cmp     eax, 5
0x140011f16  jbe     short loc_140011F44
0x140011f18  lea     rax, aFoundUserConte; "Found user context for active session."
0x140011f1f  mov     dword ptr [rbp+57h+var_B0], ebx
0x140011f22  mov     [rbp+57h+var_A8], rax
0x140011f26  lea     rdx, byte_1400231A7
0x140011f2d  lea     rax, [rbp+57h+var_B0]
0x140011f31  mov     [rsp+0E0h+var_B8], rax
0x140011f36  lea     rax, [rbp+57h+var_A8]
0x140011f3a  mov     [rsp+0E0h+var_C0], rax
0x140011f3f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140011f44  test    r14, r14
0x140011f47  jz      short loc_140011EE4
0x140011f49  mov     rdx, rsi
0x140011f4c  mov     rcx, r14
0x140011f4f  call    cs:__imp_UMgrQueryUserToken
0x140011f56  nop     dword ptr [rax+rax+00h]
0x140011f5b  mov     ebx, eax
0x140011f5d  test    eax, eax
0x140011f5f  mov     eax, cs:dword_140028000
0x140011f65  jns     short loc_140011F86
0x140011f67  cmp     eax, 5
0x140011f6a  jbe     loc_1400120BA
0x140011f70  mov     dword ptr [rbp+57h+var_B0], ebx
0x140011f73  lea     rax, aUmgrqueryusert_0; "UMgrQueryUserToken failed."
0x140011f7a  lea     rdx, word_140023452
0x140011f81  jmp     loc_14001209F
0x140011f86  cmp     eax, 5
0x140011f89  jbe     short loc_140012006
0x140011f8b  mov     rax, [rsi]
0x140011f8e  lea     rdx, byte_140023237
0x140011f95  mov     [rbp+57h+var_A8], rax
0x140011f99  lea     rcx, dword_140028000
0x140011fa0  lea     rax, [rbp+57h+var_B0]
0x140011fa4  mov     dword ptr [rbp+57h+var_B0], ebx
0x140011fa7  mov     [rbp+57h+var_30], rax
0x140011fab  xor     r9d, r9d
0x140011fae  lea     rax, [rbp+57h+var_A8]
0x140011fb2  mov     [rbp+57h+var_98], r14
0x140011fb6  mov     [rbp+57h+var_40], rax
0x140011fba  xor     r8d, r8d
0x140011fbd  lea     rax, [rbp+57h+var_98]
0x140011fc1  mov     [rbp+57h+var_28], 4
0x140011fc9  mov     [rbp+57h+var_50], rax
0x140011fcd  lea     rax, aGotUserToken; "Got user token."
0x140011fd4  mov     [rbp+57h+var_60], rax
0x140011fd8  lea     rax, [rbp+57h+var_80]
0x140011fdc  mov     [rsp+0E0h+var_B8], rax
0x140011fe1  mov     dword ptr [rsp+0E0h+var_C0], 6
0x140011fe9  mov     [rbp+57h+var_38], 8
0x140011ff1  mov     [rbp+57h+var_48], 8
0x140011ff9  mov     [rbp+57h+var_58], 10h
0x140012001  call    _tlgWriteTransfer_EventWriteTransfer
0x140012006  mov     rcx, [rsi]; hToken
0x140012009  call    cs:__imp_ImpersonateLoggedOnUser
0x140012010  nop     dword ptr [rax+rax+00h]
0x140012015  test    eax, eax
0x140012017  jnz     short loc_140012052
0x140012019  call    cs:__imp_GetLastError
0x140012020  nop     dword ptr [rax+rax+00h]
0x140012025  mov     ebx, eax
0x140012027  test    eax, eax
0x140012029  jle     short loc_140012034
0x14001202b  movzx   ebx, ax
0x14001202e  or      ebx, 80070000h
0x140012034  mov     eax, cs:dword_140028000
0x14001203a  cmp     eax, 5
0x14001203d  jbe     short loc_1400120BA
0x14001203f  mov     dword ptr [rbp+57h+var_B0], ebx
0x140012042  lea     rax, aImpersonatelog; "ImpersonateLoggedOnUser failed"
0x140012049  lea     rdx, dword_1400234C4
0x140012050  jmp     short loc_14001209F
0x140012052  mov     rcx, [rsi]; TokenHandle
0x140012055  call    ?DumpSIDString@@YAXPEAX@Z; DumpSIDString(void *)
0x14001205a  jmp     short loc_1400120DA
0x14001205c  mov     eax, cs:dword_140028000
0x140012062  cmp     eax, 5
0x140012065  jbe     short loc_1400120BA
0x140012067  mov     dword ptr [rbp+57h+var_B0], ebx
0x14001206a  lea     rax, aUserContextTok; "User context token is invalid."
0x140012071  lea     rdx, qword_140023278
0x140012078  jmp     short loc_14001209F
0x14001207a  mov     eax, cs:dword_140028000
0x140012080  mov     ebx, 80070032h
0x140012085  cmp     eax, 5
0x140012088  jbe     short loc_1400120BA
0x14001208a  mov     dword ptr [rbp+57h+var_B0], 80070032h
0x140012091  lea     rax, aUmgrNotAvailab; "UMgr not available"
0x140012098  lea     rdx, byte_140023211
0x14001209f  mov     [rbp+57h+var_A8], rax
0x1400120a3  lea     rax, [rbp+57h+var_B0]
0x1400120a7  mov     [rsp+0E0h+var_B8], rax
0x1400120ac  lea     rax, [rbp+57h+var_A8]
0x1400120b0  mov     [rsp+0E0h+var_C0], rax
0x1400120b5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400120ba  mov     rcx, [rsi]; hObject
0x1400120bd  lea     rax, [rcx-1]
0x1400120c1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400120c5  ja      short loc_1400120DA
0x1400120c7  call    cs:__imp_CloseHandle
0x1400120ce  nop     dword ptr [rax+rax+00h]
0x1400120d3  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1400120da  mov     rcx, [rbp+57h+var_90]
0x1400120de  test    rcx, rcx
0x1400120e1  jz      short loc_1400120EF
0x1400120e3  call    cs:__imp_UMgrFreeSessionUsers
0x1400120ea  nop     dword ptr [rax+rax+00h]
0x1400120ef  mov     eax, ebx
0x1400120f1  mov     rcx, [rbp+57h+var_20]
0x1400120f5  xor     rcx, rsp; StackCookie
0x1400120f8  call    __security_check_cookie
0x1400120fd  lea     r11, [rsp+0E0h+var_10]
0x140012105  mov     rbx, [r11+28h]
0x140012109  mov     rsi, [r11+30h]
0x14001210d  mov     rsp, r11
0x140012110  pop     r15
0x140012112  pop     r14
0x140012114  pop     rbp
0x140012115  retn
```
