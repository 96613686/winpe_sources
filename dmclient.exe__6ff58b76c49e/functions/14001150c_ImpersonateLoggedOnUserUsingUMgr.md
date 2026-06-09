# ImpersonateLoggedOnUserUsingUMgr

- ea: `0x14001150c`
- end: `0x140011922`
- name: `ImpersonateLoggedOnUserUsingUMgr`
- size: `1046`
- prototype: `__int64 __fastcall(int **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011250`

## callees

- `0x140001008`
- `0x14000182c`
- `0x140001b9c`
- `0x140002e10`
- `0x140002e78`
- `0x140010e70`
- `0x14001150c`
- `0x1400187e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400115bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400115bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011837`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400118df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400118df`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14001182d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14001182d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1400118f5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1400118f5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x140011779`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x140011779`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x14001163b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x14001163b`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x1400115b3`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x1400115b3`

## string_xrefs

- `0x14001158f`: `Attempting to impersonate with UMgr`
- `0x140011613`: `Attempt to find active user with UMgr`
- `0x140011882`: `User context token is invalid.`
- `0x140011797`: `UMgrQueryUserToken failed.`
- `0x1400117f1`: `Got user token.`
- `0x14001185a`: `ImpersonateLoggedOnUser failed`

## pseudocode

```c
__int64 __fastcall ImpersonateLoggedOnUserUsingUMgr(int **a1)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  signed int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
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
  struct _EVENT_DATA_DESCRIPTOR v25[2]; // [rsp+60h] [rbp-29h] BYREF
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
  *a1 = (int *)-1LL;
  if ( !(unsigned __int8)IsUMgrEnumerateSessionUsersPresent()
    || !(unsigned __int8)IsUMgrEnumerateSessionUsersPresent()
    || !(unsigned __int8)IsQueryActiveSessionPresent() )
  {
    UserToken = -2147024846;
    if ( (unsigned int)dword_140027000 <= 5 )
      goto LABEL_44;
    LODWORD(v19) = -2147024846;
    v15 = "UMgr not available";
    v16 = (__int16 *)byte_140022209;
    goto LABEL_43;
  }
  if ( (unsigned int)dword_140027000 > 5 )
  {
    v19 = "Attempting to impersonate with UMgr";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v3,
      (__int64)byte_14002215B,
      v4,
      v5,
      (const unsigned __int16 **)&v19);
  }
  if ( (unsigned int)QueryActiveSession(&v22) )
  {
    if ( (unsigned int)dword_140027000 > 5 )
    {
      v19 = "Attempt to find active user with UMgr";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v6,
        (__int64)&byte_1400222FF,
        v7,
        v8,
        (const unsigned __int16 **)&v19);
    }
    UserToken = UMgrEnumerateSessionUsers(&v21, &v24);
    if ( UserToken >= 0 && v21 && v24 )
    {
      v14 = 0;
      while ( 1 )
      {
        if ( (unsigned int)dword_140027000 > 5 )
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
          tlgWriteTransfer_EventWriteTransfer(
            (__int64)&dword_140027000,
            (unsigned __int8 *)byte_14002231D,
            0,
            0,
            6u,
            v25);
        }
        v3 = 2LL * v14;
        if ( *(_DWORD *)(v24 + 16LL * v14 + 8) == v22 )
          break;
        if ( ++v14 >= v21 )
          goto LABEL_23;
      }
      v17 = *(_QWORD *)(v24 + 16LL * v14);
      if ( (unsigned int)dword_140027000 > 5 )
      {
        LODWORD(v19) = UserToken;
        v20 = "Found user context for active session.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v3,
          (__int64)&byte_14002219F,
          v4,
          v5,
          (const unsigned __int16 **)&v20,
          (__int64)&v19);
      }
      if ( !v17 )
      {
LABEL_23:
        if ( (unsigned int)dword_140027000 <= 5 )
          goto LABEL_44;
        LODWORD(v19) = UserToken;
        v15 = "Failed to find the session context for the active session";
        v16 = &word_14002252E;
        goto LABEL_43;
      }
      UserToken = UMgrQueryUserToken(v17, a1);
      if ( UserToken >= 0 )
      {
        if ( (unsigned int)dword_140027000 > 5 )
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
          tlgWriteTransfer_EventWriteTransfer(
            (__int64)&dword_140027000,
            (unsigned __int8 *)&byte_14002222F,
            0,
            0,
            6u,
            v25);
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
        if ( (unsigned int)dword_140027000 > 5 )
        {
          LODWORD(v19) = UserToken;
          v15 = "ImpersonateLoggedOnUser failed";
          v16 = (__int16 *)&dword_1400224BC;
          goto LABEL_43;
        }
        goto LABEL_44;
      }
      if ( (unsigned int)dword_140027000 <= 5 )
        goto LABEL_44;
      LODWORD(v19) = UserToken;
      v15 = "UMgrQueryUserToken failed.";
      v16 = word_14002244A;
    }
    else
    {
      if ( (unsigned int)dword_140027000 <= 5 )
        goto LABEL_44;
      LODWORD(v19) = UserToken;
      v15 = "User context token is invalid.";
      v16 = (__int16 *)qword_140022270;
    }
LABEL_43:
    v20 = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v3,
      (__int64)v16,
      v4,
      v5,
      (const unsigned __int16 **)&v20,
      (__int64)&v19);
    goto LABEL_44;
  }
  v9 = GetLastError();
  UserToken = v9;
  if ( v9 > 0 )
    UserToken = (unsigned __int16)v9 | 0x80070000;
  if ( (unsigned int)dword_140027000 > 5 )
  {
    LODWORD(v23) = UserToken;
    v19 = "QueryActiveSession failed.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v10,
      (__int64)qword_1400223D8,
      v11,
      v12,
      (const unsigned __int16 **)&v19,
      (__int64)&v23);
  }
LABEL_44:
  if ( (unsigned __int64)*a1 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(*a1);
    *a1 = (int *)-1LL;
  }
LABEL_46:
  if ( v24 )
    UMgrFreeSessionUsers();
  return (unsigned int)UserToken;
}

```

