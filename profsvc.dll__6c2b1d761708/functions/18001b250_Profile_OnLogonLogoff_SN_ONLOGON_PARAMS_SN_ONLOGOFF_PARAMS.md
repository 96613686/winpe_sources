# Profile_OnLogonLogoff(_SN_ONLOGON_PARAMS *,_SN_ONLOGOFF_PARAMS *)

- ea: `0x18001b250`
- end: `0x18001b8a8`
- name: `?Profile_OnLogonLogoff@@YAJPEAU_SN_ONLOGON_PARAMS@@PEAU_SN_ONLOGOFF_PARAMS@@@Z`
- size: `1624`
- prototype: `__int64 __fastcall(struct _SN_ONLOGON_PARAMS *, struct _SN_ONLOGOFF_PARAMS *)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18001a830`
- `0x18001a9f0`

## callees

- `0x1800061c8`
- `0x18001a858`
- `0x18001aa1c`
- `0x18001b250`
- `0x18001b8b0`
- `0x18001c358`
- `0x18001c5b0`
- `0x18001c66c`
- `0x18001c72c`
- `0x18001c85c`
- `0x18001c8b4`
- `0x18001cc58`
- `0x18001cd6c`
- `0x180024540`
- `0x180024b84`
- `0x18002df48`
- `0x180030ad0`
- `0x180031060`
- `0x180031190`
- `0x180040bcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b594`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b64c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b594`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b64c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b6f3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b6f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b633`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b6e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b633`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b6e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4cb`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001b3ef`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001b4b6`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001b3ef`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001b4b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b871`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b871`
- `RPCRT4!RpcImpersonateClient` at `0x18001b2d3`
- `RPCRT4!RpcImpersonateClient` at `0x18001b2d3`

## pseudocode

```c
__int64 __fastcall Profile_OnLogonLogoff(struct _SN_ONLOGON_PARAMS *a1, struct _SN_ONLOGOFF_PARAMS *a2)
{
  unsigned int *v3; // rdx
  unsigned int v4; // edx
  CUserProfileManager *v5; // rcx
  __int64 v6; // rcx
  __int64 *v7; // rdx
  CUserProfileManager *v8; // rcx
  CUserProfileManager *v9; // rcx
  int SessionEntry; // edi
  __int64 v11; // rdx
  int v12; // eax
  LPCRITICAL_SECTION v13; // rsi
  struct WorkItemInfo *v14; // r14
  _QWORD *v15; // rdx
  signed int LastError; // eax
  int v17; // eax
  LPCRITICAL_SECTION v18; // rsi
  CUserProfileManager *v19; // rcx
  struct WorkItemInfo *v20; // r14
  _QWORD *v21; // rdx
  signed int v22; // eax
  void *UserToken; // rax
  unsigned int v24; // r9d
  int v25; // eax
  int v26; // eax
  __int64 v27; // rdx
  PSRWLOCK v28; // rsi
  unsigned int v29; // edi
  PVOID Ptr; // rdx
  _QWORD *v31; // rcx
  __int64 v32; // rax
  void *v33; // r14
  PSRWLOCK v34; // rsi
  unsigned int v35; // edi
  PVOID v36; // rdx
  _QWORD *v37; // rcx
  __int64 v38; // rax
  void *v39; // rdi
  const char *v40; // r9
  unsigned int v41; // ebx
  int v43; // eax
  CUserProfileManager *v44; // rcx
  CUserProfileManager *v45; // rcx
  int v46; // eax
  int MessageW; // eax
  PVOID v48; // rbx
  unsigned __int64 v49; // rdx
  unsigned __int16 *v50; // rcx
  int v51; // eax
  _QWORD v52[2]; // [rsp+20h] [rbp-29h] BYREF
  char v53; // [rsp+30h] [rbp-19h]
  int v54; // [rsp+38h] [rbp-11h] BYREF
  __int64 v55; // [rsp+40h] [rbp-9h]
  __int64 v56; // [rsp+48h] [rbp-1h]
  int v57; // [rsp+50h] [rbp+7h]
  __int128 v58; // [rsp+58h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  void *v60; // [rsp+B0h] [rbp+67h] BYREF
  unsigned int v61; // [rsp+C0h] [rbp+77h] BYREF
  PVOID pv; // [rsp+C8h] [rbp+7Fh] BYREF

  v60 = a1;
  if ( a1 )
    v3 = (unsigned int *)((char *)a1 + 8);
  else
    v3 = (unsigned int *)((char *)a2 + 8);
  v4 = *v3;
  v52[0] = &v61;
  v52[1] = &v60;
  v61 = v4;
  v53 = 1;
  if ( !(unsigned int)CUserProfileManager::DoesSessionExist(a1, v4) )
  {
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    if ( !RpcImpersonateClient(0) )
    {
      HIDWORD(v56) = 1;
      if ( v60 )
      {
        if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) == 0 )
          goto LABEL_14;
        v7 = EVENT_USER_LOGON_START;
      }
      else
      {
        if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) == 0 )
          goto LABEL_14;
        v7 = EVENT_USER_LOGOFF_START;
      }
      McTemplateU0q_EtwEventWriteTransfer(v6, v7, v61);
    }
