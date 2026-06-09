# CUserProfileManager::CreateSessionEntry(ulong)

- ea: `0x18001aa1c`
- end: `0x18001af7c`
- name: `?CreateSessionEntry@CUserProfileManager@@QEAAJK@Z`
- size: `1376`
- prototype: `__int64 __fastcall(CUserProfileManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001b250`

## callees

- `0x1800084bc`
- `0x18001a4f4`
- `0x18001a950`
- `0x18001a998`
- `0x18001a9d0`
- `0x18001aa1c`
- `0x18001af84`
- `0x18001c358`
- `0x18001c3e4`
- `0x18001c82c`
- `0x18002df48`
- `0x180030ad0`
- `0x180032e60`
- `0x180032fd8`
- `0x180034130`
- `0x18003bc70`
- `0x180040108`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001aa50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001aa50`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001ab28`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001ab5c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001ab28`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001ab5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ad1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ad77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ae28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ae6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001aeae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001aefe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ad1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ad77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ae28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ae6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001aeae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001aefe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad56`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ac1b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ac1b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001af28`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001af28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001abfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001abfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001af40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001af62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001af40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001af62`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001af51`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001af51`
- `RPCRT4!RpcRevertToSelf` at `0x18001ac6f`
- `RPCRT4!RpcRevertToSelf` at `0x18001ac6f`
- `RPCRT4!RpcImpersonateClient` at `0x18001abbf`
- `RPCRT4!RpcImpersonateClient` at `0x18001abbf`

## string_xrefs

