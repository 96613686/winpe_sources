# CUserProfileManager::CreateSessionEntry(ulong)

- ea: `0x180017bdc`
- end: `0x1800180c9`
- name: `?CreateSessionEntry@CUserProfileManager@@QEAAJK@Z`
- size: `1261`
- prototype: `__int64 __fastcall(CUserProfileManager *this, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018370`

## callees

- `0x180009120`
- `0x18000a9b8`
- `0x180016c78`
- `0x180017bdc`
- `0x1800180d0`
- `0x180018bcc`
- `0x180019048`
- `0x180019988`
- `0x180019ac4`
- `0x180019afc`
- `0x18002d2d8`
- `0x18002db38`
- `0x1800321f4`
- `0x180032360`
- `0x180033a68`
- `0x18003a730`
- `0x18003ea00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017c10`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017c10`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180017ce2`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180017d10`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180017ce2`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180017d10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017eb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017efa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017fa5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017fe2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001801f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018069`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017eb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017efa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017fa5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017fe2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001801f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018069`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017edf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017dbd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017dbd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001808d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001808d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017da4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017da4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001809f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800180b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001809f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800180b5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800180aa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800180aa`
- `RPCRT4!RpcRevertToSelf` at `0x180017e0b`
- `RPCRT4!RpcRevertToSelf` at `0x180017e0b`
- `RPCRT4!RpcImpersonateClient` at `0x180017d6d`
- `RPCRT4!RpcImpersonateClient` at `0x180017d6d`

## string_xrefs

- `0x180017dd3`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x180017e98`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x180017fbd`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x180017ffa`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x180018037`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfileManager::CreateSessionEntry(CUserProfileManager *this, int a2)
{
  PSRWLOCK v3; // rbx
  __int64 v4; // rdx
  unsigned __int64 i; // rcx
  __int64 v6; // rcx
  _QWORD *Ptr; // rdx
  __int64 v8; // rax
  wil::details *v9; // rcx
  HANDLE Event; // rdi
  int LastErrorFailHr; // eax
  unsigned int v12; // edi
  wil::details *v13; // rcx
  HANDLE v14; // rdi
  int v15; // eax
  unsigned int v16; // edi
  RPC_STATUS v17; // eax
  unsigned int v18; // edi
  HANDLE CurrentThread; // rax
  const char *v20; // r9
  unsigned int LastError; // esi
  void *v22; // rdx
  const char *v23; // r9
  __int64 result; // rax
  HANDLE v25; // rdi
  char v26[24]; // [rsp+28h] [rbp-E0h] BYREF
  int v27; // [rsp+40h] [rbp-C8h] BYREF
  wil::details *v28; // [rsp+48h] [rbp-C0h] BYREF
  void *TokenHandle[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v30; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+78h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-88h]
  char v33; // [rsp+88h] [rbp-80h]
  int v34; // [rsp+8Ch] [rbp-7Ch]
  HANDLE v35; // [rsp+90h] [rbp-78h] BYREF
  HANDLE Token; // [rsp+98h] [rbp-70h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-68h]
  int v38; // [rsp+A8h] [rbp-60h]
  __int128 v39; // [rsp+B0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]
  int v41; // [rsp+118h] [rbp+10h]

  v41 = a2;
  v3 = g_pProfMgr;
  AcquireSRWLockExclusive(g_pProfMgr);
  v4 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
    v4 = 0x100000001B3LL * (*((unsigned __int8 *)&v41 + i) ^ (unsigned __int64)v4);
  v6 = 2 * (v4 & (__int64)v3[12].Ptr);
  Ptr = v3[9].Ptr;
  v8 = Ptr[v6 + 1];
  if ( (PVOID)v8 == v3[7].Ptr )
  {
LABEL_7:
    v8 = 0;
  }
  else
  {
    while ( a2 != *(_DWORD *)(v8 + 16) )
    {
      if ( v8 == Ptr[v6] )
        goto LABEL_7;
      v8 = *(_QWORD *)(v8 + 8);
    }
  }
  try
  {
    if ( v8 && (PVOID)v8 != v3[7].Ptr )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x180,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
        (const char *)0x800700B7LL,
        (int)v3);
      if ( v3 )
        ReleaseSRWLockExclusive(v3);
      result = 2147942583LL;
    }
    else
    {
      v27 = a2;
      v28 = 0;
      *(_OWORD *)TokenHandle = 0;
      v30 = 0;
      v31 = 0;
      v32 = 7;
      LOWORD(v30) = 0;
      v33 = 1;
      v34 = -2147467259;
      Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
      if ( Event )
      {
        GetLastError();
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
          &v28,
          Event);
      }
      else
      {
        LastErrorFailHr = wil::details::GetLastErrorFailHr(v9);
        v12 = LastErrorFailHr;
        if ( LastErrorFailHr < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x183,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
            (const char *)(unsigned int)LastErrorFailHr,
            (int)v3);
          CSessionNode::~CSessionNode((CSessionNode *)&v27);
          if ( v3 )
            ReleaseSRWLockExclusive(v3);
          return v12;
        }
      }
      v14 = CreateEventExW(0, 0, 0, 0x1F0003u);
      if ( v14 )
      {
        GetLastError();
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
          TokenHandle,
          v14);
      }
      else
      {
        v15 = wil::details::GetLastErrorFailHr(v13);
        v16 = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x184,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
            (const char *)(unsigned int)v15,
            (int)v3);
          CSessionNode::~CSessionNode((CSessionNode *)&v27);
          if ( v3 )
            ReleaseSRWLockExclusive(v3);
          return v16;
        }
      }
      LODWORD(v35) = 0;
      Token = 0;
      v37 = 0;
      v38 = 0;
      v39 = 0;
      v17 = RpcImpersonateClient(0);
      v18 = v17;
      if ( !v17 )
      {
        HIDWORD(v37) = 1;
LABEL_16:
        if ( (unsigned __int64)TokenHandle[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(TokenHandle[1]);
        TokenHandle[1] = 0;
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle[1]) )
        {
          CThreadContext::~CThreadContext(&v35);
          LODWORD(v35) = a2;
          CSessionNode::CSessionNode(&Token, &v27);
          std::_Hash<std::_Umap_traits<unsigned long,CSessionNode,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,CSessionNode>>,0>>::emplace<std::pair<unsigned long const,CSessionNode>>(
            &v3[6],
            v26,
            &v35);
          CSessionNode::~CSessionNode((CSessionNode *)&Token);
          std::wstring::~wstring(&v30);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle[1]);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(TokenHandle);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
          if ( v3 )
            ReleaseSRWLockExclusive(v3);
          return 0;
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x18D,
                        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
                        v20);
          CThreadContext::RevertPrivileges((CThreadContext *)&v35);
          if ( (_DWORD)v35 )
          {
            v25 = Token;
            SetThreadToken(0, Token);
            if ( v25 )
              CloseHandle(v25);
          }
          if ( HIDWORD(v37) )
            RpcRevertToSelf();
          if ( (_DWORD)v37 )
            RevertToSelf();
          std::wstring::_Tidy_deallocate(&v30);
          if ( (unsigned __int64)TokenHandle[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(TokenHandle[1]);
          if ( TokenHandle[0] )
            wil::details::CloseHandle((wil::details *)TokenHandle[0], v22);
          if ( v28 )
            wil::details::CloseHandle(v28, v22);
          if ( v3 )
            ReleaseSRWLockExclusive(v3);
          return LastError;
        }
      }
      if ( v17 > 0 )
        v18 = (unsigned __int16)v17 | 0x80070000;
      if ( (v18 & 0x80000000) == 0 )
        goto LABEL_16;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x188,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
        (const char *)v18,
        (int)v3);
      CThreadContext::~CThreadContext(&v35);
      CSessionNode::~CSessionNode((CSessionNode *)&v27);
      if ( v3 )
        ReleaseSRWLockExclusive(v3);
      result = v18;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x193,
                           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
                           v23);
  }
  return result;
}

```

