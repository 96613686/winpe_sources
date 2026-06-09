# Profile_OnLogonLogoff(_SN_ONLOGON_PARAMS *,_SN_ONLOGOFF_PARAMS *)

- ea: `0x180018370`
- end: `0x1800189b9`
- name: `?Profile_OnLogonLogoff@@YAJPEAU_SN_ONLOGON_PARAMS@@PEAU_SN_ONLOGOFF_PARAMS@@@Z`
- size: `1609`
- prototype: `__int64 __fastcall(struct _SN_ONLOGON_PARAMS *, struct _SN_ONLOGOFF_PARAMS *)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800170a0`
- `0x1800179d0`

## callees

- `0x1800170c8`
- `0x18001717c`
- `0x180017284`
- `0x180017bdc`
- `0x180018370`
- `0x1800189c0`
- `0x180019048`
- `0x180019738`
- `0x1800197e8`
- `0x18001989c`
- `0x1800199b4`
- `0x180019a04`
- `0x180019b18`
- `0x180021980`
- `0x180021b6c`
- `0x18002d2d8`
- `0x18002db38`
- `0x18002e648`
- `0x1800352f4`
- `0x18003f42c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800186ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018776`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800186ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018776`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018811`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018811`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018763`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018808`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018763`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001854c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001854c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018607`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001845c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001845c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001846a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001846a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018480`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018480`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001853d`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800185f8`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001853d`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800185f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018989`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018989`
- `RPCRT4!RpcRevertToSelf` at `0x180018475`
- `RPCRT4!RpcRevertToSelf` at `0x180018475`
- `RPCRT4!RpcImpersonateClient` at `0x1800183f3`
- `RPCRT4!RpcImpersonateClient` at `0x1800183f3`

## string_xrefs

- `0x18001849d`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x1800184da`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x180018591`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x180018649`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x18001869f`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x18001881f`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x180018858`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x18001889a`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x1800188b2`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x180018909`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x180018950`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x180018968`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`

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
  HANDLE v9; // rdi
  CUserProfileManager *v10; // rcx
  int SessionEntry; // edi
  __int64 v12; // rdx
  int v13; // eax
  LPCRITICAL_SECTION v14; // rsi
  struct WorkItemInfo *v15; // r14
  _QWORD *v16; // rdx
  signed int LastError; // eax
  int v18; // eax
  LPCRITICAL_SECTION v19; // rsi
  CUserProfileManager *v20; // rcx
  struct WorkItemInfo *v21; // r14
  _QWORD *v22; // rdx
  signed int v23; // eax
  void *UserToken; // rax
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
  HANDLE Token; // [rsp+40h] [rbp-9h]
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
    Token = 0;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    if ( RpcImpersonateClient(0) )
      goto LABEL_14;
    HIDWORD(v56) = 1;
    if ( v60 )
    {
      if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
      {
        v7 = EVENT_USER_LOGON_START;
LABEL_13:
        McTemplateU0q_EtwEventWriteTransfer(v6, v7, v61);
      }
    }
    else if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
    {
      v7 = EVENT_USER_LOGOFF_START;
      goto LABEL_13;
    }
