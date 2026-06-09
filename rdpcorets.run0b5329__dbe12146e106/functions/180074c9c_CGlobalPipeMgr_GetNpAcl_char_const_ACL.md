# CGlobalPipeMgr::GetNpAcl(char const *,_ACL * *)

- ea: `0x180074c9c`
- end: `0x18007533d`
- name: `?GetNpAcl@CGlobalPipeMgr@@AEAAJPEBDPEAPEAU_ACL@@@Z`
- size: `1697`
- prototype: `__int64 __fastcall(CGlobalPipeMgr *this, char *, struct _ACL **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800746a8`

## callees

- `0x1800091a8`
- `0x18002e600`
- `0x180032f60`
- `0x180033940`
- `0x180033964`
- `0x180033da0`
- `0x180034970`
- `0x180055ca0`
- `0x180059878`
- `0x1800598d0`
- `0x180074b88`
- `0x180074c9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074d9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800750f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075180`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074d9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800750f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075180`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180074d7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180074d7c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180074d91`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180074d91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800752ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800752ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075311`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075311`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180074f54`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180074f54`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800750e8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180075172`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800750e8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180075172`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800752cf`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800752de`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800752cf`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800752de`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074e1d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074f0c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074e1d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074f0c`
- `RPCRT4!RpcRevertToSelf` at `0x180075303`
- `RPCRT4!RpcRevertToSelf` at `0x180075303`
- `RPCRT4!RpcImpersonateClient` at `0x180074d0b`
- `RPCRT4!RpcImpersonateClient` at `0x180074d0b`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180075272`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180075272`

## string_xrefs

- `0x180074e5c`: `TOKEN_USER`
- `0x180075011`: `GetChannelServiceSid`
- `0x180074f99`: `IsValidSid(pClientUserToken->User.Sid) return FALSE`
- `0x1800752ae`: `SetEntriesInAcl`
- `0x1800751cc`: `AllocateAndInitializeSid`

## pseudocode

```c
__int64 __fastcall CGlobalPipeMgr::GetNpAcl(CGlobalPipeMgr *this, char *a2, struct _ACL **a3)
{
  void *v3; // r12
  int LastError; // ebx
  int v5; // r13d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HANDLE CurrentThread; // rax
  unsigned int v8; // eax
  __int64 v9; // rdx
  void *v10; // rax
  PSID *v11; // r14
  unsigned int v12; // eax
  DWORD v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  signed int v18; // eax
  unsigned int v19; // eax
  int v20; // edx
  signed int v21; // eax
  ULONG v22; // ebx
  signed int v23; // eax
  unsigned int v24; // eax
  DWORD TokenInformationLength; // [rsp+60h] [rbp-A0h] BYREF
  void *v27; // [rsp+68h] [rbp-98h]
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  PSID pSid; // [rsp+78h] [rbp-88h] BYREF
  PSID v30; // [rsp+80h] [rbp-80h] BYREF
  void *Block; // [rsp+88h] [rbp-78h]
  char *String1; // [rsp+90h] [rbp-70h]
  PACL NewAcl; // [rsp+98h] [rbp-68h] BYREF
  struct _ACL **v34; // [rsp+A0h] [rbp-60h]
  struct _SID_IDENTIFIER_AUTHORITY v35; // [rsp+A8h] [rbp-58h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B0h] [rbp-50h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+C0h] [rbp-40h] BYREF
  int v38; // [rsp+F0h] [rbp-10h]
  int v39; // [rsp+F4h] [rbp-Ch]
  int v40; // [rsp+10Ch] [rbp+Ch]
  PSID v41; // [rsp+118h] [rbp+18h]
  int v42; // [rsp+120h] [rbp+20h]
  int v43; // [rsp+124h] [rbp+24h]
  int v44; // [rsp+13Ch] [rbp+3Ch]
  PSID v45; // [rsp+148h] [rbp+48h]

  v34 = a3;
  NewAcl = 0;
  Block = 0;
  v3 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_DWORD *)v35.Value = 0;
  v30 = 0;
  pSid = 0;
  v27 = 0;
  TokenInformationLength = 0;
  String1 = a2;
  TokenHandle = (void *)-1LL;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_WORD *)&v35.Value[4] = 1280;
  LastError = RpcImpersonateClient(0);
  if ( LastError )
  {
    v5 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        &WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
        CurrentThreadActivityIdPrefix,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_83;
  }
  v5 = 1;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_14;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 18;