- `0x18001ac37`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x18001ad03`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x18001ae46`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x18001ae89`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x18001aecc`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  int v35; // [rsp+90h] [rbp-78h] BYREF
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
      v35 = 0;
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
          CThreadContext::~CThreadContext((CThreadContext *)&v35);
          v35 = a2;
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
          if ( v35 )
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
      CThreadContext::~CThreadContext((CThreadContext *)&v35);
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
0x18001aa1c  mov     [rsp+arg_0], rbx
0x18001aa21  mov     [rsp+arg_10], rsi
0x18001aa26  mov     [rsp+arg_8], edx
0x18001aa2a  push    rdi
0x18001aa2b  sub     rsp, 100h
0x18001aa32  mov     rax, cs:__security_cookie
0x18001aa39  xor     rax, rsp
0x18001aa3c  mov     [rsp+108h+var_18], rax
0x18001aa44  mov     esi, edx
0x18001aa46  mov     rbx, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; CUserProfileManager * g_pProfMgr
0x18001aa4d  mov     rcx, rbx; SRWLock
0x18001aa50  call    cs:__imp_AcquireSRWLockExclusive
0x18001aa57  nop     dword ptr [rax+rax+00h]
0x18001aa5c  mov     qword ptr [rsp+108h+var_E8], rbx; int
0x18001aa61  mov     rdx, 0CBF29CE484222325h
0x18001aa6b  xor     ecx, ecx
0x18001aa6d  movzx   eax, byte ptr [rsp+rcx+108h+arg_8]
0x18001aa75  xor     rdx, rax
0x18001aa78  mov     r8, 100000001B3h
0x18001aa82  imul    rdx, r8
0x18001aa86  inc     rcx
0x18001aa89  cmp     rcx, 4
0x18001aa8d  jb      short loc_18001AA6D
0x18001aa8f  mov     rcx, [rbx+60h]
0x18001aa93  and     rcx, rdx
0x18001aa96  add     rcx, rcx
0x18001aa99  mov     rdx, [rbx+48h]
0x18001aa9d  mov     rax, [rdx+rcx*8+8]
0x18001aaa2  cmp     rax, [rbx+38h]
0x18001aaa6  jz      short loc_18001AABC
0x18001aaa8  mov     r8, [rdx+rcx*8]
0x18001aaac  cmp     esi, [rax+10h]
0x18001aaaf  jz      short loc_18001AABE
0x18001aab1  cmp     rax, r8
0x18001aab4  jz      short loc_18001AABC
0x18001aab6  mov     rax, [rax+8]
0x18001aaba  jmp     short loc_18001AAAC
0x18001aabc  xor     eax, eax
0x18001aabe  test    rax, rax
0x18001aac1  jz      short loc_18001AACD
0x18001aac3  cmp     rax, [rbx+38h]
0x18001aac7  jnz     loc_18001ACF3
0x18001aacd  mov     [rsp+108h+var_C8], esi
0x18001aad1  mov     [rsp+108h+var_C0], 0
0x18001aada  xorps   xmm0, xmm0
0x18001aadd  movdqa  xmmword ptr [rsp+108h+TokenHandle], xmm0
0x18001aae3  xorps   xmm1, xmm1
0x18001aae6  movups  [rsp+108h+var_A0], xmm1
0x18001aaeb  mov     [rsp+108h+var_90], 0
0x18001aaf4  mov     [rsp+108h+var_88], 7
0x18001ab00  xor     eax, eax
0x18001ab02  mov     word ptr [rsp+108h+var_A0], ax
0x18001ab07  mov     [rsp+108h+var_80], 1
0x18001ab0f  mov     [rsp+108h+var_7C], 80004005h
0x18001ab1a  xor     edx, edx; lpName
0x18001ab1c  xor     ecx, ecx; lpEventAttributes
0x18001ab1e  mov     r9d, 1F0003h; dwDesiredAccess
0x18001ab24  lea     r8d, [rax+1]; dwFlags
0x18001ab28  call    cs:__imp_CreateEventExW
0x18001ab2f  nop     dword ptr [rax+rax+00h]
0x18001ab34  mov     rdi, rax
0x18001ab37  test    rax, rax
0x18001ab3a  jnz     loc_18001AD38
0x18001ab40  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001ab45  mov     edi, eax
0x18001ab47  test    eax, eax
0x18001ab49  js      loc_18001AE3B
0x18001ab4f  mov     r9d, 1F0003h; dwDesiredAccess
0x18001ab55  xor     r8d, r8d; dwFlags
0x18001ab58  xor     edx, edx; lpName
0x18001ab5a  xor     ecx, ecx; lpEventAttributes
0x18001ab5c  call    cs:__imp_CreateEventExW
0x18001ab63  nop     dword ptr [rax+rax+00h]
0x18001ab68  mov     rdi, rax
0x18001ab6b  test    rax, rax
0x18001ab6e  jnz     loc_18001AD56
0x18001ab74  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001ab79  mov     edi, eax
0x18001ab7b  test    eax, eax
0x18001ab7d  js      loc_18001AE7E
0x18001ab83  mov     [rsp+108h+var_78], 0
0x18001ab8e  mov     [rsp+108h+Token], 0
0x18001ab9a  mov     [rsp+108h+var_68], 0
0x18001aba6  mov     [rsp+108h+var_60], 0
0x18001abb1  xorps   xmm0, xmm0
0x18001abb4  movdqu  [rsp+108h+var_58], xmm0
0x18001abbd  xor     ecx, ecx; BindingHandle
0x18001abbf  call    cs:__imp_RpcImpersonateClient
0x18001abc6  nop     dword ptr [rax+rax+00h]
0x18001abcb  mov     edi, eax
0x18001abcd  test    eax, eax
0x18001abcf  jnz     loc_18001AD9C
0x18001abd5  mov     dword ptr [rsp+108h+var_68+4], 1
0x18001abe0  mov     rcx, [rsp+108h+TokenHandle+8]; hObject
0x18001abe5  lea     rax, [rcx-1]
0x18001abe9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001abed  jbe     loc_18001AF11
0x18001abf3  mov     [rsp+108h+TokenHandle+8], 0
0x18001abfc  call    cs:__imp_GetCurrentThread
0x18001ac03  nop     dword ptr [rax+rax+00h]
0x18001ac08  lea     r9, [rsp+108h+TokenHandle+8]; TokenHandle
0x18001ac0d  mov     edx, 0F01FFh; DesiredAccess
0x18001ac12  mov     r8d, 1; OpenAsSelf
0x18001ac18  mov     rcx, rax; ThreadHandle
0x18001ac1b  call    cs:__imp_OpenThreadToken
0x18001ac22  nop     dword ptr [rax+rax+00h]
0x18001ac27  test    eax, eax
0x18001ac29  jnz     loc_18001ADAB
0x18001ac2f  mov     rcx, [rsp+108h]; this
0x18001ac37  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001ac3e  mov     edx, 18Dh; void *
0x18001ac43  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ac48  mov     esi, eax
0x18001ac4a  lea     rcx, [rsp+108h+var_78]; this
0x18001ac52  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x18001ac57  cmp     [rsp+108h+var_78], 0
0x18001ac5f  jnz     loc_18001AF1B
0x18001ac65  cmp     dword ptr [rsp+108h+var_68+4], 0
0x18001ac6d  jz      short loc_18001AC7B
0x18001ac6f  call    cs:__imp_RpcRevertToSelf
0x18001ac76  nop     dword ptr [rax+rax+00h]
0x18001ac7b  cmp     dword ptr [rsp+108h+var_68], 0
0x18001ac83  jnz     loc_18001AF51
0x18001ac89  lea     rcx, [rsp+108h+var_A0]
0x18001ac8e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ac93  mov     rcx, [rsp+108h+TokenHandle+8]; hObject
0x18001ac98  lea     rax, [rcx-1]
0x18001ac9c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001aca0  jbe     loc_18001AF62
0x18001aca6  mov     rcx, [rsp+108h+TokenHandle]; this
0x18001acab  test    rcx, rcx
0x18001acae  jnz     loc_18001AD88
0x18001acb4  mov     rcx, [rsp+108h+var_C0]; this
0x18001acb9  test    rcx, rcx
0x18001acbc  jnz     loc_18001AD92
0x18001acc2  test    rbx, rbx
0x18001acc5  jnz     loc_18001AD74
0x18001accb  mov     eax, esi
0x18001accd  mov     rcx, [rsp+108h+var_18]
0x18001acd5  xor     rcx, rsp; StackCookie
0x18001acd8  call    __security_check_cookie
0x18001acdd  lea     r11, [rsp+108h+var_8]
0x18001ace5  mov     rbx, [r11+10h]
0x18001ace9  mov     rsi, [r11+20h]
0x18001aced  mov     rsp, r11
0x18001acf0  pop     rdi
0x18001acf1  retn
0x18001acf3  mov     rcx, [rsp+108h]; this
0x18001acfb  mov     edi, 800700B7h
0x18001ad00  mov     r9d, edi; char *
0x18001ad03  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001ad0a  mov     edx, 180h; void *
0x18001ad0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ad14  nop
0x18001ad15  test    rbx, rbx
0x18001ad18  jz      short loc_18001AD29
0x18001ad1a  mov     rcx, rbx; SRWLock
0x18001ad1d  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ad24  nop     dword ptr [rax+rax+00h]
0x18001ad29  mov     eax, edi
0x18001ad2b  jmp     short loc_18001ACCD
0x18001ad2d  movzx   edi, ax
0x18001ad30  or      edi, 80070000h
0x18001ad36  jmp     short loc_18001AD9E
0x18001ad38  call    cs:__imp_GetLastError
0x18001ad3f  nop     dword ptr [rax+rax+00h]
0x18001ad44  mov     rdx, rdi
0x18001ad47  lea     rcx, [rsp+108h+var_C0]
0x18001ad4c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001ad51  jmp     loc_18001AB4F
0x18001ad56  call    cs:__imp_GetLastError
0x18001ad5d  nop     dword ptr [rax+rax+00h]
0x18001ad62  mov     rdx, rdi
0x18001ad65  lea     rcx, [rsp+108h+TokenHandle]
0x18001ad6a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001ad6f  jmp     loc_18001AB83
0x18001ad74  mov     rcx, rbx; SRWLock
0x18001ad77  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ad7e  nop     dword ptr [rax+rax+00h]
0x18001ad83  jmp     loc_18001ACCB
0x18001ad88  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001ad8d  jmp     loc_18001ACB4
0x18001ad92  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001ad97  jmp     loc_18001ACC2
0x18001ad9c  jg      short loc_18001AD2D
0x18001ad9e  test    edi, edi
0x18001ada0  jns     loc_18001ABE0
0x18001ada6  jmp     loc_18001AEC1
0x18001adab  lea     rcx, [rsp+108h+var_78]; this
0x18001adb3  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001adb8  mov     [rsp+108h+var_78], esi
0x18001adbf  lea     rdx, [rsp+108h+var_C8]
0x18001adc4  lea     rcx, [rsp+108h+Token]
0x18001adcc  call    ??0CSessionNode@@QEAA@$$QEAU0@@Z; CSessionNode::CSessionNode(CSessionNode &&)
0x18001add1  nop
0x18001add2  lea     r8, [rsp+108h+var_78]
0x18001adda  lea     rdx, [rsp+108h+var_E0]
0x18001addf  lea     rcx, [rbx+30h]
0x18001ade3  call    ??$emplace@U?$pair@$$CBKUCSessionNode@@@std@@@?$_Hash@V?$_Umap_traits@KUCSessionNode@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKUCSessionNode@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKUCSessionNode@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBKUCSessionNode@@@1@@Z; std::_Hash<std::_Umap_traits<ulong,CSessionNode,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,CSessionNode>>,0>>::emplace<std::pair<ulong const,CSessionNode>>(std::pair<ulong const,CSessionNode> &&)
0x18001ade8  nop
0x18001ade9  lea     rcx, [rsp+108h+Token]; this
0x18001adf1  call    ??1CSessionNode@@QEAA@XZ; CSessionNode::~CSessionNode(void)
0x18001adf6  nop
0x18001adf7  lea     rcx, [rsp+108h+var_A0]
0x18001adfc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ae01  lea     rcx, [rsp+108h+TokenHandle+8]
0x18001ae06  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001ae0b  lea     rcx, [rsp+108h+TokenHandle]
0x18001ae10  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ae15  lea     rcx, [rsp+108h+var_C0]
0x18001ae1a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ae1f  nop
0x18001ae20  test    rbx, rbx
0x18001ae23  jz      short loc_18001AE34
0x18001ae25  mov     rcx, rbx; SRWLock
0x18001ae28  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ae2f  nop     dword ptr [rax+rax+00h]
0x18001ae34  xor     eax, eax
0x18001ae36  jmp     loc_18001ACCD
0x18001ae3b  mov     rcx, [rsp+108h]; this
0x18001ae43  mov     r9d, edi; char *
0x18001ae46  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001ae4d  mov     edx, 183h; void *
0x18001ae52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ae57  nop
0x18001ae58  lea     rcx, [rsp+108h+var_C8]; this
0x18001ae5d  call    ??1CSessionNode@@QEAA@XZ; CSessionNode::~CSessionNode(void)
0x18001ae62  nop
0x18001ae63  test    rbx, rbx
0x18001ae66  jz      short loc_18001AE77
0x18001ae68  mov     rcx, rbx; SRWLock
0x18001ae6b  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ae72  nop     dword ptr [rax+rax+00h]
0x18001ae77  mov     eax, edi
0x18001ae79  jmp     loc_18001ACCD
0x18001ae7e  mov     rcx, [rsp+108h]; this
0x18001ae86  mov     r9d, edi; char *
0x18001ae89  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001ae90  mov     edx, 184h; void *
0x18001ae95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ae9a  nop
0x18001ae9b  lea     rcx, [rsp+108h+var_C8]; this
0x18001aea0  call    ??1CSessionNode@@QEAA@XZ; CSessionNode::~CSessionNode(void)
0x18001aea5  nop
0x18001aea6  test    rbx, rbx
0x18001aea9  jz      short loc_18001AEBA
0x18001aeab  mov     rcx, rbx; SRWLock
0x18001aeae  call    cs:__imp_ReleaseSRWLockExclusive
0x18001aeb5  nop     dword ptr [rax+rax+00h]
0x18001aeba  mov     eax, edi
0x18001aebc  jmp     loc_18001ACCD
0x18001aec1  mov     rcx, [rsp+108h]; this
0x18001aec9  mov     r9d, edi; char *
0x18001aecc  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001aed3  mov     edx, 188h; void *
0x18001aed8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aedd  lea     rcx, [rsp+108h+var_78]; this
0x18001aee5  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001aeea  nop
0x18001aeeb  lea     rcx, [rsp+108h+var_C8]; this
0x18001aef0  call    ??1CSessionNode@@QEAA@XZ; CSessionNode::~CSessionNode(void)
0x18001aef5  nop
0x18001aef6  test    rbx, rbx
0x18001aef9  jz      short loc_18001AF0A
0x18001aefb  mov     rcx, rbx; SRWLock
0x18001aefe  call    cs:__imp_ReleaseSRWLockExclusive
0x18001af05  nop     dword ptr [rax+rax+00h]
0x18001af0a  mov     eax, edi
0x18001af0c  jmp     loc_18001ACCD
0x18001af11  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18001af16  jmp     loc_18001ABF3
0x18001af1b  mov     rdi, [rsp+108h+Token]
0x18001af23  mov     rdx, rdi; Token
0x18001af26  xor     ecx, ecx; Thread
0x18001af28  call    cs:__imp_SetThreadToken
0x18001af2f  nop     dword ptr [rax+rax+00h]
0x18001af34  test    rdi, rdi
0x18001af37  jz      loc_18001AC65
0x18001af3d  mov     rcx, rdi; hObject
0x18001af40  call    cs:__imp_CloseHandle
0x18001af47  nop     dword ptr [rax+rax+00h]
0x18001af4c  jmp     loc_18001AC65
0x18001af51  call    cs:__imp_RevertToSelf
0x18001af58  nop     dword ptr [rax+rax+00h]
0x18001af5d  jmp     loc_18001AC89
0x18001af62  call    cs:__imp_CloseHandle
0x18001af69  nop     dword ptr [rax+rax+00h]
0x18001af6e  jmp     loc_18001ACA6
0x18001af73  mov     eax, [rsp+108h+var_E8]
0x18001af77  jmp     loc_18001ACCD
```