## disassembly

```asm
0x180017bdc  mov     [rsp+arg_0], rbx
0x180017be1  mov     [rsp+arg_10], rsi
0x180017be6  mov     [rsp+arg_8], edx
0x180017bea  push    rdi
0x180017beb  sub     rsp, 100h
0x180017bf2  mov     rax, cs:__security_cookie
0x180017bf9  xor     rax, rsp
0x180017bfc  mov     [rsp+108h+var_18], rax
0x180017c04  mov     esi, edx
0x180017c06  mov     rbx, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; CUserProfileManager * g_pProfMgr
0x180017c0d  mov     rcx, rbx; SRWLock
0x180017c10  call    cs:__imp_AcquireSRWLockExclusive
0x180017c16  mov     qword ptr [rsp+108h+var_E8], rbx; int
0x180017c1b  mov     rdx, 0CBF29CE484222325h
0x180017c25  xor     ecx, ecx
0x180017c27  movzx   eax, byte ptr [rsp+rcx+108h+arg_8]
0x180017c2f  xor     rdx, rax
0x180017c32  mov     r8, 100000001B3h
0x180017c3c  imul    rdx, r8
0x180017c40  inc     rcx
0x180017c43  cmp     rcx, 4
0x180017c47  jb      short loc_180017C27
0x180017c49  mov     rcx, [rbx+60h]
0x180017c4d  and     rcx, rdx
0x180017c50  add     rcx, rcx
0x180017c53  mov     rdx, [rbx+48h]
0x180017c57  mov     rax, [rdx+rcx*8+8]
0x180017c5c  cmp     rax, [rbx+38h]
0x180017c60  jz      short loc_180017C76
0x180017c62  mov     r8, [rdx+rcx*8]
0x180017c66  cmp     esi, [rax+10h]
0x180017c69  jz      short loc_180017C78
0x180017c6b  cmp     rax, r8
0x180017c6e  jz      short loc_180017C76
0x180017c70  mov     rax, [rax+8]
0x180017c74  jmp     short loc_180017C66
0x180017c76  xor     eax, eax
0x180017c78  test    rax, rax
0x180017c7b  jz      short loc_180017C87
0x180017c7d  cmp     rax, [rbx+38h]
0x180017c81  jnz     loc_180017E88
0x180017c87  mov     [rsp+108h+var_C8], esi
0x180017c8b  mov     [rsp+108h+var_C0], 0
0x180017c94  xorps   xmm0, xmm0
0x180017c97  movdqa  xmmword ptr [rsp+108h+TokenHandle], xmm0
0x180017c9d  xorps   xmm1, xmm1
0x180017ca0  movups  [rsp+108h+var_A0], xmm1
0x180017ca5  mov     [rsp+108h+var_90], 0
0x180017cae  mov     [rsp+108h+var_88], 7
0x180017cba  xor     eax, eax
0x180017cbc  mov     word ptr [rsp+108h+var_A0], ax
0x180017cc1  mov     [rsp+108h+var_80], 1
0x180017cc9  mov     [rsp+108h+var_7C], 80004005h
0x180017cd4  xor     edx, edx; lpName
0x180017cd6  xor     ecx, ecx; lpEventAttributes
0x180017cd8  mov     r9d, 1F0003h; dwDesiredAccess
0x180017cde  lea     r8d, [rax+1]; dwFlags
0x180017ce2  call    cs:__imp_CreateEventExW
0x180017ce8  mov     rdi, rax
0x180017ceb  test    rax, rax
0x180017cee  jnz     loc_180017EC7
0x180017cf4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180017cf9  mov     edi, eax
0x180017cfb  test    eax, eax
0x180017cfd  js      loc_180017FB2
0x180017d03  mov     r9d, 1F0003h; dwDesiredAccess
0x180017d09  xor     r8d, r8d; dwFlags
0x180017d0c  xor     edx, edx; lpName
0x180017d0e  xor     ecx, ecx; lpEventAttributes
0x180017d10  call    cs:__imp_CreateEventExW
0x180017d16  mov     rdi, rax
0x180017d19  test    rax, rax
0x180017d1c  jnz     loc_180017EDF
0x180017d22  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180017d27  mov     edi, eax
0x180017d29  test    eax, eax
0x180017d2b  js      loc_180017FEF
0x180017d31  mov     dword ptr [rsp+108h+var_78], 0
0x180017d3c  mov     [rsp+108h+Token], 0
0x180017d48  mov     [rsp+108h+var_68], 0
0x180017d54  mov     [rsp+108h+var_60], 0
0x180017d5f  xorps   xmm0, xmm0
0x180017d62  movdqu  [rsp+108h+var_58], xmm0
0x180017d6b  xor     ecx, ecx; BindingHandle
0x180017d6d  call    cs:__imp_RpcImpersonateClient
0x180017d73  mov     edi, eax
0x180017d75  test    eax, eax
0x180017d77  jnz     loc_180017F19
0x180017d7d  mov     dword ptr [rsp+108h+var_68+4], 1
0x180017d88  mov     rcx, [rsp+108h+TokenHandle+8]; hObject
0x180017d8d  lea     rax, [rcx-1]
0x180017d91  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017d95  jbe     loc_180018076
0x180017d9b  mov     [rsp+108h+TokenHandle+8], 0
0x180017da4  call    cs:__imp_GetCurrentThread
0x180017daa  lea     r9, [rsp+108h+TokenHandle+8]; TokenHandle
0x180017daf  mov     edx, 0F01FFh; DesiredAccess
0x180017db4  mov     r8d, 1; OpenAsSelf
0x180017dba  mov     rcx, rax; ThreadHandle
0x180017dbd  call    cs:__imp_OpenThreadToken
0x180017dc3  test    eax, eax
0x180017dc5  jnz     loc_180017F28
0x180017dcb  mov     rcx, [rsp+108h]; this
0x180017dd3  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180017dda  mov     edx, 18Dh; void *
0x180017ddf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017de4  mov     esi, eax
0x180017de6  lea     rcx, [rsp+108h+var_78]; this
0x180017dee  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x180017df3  cmp     dword ptr [rsp+108h+var_78], 0
0x180017dfb  jnz     loc_180018080
0x180017e01  cmp     dword ptr [rsp+108h+var_68+4], 0
0x180017e09  jz      short loc_180017E11
0x180017e0b  call    cs:__imp_RpcRevertToSelf
0x180017e11  cmp     dword ptr [rsp+108h+var_68], 0
0x180017e19  jnz     loc_1800180AA
0x180017e1f  lea     rcx, [rsp+108h+var_A0]
0x180017e24  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017e29  mov     rcx, [rsp+108h+TokenHandle+8]; hObject
0x180017e2e  lea     rax, [rcx-1]
0x180017e32  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017e36  jbe     loc_1800180B5
0x180017e3c  mov     rcx, [rsp+108h+TokenHandle]; this
0x180017e41  test    rcx, rcx
0x180017e44  jnz     loc_180017F05
0x180017e4a  mov     rcx, [rsp+108h+var_C0]; this
0x180017e4f  test    rcx, rcx
0x180017e52  jnz     loc_180017F0F
0x180017e58  test    rbx, rbx
0x180017e5b  jnz     loc_180017EF7
0x180017e61  mov     eax, esi
0x180017e63  mov     rcx, [rsp+108h+var_18]
0x180017e6b  xor     rcx, rsp; StackCookie
0x180017e6e  call    __security_check_cookie
0x180017e73  lea     r11, [rsp+108h+var_8]
0x180017e7b  mov     rbx, [r11+10h]
0x180017e7f  mov     rsi, [r11+20h]
0x180017e83  mov     rsp, r11
0x180017e86  pop     rdi
0x180017e87  retn
0x180017e88  mov     rcx, [rsp+108h]; this
0x180017e90  mov     edi, 800700B7h
0x180017e95  mov     r9d, edi; char *
0x180017e98  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180017e9f  mov     edx, 180h; void *
0x180017ea4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ea9  nop
0x180017eaa  test    rbx, rbx
0x180017ead  jz      short loc_180017EB8
0x180017eaf  mov     rcx, rbx; SRWLock
0x180017eb2  call    cs:__imp_ReleaseSRWLockExclusive
0x180017eb8  mov     eax, edi
0x180017eba  jmp     short loc_180017E63
0x180017ebc  movzx   edi, ax
0x180017ebf  or      edi, 80070000h
0x180017ec5  jmp     short loc_180017F1B
0x180017ec7  call    cs:__imp_GetLastError
0x180017ecd  mov     rdx, rdi
0x180017ed0  lea     rcx, [rsp+108h+var_C0]
0x180017ed5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180017eda  jmp     loc_180017D03
0x180017edf  call    cs:__imp_GetLastError
0x180017ee5  mov     rdx, rdi
0x180017ee8  lea     rcx, [rsp+108h+TokenHandle]
0x180017eed  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180017ef2  jmp     loc_180017D31
0x180017ef7  mov     rcx, rbx; SRWLock
0x180017efa  call    cs:__imp_ReleaseSRWLockExclusive
0x180017f00  jmp     loc_180017E61
0x180017f05  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180017f0a  jmp     loc_180017E4A
0x180017f0f  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180017f14  jmp     loc_180017E58
0x180017f19  jg      short loc_180017EBC
0x180017f1b  test    edi, edi
0x180017f1d  jns     loc_180017D88
0x180017f23  jmp     loc_18001802C
0x180017f28  lea     rcx, [rsp+108h+var_78]; this
0x180017f30  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180017f35  mov     dword ptr [rsp+108h+var_78], esi
0x180017f3c  lea     rdx, [rsp+108h+var_C8]
0x180017f41  lea     rcx, [rsp+108h+Token]
0x180017f49  call    ??0CSessionNode@@QEAA@$$QEAU0@@Z; CSessionNode::CSessionNode(CSessionNode &&)
0x180017f4e  nop
0x180017f4f  lea     r8, [rsp+108h+var_78]
0x180017f57  lea     rdx, [rsp+108h+var_E0]
0x180017f5c  lea     rcx, [rbx+30h]
0x180017f60  call    ??$emplace@U?$pair@$$CBKUCSessionNode@@@std@@@?$_Hash@V?$_Umap_traits@KUCSessionNode@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKUCSessionNode@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKUCSessionNode@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBKUCSessionNode@@@1@@Z; std::_Hash<std::_Umap_traits<ulong,CSessionNode,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,CSessionNode>>,0>>::emplace<std::pair<ulong const,CSessionNode>>(std::pair<ulong const,CSessionNode> &&)
0x180017f65  nop
0x180017f66  lea     rcx, [rsp+108h+Token]; this
0x180017f6e  call    ??1CSessionNode@@QEAA@XZ; CSessionNode::~CSessionNode(void)
0x180017f73  nop
0x180017f74  lea     rcx, [rsp+108h+var_A0]
0x180017f79  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017f7e  lea     rcx, [rsp+108h+TokenHandle+8]
0x180017f83  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017f88  lea     rcx, [rsp+108h+TokenHandle]
0x180017f8d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017f92  lea     rcx, [rsp+108h+var_C0]
0x180017f97  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017f9c  nop
0x180017f9d  test    rbx, rbx
0x180017fa0  jz      short loc_180017FAB
0x180017fa2  mov     rcx, rbx; SRWLock
0x180017fa5  call    cs:__imp_ReleaseSRWLockExclusive
0x180017fab  xor     eax, eax
0x180017fad  jmp     loc_180017E63
0x180017fb2  mov     rcx, [rsp+108h]; this
0x180017fba  mov     r9d, edi; char *
0x180017fbd  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180017fc4  mov     edx, 183h; void *
0x180017fc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017fce  nop
0x180017fcf  lea     rcx, [rsp+108h+var_C8]; this
0x180017fd4  call    ??1CSessionNode@@QEAA@XZ; CSessionNode::~CSessionNode(void)
0x180017fd9  nop
0x180017fda  test    rbx, rbx
0x180017fdd  jz      short loc_180017FE8
0x180017fdf  mov     rcx, rbx; SRWLock
0x180017fe2  call    cs:__imp_ReleaseSRWLockExclusive
0x180017fe8  mov     eax, edi
0x180017fea  jmp     loc_180017E63
0x180017fef  mov     rcx, [rsp+108h]; this
0x180017ff7  mov     r9d, edi; char *
0x180017ffa  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180018001  mov     edx, 184h; void *
0x180018006  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001800b  nop
0x18001800c  lea     rcx, [rsp+108h+var_C8]; this
0x180018011  call    ??1CSessionNode@@QEAA@XZ; CSessionNode::~CSessionNode(void)
0x180018016  nop
0x180018017  test    rbx, rbx
0x18001801a  jz      short loc_180018025
0x18001801c  mov     rcx, rbx; SRWLock
0x18001801f  call    cs:__imp_ReleaseSRWLockExclusive
0x180018025  mov     eax, edi
0x180018027  jmp     loc_180017E63
0x18001802c  mov     rcx, [rsp+108h]; this
0x180018034  mov     r9d, edi; char *
0x180018037  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001803e  mov     edx, 188h; void *
0x180018043  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018048  lea     rcx, [rsp+108h+var_78]; this
0x180018050  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180018055  nop
0x180018056  lea     rcx, [rsp+108h+var_C8]; this
0x18001805b  call    ??1CSessionNode@@QEAA@XZ; CSessionNode::~CSessionNode(void)
0x180018060  nop
0x180018061  test    rbx, rbx
0x180018064  jz      short loc_18001806F
0x180018066  mov     rcx, rbx; SRWLock
0x180018069  call    cs:__imp_ReleaseSRWLockExclusive
0x18001806f  mov     eax, edi
0x180018071  jmp     loc_180017E63
0x180018076  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18001807b  jmp     loc_180017D9B
0x180018080  mov     rdi, [rsp+108h+Token]
0x180018088  mov     rdx, rdi; Token
0x18001808b  xor     ecx, ecx; Thread
0x18001808d  call    cs:__imp_SetThreadToken
0x180018093  test    rdi, rdi
0x180018096  jz      loc_180017E01
0x18001809c  mov     rcx, rdi; hObject
0x18001809f  call    cs:__imp_CloseHandle
0x1800180a5  jmp     loc_180017E01
0x1800180aa  call    cs:__imp_RevertToSelf
0x1800180b0  jmp     loc_180017E1F
0x1800180b5  call    cs:__imp_CloseHandle
0x1800180bb  jmp     loc_180017E3C
0x1800180c0  mov     eax, [rsp+108h+var_E8]
0x1800180c4  jmp     loc_180017E63
```