LABEL_13:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids, v8, LastError);
LABEL_14:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_83;
  }
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  v10 = operator new(TokenInformationLength);
  Block = v10;
  v11 = (PSID *)v10;
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
        v12,
        (__int64)"TOKEN_USER");
    }
    LastError = -2147024882;
    goto LABEL_83;
  }
  memset_0(v10, 0, TokenInformationLength);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v13 = TokenInformationLength;
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids, v14, v13, 16);
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v11, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_14;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 21;
    goto LABEL_13;
  }
  if ( !IsValidSid(*v11) )
  {
    LastError = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
        v15,
        (__int64)"IsValidSid(pClientUserToken->User.Sid) return FALSE",
        5);
    }
    goto LABEL_83;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LockdownDVCs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LockdownDVCs>::GetImpl'::`2'::impl) )
  {
    LastError = GetChannelServiceSid(String1);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
          v16,
          (__int64)"GetChannelServiceSid",
          LastError);
      }
      v3 = v27;
      goto LABEL_83;
    }
    v3 = v27;
    if ( v27
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
        v17,
        (__int64)String1);
    }
  }
  else if ( !AllocateAndInitializeSid(&v35, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &v30) )
  {
    v21 = GetLastError();
    LastError = v21;
    if ( v21 > 0 )
      LastError = (unsigned __int16)v21 | 0x80070000;
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_83;
      }
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 25;
LABEL_68:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
        v19,
        (__int64)"AllocateAndInitializeSid",
        LastError);
      goto LABEL_83;
    }
  }
  if ( !AllocateAndInitializeSid(
          &pIdentifierAuthority,
          6u,
          0x50u,
          0x1A963466u,
          0x5CF1AAB9u,
          0xF8123019,
          0x7448CE95u,
          0x304EFDA0u,
          0,
          0,
          &pSid) )
  {
    v18 = GetLastError();
    LastError = v18;
    if ( v18 > 0 )
      LastError = (unsigned __int16)v18 | 0x80070000;
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_83;
      }
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 26;
      goto LABEL_68;
    }
  }
  v22 = 2;
  memset_0(&pListOfExplicitEntries, 0, 0x90u);
  pListOfExplicitEntries.grfAccessPermissions = -1073741824;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.ptstrName = *(LPWCH *)Block;
  v41 = pSid;
  v38 = 0x10000000;
  v39 = 1;
  v40 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LockdownDVCs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LockdownDVCs>::GetImpl'::`2'::impl) )
  {
    if ( v3 )
    {
      v44 = 0;
      v45 = v3;
LABEL_74:
      v22 = 3;
      v43 = 1;
      v42 = -1073741824;
    }
  }
  else if ( v30 )
  {
    v45 = v30;
    goto LABEL_74;
  }
  v23 = SetEntriesInAclW(v22, &pListOfExplicitEntries, 0, &NewAcl);
  LastError = v23;
  if ( v23 > 0 )
    LastError = (unsigned __int16)v23 | 0x80070000;
  if ( LastError >= 0 )
  {
    *v34 = NewAcl;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
      v24,
      (__int64)"SetEntriesInAcl",
      LastError);
  }
LABEL_83:
  if ( pSid )
    FreeSid(pSid);
  if ( v30 )
    FreeSid(v30);
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  operator delete(Block);
  if ( v5 )
    RpcRevertToSelf();
  if ( v3 )
    LocalFree(v3);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180074c9c  mov     [rsp-8+arg_0], rbx
