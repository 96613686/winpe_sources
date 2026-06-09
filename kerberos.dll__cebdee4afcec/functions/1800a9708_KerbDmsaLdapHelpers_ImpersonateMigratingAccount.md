# KerbDmsaLdapHelpers::ImpersonateMigratingAccount

- ea: `0x1800a9708`
- end: `0x1800a99e1`
- name: `KerbDmsaLdapHelpers::ImpersonateMigratingAccount`
- size: `729`
- prototype: `__int64 __fastcall(_DWORD *, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a8380`

## callees

- `0x1800093f0`
- `0x180032964`
- `0x18008b70c`
- `0x1800a0300`
- `0x1800a8098`
- `0x1800a9708`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a982a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a98e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a992a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a982a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a98e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a992a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9979`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a9920`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a996f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a9920`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a996f`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1800a98dc`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1800a98dc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a97b7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a9820`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a97b7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a9820`

## string_xrefs

- `0x1800a9770`: `Unable to get the client token handle for %#x:%#x, error %#x.\n`
- `0x1800a977d`: `KerbDmsaLdapHelpers::ImpersonateMigratingAccount`
- `0x1800a9841`: `KerbDmsaLdapHelpers::ImpersonateMigratingAccount`
- `0x1800a98fd`: `KerbDmsaLdapHelpers::ImpersonateMigratingAccount`
- `0x1800a9941`: `KerbDmsaLdapHelpers::ImpersonateMigratingAccount`
- `0x1800a9990`: `KerbDmsaLdapHelpers::ImpersonateMigratingAccount`
- `0x1800a9834`: `GetTokenInformation failed with class TokenGroups %d.\n`
- `0x1800a9934`: `Unable to impersonate the token handle %d.\n`
- `0x1800a9983`: `Unable to impersonate the token handle %d.\n`
- `0x1800a98f0`: `Unable to create restricted token %d.\n`

## pseudocode