LABEL_14:
    CThreadContext::~CThreadContext((CThreadContext *)&v54);
    SessionEntry = CUserProfileManager::CreateSessionEntry(v8, v61);
    if ( SessionEntry < 0 )
    {
      v11 = 305;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
        (const char *)(unsigned int)SessionEntry,
        v52[0]);
      v53 = 0;
      lambda_5ea0ea092935807d452b9f4138fd86e2_::operator()(v52);
      return (unsigned int)SessionEntry;
    }
    if ( v60 )
    {
      v12 = CUserProfileManager::SetParams(v9, v61, v60);
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x135,
          (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
          (const char *)(unsigned int)v12,
          v52[0]);
      v13 = g_pUPSvc;
      if ( g_pUPSvc )
      {
        pv = 0;
        SessionEntry = _CreateWorkItemInfo((struct WorkItemInfo **)&pv);
        if ( SessionEntry >= 0 )
        {
          v14 = (struct WorkItemInfo *)pv;
          v15 = pv;
          *((_DWORD *)pv + 6) = 16;
          *v15 = LogonThreadProc;
          v15[1] = &v61;
          v15[2] = 0;
          if ( TrySubmitThreadpoolCallback(_WorkItemWrapper, v15, (PTP_CALLBACK_ENVIRON)&v13[1].LockSemaphore) )
          {
            v14 = 0;
          }
          else
          {
            LastError = GetLastError();
            SessionEntry = LastError;
            if ( LastError > 0 )
              SessionEntry = (unsigned __int16)LastError | 0x80070000;
          }
          _DestroyWorkItemInfo(v14);
        }
        if ( SessionEntry >= 0 )
          goto LABEL_51;
      }
      else
      {
        SessionEntry = -2147467259;
      }
      v11 = 310;
      goto LABEL_16;
    }
    v17 = CUserProfileManager::SetParams(v9, v61, a2);
    if ( v17 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x13A,
        (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
        (const char *)(unsigned int)v17,
        v52[0]);
    v18 = g_pUPSvc;
    if ( g_pUPSvc )
    {
      pv = 0;
      SessionEntry = _CreateWorkItemInfo((struct WorkItemInfo **)&pv);
      if ( SessionEntry >= 0 )
      {
        v20 = (struct WorkItemInfo *)pv;
        v21 = pv;
        *((_DWORD *)pv + 6) = 16;
        *v21 = LogoffThreadProc;
        v21[1] = &v61;
        v21[2] = 0;
        if ( TrySubmitThreadpoolCallback(_WorkItemWrapper, v21, (PTP_CALLBACK_ENVIRON)&v18[1].LockSemaphore) )
        {
          v20 = 0;
        }
        else
        {
          v22 = GetLastError();
          SessionEntry = v22;
          if ( v22 > 0 )
            SessionEntry = (unsigned __int16)v22 | 0x80070000;
        }
        _DestroyWorkItemInfo(v20);
      }
      if ( SessionEntry >= 0 )
      {
        UserToken = CUserProfileManager::GetUserToken(v19, v61);
        v25 = UserProfileServiceAddWorkItem((unsigned int (*)(void *))CheckForUserObjectUpdates, 0, UserToken, v24);
        if ( v25 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x13F,
            (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
            (const char *)(unsigned int)v25,
            v52[0]);
        goto LABEL_51;
      }
    }
    else
    {
      SessionEntry = -2147467259;
    }
    v11 = 315;
    goto LABEL_16;
  }
  if ( v60 )
  {
    v26 = CUserProfileManager::SetParams(v5, v61, v60);
    if ( v26 >= 0 )
      goto LABEL_51;
    v27 = 330;
  }
  else
  {
    v26 = CUserProfileManager::SetParams(v5, v61, a2);
    if ( v26 >= 0 )
      goto LABEL_51;
    v27 = 334;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v27,
    (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
    (const char *)(unsigned int)v26,
    v52[0]);
LABEL_51:
  v28 = g_pProfMgr;
  v29 = v61;
  AcquireSRWLockShared(g_pProfMgr);
  _mm_lfence();
  Ptr = v28[7].Ptr;
  v31 = (char *)v28[9].Ptr
      + 16
      * ((unsigned __int64)v28[12].Ptr
       & (0x100000001B3LL
        * (HIBYTE(v29)
         ^ (0x100000001B3LL
          * (BYTE2(v29)
           ^ (0x100000001B3LL * ((0x100000001B3LL * ((unsigned __int8)v29 ^ 0xCBF29CE484222325uLL)) ^ BYTE1(v29))))))));
  v32 = v31[1];
  if ( (PVOID)v32 == Ptr )
  {
LABEL_55:
    v32 = 0;
  }
  else
  {
    while ( v29 != *(_DWORD *)(v32 + 16) )
    {
      if ( v32 == *v31 )
        goto LABEL_55;
      v32 = *(_QWORD *)(v32 + 8);
    }
  }
  if ( !v32 || (PVOID)v32 == Ptr )
    v33 = 0;
  else
    v33 = *(void **)(v32 + 32);
  ReleaseSRWLockShared(v28);
  v34 = g_pProfMgr;
  v35 = v61;
  AcquireSRWLockShared(g_pProfMgr);
  _mm_lfence();
  v36 = v34[7].Ptr;
  v37 = (char *)v34[9].Ptr
      + 16
      * ((unsigned __int64)v34[12].Ptr
       & (0x100000001B3LL
        * (HIBYTE(v35)
         ^ (0x100000001B3LL
          * (BYTE2(v35)
           ^ (0x100000001B3LL * ((0x100000001B3LL * ((unsigned __int8)v35 ^ 0xCBF29CE484222325uLL)) ^ BYTE1(v35))))))));
  v38 = v37[1];
  if ( (PVOID)v38 == v36 )
  {
LABEL_64:
    v38 = 0;
  }
  else
  {
    while ( v35 != *(_DWORD *)(v38 + 16) )
    {
      if ( v38 == *v37 )
        goto LABEL_64;
      v38 = *(_QWORD *)(v38 + 8);
    }
  }
  if ( !v38 || (PVOID)v38 == v36 )
    v39 = 0;
  else
    v39 = *(void **)(v38 + 40);
  ReleaseSRWLockShared(v34);
  if ( !SetEvent(v33) )
  {
    v53 = 0;
    v41 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x159,
            (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
            v40);
    lambda_5ea0ea092935807d452b9f4138fd86e2_::operator()(v52);
    return v41;
  }
  v43 = WaitForEventInternal(v39);
  SessionEntry = v43;
  if ( v43 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15C,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)(unsigned int)v43,
      v52[0]);
    v53 = 0;
    lambda_5ea0ea092935807d452b9f4138fd86e2_::operator()(v52);
    return (unsigned int)SessionEntry;
  }
  if ( !CUserProfileManager::GetSessionDone(v44, v61) )
  {
    pv = 0;
    MessageW = CUserProfileManager::GetMessageW(v45, v61, (unsigned __int16 **)&pv);
    if ( MessageW < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x168,
        (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
        (const char *)(unsigned int)MessageW,
        v52[0]);
    v48 = pv;
    if ( pv )
    {
      if ( v60 )
      {
        v49 = *((unsigned int *)v60 + 6);
        v50 = (unsigned __int16 *)*((_QWORD *)v60 + 2);
      }
      else
      {
        v49 = *((unsigned int *)a2 + 8);
        v50 = (unsigned __int16 *)*((_QWORD *)a2 + 3);
      }
      v51 = StringCchCopyW(v50, v49, (const unsigned __int16 *)pv);
      if ( v51 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x16D,
          (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
          (const char *)(unsigned int)v51,
          v52[0]);
    }
    SessionEntry = wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)0x174,
                     (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
                     (const char *)0x3E5,
                     v52[0]);
    if ( v48 )
      CoTaskMemFree(v48);
    return (unsigned int)SessionEntry;
  }
  v46 = CUserProfileManager::GetResult(v45, v61);
  if ( v46 >= 0 )
  {
    v53 = 0;
    lambda_5ea0ea092935807d452b9f4138fd86e2_::operator()(v52);
    return 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)(unsigned int)v46,
      v52[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)0x800701F4LL,
      v52[0]);
    v53 = 0;
    lambda_5ea0ea092935807d452b9f4138fd86e2_::operator()(v52);
    return 2147942900LL;
  }
}