0x180074ca1  push    rbp
0x180074ca2  push    rdi
0x180074ca3  push    r12
0x180074ca5  push    r13
0x180074ca7  push    r14
0x180074ca9  lea     rbp, [rsp-60h]
0x180074cae  sub     rsp, 160h
0x180074cb5  mov     rax, cs:__security_cookie
0x180074cbc  xor     rax, rsp
0x180074cbf  mov     [rbp+80h+var_30], rax
0x180074cc3  xor     r14d, r14d
0x180074cc6  mov     [rbp+80h+var_E0], r8
0x180074cca  xor     ecx, ecx; BindingHandle
0x180074ccc  mov     [rbp+80h+NewAcl], r14
0x180074cd0  mov     [rbp+80h+Block], r14
0x180074cd4  mov     r12d, r14d
0x180074cd7  mov     dword ptr [rbp+80h+pIdentifierAuthority.Value], r14d
0x180074cdb  mov     dword ptr [rbp+80h+var_D8.Value], r14d
0x180074cdf  mov     [rbp+80h+var_100], r14
0x180074ce3  mov     [rsp+180h+var_108], r14
0x180074ce8  mov     [rsp+180h+var_118], r14
0x180074ced  mov     [rsp+180h+TokenInformationLength], r14d
0x180074cf2  mov     [rbp+80h+String1], rdx
0x180074cf6  mov     [rsp+180h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180074cff  mov     word ptr [rbp+80h+pIdentifierAuthority.Value+4], 500h
0x180074d05  mov     word ptr [rbp+80h+var_D8.Value+4], 500h
0x180074d0b  call    cs:__imp_RpcImpersonateClient
0x180074d11  mov     ebx, eax
0x180074d13  test    eax, eax
0x180074d15  jz      short loc_180074D76
0x180074d17  mov     r13d, r14d
0x180074d1a  mov     rax, cs:WPP_GLOBAL_Control
0x180074d21  lea     rdi, WPP_GLOBAL_Control
0x180074d28  cmp     rax, rdi
0x180074d2b  jz      short loc_180074D60
0x180074d2d  test    byte ptr [rax+1Ch], 8
0x180074d31  jz      short loc_180074D60
0x180074d33  cmp     byte ptr [rax+19h], 2
0x180074d37  jb      short loc_180074D60
0x180074d39  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180074d45  lea     edx, [r14+11h]
0x180074d49  mov     r9d, eax
0x180074d4c  mov     dword ptr [rsp+180h+ReturnLength], ebx
0x180074d50  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x180074d57  mov     rcx, [rcx+10h]
0x180074d5b  call    WPP_SF_Dd
0x180074d60  test    ebx, ebx
0x180074d62  jle     loc_1800752C5
0x180074d68  movzx   ebx, bx
0x180074d6b  or      ebx, 80070000h
0x180074d71  jmp     loc_1800752C5
0x180074d76  mov     r13d, 1
0x180074d7c  call    cs:__imp_GetCurrentThread
0x180074d82  lea     r9, [rsp+180h+TokenHandle]; TokenHandle
0x180074d87  mov     r8d, r13d; OpenAsSelf
0x180074d8a  mov     rcx, rax; ThreadHandle
0x180074d8d  lea     edx, [r13+7]; DesiredAccess
0x180074d91  call    cs:__imp_OpenThreadToken
0x180074d97  test    eax, eax
0x180074d99  jnz     short loc_180074E05
0x180074d9b  call    cs:__imp_GetLastError
0x180074da1  mov     ebx, eax
0x180074da3  mov     rax, cs:WPP_GLOBAL_Control
0x180074daa  lea     rdi, WPP_GLOBAL_Control
0x180074db1  cmp     rax, rdi
0x180074db4  jz      short loc_180074DE9
0x180074db6  test    byte ptr [rax+1Ch], 8
0x180074dba  jz      short loc_180074DE9
0x180074dbc  cmp     byte ptr [rax+19h], 2
0x180074dc0  jb      short loc_180074DE9
0x180074dc2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074dc7  lea     edx, [r13+11h]
0x180074dcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180074dd2  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x180074dd9  mov     r9d, eax
0x180074ddc  mov     dword ptr [rsp+180h+ReturnLength], ebx
0x180074de0  mov     rcx, [rcx+10h]
0x180074de4  call    WPP_SF_Dd
0x180074de9  test    ebx, ebx
0x180074deb  jle     short loc_180074DF6
0x180074ded  movzx   ebx, bx
0x180074df0  or      ebx, 80070000h
0x180074df6  test    ebx, ebx
0x180074df8  mov     eax, 80004005h
0x180074dfd  cmovns  ebx, eax
0x180074e00  jmp     loc_1800752C5
0x180074e05  mov     rcx, [rsp+180h+TokenHandle]; TokenHandle
0x180074e0a  lea     rax, [rsp+180h+TokenInformationLength]
0x180074e0f  xor     r9d, r9d; TokenInformationLength
0x180074e12  mov     [rsp+180h+ReturnLength], rax; ReturnLength
0x180074e17  xor     r8d, r8d; TokenInformation
0x180074e1a  mov     edx, r13d; TokenInformationClass
0x180074e1d  call    cs:__imp_GetTokenInformation
0x180074e23  mov     ecx, [rsp+180h+TokenInformationLength]; Size
0x180074e27  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180074e2c  mov     [rbp+80h+Block], rax
0x180074e30  mov     r14, rax
0x180074e33  test    rax, rax
0x180074e36  jnz     short loc_180074E90
0x180074e38  mov     rax, cs:WPP_GLOBAL_Control
0x180074e3f  lea     rdi, WPP_GLOBAL_Control
0x180074e46  cmp     rax, rdi
0x180074e49  jz      short loc_180074E86
0x180074e4b  test    byte ptr [rax+1Ch], 8
0x180074e4f  jz      short loc_180074E86
0x180074e51  cmp     byte ptr [rax+19h], 2
0x180074e55  jb      short loc_180074E86
0x180074e57  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074e5c  lea     rcx, aTokenUser; "TOKEN_USER"
0x180074e63  mov     r9d, eax
0x180074e66  mov     [rsp+180h+ReturnLength], rcx
0x180074e6b  lea     edx, [r14+13h]
0x180074e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180074e76  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x180074e7d  mov     rcx, [rcx+10h]
0x180074e81  call    WPP_SF_Ds
0x180074e86  mov     ebx, 8007000Eh
0x180074e8b  jmp     loc_1800752C5
0x180074e90  mov     r8d, [rsp+180h+TokenInformationLength]; Size
0x180074e95  xor     edx, edx; Val
0x180074e97  mov     rcx, r14; void *
0x180074e9a  call    memset_0
0x180074e9f  mov     rax, cs:WPP_GLOBAL_Control
0x180074ea6  lea     rdi, WPP_GLOBAL_Control
0x180074ead  cmp     rax, rdi
0x180074eb0  jz      short loc_180074EF2
0x180074eb2  test    [rax+1Ch], r13b
0x180074eb6  jz      short loc_180074EF2
0x180074eb8  cmp     byte ptr [rax+19h], 4
0x180074ebc  jb      short loc_180074EF2
0x180074ebe  mov     ebx, [rsp+180h+TokenInformationLength]
0x180074ec2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074ec7  mov     rcx, cs:WPP_GLOBAL_Control
0x180074ece  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x180074ed5  mov     edx, 14h
0x180074eda  mov     [rsp+180h+nSubAuthority3], 10h
0x180074ee2  mov     r9d, eax
0x180074ee5  mov     dword ptr [rsp+180h+ReturnLength], ebx
0x180074ee9  mov     rcx, [rcx+10h]
0x180074eed  call    WPP_SF_DdD
0x180074ef2  mov     r9d, [rsp+180h+TokenInformationLength]; TokenInformationLength
0x180074ef7  lea     rax, [rsp+180h+TokenInformationLength]
0x180074efc  mov     rcx, [rsp+180h+TokenHandle]; TokenHandle
0x180074f01  mov     r8, r14; TokenInformation
0x180074f04  mov     edx, r13d; TokenInformationClass
0x180074f07  mov     [rsp+180h+ReturnLength], rax; ReturnLength
0x180074f0c  call    cs:__imp_GetTokenInformation
0x180074f12  test    eax, eax
0x180074f14  jnz     short loc_180074F51
0x180074f16  call    cs:__imp_GetLastError
0x180074f1c  mov     ebx, eax
0x180074f1e  mov     rax, cs:WPP_GLOBAL_Control
0x180074f25  cmp     rax, rdi
0x180074f28  jz      loc_180074DE9
0x180074f2e  test    byte ptr [rax+1Ch], 8
0x180074f32  jz      loc_180074DE9
0x180074f38  cmp     byte ptr [rax+19h], 2
0x180074f3c  jb      loc_180074DE9
0x180074f42  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074f47  mov     edx, 15h
0x180074f4c  jmp     loc_180074DCB
0x180074f51  mov     rcx, [r14]; pSid
0x180074f54  call    cs:__imp_IsValidSid
0x180074f5a  test    eax, eax
0x180074f5c  jnz     short loc_180074FC4
0x180074f5e  mov     ebx, 80004005h
0x180074f63  mov     rax, cs:WPP_GLOBAL_Control
0x180074f6a  cmp     rax, rdi
0x180074f6d  jz      loc_1800752C5
0x180074f73  test    byte ptr [rax+1Ch], 8
0x180074f77  jz      loc_1800752C5
0x180074f7d  cmp     byte ptr [rax+19h], 2
0x180074f81  jb      loc_1800752C5
0x180074f87  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074f8c  mov     edx, 16h
0x180074f91  mov     [rsp+180h+nSubAuthority3], 80004005h
0x180074f99  lea     rcx, aIsvalidsidPcli; "IsValidSid(pClientUserToken->User.Sid) "...
0x180074fa0  mov     [rsp+180h+ReturnLength], rcx
0x180074fa5  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x180074fac  mov     rcx, cs:WPP_GLOBAL_Control
0x180074fb3  mov     r9d, eax
0x180074fb6  mov     rcx, [rcx+10h]
0x180074fba  call    WPP_SF_DsD
0x180074fbf  jmp     loc_1800752C5
0x180074fc4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LockdownDVCs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LockdownDVCs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LockdownDVCs> `wil::Feature<__WilFeatureTraits_Feature_LockdownDVCs>::GetImpl(void)'::`2'::impl
0x180074fcb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LockdownDVCs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LockdownDVCs>::__private_IsEnabled(void)
0x180074fd0  xor     ecx, ecx
0x180074fd2  mov     r14d, 80070000h
0x180074fd8  test    al, al
0x180074fda  jz      loc_180075143
0x180074fe0  mov     rcx, [rbp+80h+String1]; String1
0x180074fe4  lea     rdx, [rsp+180h+var_118]
0x180074fe9  call    GetChannelServiceSid
0x180074fee  mov     ebx, eax
0x180074ff0  test    eax, eax
0x180074ff2  jns     short loc_18007504A
0x180074ff4  mov     rax, cs:WPP_GLOBAL_Control
0x180074ffb  cmp     rax, rdi
0x180074ffe  jz      short loc_180075040
0x180075000  test    byte ptr [rax+1Ch], 8
0x180075004  jz      short loc_180075040
0x180075006  cmp     byte ptr [rax+19h], 2
0x18007500a  jb      short loc_180075040
0x18007500c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180075011  lea     rcx, aGetchannelserv; "GetChannelServiceSid"
0x180075018  mov     [rsp+180h+nSubAuthority3], ebx
0x18007501c  mov     [rsp+180h+ReturnLength], rcx
0x180075021  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x180075028  mov     rcx, cs:WPP_GLOBAL_Control
0x18007502f  mov     edx, 17h
0x180075034  mov     r9d, eax
0x180075037  mov     rcx, [rcx+10h]
0x18007503b  call    WPP_SF_DsD
0x180075040  mov     r12, [rsp+180h+var_118]
0x180075045  jmp     loc_1800752C5
0x18007504a  mov     r12, [rsp+180h+var_118]
0x18007504f  test    r12, r12
0x180075052  jz      short loc_18007509C
0x180075054  mov     rax, cs:WPP_GLOBAL_Control
0x18007505b  cmp     rax, rdi
0x18007505e  jz      short loc_18007509C
0x180075060  test    dword ptr [rax+1Ch], 800h
0x180075067  jz      short loc_18007509C
0x180075069  cmp     byte ptr [rax+19h], 4
0x18007506d  jb      short loc_18007509C
0x18007506f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180075074  mov     rcx, [rbp+80h+String1]
0x180075078  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x18007507f  mov     [rsp+180h+ReturnLength], rcx
0x180075084  mov     edx, 18h
0x180075089  mov     rcx, cs:WPP_GLOBAL_Control
0x180075090  mov     r9d, eax
0x180075093  mov     rcx, [rcx+10h]
0x180075097  call    WPP_SF_Ds
0x18007509c  lea     rax, [rsp+180h+var_108]
0x1800750a1  mov     r9d, 1A963466h; nSubAuthority1
0x1800750a7  mov     [rsp+180h+pSid], rax; pSid
0x1800750ac  lea     rcx, [rbp+80h+pIdentifierAuthority]; pIdentifierAuthority
0x1800750b0  mov     [rsp+180h+nSubAuthority7], 0; nSubAuthority7
0x1800750b8  mov     r8d, 50h ; 'P'; nSubAuthority0
0x1800750be  mov     [rsp+180h+nSubAuthority6], 0; nSubAuthority6
0x1800750c6  mov     dl, 6; nSubAuthorityCount
0x1800750c8  mov     [rsp+180h+nSubAuthority5], 304EFDA0h; nSubAuthority5
0x1800750d0  mov     [rsp+180h+nSubAuthority4], 7448CE95h; nSubAuthority4
0x1800750d8  mov     [rsp+180h+nSubAuthority3], 0F8123019h; nSubAuthority3
0x1800750e0  mov     dword ptr [rsp+180h+ReturnLength], 5CF1AAB9h; nSubAuthority2
0x1800750e8  call    cs:__imp_AllocateAndInitializeSid
0x1800750ee  test    eax, eax
0x1800750f0  jnz     loc_1800751D8
0x1800750f6  call    cs:__imp_GetLastError
0x1800750fc  mov     ebx, eax
0x1800750fe  test    eax, eax
0x180075100  jle     short loc_180075108
0x180075102  movzx   ebx, ax
0x180075105  or      ebx, r14d
0x180075108  test    ebx, ebx
0x18007510a  jns     loc_1800751D8
0x180075110  mov     rax, cs:WPP_GLOBAL_Control
0x180075117  cmp     rax, rdi
0x18007511a  jz      loc_1800752C5
0x180075120  test    byte ptr [rax+1Ch], 8
0x180075124  jz      loc_1800752C5
0x18007512a  cmp     byte ptr [rax+19h], 2
0x18007512e  jb      loc_1800752C5
0x180075134  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180075139  mov     edx, 1Ah
0x18007513e  jmp     loc_1800751C8
0x180075143  lea     rax, [rbp+80h+var_100]
0x180075147  xor     r9d, r9d; nSubAuthority1
0x18007514a  mov     [rsp+180h+pSid], rax; pSid
0x18007514f  mov     dl, r13b; nSubAuthorityCount
0x180075152  mov     [rsp+180h+nSubAuthority7], ecx; nSubAuthority7
0x180075156  mov     [rsp+180h+nSubAuthority6], ecx; nSubAuthority6
0x18007515a  mov     [rsp+180h+nSubAuthority5], ecx; nSubAuthority5
0x18007515e  lea     r8d, [r9+13h]; nSubAuthority0
0x180075162  mov     [rsp+180h+nSubAuthority4], ecx; nSubAuthority4
0x180075166  mov     [rsp+180h+nSubAuthority3], ecx; nSubAuthority3
0x18007516a  mov     dword ptr [rsp+180h+ReturnLength], ecx; nSubAuthority2
0x18007516e  lea     rcx, [rbp+80h+var_D8]; pIdentifierAuthority
0x180075172  call    cs:__imp_AllocateAndInitializeSid
0x180075178  test    eax, eax
0x18007517a  jnz     loc_18007509C
0x180075180  call    cs:__imp_GetLastError
0x180075186  mov     ebx, eax
0x180075188  test    eax, eax
0x18007518a  jle     short loc_180075192
0x18007518c  movzx   ebx, ax
0x18007518f  or      ebx, r14d
0x180075192  test    ebx, ebx
0x180075194  jns     loc_18007509C
0x18007519a  mov     rax, cs:WPP_GLOBAL_Control
0x1800751a1  cmp     rax, rdi
0x1800751a4  jz      loc_1800752C5
0x1800751aa  test    byte ptr [rax+1Ch], 8
0x1800751ae  jz      loc_1800752C5
0x1800751b4  cmp     byte ptr [rax+19h], 2
0x1800751b8  jb      loc_1800752C5
0x1800751be  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
  ... truncated ...
```