## disassembly

```asm
0x14001150c  mov     [rsp-8+arg_8], rbx
0x140011511  mov     [rsp-8+arg_10], rsi
0x140011516  push    rbp
0x140011517  push    r14
0x140011519  push    r15
0x14001151b  lea     rbp, [rsp-47h]
0x140011520  sub     rsp, 0D0h
0x140011527  mov     rax, cs:__security_cookie
0x14001152e  xor     rax, rsp
0x140011531  mov     [rbp+57h+var_20], rax
0x140011535  xor     r15d, r15d
0x140011538  mov     rsi, rcx
0x14001153b  mov     [rbp+57h+var_9C], r15d
0x14001153f  mov     [rbp+57h+var_A0], r15d
0x140011543  mov     [rbp+57h+var_90], r15
0x140011547  test    rcx, rcx
0x14001154a  jnz     short loc_140011556
0x14001154c  mov     eax, 80070057h
0x140011551  jmp     loc_1400118FD
0x140011556  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x14001155d  call    IsUMgrEnumerateSessionUsersPresent
0x140011562  test    al, al
0x140011564  jz      loc_140011892
0x14001156a  call    IsUMgrEnumerateSessionUsersPresent
0x14001156f  test    al, al
0x140011571  jz      loc_140011892
0x140011577  call    IsQueryActiveSessionPresent
0x14001157c  test    al, al
0x14001157e  jz      loc_140011892
0x140011584  mov     eax, cs:dword_140027000
0x14001158a  cmp     eax, 5
0x14001158d  jbe     short loc_1400115AF
0x14001158f  lea     rax, aAttemptingToIm_0; "Attempting to impersonate with UMgr"
0x140011596  mov     [rbp+57h+var_B0], rax
0x14001159a  lea     rdx, byte_14002215B
0x1400115a1  lea     rax, [rbp+57h+var_B0]
0x1400115a5  mov     [rsp+0E0h+var_C0], rax
0x1400115aa  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1400115af  lea     rcx, [rbp+57h+var_9C]
0x1400115b3  call    cs:__imp_QueryActiveSession
0x1400115b9  test    eax, eax
0x1400115bb  jnz     short loc_140011608
0x1400115bd  call    cs:__imp_GetLastError
0x1400115c3  mov     ebx, eax
0x1400115c5  test    eax, eax
0x1400115c7  jle     short loc_1400115D2
0x1400115c9  movzx   ebx, ax
0x1400115cc  or      ebx, 80070000h
0x1400115d2  mov     eax, cs:dword_140027000
0x1400115d8  cmp     eax, 5
0x1400115db  jbe     loc_1400118D2
0x1400115e1  lea     rax, aQueryactiveses_0; "QueryActiveSession failed."
0x1400115e8  mov     dword ptr [rbp+57h+var_98], ebx
0x1400115eb  mov     [rbp+57h+var_B0], rax
0x1400115ef  lea     rdx, qword_1400223D8
0x1400115f6  lea     rax, [rbp+57h+var_98]
0x1400115fa  mov     [rsp+0E0h+var_B8], rax
0x1400115ff  lea     rax, [rbp+57h+var_B0]
0x140011603  jmp     loc_1400118C8
0x140011608  mov     eax, cs:dword_140027000
0x14001160e  cmp     eax, 5
0x140011611  jbe     short loc_140011633
0x140011613  lea     rax, aAttemptToFindA; "Attempt to find active user with UMgr"
0x14001161a  mov     [rbp+57h+var_B0], rax
0x14001161e  lea     rdx, byte_1400222FF
0x140011625  lea     rax, [rbp+57h+var_B0]
0x140011629  mov     [rsp+0E0h+var_C0], rax
0x14001162e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140011633  lea     rdx, [rbp+57h+var_90]
0x140011637  lea     rcx, [rbp+57h+var_A0]
0x14001163b  call    cs:__imp_UMgrEnumerateSessionUsers
0x140011641  mov     ebx, eax
0x140011643  test    eax, eax
0x140011645  js      loc_140011874
0x14001164b  mov     eax, [rbp+57h+var_A0]
0x14001164e  test    eax, eax
0x140011650  jz      loc_140011874
0x140011656  cmp     [rbp+57h+var_90], r15
0x14001165a  jz      loc_140011874
0x140011660  mov     r14d, r15d
0x140011663  test    eax, eax
0x140011665  jz      loc_14001170E
0x14001166b  mov     eax, cs:dword_140027000
0x140011671  cmp     eax, 5
0x140011674  jbe     short loc_1400116EE
0x140011676  lea     rax, [rbp+57h+var_98]
0x14001167a  mov     dword ptr [rbp+57h+var_98], ebx
0x14001167d  mov     [rbp+57h+var_30], rax
0x140011681  lea     rdx, byte_14002231D
0x140011688  lea     rax, [rbp+57h+var_A8]
0x14001168c  mov     dword ptr [rbp+57h+var_A8], r14d
0x140011690  mov     [rbp+57h+var_40], rax
0x140011694  lea     rcx, dword_140027000
0x14001169b  lea     rax, [rbp+57h+var_B0]
0x14001169f  mov     dword ptr [rbp+57h+var_B0], r14d
0x1400116a3  mov     [rbp+57h+var_50], rax
0x1400116a7  xor     r9d, r9d
0x1400116aa  lea     rax, aSessionInfo; "Session info."
0x1400116b1  mov     [rbp+57h+var_28], 4
0x1400116b9  mov     [rbp+57h+var_60], rax
0x1400116bd  xor     r8d, r8d
0x1400116c0  lea     rax, [rbp+57h+var_80]
0x1400116c4  mov     [rbp+57h+var_38], 4
0x1400116cc  mov     [rsp+0E0h+var_B8], rax
0x1400116d1  mov     dword ptr [rsp+0E0h+var_C0], 6
0x1400116d9  mov     [rbp+57h+var_48], 4
0x1400116e1  mov     [rbp+57h+var_58], 0Eh
0x1400116e9  call    _tlgWriteTransfer_EventWriteTransfer
0x1400116ee  mov     rdx, [rbp+57h+var_90]
0x1400116f2  mov     eax, [rbp+57h+var_9C]
0x1400116f5  mov     ecx, r14d
0x1400116f8  add     rcx, rcx
0x1400116fb  cmp     [rdx+rcx*8+8], eax
0x1400116ff  jz      short loc_140011733
0x140011701  inc     r14d
0x140011704  cmp     r14d, [rbp+57h+var_A0]
0x140011708  jb      loc_14001166B
0x14001170e  mov     eax, cs:dword_140027000
0x140011714  cmp     eax, 5
0x140011717  jbe     loc_1400118D2
0x14001171d  mov     dword ptr [rbp+57h+var_B0], ebx
0x140011720  lea     rax, aFailedToFindTh; "Failed to find the session context for "...
0x140011727  lea     rdx, word_14002252E
0x14001172e  jmp     loc_1400118B7
0x140011733  mov     eax, cs:dword_140027000
0x140011739  mov     r14, [rdx+rcx*8]
0x14001173d  cmp     eax, 5
0x140011740  jbe     short loc_14001176E
0x140011742  lea     rax, aFoundUserConte; "Found user context for active session."
0x140011749  mov     dword ptr [rbp+57h+var_B0], ebx
0x14001174c  mov     [rbp+57h+var_A8], rax
0x140011750  lea     rdx, byte_14002219F
0x140011757  lea     rax, [rbp+57h+var_B0]
0x14001175b  mov     [rsp+0E0h+var_B8], rax
0x140011760  lea     rax, [rbp+57h+var_A8]
0x140011764  mov     [rsp+0E0h+var_C0], rax
0x140011769  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001176e  test    r14, r14
0x140011771  jz      short loc_14001170E
0x140011773  mov     rdx, rsi
0x140011776  mov     rcx, r14
0x140011779  call    cs:__imp_UMgrQueryUserToken
0x14001177f  mov     ebx, eax
0x140011781  test    eax, eax
0x140011783  mov     eax, cs:dword_140027000
0x140011789  jns     short loc_1400117AA
0x14001178b  cmp     eax, 5
0x14001178e  jbe     loc_1400118D2
0x140011794  mov     dword ptr [rbp+57h+var_B0], ebx
0x140011797  lea     rax, aUmgrqueryusert_0; "UMgrQueryUserToken failed."
0x14001179e  lea     rdx, word_14002244A
0x1400117a5  jmp     loc_1400118B7
0x1400117aa  cmp     eax, 5
0x1400117ad  jbe     short loc_14001182A
0x1400117af  mov     rax, [rsi]
0x1400117b2  lea     rdx, byte_14002222F
0x1400117b9  mov     [rbp+57h+var_A8], rax
0x1400117bd  lea     rcx, dword_140027000
0x1400117c4  lea     rax, [rbp+57h+var_B0]
0x1400117c8  mov     dword ptr [rbp+57h+var_B0], ebx
0x1400117cb  mov     [rbp+57h+var_30], rax
0x1400117cf  xor     r9d, r9d
0x1400117d2  lea     rax, [rbp+57h+var_A8]
0x1400117d6  mov     [rbp+57h+var_98], r14
0x1400117da  mov     [rbp+57h+var_40], rax
0x1400117de  xor     r8d, r8d
0x1400117e1  lea     rax, [rbp+57h+var_98]
0x1400117e5  mov     [rbp+57h+var_28], 4
0x1400117ed  mov     [rbp+57h+var_50], rax
0x1400117f1  lea     rax, aGotUserToken; "Got user token."
0x1400117f8  mov     [rbp+57h+var_60], rax
0x1400117fc  lea     rax, [rbp+57h+var_80]
0x140011800  mov     [rsp+0E0h+var_B8], rax
0x140011805  mov     dword ptr [rsp+0E0h+var_C0], 6
0x14001180d  mov     [rbp+57h+var_38], 8
0x140011815  mov     [rbp+57h+var_48], 8
0x14001181d  mov     [rbp+57h+var_58], 10h
0x140011825  call    _tlgWriteTransfer_EventWriteTransfer
0x14001182a  mov     rcx, [rsi]; hToken
0x14001182d  call    cs:__imp_ImpersonateLoggedOnUser
0x140011833  test    eax, eax
0x140011835  jnz     short loc_14001186A
0x140011837  call    cs:__imp_GetLastError
0x14001183d  mov     ebx, eax
0x14001183f  test    eax, eax
0x140011841  jle     short loc_14001184C
0x140011843  movzx   ebx, ax
0x140011846  or      ebx, 80070000h
0x14001184c  mov     eax, cs:dword_140027000
0x140011852  cmp     eax, 5
0x140011855  jbe     short loc_1400118D2
0x140011857  mov     dword ptr [rbp+57h+var_B0], ebx
0x14001185a  lea     rax, aImpersonatelog; "ImpersonateLoggedOnUser failed"
0x140011861  lea     rdx, dword_1400224BC
0x140011868  jmp     short loc_1400118B7
0x14001186a  mov     rcx, [rsi]; TokenHandle
0x14001186d  call    ?DumpSIDString@@YAXPEAX@Z; DumpSIDString(void *)
0x140011872  jmp     short loc_1400118EC
0x140011874  mov     eax, cs:dword_140027000
0x14001187a  cmp     eax, 5
0x14001187d  jbe     short loc_1400118D2
0x14001187f  mov     dword ptr [rbp+57h+var_B0], ebx
0x140011882  lea     rax, aUserContextTok; "User context token is invalid."
0x140011889  lea     rdx, qword_140022270
0x140011890  jmp     short loc_1400118B7
0x140011892  mov     eax, cs:dword_140027000
0x140011898  mov     ebx, 80070032h
0x14001189d  cmp     eax, 5
0x1400118a0  jbe     short loc_1400118D2
0x1400118a2  mov     dword ptr [rbp+57h+var_B0], 80070032h
0x1400118a9  lea     rax, aUmgrNotAvailab; "UMgr not available"
0x1400118b0  lea     rdx, byte_140022209
0x1400118b7  mov     [rbp+57h+var_A8], rax
0x1400118bb  lea     rax, [rbp+57h+var_B0]
0x1400118bf  mov     [rsp+0E0h+var_B8], rax
0x1400118c4  lea     rax, [rbp+57h+var_A8]
0x1400118c8  mov     [rsp+0E0h+var_C0], rax
0x1400118cd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400118d2  mov     rcx, [rsi]; hObject
0x1400118d5  lea     rax, [rcx-1]
0x1400118d9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400118dd  ja      short loc_1400118EC
0x1400118df  call    cs:__imp_CloseHandle
0x1400118e5  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1400118ec  mov     rcx, [rbp+57h+var_90]
0x1400118f0  test    rcx, rcx
0x1400118f3  jz      short loc_1400118FB
0x1400118f5  call    cs:__imp_UMgrFreeSessionUsers
0x1400118fb  mov     eax, ebx
0x1400118fd  mov     rcx, [rbp+57h+var_20]
0x140011901  xor     rcx, rsp; StackCookie
0x140011904  call    __security_check_cookie
0x140011909  lea     r11, [rsp+0E0h+var_10]
0x140011911  mov     rbx, [r11+28h]
0x140011915  mov     rsi, [r11+30h]
0x140011919  mov     rsp, r11
0x14001191c  pop     r15
0x14001191e  pop     r14
0x140011920  pop     rbp
0x140011921  retn
```