```

## disassembly

```asm
0x18001b250  mov     [rsp-8+arg_0], rcx
0x18001b255  push    rbp
0x18001b256  push    r15
0x18001b258  lea     rbp, [rsp-4Fh]
0x18001b25d  sub     rsp, 98h
0x18001b264  mov     r15, rdx
0x18001b267  test    rcx, rcx
0x18001b26a  jz      short loc_18001B272
0x18001b26c  lea     rdx, [rcx+8]
0x18001b270  jmp     short loc_18001B276
0x18001b272  add     rdx, 8
0x18001b276  mov     [rsp+0A0h+arg_8], rbx
0x18001b27e  lea     rax, [rbp+57h+arg_10]
0x18001b282  mov     [rsp+0A0h+var_10], rsi
0x18001b28a  mov     [rsp+0A0h+var_18], rdi
0x18001b292  mov     [rsp+0A0h+var_30], r14
0x18001b297  mov     edx, [rdx]; unsigned int
0x18001b299  mov     [rbp+57h+var_80], rax
0x18001b29d  lea     rax, [rbp+57h+arg_0]
0x18001b2a1  mov     [rbp+57h+var_78], rax
0x18001b2a5  mov     [rbp+57h+arg_10], edx
0x18001b2a8  mov     [rbp+57h+var_70], 1
0x18001b2ac  call    ?DoesSessionExist@CUserProfileManager@@QEAAHK@Z; CUserProfileManager::DoesSessionExist(ulong)
0x18001b2b1  test    eax, eax
0x18001b2b3  jnz     loc_18001B538
0x18001b2b9  xor     ebx, ebx
0x18001b2bb  xorps   xmm0, xmm0
0x18001b2be  xor     ecx, ecx; BindingHandle
0x18001b2c0  mov     [rbp+57h+var_68], ebx
0x18001b2c3  mov     [rbp+57h+var_60], rbx
0x18001b2c7  mov     [rbp+57h+var_58], rbx
0x18001b2cb  mov     [rbp+57h+var_50], ebx
0x18001b2ce  movdqu  [rbp+57h+var_48], xmm0
0x18001b2d3  call    cs:__imp_RpcImpersonateClient
0x18001b2da  nop     dword ptr [rax+rax+00h]
0x18001b2df  test    eax, eax
0x18001b2e1  jnz     short loc_18001B2EC
0x18001b2e3  mov     dword ptr [rbp+57h+var_58+4], 1
0x18001b2ea  jmp     short loc_18001B2FA
0x18001b2ec  jle     short loc_18001B2F6
0x18001b2ee  movzx   eax, ax
0x18001b2f1  or      eax, 80070000h
0x18001b2f6  test    eax, eax
0x18001b2f8  js      short loc_18001B32B
0x18001b2fa  cmp     [rbp+57h+arg_0], rbx
0x18001b2fe  jz      short loc_18001B312
0x18001b300  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x18001b307  jz      short loc_18001B32B
0x18001b309  lea     rdx, EVENT_USER_LOGON_START
0x18001b310  jmp     short loc_18001B322
0x18001b312  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x18001b319  jz      short loc_18001B32B
0x18001b31b  lea     rdx, EVENT_USER_LOGOFF_START
0x18001b322  mov     r8d, [rbp+57h+arg_10]
0x18001b326  call    McTemplateU0q_EtwEventWriteTransfer
0x18001b32b  lea     rcx, [rbp+57h+var_68]; this
0x18001b32f  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001b334  mov     edx, [rbp+57h+arg_10]; unsigned int
0x18001b337  call    ?CreateSessionEntry@CUserProfileManager@@QEAAJK@Z; CUserProfileManager::CreateSessionEntry(ulong)
0x18001b33c  mov     edi, eax
0x18001b33e  test    eax, eax
0x18001b340  jns     short loc_18001B36B
0x18001b342  mov     edx, 131h; void *
0x18001b347  mov     rcx, [rbp+5Fh]; this
0x18001b34b  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x18001b352  mov     r9d, edi; char *
0x18001b355  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b35a  lea     rcx, [rbp+57h+var_80]
0x18001b35e  mov     [rbp+57h+var_70], bl
0x18001b361  call    _lambda_5ea0ea092935807d452b9f4138fd86e2___operator__
0x18001b366  jmp     loc_18001B87D
0x18001b36b  mov     r8, [rbp+57h+arg_0]; void *
0x18001b36f  mov     edx, [rbp+57h+arg_10]; unsigned int
0x18001b372  test    r8, r8
0x18001b375  jz      loc_18001B43F
0x18001b37b  call    ?SetParams@CUserProfileManager@@QEAAJKPEAX@Z; CUserProfileManager::SetParams(ulong,void *)
0x18001b380  test    eax, eax
0x18001b382  jns     short loc_18001B39C
0x18001b384  mov     rcx, [rbp+5Fh]; this
0x18001b388  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x18001b38f  mov     r9d, eax; char *
0x18001b392  mov     edx, 135h; void *
0x18001b397  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b39c  mov     rsi, cs:?g_pUPSvc@@3PEAVCUserProfileService@@EA; CUserProfileService * g_pUPSvc
0x18001b3a3  test    rsi, rsi
0x18001b3a6  jz      loc_18001B430
0x18001b3ac  lea     rcx, [rbp+57h+pv]; struct WorkItemInfo **
0x18001b3b0  mov     [rbp+57h+pv], rbx
0x18001b3b4  call    ?_CreateWorkItemInfo@@YAJPEAPEAUWorkItemInfo@@@Z; _CreateWorkItemInfo(WorkItemInfo * *)
0x18001b3b9  mov     edi, eax
0x18001b3bb  test    eax, eax
0x18001b3bd  js      short loc_18001B427
0x18001b3bf  mov     r14, [rbp+57h+pv]
0x18001b3c3  lea     rax, ?LogonThreadProc@@YAKPEAX@Z; LogonThreadProc(void *)
0x18001b3ca  lea     r8, [rsi+40h]; pcbe
0x18001b3ce  mov     rdx, r14; pv
0x18001b3d1  lea     rcx, ?_WorkItemWrapper@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18001b3d8  mov     dword ptr [r14+18h], 10h
0x18001b3e0  mov     [r14], rax
0x18001b3e3  lea     rax, [rbp+57h+arg_10]
0x18001b3e7  mov     [r14+8], rax
0x18001b3eb  mov     [r14+10h], rbx
0x18001b3ef  call    cs:__imp_TrySubmitThreadpoolCallback
0x18001b3f6  nop     dword ptr [rax+rax+00h]
0x18001b3fb  test    eax, eax
0x18001b3fd  jz      short loc_18001B404
0x18001b3ff  mov     r14, rbx
0x18001b402  jmp     short loc_18001B41F
0x18001b404  call    cs:__imp_GetLastError
0x18001b40b  nop     dword ptr [rax+rax+00h]
0x18001b410  mov     edi, eax
0x18001b412  test    eax, eax
0x18001b414  jle     short loc_18001B41F
0x18001b416  movzx   edi, ax
0x18001b419  or      edi, 80070000h
0x18001b41f  mov     rcx, r14; lpMem
0x18001b422  call    ?_DestroyWorkItemInfo@@YAXPEAUWorkItemInfo@@@Z; _DestroyWorkItemInfo(WorkItemInfo *)
0x18001b427  test    edi, edi
0x18001b429  js      short loc_18001B435
0x18001b42b  jmp     loc_18001B57A
0x18001b430  mov     edi, 80004005h
0x18001b435  mov     edx, 136h
0x18001b43a  jmp     loc_18001B347
0x18001b43f  mov     r8, r15; void *
0x18001b442  call    ?SetParams@CUserProfileManager@@QEAAJKPEAX@Z; CUserProfileManager::SetParams(ulong,void *)
0x18001b447  test    eax, eax
0x18001b449  jns     short loc_18001B463
0x18001b44b  mov     rcx, [rbp+5Fh]; this
0x18001b44f  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x18001b456  mov     r9d, eax; char *
0x18001b459  mov     edx, 13Ah; void *
0x18001b45e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b463  mov     rsi, cs:?g_pUPSvc@@3PEAVCUserProfileService@@EA; CUserProfileService * g_pUPSvc
0x18001b46a  test    rsi, rsi
0x18001b46d  jz      loc_18001B529
0x18001b473  lea     rcx, [rbp+57h+pv]; struct WorkItemInfo **
0x18001b477  mov     [rbp+57h+pv], rbx
0x18001b47b  call    ?_CreateWorkItemInfo@@YAJPEAPEAUWorkItemInfo@@@Z; _CreateWorkItemInfo(WorkItemInfo * *)
0x18001b480  mov     edi, eax
0x18001b482  test    eax, eax
0x18001b484  js      short loc_18001B4EE
0x18001b486  mov     r14, [rbp+57h+pv]
0x18001b48a  lea     rax, ?LogoffThreadProc@@YAKPEAX@Z; LogoffThreadProc(void *)
0x18001b491  lea     r8, [rsi+40h]; pcbe
0x18001b495  mov     rdx, r14; pv
0x18001b498  lea     rcx, ?_WorkItemWrapper@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18001b49f  mov     dword ptr [r14+18h], 10h
0x18001b4a7  mov     [r14], rax
0x18001b4aa  lea     rax, [rbp+57h+arg_10]
0x18001b4ae  mov     [r14+8], rax
0x18001b4b2  mov     [r14+10h], rbx
0x18001b4b6  call    cs:__imp_TrySubmitThreadpoolCallback
0x18001b4bd  nop     dword ptr [rax+rax+00h]
0x18001b4c2  test    eax, eax
0x18001b4c4  jz      short loc_18001B4CB
0x18001b4c6  mov     r14, rbx
0x18001b4c9  jmp     short loc_18001B4E6
0x18001b4cb  call    cs:__imp_GetLastError
0x18001b4d2  nop     dword ptr [rax+rax+00h]
0x18001b4d7  mov     edi, eax
0x18001b4d9  test    eax, eax
0x18001b4db  jle     short loc_18001B4E6
0x18001b4dd  movzx   edi, ax
0x18001b4e0  or      edi, 80070000h
0x18001b4e6  mov     rcx, r14; lpMem
0x18001b4e9  call    ?_DestroyWorkItemInfo@@YAXPEAUWorkItemInfo@@@Z; _DestroyWorkItemInfo(WorkItemInfo *)
0x18001b4ee  test    edi, edi
0x18001b4f0  js      short loc_18001B52E
0x18001b4f2  mov     edx, [rbp+57h+arg_10]; unsigned int
0x18001b4f5  call    ?GetUserToken@CUserProfileManager@@QEAAPEAXK@Z; CUserProfileManager::GetUserToken(ulong)
0x18001b4fa  mov     r8, rax; void *
0x18001b4fd  lea     rcx, ?CheckForUserObjectUpdates@@YAKPEAX@Z; unsigned int (*)(void *)
0x18001b504  xor     edx, edx; void *
0x18001b506  call    ?UserProfileServiceAddWorkItem@@YAJP6AKPEAX@Z00K@Z; UserProfileServiceAddWorkItem(ulong (*)(void *),void *,void *,ulong)
0x18001b50b  test    eax, eax
0x18001b50d  jns     short loc_18001B57A
0x18001b50f  mov     rcx, [rbp+5Fh]; this
0x18001b513  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x18001b51a  mov     r9d, eax; char *
0x18001b51d  mov     edx, 13Fh; void *
0x18001b522  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b527  jmp     short loc_18001B57A
0x18001b529  mov     edi, 80004005h
0x18001b52e  mov     edx, 13Bh
0x18001b533  jmp     loc_18001B347
0x18001b538  mov     r8, [rbp+57h+arg_0]; void *
0x18001b53c  mov     edx, [rbp+57h+arg_10]; unsigned int
0x18001b53f  test    r8, r8
0x18001b542  jz      short loc_18001B554
0x18001b544  call    ?SetParams@CUserProfileManager@@QEAAJKPEAX@Z; CUserProfileManager::SetParams(ulong,void *)
0x18001b549  test    eax, eax
0x18001b54b  jns     short loc_18001B578
0x18001b54d  mov     edx, 14Ah
0x18001b552  jmp     short loc_18001B565
0x18001b554  mov     r8, r15; void *
0x18001b557  call    ?SetParams@CUserProfileManager@@QEAAJKPEAX@Z; CUserProfileManager::SetParams(ulong,void *)
0x18001b55c  test    eax, eax
0x18001b55e  jns     short loc_18001B578
0x18001b560  mov     edx, 14Eh; void *
0x18001b565  mov     rcx, [rbp+5Fh]; this
0x18001b569  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x18001b570  mov     r9d, eax; char *
0x18001b573  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b578  xor     ebx, ebx
0x18001b57a  mov     rsi, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; CUserProfileManager * g_pProfMgr
0x18001b581  mov     edi, [rbp+57h+arg_10]
0x18001b584  mov     rcx, rsi; SRWLock
0x18001b587  mov     [rsp+0A0h+var_20], r12
0x18001b58f  mov     [rsp+0A0h+var_28], r13
0x18001b594  call    cs:__imp_AcquireSRWLockShared
0x18001b59b  nop     dword ptr [rax+rax+00h]
0x18001b5a0  mov     eax, edi
0x18001b5a2  movzx   r9d, dil
0x18001b5a6  shr     eax, 10h
0x18001b5a9  mov     r8d, edi
0x18001b5ac  movzx   edx, al
0x18001b5af  mov     eax, edi
0x18001b5b1  shr     r8d, 18h
0x18001b5b5  shr     eax, 8
0x18001b5b8  movzx   ecx, al
0x18001b5bb  lfence
0x18001b5be  mov     r12, 100000001B3h
0x18001b5c8  mov     r13, 0CBF29CE484222325h
0x18001b5d2  xor     r9, r13
0x18001b5d5  imul    r9, r12
0x18001b5d9  xor     rcx, r9
0x18001b5dc  imul    rcx, r12
0x18001b5e0  xor     rcx, rdx
0x18001b5e3  mov     rdx, [rsi+38h]
0x18001b5e7  imul    rcx, r12
0x18001b5eb  xor     rcx, r8
0x18001b5ee  imul    rcx, r12
0x18001b5f2  and     rcx, [rsi+60h]
0x18001b5f6  shl     rcx, 4
0x18001b5fa  add     rcx, [rsi+48h]
0x18001b5fe  mov     rax, [rcx+8]
0x18001b602  cmp     rax, rdx
0x18001b605  jz      short loc_18001B61A
0x18001b607  mov     r8, [rcx]
0x18001b60a  cmp     edi, [rax+10h]
0x18001b60d  jz      short loc_18001B61D
0x18001b60f  cmp     rax, r8
0x18001b612  jz      short loc_18001B61A
0x18001b614  mov     rax, [rax+8]
0x18001b618  jmp     short loc_18001B60A
0x18001b61a  mov     rax, rbx
0x18001b61d  test    rax, rax
0x18001b620  jz      short loc_18001B62D
0x18001b622  cmp     rax, rdx
0x18001b625  jz      short loc_18001B62D
0x18001b627  mov     r14, [rax+20h]
0x18001b62b  jmp     short loc_18001B630
0x18001b62d  mov     r14, rbx
0x18001b630  mov     rcx, rsi; SRWLock
0x18001b633  call    cs:__imp_ReleaseSRWLockShared
0x18001b63a  nop     dword ptr [rax+rax+00h]
0x18001b63f  mov     rsi, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; CUserProfileManager * g_pProfMgr
0x18001b646  mov     edi, [rbp+57h+arg_10]
0x18001b649  mov     rcx, rsi; SRWLock
0x18001b64c  call    cs:__imp_AcquireSRWLockShared
0x18001b653  nop     dword ptr [rax+rax+00h]
0x18001b658  mov     eax, edi
0x18001b65a  movzx   r9d, dil
0x18001b65e  shr     eax, 10h
0x18001b661  mov     r8d, edi
0x18001b664  movzx   edx, al
0x18001b667  mov     eax, edi
0x18001b669  shr     r8d, 18h
0x18001b66d  shr     eax, 8
0x18001b670  movzx   ecx, al
0x18001b673  lfence
0x18001b676  xor     r9, r13
0x18001b679  mov     r13, [rsp+0A0h+var_28]
0x18001b67e  imul    r9, r12
0x18001b682  xor     rcx, r9
0x18001b685  imul    rcx, r12
0x18001b689  xor     rcx, rdx
0x18001b68c  mov     rdx, [rsi+38h]
0x18001b690  imul    rcx, r12
0x18001b694  xor     rcx, r8
0x18001b697  imul    rcx, r12
0x18001b69b  mov     r12, [rsp+0A0h+var_20]
0x18001b6a3  and     rcx, [rsi+60h]
0x18001b6a7  shl     rcx, 4
0x18001b6ab  add     rcx, [rsi+48h]
0x18001b6af  mov     rax, [rcx+8]
0x18001b6b3  cmp     rax, rdx
0x18001b6b6  jz      short loc_18001B6CB
0x18001b6b8  mov     r8, [rcx]
0x18001b6bb  cmp     edi, [rax+10h]
0x18001b6be  jz      short loc_18001B6CE
0x18001b6c0  cmp     rax, r8
0x18001b6c3  jz      short loc_18001B6CB
0x18001b6c5  mov     rax, [rax+8]
0x18001b6c9  jmp     short loc_18001B6BB
0x18001b6cb  mov     rax, rbx
0x18001b6ce  test    rax, rax
0x18001b6d1  jz      short loc_18001B6DE
0x18001b6d3  cmp     rax, rdx
0x18001b6d6  jz      short loc_18001B6DE
  ... truncated ...
```