LABEL_14:
    CThreadContext::RevertPrivileges((CThreadContext *)&v54);
    if ( v54 )
    {
      v9 = Token;
      SetThreadToken(0, Token);
      if ( v9 )
        CloseHandle(v9);
    }
    if ( HIDWORD(v56) )
      RpcRevertToSelf();
    if ( (_DWORD)v56 )
      RevertToSelf();
    SessionEntry = CUserProfileManager::CreateSessionEntry(v8, v61);
    if ( SessionEntry < 0 )
    {
      v12 = 305;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
        (const char *)(unsigned int)SessionEntry,
        v52[0]);
      v53 = 0;
      lambda_5ea0ea092935807d452b9f4138fd86e2_::operator()(v52);
      return (unsigned int)SessionEntry;
    }
    if ( v60 )
    {
      v13 = CUserProfileManager::SetParams(v10, v61, v60);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x135,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
          (const char *)(unsigned int)v13,
          v52[0]);
      v14 = g_pUPSvc;
      if ( g_pUPSvc )
      {
        pv = 0;
        SessionEntry = _CreateWorkItemInfo((struct WorkItemInfo **)&pv);
        if ( SessionEntry >= 0 )
        {
          v15 = (struct WorkItemInfo *)pv;
          v16 = pv;
          *((_DWORD *)pv + 6) = 16;
          *v16 = LogonThreadProc;
          v16[1] = &v61;
          v16[2] = 0;
          if ( TrySubmitThreadpoolCallback(
                 (PTP_SIMPLE_CALLBACK)_WorkItemWrapper,
                 v16,
                 (PTP_CALLBACK_ENVIRON)&v14[1].LockSemaphore) )
          {
            v15 = 0;
          }
          else
          {
            LastError = GetLastError();
            SessionEntry = LastError;
            if ( LastError > 0 )
              SessionEntry = (unsigned __int16)LastError | 0x80070000;
          }
          _DestroyWorkItemInfo(v15);
        }
        if ( SessionEntry >= 0 )
          goto LABEL_58;
      }
      else
      {
        SessionEntry = -2147467259;
      }
      v12 = 310;
      goto LABEL_23;
    }
    v18 = CUserProfileManager::SetParams(v10, v61, a2);
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x13A,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
        (const char *)(unsigned int)v18,
        v52[0]);
    v19 = g_pUPSvc;
    if ( g_pUPSvc )
    {
      pv = 0;
      SessionEntry = _CreateWorkItemInfo((struct WorkItemInfo **)&pv);
      if ( SessionEntry >= 0 )
      {
        v21 = (struct WorkItemInfo *)pv;
        v22 = pv;
        *((_DWORD *)pv + 6) = 16;
        *v22 = LogoffThreadProc;
        v22[1] = &v61;
        v22[2] = 0;
        if ( TrySubmitThreadpoolCallback(
               (PTP_SIMPLE_CALLBACK)_WorkItemWrapper,
               v22,
               (PTP_CALLBACK_ENVIRON)&v19[1].LockSemaphore) )
        {
          v21 = 0;
        }
        else
        {
          v23 = GetLastError();
          SessionEntry = v23;
          if ( v23 > 0 )
            SessionEntry = (unsigned __int16)v23 | 0x80070000;
        }
        _DestroyWorkItemInfo(v21);
      }
      if ( SessionEntry >= 0 )
      {
        UserToken = CUserProfileManager::GetUserToken(v20, v61);
        v25 = UserProfileServiceAddWorkItem((unsigned int (*)(void *))CheckForUserObjectUpdates, 0, UserToken);
        if ( v25 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x13F,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
            (const char *)(unsigned int)v25,
            v52[0]);
        goto LABEL_58;
      }
    }
    else
    {
      SessionEntry = -2147467259;
    }
    v12 = 315;
    goto LABEL_23;
  }
  if ( v60 )
  {
    v26 = CUserProfileManager::SetParams(v5, v61, v60);
    if ( v26 >= 0 )
      goto LABEL_58;
    v27 = 330;
  }
  else
  {
    v26 = CUserProfileManager::SetParams(v5, v61, a2);
    if ( v26 >= 0 )
      goto LABEL_58;
    v27 = 334;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v27,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
    (const char *)(unsigned int)v26,
    v52[0]);