```c
__int64 __fastcall KerbDmsaLdapHelpers::ImpersonateMigratingAccount(_DWORD *a1, _BYTE *a2)
{
  PLSA_OPEN_TOKEN_BY_LOGON_ID OpenTokenByLogonId; // rax
  int v5; // eax
  unsigned int v6; // ebx
  unsigned int *v7; // rbx
  unsigned int *v8; // rax
  DWORD LastError; // eax
  __int64 v10; // rcx
  unsigned int v11; // esi
  __int64 v12; // r14
  DWORD v13; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  HANDLE Token; // [rsp+50h] [rbp-20h] BYREF
  _SID_AND_ATTRIBUTES SidsToDisable; // [rsp+58h] [rbp-18h] BYREF
  DWORD TokenInformationLength; // [rsp+B8h] [rbp+48h] BYREF
  HANDLE TokenHandle; // [rsp+C0h] [rbp+50h] BYREF
  unsigned int *v21; // [rsp+C8h] [rbp+58h] BYREF

  if ( NtCurrentTeb()->IsImpersonating )
    ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
  *a2 = 0;
  TokenHandle = 0;
  OpenTokenByLogonId = LsaFunctions->OpenTokenByLogonId;
  TokenHandle = 0;
  v5 = ((__int64 (__fastcall *)(_DWORD *, HANDLE *))OpenTokenByLogonId)(a1, &TokenHandle);
  v6 = v5;
  if ( v5 < 0 )
  {
    KerbTracerT::Log(
      1,
      "KerbDmsaLdapHelpers::ImpersonateMigratingAccount",
      1983,
      "Unable to get the client token handle for %#x:%#x, error %#x.\n",
      a1[1],
      *a1,
      v5);
LABEL_31:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v6;
  }
  TokenInformationLength = 0;
  SidsToDisable = 0;
  GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength);
  if ( !TokenInformationLength )
  {
    v6 = 0;
    goto LABEL_31;
  }
  if ( TokenInformationLength >= 0x18uLL )
  {
    v8 = (unsigned int *)MIDL_user_allocate(TokenInformationLength);
    v7 = v8;
    v21 = v8;
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(TokenInformationLength);
    v7 = 0;
    v21 = 0;
    v8 = 0;
  }
  if ( !v8 )
  {
    wil::details::unique_storage<wil::details::resource_policy<_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,void (void *),&void KerbFree(void *),wistd::integral_constant<unsigned __int64,0>,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,void (void *),&void KerbFree(void *),wistd::integral_constant<unsigned __int64,0>,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,0,std::nullptr_t>>(&v21);
    v6 = -1073741801;
    goto LABEL_31;
  }
  if ( !GetTokenInformation(TokenHandle, TokenGroups, v7, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = GetLastError();
    KerbTracerT::Log(
      1,
      "KerbDmsaLdapHelpers::ImpersonateMigratingAccount",
      2008,
      "GetTokenInformation failed with class TokenGroups %d.\n",
      LastError);
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,void (void *),&void KerbFree(void *),wistd::integral_constant<unsigned __int64,0>,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,void (void *),&void KerbFree(void *),wistd::integral_constant<unsigned __int64,0>,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,0,std::nullptr_t>>(&v21);
    v6 = -1073741595;
    goto LABEL_31;
  }
  v10 = 0;
  v11 = 0;
  if ( !*v7 )
    goto LABEL_36;
  do
  {
    v12 = *(_QWORD *)&v7[4 * v11 + 2];
    if ( *(_BYTE *)(v12 + 1) && *(_DWORD *)(v12 + 8) == 80 )
    {
      if ( (_DWORD)v10 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v10);
      SidsToDisable.Sid = (PSID)v12;
      v10 = 1;
    }
    ++v11;
  }
  while ( v11 < *v7 );
  if ( (_DWORD)v10 )
  {
    Token = 0;
    if ( !CreateRestrictedToken(TokenHandle, 0, 1u, &SidsToDisable, 0, 0, 0, 0, &Token) )
    {
      v13 = GetLastError();
      KerbTracerT::Log(
        1,
        "KerbDmsaLdapHelpers::ImpersonateMigratingAccount",
        2041,
        "Unable to create restricted token %d.\n",
        v13);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Token);
      goto LABEL_14;
    }
    if ( !SetThreadToken(0, Token) )
    {
      v14 = GetLastError();
      KerbTracerT::Log(
        1,
        "KerbDmsaLdapHelpers::ImpersonateMigratingAccount",
        2047,
        "Unable to impersonate the token handle %d.\n",
        v14);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Token);
LABEL_30:
      wil::details::unique_storage<wil::details::resource_policy<_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,void (void *),&void KerbFree(void *),wistd::integral_constant<unsigned __int64,0>,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,void (void *),&void KerbFree(void *),wistd::integral_constant<unsigned __int64,0>,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,0,std::nullptr_t>>(&v21);
      v6 = -1073741555;
      goto LABEL_31;
    }
    *a2 = 1;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Token);
  }
  else
  {
LABEL_36:
    if ( !SetThreadToken(0, TokenHandle) )
    {
      v15 = GetLastError();
      KerbTracerT::Log(
        1,
        "KerbDmsaLdapHelpers::ImpersonateMigratingAccount",
        2030,
        "Unable to impersonate the token handle %d.\n",
        v15);
      goto LABEL_30;
    }
    *a2 = 1;
  }
  wil::details::unique_storage<wil::details::resource_policy<_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,void (void *),&void KerbFree(void *),wistd::integral_constant<unsigned __int64,0>,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,void (void *),&void KerbFree(void *),wistd::integral_constant<unsigned __int64,0>,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,0,std::nullptr_t>>(&v21);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x1800a9708  push    rbp
0x1800a970a  push    rbx
0x1800a970b  push    rsi
0x1800a970c  push    rdi
0x1800a970d  push    r12
0x1800a970f  push    r14
0x1800a9711  push    r15
0x1800a9713  mov     rbp, rsp
0x1800a9716  sub     rsp, 70h
0x1800a971a  mov     r15, rdx
0x1800a971d  mov     rdi, rcx
0x1800a9720  xor     r12d, r12d
0x1800a9723  mov     eax, gs:179Ch
0x1800a972b  test    eax, eax
0x1800a972d  jz      short loc_1800A9734
0x1800a972f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a9734  mov     [r15], r12b
0x1800a9737  mov     [rbp+TokenHandle], r12
0x1800a973b  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800a9742  mov     rax, [rax+170h]
0x1800a9749  mov     [rbp+TokenHandle], r12
0x1800a974d  lea     rdx, [rbp+TokenHandle]
0x1800a9751  mov     rcx, rdi
0x1800a9754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9759  mov     ebx, eax
0x1800a975b  test    eax, eax
0x1800a975d  jns     short loc_1800A9793
0x1800a975f  mov     [rsp+70h+RestrictedSidCount], eax
0x1800a9763  mov     ecx, [rdi]
0x1800a9765  mov     dword ptr [rsp+70h+PrivilegesToDelete], ecx
0x1800a9769  mov     ecx, [rdi+4]
0x1800a976c  mov     dword ptr [rsp+70h+ReturnLength], ecx
0x1800a9770  lea     r9, aUnableToGetThe_1; "Unable to get the client token handle f"...
0x1800a9777  mov     r8d, 7BFh
0x1800a977d  lea     rdx, aKerbdmsaldaphe_2; "KerbDmsaLdapHelpers::ImpersonateMigrati"...
0x1800a9784  mov     ecx, 1
0x1800a9789  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a978e  jmp     loc_1800A99AD
0x1800a9793  mov     [rbp+TokenInformationLength], r12d
0x1800a9797  xorps   xmm0, xmm0
0x1800a979a  movups  xmmword ptr [rbp+SidsToDisable.Sid], xmm0
0x1800a979e  lea     rax, [rbp+TokenInformationLength]
0x1800a97a2  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800a97a7  xor     r9d, r9d; TokenInformationLength
0x1800a97aa  xor     r8d, r8d; TokenInformation
0x1800a97ad  lea     edi, [r9+2]
0x1800a97b1  mov     edx, edi; TokenInformationClass
0x1800a97b3  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800a97b7  call    cs:__imp_GetTokenInformation
0x1800a97bd  mov     eax, [rbp+TokenInformationLength]
0x1800a97c0  test    eax, eax
0x1800a97c2  jnz     short loc_1800A97CC
0x1800a97c4  mov     ebx, r12d
0x1800a97c7  jmp     loc_1800A99AD
0x1800a97cc  mov     rcx, rax; size
0x1800a97cf  cmp     rax, 18h
0x1800a97d3  jnb     short loc_1800A97E6
0x1800a97d5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a97da  mov     rbx, r12
0x1800a97dd  mov     [rbp+arg_18], rbx
0x1800a97e1  mov     rax, r12
0x1800a97e4  jmp     short loc_1800A97F2
0x1800a97e6  call    MIDL_user_allocate
0x1800a97eb  mov     rbx, rax
0x1800a97ee  mov     [rbp+arg_18], rax
0x1800a97f2  test    rax, rax
0x1800a97f5  jnz     short loc_1800A980A
0x1800a97f7  lea     rcx, [rbp+arg_18]
0x1800a97fb  call    ??1?$unique_storage@U?$resource_policy@PEAU_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE@@$$A6AXPEAX@Z$1?KerbFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,void (void *),&KerbFree(void *),wistd::integral_constant<unsigned __int64,0>,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,void (void *),&KerbFree(void *),wistd::integral_constant<unsigned __int64,0>,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,0,std::nullptr_t>>(void)
0x1800a9800  mov     ebx, 0C0000017h
0x1800a9805  jmp     loc_1800A99AD
0x1800a980a  lea     rax, [rbp+TokenInformationLength]
0x1800a980e  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800a9813  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800a9817  mov     r8, rbx; TokenInformation
0x1800a981a  mov     edx, edi; TokenInformationClass
0x1800a981c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800a9820  call    cs:__imp_GetTokenInformation
0x1800a9826  test    eax, eax
0x1800a9828  jnz     short loc_1800A9866
0x1800a982a  call    cs:__imp_GetLastError
0x1800a9830  mov     dword ptr [rsp+70h+ReturnLength], eax
0x1800a9834  lea     r9, aGettokeninform; "GetTokenInformation failed with class T"...
0x1800a983b  mov     r8d, 7D8h
0x1800a9841  lea     rdx, aKerbdmsaldaphe_2; "KerbDmsaLdapHelpers::ImpersonateMigrati"...
0x1800a9848  mov     ecx, 1
0x1800a984d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a9852  nop
0x1800a9853  lea     rcx, [rbp+arg_18]
0x1800a9857  call    ??1?$unique_storage@U?$resource_policy@PEAU_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE@@$$A6AXPEAX@Z$1?KerbFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,void (void *),&KerbFree(void *),wistd::integral_constant<unsigned __int64,0>,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,void (void *),&KerbFree(void *),wistd::integral_constant<unsigned __int64,0>,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,0,std::nullptr_t>>(void)
0x1800a985c  mov     ebx, 0C00000E5h
0x1800a9861  jmp     loc_1800A99AD
0x1800a9866  mov     ecx, r12d
0x1800a9869  mov     esi, r12d
0x1800a986c  mov     edi, 1
0x1800a9871  cmp     [rbx], r12d
0x1800a9874  jbe     loc_1800A9969
0x1800a987a  mov     eax, esi
0x1800a987c  add     rax, rax
0x1800a987f  mov     r14, [rbx+rax*8+8]
0x1800a9884  cmp     [r14+1], r12b
0x1800a9888  jbe     short loc_1800A98A0
0x1800a988a  cmp     dword ptr [r14+8], 50h ; 'P'
0x1800a988f  jnz     short loc_1800A98A0
0x1800a9891  test    ecx, ecx
0x1800a9893  jz      short loc_1800A989A
0x1800a9895  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a989a  mov     [rbp+SidsToDisable.Sid], r14
0x1800a989e  mov     ecx, edi
0x1800a98a0  add     esi, edi
0x1800a98a2  cmp     esi, [rbx]
0x1800a98a4  jb      short loc_1800A987A
0x1800a98a6  test    ecx, ecx
0x1800a98a8  jz      loc_1800A9969
0x1800a98ae  mov     [rbp+Token], r12
0x1800a98b2  lea     rax, [rbp+Token]
0x1800a98b6  mov     [rsp+70h+NewTokenHandle], rax; NewTokenHandle
0x1800a98bb  mov     [rsp+70h+SidsToRestrict], r12; SidsToRestrict
0x1800a98c0  mov     [rsp+70h+RestrictedSidCount], r12d; RestrictedSidCount
0x1800a98c5  mov     [rsp+70h+PrivilegesToDelete], r12; PrivilegesToDelete
0x1800a98ca  mov     dword ptr [rsp+70h+ReturnLength], r12d; DeletePrivilegeCount
0x1800a98cf  lea     r9, [rbp+SidsToDisable]; SidsToDisable
0x1800a98d3  mov     r8d, edi; DisableSidCount
0x1800a98d6  xor     edx, edx; Flags
0x1800a98d8  mov     rcx, [rbp+TokenHandle]; ExistingTokenHandle
0x1800a98dc  call    cs:__imp_CreateRestrictedToken
0x1800a98e2  test    eax, eax
0x1800a98e4  jnz     short loc_1800A991A
0x1800a98e6  call    cs:__imp_GetLastError
0x1800a98ec  mov     dword ptr [rsp+70h+ReturnLength], eax
0x1800a98f0  lea     r9, aUnableToCreate; "Unable to create restricted token %d.\n"
0x1800a98f7  mov     r8d, 7F9h
0x1800a98fd  lea     rdx, aKerbdmsaldaphe_2; "KerbDmsaLdapHelpers::ImpersonateMigrati"...
0x1800a9904  mov     ecx, edi
0x1800a9906  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a990b  nop
0x1800a990c  lea     rcx, [rbp+Token]
0x1800a9910  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a9915  jmp     loc_1800A9853
0x1800a991a  mov     rdx, [rbp+Token]; Token
0x1800a991e  xor     ecx, ecx; Thread
0x1800a9920  call    cs:__imp_SetThreadToken
0x1800a9926  test    eax, eax
0x1800a9928  jnz     short loc_1800A995B
0x1800a992a  call    cs:__imp_GetLastError
0x1800a9930  mov     dword ptr [rsp+70h+ReturnLength], eax
0x1800a9934  lea     r9, aUnableToImpers_4; "Unable to impersonate the token handle "...
0x1800a993b  mov     r8d, 7FFh
0x1800a9941  lea     rdx, aKerbdmsaldaphe_2; "KerbDmsaLdapHelpers::ImpersonateMigrati"...
0x1800a9948  mov     ecx, edi
0x1800a994a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a994f  nop
0x1800a9950  lea     rcx, [rbp+Token]
0x1800a9954  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a9959  jmp     short loc_1800A999F
0x1800a995b  mov     [r15], dil
0x1800a995e  lea     rcx, [rbp+Token]
0x1800a9962  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a9967  jmp     short loc_1800A99BD
0x1800a9969  mov     rdx, [rbp+TokenHandle]; Token
0x1800a996d  xor     ecx, ecx; Thread
0x1800a996f  call    cs:__imp_SetThreadToken
0x1800a9975  test    eax, eax
0x1800a9977  jnz     short loc_1800A99BA
0x1800a9979  call    cs:__imp_GetLastError
0x1800a997f  mov     dword ptr [rsp+70h+ReturnLength], eax
0x1800a9983  lea     r9, aUnableToImpers_4; "Unable to impersonate the token handle "...
0x1800a998a  mov     r8d, 7EEh
0x1800a9990  lea     rdx, aKerbdmsaldaphe_2; "KerbDmsaLdapHelpers::ImpersonateMigrati"...
0x1800a9997  mov     ecx, edi
0x1800a9999  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a999e  nop
0x1800a999f  lea     rcx, [rbp+arg_18]
0x1800a99a3  call    ??1?$unique_storage@U?$resource_policy@PEAU_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE@@$$A6AXPEAX@Z$1?KerbFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,void (void *),&KerbFree(void *),wistd::integral_constant<unsigned __int64,0>,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,void (void *),&KerbFree(void *),wistd::integral_constant<unsigned __int64,0>,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,0,std::nullptr_t>>(void)
0x1800a99a8  mov     ebx, 0C000010Dh
0x1800a99ad  lea     rcx, [rbp+TokenHandle]
0x1800a99b1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a99b6  mov     eax, ebx
0x1800a99b8  jmp     short loc_1800A99D2
0x1800a99ba  mov     [r15], dil
0x1800a99bd  lea     rcx, [rbp+arg_18]
0x1800a99c1  call    ??1?$unique_storage@U?$resource_policy@PEAU_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE@@$$A6AXPEAX@Z$1?KerbFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,void (void *),&KerbFree(void *),wistd::integral_constant<unsigned __int64,0>,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,void (void *),&KerbFree(void *),wistd::integral_constant<unsigned __int64,0>,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,_KERB_CLOUD_KERBEROS_DEBUG_RESPONSE *,0,std::nullptr_t>>(void)
0x1800a99c6  nop
0x1800a99c7  lea     rcx, [rbp+TokenHandle]
0x1800a99cb  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a99d0  xor     eax, eax
0x1800a99d2  add     rsp, 70h
0x1800a99d6  pop     r15
0x1800a99d8  pop     r14
0x1800a99da  pop     r12
0x1800a99dc  pop     rdi
0x1800a99dd  pop     rsi
0x1800a99de  pop     rbx
0x1800a99df  pop     rbp
0x1800a99e0  retn
```