LABEL_58:
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
LABEL_62:
    v32 = 0;
  }
  else
  {
    while ( v29 != *(_DWORD *)(v32 + 16) )
    {
      if ( v32 == *v31 )
        goto LABEL_62;
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
LABEL_71:
    v38 = 0;
  }
  else
  {
    while ( v35 != *(_DWORD *)(v38 + 16) )
    {
      if ( v38 == *v37 )
        goto LABEL_71;
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
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
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
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
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
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
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
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
          (const char *)(unsigned int)v51,
          v52[0]);
    }
    SessionEntry = wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)0x174,
                     (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
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
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
      (const char *)(unsigned int)v46,
      v52[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
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
0x180018370  mov     [rsp-8+arg_0], rcx
0x180018375  push    rbp
0x180018376  push    r15
0x180018378  lea     rbp, [rsp-4Fh]
0x18001837d  sub     rsp, 98h
0x180018384  mov     r15, rdx
0x180018387  test    rcx, rcx
0x18001838a  jz      short loc_180018392
0x18001838c  lea     rdx, [rcx+8]
0x180018390  jmp     short loc_180018396
0x180018392  add     rdx, 8
0x180018396  mov     [rsp+0A0h+arg_8], rbx
0x18001839e  lea     rax, [rbp+57h+arg_10]
0x1800183a2  mov     [rsp+0A0h+var_10], rsi
0x1800183aa  mov     [rsp+0A0h+var_18], rdi
0x1800183b2  mov     [rsp+0A0h+var_30], r14
0x1800183b7  mov     edx, [rdx]; unsigned int
0x1800183b9  mov     [rbp+57h+var_80], rax
0x1800183bd  lea     rax, [rbp+57h+arg_0]
0x1800183c1  mov     [rbp+57h+var_78], rax
0x1800183c5  mov     [rbp+57h+arg_10], edx
0x1800183c8  mov     [rbp+57h+var_70], 1
0x1800183cc  call    ?DoesSessionExist@CUserProfileManager@@QEAAHK@Z; CUserProfileManager::DoesSessionExist(ulong)
0x1800183d1  test    eax, eax
0x1800183d3  jnz     loc_18001866E
0x1800183d9  xor     ebx, ebx
0x1800183db  xorps   xmm0, xmm0
0x1800183de  xor     ecx, ecx; BindingHandle
0x1800183e0  mov     [rbp+57h+var_68], ebx
0x1800183e3  mov     [rbp+57h+Token], rbx
0x1800183e7  mov     [rbp+57h+var_58], rbx
0x1800183eb  mov     [rbp+57h+var_50], ebx
0x1800183ee  movdqu  [rbp+57h+var_48], xmm0
0x1800183f3  call    cs:__imp_RpcImpersonateClient
0x1800183f9  test    eax, eax
0x1800183fb  jnz     short loc_180018406
0x1800183fd  mov     dword ptr [rbp+57h+var_58+4], 1
0x180018404  jmp     short loc_180018414
0x180018406  jle     short loc_180018410
0x180018408  movzx   eax, ax
0x18001840b  or      eax, 80070000h
0x180018410  test    eax, eax
0x180018412  js      short loc_180018445
0x180018414  cmp     [rbp+57h+arg_0], rbx
0x180018418  jz      short loc_18001842C
0x18001841a  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x180018421  jz      short loc_180018445
0x180018423  lea     rdx, EVENT_USER_LOGON_START
0x18001842a  jmp     short loc_18001843C
0x18001842c  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x180018433  jz      short loc_180018445
0x180018435  lea     rdx, EVENT_USER_LOGOFF_START
0x18001843c  mov     r8d, [rbp+57h+arg_10]
0x180018440  call    McTemplateU0q_EtwEventWriteTransfer
0x180018445  lea     rcx, [rbp+57h+var_68]; this
0x180018449  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x18001844e  cmp     [rbp+57h+var_68], ebx
0x180018451  jz      short loc_180018470
0x180018453  mov     rdi, [rbp+57h+Token]
0x180018457  xor     ecx, ecx; Thread
0x180018459  mov     rdx, rdi; Token
0x18001845c  call    cs:__imp_SetThreadToken
0x180018462  test    rdi, rdi
0x180018465  jz      short loc_180018470
0x180018467  mov     rcx, rdi; hObject
0x18001846a  call    cs:__imp_CloseHandle
0x180018470  cmp     dword ptr [rbp+57h+var_58+4], ebx
0x180018473  jz      short loc_18001847B
0x180018475  call    cs:__imp_RpcRevertToSelf
0x18001847b  cmp     dword ptr [rbp+57h+var_58], ebx
0x18001847e  jz      short loc_180018486
0x180018480  call    cs:__imp_RevertToSelf
0x180018486  mov     edx, [rbp+57h+arg_10]; unsigned int
0x180018489  call    ?CreateSessionEntry@CUserProfileManager@@QEAAJK@Z; CUserProfileManager::CreateSessionEntry(ulong)
0x18001848e  mov     edi, eax
0x180018490  test    eax, eax
0x180018492  jns     short loc_1800184BD
0x180018494  mov     edx, 131h; void *
0x180018499  mov     rcx, [rbp+5Fh]; this
0x18001849d  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800184a4  mov     r9d, edi; char *
0x1800184a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800184ac  lea     rcx, [rbp+57h+var_80]
0x1800184b0  mov     [rbp+57h+var_70], bl
0x1800184b3  call    _lambda_5ea0ea092935807d452b9f4138fd86e2___operator__
0x1800184b8  jmp     loc_18001898F
0x1800184bd  mov     r8, [rbp+57h+arg_0]; void *
0x1800184c1  mov     edx, [rbp+57h+arg_10]; unsigned int
0x1800184c4  test    r8, r8
0x1800184c7  jz      loc_180018581
0x1800184cd  call    ?SetParams@CUserProfileManager@@QEAAJKPEAX@Z; CUserProfileManager::SetParams(ulong,void *)
0x1800184d2  test    eax, eax
0x1800184d4  jns     short loc_1800184EE
0x1800184d6  mov     rcx, [rbp+5Fh]; this
0x1800184da  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800184e1  mov     r9d, eax; char *
0x1800184e4  mov     edx, 135h; void *
0x1800184e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800184ee  mov     rsi, cs:?g_pUPSvc@@3PEAVCUserProfileService@@EA; CUserProfileService * g_pUPSvc
0x1800184f5  test    rsi, rsi
0x1800184f8  jz      short loc_180018572
0x1800184fa  lea     rcx, [rbp+57h+pv]; struct WorkItemInfo **
0x1800184fe  mov     [rbp+57h+pv], rbx
0x180018502  call    ?_CreateWorkItemInfo@@YAJPEAPEAUWorkItemInfo@@@Z; _CreateWorkItemInfo(WorkItemInfo * *)
0x180018507  mov     edi, eax
0x180018509  test    eax, eax
0x18001850b  js      short loc_180018569
0x18001850d  mov     r14, [rbp+57h+pv]
0x180018511  lea     rax, ?LogonThreadProc@@YAKPEAX@Z; LogonThreadProc(void *)
0x180018518  lea     r8, [rsi+40h]; pcbe
0x18001851c  mov     rdx, r14; pv
0x18001851f  lea     rcx, ?_WorkItemWrapper@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180018526  mov     dword ptr [r14+18h], 10h
0x18001852e  mov     [r14], rax
0x180018531  lea     rax, [rbp+57h+arg_10]
0x180018535  mov     [r14+8], rax
0x180018539  mov     [r14+10h], rbx
0x18001853d  call    cs:__imp_TrySubmitThreadpoolCallback
0x180018543  test    eax, eax
0x180018545  jz      short loc_18001854C
0x180018547  mov     r14, rbx
0x18001854a  jmp     short loc_180018561
0x18001854c  call    cs:__imp_GetLastError
0x180018552  mov     edi, eax
0x180018554  test    eax, eax
0x180018556  jle     short loc_180018561
0x180018558  movzx   edi, ax
0x18001855b  or      edi, 80070000h
0x180018561  mov     rcx, r14; lpMem
0x180018564  call    ?_DestroyWorkItemInfo@@YAXPEAUWorkItemInfo@@@Z; _DestroyWorkItemInfo(WorkItemInfo *)
0x180018569  test    edi, edi
0x18001856b  js      short loc_180018577
0x18001856d  jmp     loc_1800186B0
0x180018572  mov     edi, 80004005h
0x180018577  mov     edx, 136h
0x18001857c  jmp     loc_180018499
0x180018581  mov     r8, r15; void *
0x180018584  call    ?SetParams@CUserProfileManager@@QEAAJKPEAX@Z; CUserProfileManager::SetParams(ulong,void *)
0x180018589  test    eax, eax
0x18001858b  jns     short loc_1800185A5
0x18001858d  mov     rcx, [rbp+5Fh]; this
0x180018591  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x180018598  mov     r9d, eax; char *
0x18001859b  mov     edx, 13Ah; void *
0x1800185a0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800185a5  mov     rsi, cs:?g_pUPSvc@@3PEAVCUserProfileService@@EA; CUserProfileService * g_pUPSvc
0x1800185ac  test    rsi, rsi
0x1800185af  jz      loc_18001865F
0x1800185b5  lea     rcx, [rbp+57h+pv]; struct WorkItemInfo **
0x1800185b9  mov     [rbp+57h+pv], rbx
0x1800185bd  call    ?_CreateWorkItemInfo@@YAJPEAPEAUWorkItemInfo@@@Z; _CreateWorkItemInfo(WorkItemInfo * *)
0x1800185c2  mov     edi, eax
0x1800185c4  test    eax, eax
0x1800185c6  js      short loc_180018624
0x1800185c8  mov     r14, [rbp+57h+pv]
0x1800185cc  lea     rax, ?LogoffThreadProc@@YAKPEAX@Z; LogoffThreadProc(void *)
0x1800185d3  lea     r8, [rsi+40h]; pcbe
0x1800185d7  mov     rdx, r14; pv
0x1800185da  lea     rcx, ?_WorkItemWrapper@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x1800185e1  mov     dword ptr [r14+18h], 10h
0x1800185e9  mov     [r14], rax
0x1800185ec  lea     rax, [rbp+57h+arg_10]
0x1800185f0  mov     [r14+8], rax
0x1800185f4  mov     [r14+10h], rbx
0x1800185f8  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800185fe  test    eax, eax
0x180018600  jz      short loc_180018607
0x180018602  mov     r14, rbx
0x180018605  jmp     short loc_18001861C
0x180018607  call    cs:__imp_GetLastError
0x18001860d  mov     edi, eax
0x18001860f  test    eax, eax
0x180018611  jle     short loc_18001861C
0x180018613  movzx   edi, ax
0x180018616  or      edi, 80070000h
0x18001861c  mov     rcx, r14; lpMem
0x18001861f  call    ?_DestroyWorkItemInfo@@YAXPEAUWorkItemInfo@@@Z; _DestroyWorkItemInfo(WorkItemInfo *)
0x180018624  test    edi, edi
0x180018626  js      short loc_180018664
0x180018628  mov     edx, [rbp+57h+arg_10]; unsigned int
0x18001862b  call    ?GetUserToken@CUserProfileManager@@QEAAPEAXK@Z; CUserProfileManager::GetUserToken(ulong)
0x180018630  mov     r8, rax; void *
0x180018633  lea     rcx, ?CheckForUserObjectUpdates@@YAKPEAX@Z; unsigned int (*)(void *)
0x18001863a  xor     edx, edx; void *
0x18001863c  call    ?UserProfileServiceAddWorkItem@@YAJP6AKPEAX@Z00K@Z; UserProfileServiceAddWorkItem(ulong (*)(void *),void *,void *,ulong)
0x180018641  test    eax, eax
0x180018643  jns     short loc_1800186B0
0x180018645  mov     rcx, [rbp+5Fh]; this
0x180018649  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x180018650  mov     r9d, eax; char *
0x180018653  mov     edx, 13Fh; void *
0x180018658  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001865d  jmp     short loc_1800186B0
0x18001865f  mov     edi, 80004005h
0x180018664  mov     edx, 13Bh
0x180018669  jmp     loc_180018499
0x18001866e  mov     r8, [rbp+57h+arg_0]; void *
0x180018672  mov     edx, [rbp+57h+arg_10]; unsigned int
0x180018675  test    r8, r8
0x180018678  jz      short loc_18001868A
0x18001867a  call    ?SetParams@CUserProfileManager@@QEAAJKPEAX@Z; CUserProfileManager::SetParams(ulong,void *)
0x18001867f  test    eax, eax
0x180018681  jns     short loc_1800186AE
0x180018683  mov     edx, 14Ah
0x180018688  jmp     short loc_18001869B
0x18001868a  mov     r8, r15; void *
0x18001868d  call    ?SetParams@CUserProfileManager@@QEAAJKPEAX@Z; CUserProfileManager::SetParams(ulong,void *)
0x180018692  test    eax, eax
0x180018694  jns     short loc_1800186AE
0x180018696  mov     edx, 14Eh; void *
0x18001869b  mov     rcx, [rbp+5Fh]; this
0x18001869f  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800186a6  mov     r9d, eax; char *
0x1800186a9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800186ae  xor     ebx, ebx
0x1800186b0  mov     rsi, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; CUserProfileManager * g_pProfMgr
0x1800186b7  mov     edi, [rbp+57h+arg_10]
0x1800186ba  mov     rcx, rsi; SRWLock
0x1800186bd  mov     [rsp+0A0h+var_20], r12
0x1800186c5  mov     [rsp+0A0h+var_28], r13
0x1800186ca  call    cs:__imp_AcquireSRWLockShared
0x1800186d0  mov     eax, edi
0x1800186d2  movzx   r9d, dil
0x1800186d6  shr     eax, 10h
0x1800186d9  mov     r8d, edi
0x1800186dc  movzx   edx, al
0x1800186df  mov     eax, edi
0x1800186e1  shr     r8d, 18h
0x1800186e5  shr     eax, 8
0x1800186e8  movzx   ecx, al
0x1800186eb  lfence
0x1800186ee  mov     r12, 100000001B3h
0x1800186f8  mov     r13, 0CBF29CE484222325h
0x180018702  xor     r9, r13
0x180018705  imul    r9, r12
0x180018709  xor     rcx, r9
0x18001870c  imul    rcx, r12
0x180018710  xor     rcx, rdx
0x180018713  mov     rdx, [rsi+38h]
0x180018717  imul    rcx, r12
0x18001871b  xor     rcx, r8
0x18001871e  imul    rcx, r12
0x180018722  and     rcx, [rsi+60h]
0x180018726  shl     rcx, 4
0x18001872a  add     rcx, [rsi+48h]
0x18001872e  mov     rax, [rcx+8]
0x180018732  cmp     rax, rdx
0x180018735  jz      short loc_18001874A
0x180018737  mov     r8, [rcx]
0x18001873a  cmp     edi, [rax+10h]
0x18001873d  jz      short loc_18001874D
0x18001873f  cmp     rax, r8
0x180018742  jz      short loc_18001874A
0x180018744  mov     rax, [rax+8]
0x180018748  jmp     short loc_18001873A
0x18001874a  mov     rax, rbx
0x18001874d  test    rax, rax
0x180018750  jz      short loc_18001875D
0x180018752  cmp     rax, rdx
0x180018755  jz      short loc_18001875D
0x180018757  mov     r14, [rax+20h]
0x18001875b  jmp     short loc_180018760
0x18001875d  mov     r14, rbx
0x180018760  mov     rcx, rsi; SRWLock
0x180018763  call    cs:__imp_ReleaseSRWLockShared
0x180018769  mov     rsi, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; CUserProfileManager * g_pProfMgr
0x180018770  mov     edi, [rbp+57h+arg_10]
0x180018773  mov     rcx, rsi; SRWLock
0x180018776  call    cs:__imp_AcquireSRWLockShared
0x18001877c  mov     eax, edi
0x18001877e  movzx   r9d, dil
0x180018782  shr     eax, 10h
0x180018785  mov     r8d, edi
0x180018788  movzx   edx, al
0x18001878b  mov     eax, edi
0x18001878d  shr     r8d, 18h
0x180018791  shr     eax, 8
0x180018794  movzx   ecx, al
0x180018797  lfence
0x18001879a  xor     r9, r13
0x18001879d  mov     r13, [rsp+0A0h+var_28]
0x1800187a2  imul    r9, r12
0x1800187a6  xor     rcx, r9
0x1800187a9  imul    rcx, r12
0x1800187ad  xor     rcx, rdx
0x1800187b0  mov     rdx, [rsi+38h]
0x1800187b4  imul    rcx, r12
0x1800187b8  xor     rcx, r8
0x1800187bb  imul    rcx, r12
0x1800187bf  mov     r12, [rsp+0A0h+var_20]
0x1800187c7  and     rcx, [rsi+60h]
0x1800187cb  shl     rcx, 4
0x1800187cf  add     rcx, [rsi+48h]
0x1800187d3  mov     rax, [rcx+8]
0x1800187d7  cmp     rax, rdx
0x1800187da  jz      short loc_1800187EF
0x1800187dc  mov     r8, [rcx]
0x1800187df  cmp     edi, [rax+10h]
0x1800187e2  jz      short loc_1800187F2
0x1800187e4  cmp     rax, r8
  ... truncated ...
```
