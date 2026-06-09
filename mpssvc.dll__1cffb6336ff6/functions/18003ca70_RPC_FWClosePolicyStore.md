# RPC_FWClosePolicyStore

- ea: `0x18003ca70`
- end: `0x18003d0d1`
- name: `RPC_FWClosePolicyStore`
- size: `1633`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800093b0`
- `0x18000af3c`
- `0x18003ca70`
- `0x18003d0d8`
- `0x1800670c0`
- `0x18006f520`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18003cabd`
- `ntdll!EtwEventWrite` at `0x18003cd1b`
- `ntdll!EtwEventWrite` at `0x18003cabd`
- `ntdll!EtwEventWrite` at `0x18003cd1b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003cb17`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003cc38`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003cb17`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003cc38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003cb03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003cc24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003cb03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003cc24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ce8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ced6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cf65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cfae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ce8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ced6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cf65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cfae`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18003cbb5`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18003ccc4`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18003cbb5`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18003ccc4`
- `RPCRT4!RpcRevertToSelf` at `0x18003cb42`
- `RPCRT4!RpcRevertToSelf` at `0x18003cc53`
- `RPCRT4!RpcRevertToSelf` at `0x18003cb42`
- `RPCRT4!RpcRevertToSelf` at `0x18003cc53`
- `RPCRT4!RpcImpersonateClient` at `0x18003caf3`
- `RPCRT4!RpcImpersonateClient` at `0x18003cc14`
- `RPCRT4!RpcImpersonateClient` at `0x18003caf3`
- `RPCRT4!RpcImpersonateClient` at `0x18003cc14`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x18003cacb`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x18003cbef`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x18003cacb`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x18003cbef`
- `fwbase!FwHResultToWindowsError` at `0x18003cd50`
- `fwbase!FwHResultToWindowsError` at `0x18003cd50`
- `fwbase!FwCloseHandle` at `0x18003cbcc`
- `fwbase!FwCloseHandle` at `0x18003ccda`
- `fwbase!FwCloseHandle` at `0x18003cbcc`
- `fwbase!FwCloseHandle` at `0x18003ccda`

## string_xrefs

- `0x18003d00f`: `mpssvc.dll`
- `0x18003d07a`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall RPC_FWClosePolicyStore(void *a1, void **a2)
{
  void *v3; // r15
  PSECURITY_DESCRIPTOR v4; // rbx
  void *v5; // rsi
  RPC_STATUS v6; // eax
  signed int v7; // edi
  HANDLE CurrentThread; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // eax
  __int64 v14; // rcx
  WINBOOL v15; // ebx
  PSECURITY_DESCRIPTOR v16; // rsi
  RPC_STATUS v17; // eax
  signed int v18; // ebx
  HANDLE v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned int v24; // eax
  __int64 v25; // rcx
  WINBOOL v26; // esi
  unsigned int v27; // eax
  unsigned int v28; // ebx
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // r9
  __int64 v33; // r9
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  signed int LastError; // eax
  signed int v39; // eax
  signed int v40; // eax
  signed int v41; // eax
  void *TokenHandle; // [rsp+48h] [rbp-21h] BYREF
  BOOLEAN pfEnabled[4]; // [rsp+50h] [rbp-19h] BYREF
  WINBOOL AccessStatus; // [rsp+54h] [rbp-15h] BYREF
  DWORD GrantedAccess; // [rsp+58h] [rbp-11h] BYREF
  DWORD PrivilegeSetLength; // [rsp+5Ch] [rbp-Dh] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp-9h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+78h] [rbp+Fh] BYREF

  v3 = 0;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_API_Enter_ClosePolicyStore, 0, 0);
  pfEnabled[0] = 0;
  if ( BCryptGetFipsAlgorithmMode(pfEnabled) < 0 || (v4 = pSecurityDescriptor, !pfEnabled[0]) )
    v4 = (PSECURITY_DESCRIPTOR)qword_18012C848[0];
  TokenHandle = 0;
  v5 = 0;
  v6 = RpcImpersonateClient(a1);
  v7 = v6;
  if ( !v6 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v5 = TokenHandle;
      v7 = 0;
      if ( !TokenHandle )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v11, v12);
        v5 = TokenHandle;
      }
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          35,
          WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
          (unsigned int)v7);
    }
    v13 = RpcRevertToSelf();
    if ( v13 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v13, 0);
    goto LABEL_12;
  }
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  v14 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      34,
      WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
      (unsigned int)v7);
LABEL_12:
    v14 = WPP_GLOBAL_Control;
  }
  if ( v7 < 0 )
  {
    v15 = 0;
    if ( (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 1) != 0 )
    {
      v36 = 36;
      goto LABEL_52;
    }
  }
  else
  {
    PrivilegeSetLength = 20;
    GrantedAccess = 0;
    AccessStatus = 0;
    GenericMapping = 0;
    memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
    if ( AccessCheck(
           v4,
           v5,
           0x20000u,
           &GenericMapping,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus) )
    {
      v15 = AccessStatus;
      v7 = 0;
      goto LABEL_16;
    }
    v39 = GetLastError();
    v7 = v39;
    if ( v39 > 0 )
      v7 = (unsigned __int16)v39 | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        38,
        WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
        (unsigned int)v7);
      v14 = WPP_GLOBAL_Control;
    }
    v15 = 0;
    if ( v7 < 0 && (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 1) != 0 )
    {
      v36 = 37;
LABEL_52:
      WPP_SF_d(*(_QWORD *)(v14 + 16), v36, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, (unsigned int)v7);
    }
  }
LABEL_16:
  FwCloseHandle(v5);
  if ( v7 < 0 )
  {
    v30 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v31 = 16;
      v32 = (unsigned int)v7;
      goto LABEL_43;
    }
  }
  else if ( !v15 )
  {
    v7 = -2147024891;
    v30 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v31 = 17;
      v32 = 2147942405LL;
LABEL_43:
      WPP_SF_d(*(_QWORD *)(v30 + 16), v31, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids, v32);
    }
  }
  pfEnabled[0] = 0;
  if ( BCryptGetFipsAlgorithmMode(pfEnabled) < 0 || (v16 = qword_18012C870, !pfEnabled[0]) )
    v16 = (PSECURITY_DESCRIPTOR)qword_18012C858;
  TokenHandle = 0;
  v17 = RpcImpersonateClient(a1);
  v18 = v17;
  if ( !v17 )
  {
    v19 = GetCurrentThread();
    if ( OpenThreadToken(v19, 8u, 1, &TokenHandle) )
    {
      v3 = TokenHandle;
      if ( !TokenHandle )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v21, v20, v22, v23);
        v3 = TokenHandle;
      }
    }
    else
    {
      v40 = GetLastError();
      v18 = v40;
      if ( v40 > 0 )
        v18 = (unsigned __int16)v40 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          35,
          WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
          (unsigned int)v18);
    }
    v24 = RpcRevertToSelf();
    if ( v24 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v24, 0);
    goto LABEL_27;
  }
  if ( v17 > 0 )
    v18 = (unsigned __int16)v17 | 0x80070000;
  v25 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      34,
      WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
      (unsigned int)v18);
LABEL_27:
    v25 = WPP_GLOBAL_Control;
  }
  if ( v18 < 0 )
  {
    v26 = 0;
    if ( (_UNKNOWN *)v25 != &WPP_GLOBAL_Control && (*(_BYTE *)(v25 + 28) & 1) != 0 )
    {
      v37 = 36;
      goto LABEL_57;
    }
  }
  else
  {
    GrantedAccess = 20;
    PrivilegeSetLength = 0;
    AccessStatus = 0;
    GenericMapping = 0;
    memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
    if ( AccessCheck(
           v16,
           v3,
           0x20000u,
           &GenericMapping,
           &PrivilegeSet,
           &GrantedAccess,
           &PrivilegeSetLength,
           &AccessStatus) )
    {
      v26 = AccessStatus;
      v18 = 0;
      goto LABEL_31;
    }
    v41 = GetLastError();
    v18 = v41;
    if ( v41 > 0 )
      v18 = (unsigned __int16)v41 | 0x80070000;
    v25 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        38,
        WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
        (unsigned int)v18);
      v25 = WPP_GLOBAL_Control;
    }
    v26 = 0;
    if ( v18 < 0 && (_UNKNOWN *)v25 != &WPP_GLOBAL_Control && (*(_BYTE *)(v25 + 28) & 1) != 0 )
    {
      v37 = 37;
LABEL_57:
      WPP_SF_d(*(_QWORD *)(v25 + 16), v37, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, (unsigned int)v18);
    }
  }
LABEL_31:
  FwCloseHandle(v3);
  if ( v18 < 0 )
  {
    v34 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v35 = 16;
      v33 = (unsigned int)v18;
      goto LABEL_47;
    }
  }
  else if ( !v26 )
  {
    v33 = 2147942405LL;
    v18 = -2147024891;
    v34 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v35 = 17;
LABEL_47:
      WPP_SF_d(*(_QWORD *)(v34 + 16), v35, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids, v33);
    }
  }
  if ( v7 >= 0 || v18 >= 0 )
    v27 = SvrImpl_FWClosePolicyStore(a1, a2);
  else
    v27 = FwHResultToWindowsError((unsigned int)v7);
  v28 = v27;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_API_Exit_ClosePolicyStore, 0, 0);
  return v28;
}

```

## disassembly

```asm
0x18003ca70  mov     [rsp-8+arg_10], rbx
0x18003ca75  push    rbp
0x18003ca76  push    rsi
0x18003ca77  push    rdi
0x18003ca78  push    r12
0x18003ca7a  push    r13
0x18003ca7c  push    r14
0x18003ca7e  push    r15
0x18003ca80  lea     rbp, [rsp-27h]
0x18003ca85  sub     rsp, 90h
0x18003ca8c  mov     rax, cs:__security_cookie
0x18003ca93  xor     rax, rsp
0x18003ca96  mov     [rbp+57h+var_38], rax
0x18003ca9a  mov     r13, rcx
0x18003ca9d  mov     [rbp+57h+var_80], rdx
0x18003caa1  mov     rcx, cs:g_Provider
0x18003caa8  xor     r15d, r15d
0x18003caab  test    rcx, rcx
0x18003caae  jz      short loc_18003CAC3
0x18003cab0  xor     r9d, r9d
0x18003cab3  lea     rdx, MPS_SVC_API_Enter_ClosePolicyStore
0x18003caba  xor     r8d, r8d
0x18003cabd  call    cs:__imp_EtwEventWrite
0x18003cac3  lea     rcx, [rbp+57h+pfEnabled]; pfEnabled
0x18003cac7  mov     [rbp+57h+pfEnabled], r15b
0x18003cacb  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x18003cad1  test    eax, eax
0x18003cad3  js      short loc_18003CAE2
0x18003cad5  mov     rbx, cs:pSecurityDescriptor
0x18003cadc  cmp     [rbp+57h+pfEnabled], r15b
0x18003cae0  jnz     short loc_18003CAE9
0x18003cae2  mov     rbx, cs:qword_18012C848
0x18003cae9  mov     rcx, r13; BindingHandle
0x18003caec  mov     [rbp+57h+TokenHandle], r15
0x18003caf0  mov     rsi, r15
0x18003caf3  call    cs:__imp_RpcImpersonateClient
0x18003caf9  mov     edi, eax
0x18003cafb  test    eax, eax
0x18003cafd  jnz     loc_18003CE41
0x18003cb03  call    cs:__imp_GetCurrentThread
0x18003cb09  mov     rcx, rax; ThreadHandle
0x18003cb0c  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18003cb10  lea     edx, [rdi+8]; DesiredAccess
0x18003cb13  lea     r8d, [rdi+1]; OpenAsSelf
0x18003cb17  call    cs:__imp_OpenThreadToken
0x18003cb1d  mov     r12d, 80070000h
0x18003cb23  lea     r14, WPP_GLOBAL_Control
0x18003cb2a  test    eax, eax
0x18003cb2c  jz      loc_18003CE8D
0x18003cb32  mov     rsi, [rbp+57h+TokenHandle]
0x18003cb36  mov     edi, r15d
0x18003cb39  test    rsi, rsi
0x18003cb3c  jz      loc_18003CFFE
0x18003cb42  call    cs:__imp_RpcRevertToSelf
0x18003cb48  test    eax, eax
0x18003cb4a  jnz     loc_18003D00C
0x18003cb50  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cb57  test    edi, edi
0x18003cb59  js      loc_18003D022
0x18003cb5f  xor     eax, eax
0x18003cb61  mov     [rbp+57h+var_64], 14h
0x18003cb68  mov     [rbp+57h+var_60.Privilege.Attributes], eax
0x18003cb6b  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18003cb6f  lea     rax, [rbp+57h+var_6C]
0x18003cb73  mov     [rbp+57h+var_68], r15d
0x18003cb77  mov     [rsp+0C0h+AccessStatus], rax; AccessStatus
0x18003cb7c  xorps   xmm0, xmm0
0x18003cb7f  lea     rax, [rbp+57h+var_68]
0x18003cb83  mov     [rbp+57h+var_6C], r15d
0x18003cb87  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x18003cb8c  xorps   xmm1, xmm1
0x18003cb8f  lea     rax, [rbp+57h+var_64]
0x18003cb93  mov     r8d, 20000h; DesiredAccess
0x18003cb99  mov     [rsp+0C0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18003cb9e  mov     rdx, rsi; ClientToken
0x18003cba1  lea     rax, [rbp+57h+var_60]
0x18003cba5  mov     rcx, rbx; pSecurityDescriptor
0x18003cba8  mov     [rsp+0C0h+PrivilegeSet], rax; PrivilegeSet
0x18003cbad  movups  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x18003cbb1  movups  xmmword ptr [rbp+57h+var_60.PrivilegeCount], xmm1
0x18003cbb5  call    cs:__imp_AccessCheck
0x18003cbbb  test    eax, eax
0x18003cbbd  jz      loc_18003CED6
0x18003cbc3  mov     ebx, [rbp+57h+var_6C]
0x18003cbc6  mov     edi, r15d
0x18003cbc9  mov     rcx, rsi
0x18003cbcc  call    cs:__imp_FwCloseHandle
0x18003cbd2  mov     eax, 80070005h
0x18003cbd7  test    edi, edi
0x18003cbd9  js      loc_18003D042
0x18003cbdf  test    ebx, ebx
0x18003cbe1  jz      loc_18003CD58
0x18003cbe7  lea     rcx, [rbp+57h+pfEnabled]; pfEnabled
0x18003cbeb  mov     [rbp+57h+pfEnabled], r15b
0x18003cbef  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x18003cbf5  test    eax, eax
0x18003cbf7  js      short loc_18003CC06
0x18003cbf9  mov     rsi, cs:qword_18012C870
0x18003cc00  cmp     [rbp+57h+pfEnabled], r15b
0x18003cc04  jnz     short loc_18003CC0D
0x18003cc06  mov     rsi, cs:qword_18012C858
0x18003cc0d  mov     rcx, r13; BindingHandle
0x18003cc10  mov     [rbp+57h+TokenHandle], r15
0x18003cc14  call    cs:__imp_RpcImpersonateClient
0x18003cc1a  mov     ebx, eax
0x18003cc1c  test    eax, eax
0x18003cc1e  jnz     loc_18003CF26
0x18003cc24  call    cs:__imp_GetCurrentThread
0x18003cc2a  mov     rcx, rax; ThreadHandle
0x18003cc2d  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18003cc31  lea     edx, [rbx+8]; DesiredAccess
0x18003cc34  lea     r8d, [rbx+1]; OpenAsSelf
0x18003cc38  call    cs:__imp_OpenThreadToken
0x18003cc3e  test    eax, eax
0x18003cc40  jz      loc_18003CF65
0x18003cc46  mov     r15, [rbp+57h+TokenHandle]
0x18003cc4a  test    r15, r15
0x18003cc4d  jz      loc_18003D069
0x18003cc53  call    cs:__imp_RpcRevertToSelf
0x18003cc59  test    eax, eax
0x18003cc5b  jnz     loc_18003D077
0x18003cc61  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cc68  test    ebx, ebx
0x18003cc6a  js      loc_18003D08D
0x18003cc70  xor     eax, eax
0x18003cc72  mov     [rbp+57h+var_68], 14h
0x18003cc79  mov     [rbp+57h+var_60.Privilege.Attributes], eax
0x18003cc7c  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18003cc80  mov     [rbp+57h+var_64], eax
0x18003cc83  xorps   xmm0, xmm0
0x18003cc86  mov     [rbp+57h+var_6C], eax
0x18003cc89  xorps   xmm1, xmm1
0x18003cc8c  lea     rax, [rbp+57h+var_6C]
0x18003cc90  mov     r8d, 20000h; DesiredAccess
0x18003cc96  mov     [rsp+0C0h+AccessStatus], rax; AccessStatus
0x18003cc9b  mov     rdx, r15; ClientToken
0x18003cc9e  lea     rax, [rbp+57h+var_64]
0x18003cca2  mov     rcx, rsi; pSecurityDescriptor
0x18003cca5  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x18003ccaa  lea     rax, [rbp+57h+var_68]
0x18003ccae  mov     [rsp+0C0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18003ccb3  lea     rax, [rbp+57h+var_60]
0x18003ccb7  mov     [rsp+0C0h+PrivilegeSet], rax; PrivilegeSet
0x18003ccbc  movups  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x18003ccc0  movups  xmmword ptr [rbp+57h+var_60.PrivilegeCount], xmm1
0x18003ccc4  call    cs:__imp_AccessCheck
0x18003ccca  test    eax, eax
0x18003cccc  jz      loc_18003CFAE
0x18003ccd2  mov     esi, [rbp+57h+var_6C]
0x18003ccd5  xor     ebx, ebx
0x18003ccd7  mov     rcx, r15
0x18003ccda  call    cs:__imp_FwCloseHandle
0x18003cce0  test    ebx, ebx
0x18003cce2  js      loc_18003D0AA
0x18003cce8  test    esi, esi
0x18003ccea  jz      loc_18003CD91
0x18003ccf0  test    edi, edi
0x18003ccf2  js      short loc_18003CD4A
0x18003ccf4  mov     rdx, [rbp+57h+var_80]; void **
0x18003ccf8  mov     rcx, r13; void *
0x18003ccfb  call    ?SvrImpl_FWClosePolicyStore@@YAKPEAXPEAPEAX@Z; SvrImpl_FWClosePolicyStore(void *,void * *)
0x18003cd00  mov     rcx, cs:g_Provider
0x18003cd07  mov     ebx, eax
0x18003cd09  test    rcx, rcx
0x18003cd0c  jz      short loc_18003CD21
0x18003cd0e  xor     r9d, r9d
0x18003cd11  lea     rdx, MPS_SVC_API_Exit_ClosePolicyStore
0x18003cd18  xor     r8d, r8d
0x18003cd1b  call    cs:__imp_EtwEventWrite
0x18003cd21  mov     eax, ebx
0x18003cd23  mov     rcx, [rbp+57h+var_38]
0x18003cd27  xor     rcx, rsp; StackCookie
0x18003cd2a  call    __security_check_cookie
0x18003cd2f  mov     rbx, [rsp+0C0h+arg_10]
0x18003cd37  add     rsp, 90h
0x18003cd3e  pop     r15
0x18003cd40  pop     r14
0x18003cd42  pop     r13
0x18003cd44  pop     r12
0x18003cd46  pop     rdi
0x18003cd47  pop     rsi
0x18003cd48  pop     rbp
0x18003cd49  retn
0x18003cd4a  test    ebx, ebx
0x18003cd4c  jns     short loc_18003CCF4
0x18003cd4e  mov     ecx, edi
0x18003cd50  call    cs:__imp_FwHResultToWindowsError
0x18003cd56  jmp     short loc_18003CD00
0x18003cd58  mov     edi, eax
0x18003cd5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cd61  cmp     rcx, r14
0x18003cd64  jz      loc_18003CBE7
0x18003cd6a  test    byte ptr [rcx+1Ch], 1
0x18003cd6e  jz      loc_18003CBE7
0x18003cd74  mov     edx, 11h
0x18003cd79  mov     r9d, eax
0x18003cd7c  mov     rcx, [rcx+10h]
0x18003cd80  lea     r8, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x18003cd87  call    WPP_SF_d
0x18003cd8c  jmp     loc_18003CBE7
0x18003cd91  mov     r9d, 80070005h
0x18003cd97  mov     ebx, r9d
0x18003cd9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cda1  cmp     rcx, r14
0x18003cda4  jz      loc_18003CCF0
0x18003cdaa  test    byte ptr [rcx+1Ch], 1
0x18003cdae  jz      loc_18003CCF0
0x18003cdb4  mov     edx, 11h
0x18003cdb9  mov     rcx, [rcx+10h]
0x18003cdbd  lea     r8, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x18003cdc4  call    WPP_SF_d
0x18003cdc9  jmp     loc_18003CCF0
0x18003cdce  mov     ebx, r15d
0x18003cdd1  test    edi, edi
0x18003cdd3  jns     loc_18003CBC9
0x18003cdd9  cmp     rcx, r14
0x18003cddc  jz      loc_18003CBC9
0x18003cde2  test    byte ptr [rcx+1Ch], 1
0x18003cde6  jz      loc_18003CBC9
0x18003cdec  mov     edx, 25h ; '%'
0x18003cdf1  mov     rcx, [rcx+10h]
0x18003cdf5  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003cdfc  mov     r9d, edi
0x18003cdff  call    WPP_SF_d
0x18003ce04  jmp     loc_18003CBC9
0x18003ce09  xor     esi, esi
0x18003ce0b  test    ebx, ebx
0x18003ce0d  jns     loc_18003CCD7
0x18003ce13  cmp     rcx, r14
0x18003ce16  jz      loc_18003CCD7
0x18003ce1c  test    byte ptr [rcx+1Ch], 1
0x18003ce20  jz      loc_18003CCD7
0x18003ce26  lea     edx, [rsi+25h]
0x18003ce29  mov     rcx, [rcx+10h]
0x18003ce2d  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003ce34  mov     r9d, ebx
0x18003ce37  call    WPP_SF_d
0x18003ce3c  jmp     loc_18003CCD7
0x18003ce41  mov     r12d, 80070000h
0x18003ce47  jle     short loc_18003CE4F
0x18003ce49  movzx   edi, ax
0x18003ce4c  or      edi, r12d
0x18003ce4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ce56  lea     r14, WPP_GLOBAL_Control
0x18003ce5d  cmp     rcx, r14
0x18003ce60  jz      loc_18003CB57
0x18003ce66  test    byte ptr [rcx+1Ch], 1
0x18003ce6a  jz      loc_18003CB57
0x18003ce70  mov     rcx, [rcx+10h]
0x18003ce74  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003ce7b  mov     edx, 22h ; '"'
0x18003ce80  mov     r9d, edi
0x18003ce83  call    WPP_SF_d
0x18003ce88  jmp     loc_18003CB50
0x18003ce8d  call    cs:__imp_GetLastError
0x18003ce93  mov     edi, eax
0x18003ce95  test    eax, eax
0x18003ce97  jle     short loc_18003CE9F
0x18003ce99  movzx   edi, ax
0x18003ce9c  or      edi, r12d
0x18003ce9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cea6  cmp     rcx, r14
0x18003cea9  jz      loc_18003CB42
0x18003ceaf  test    byte ptr [rcx+1Ch], 1
0x18003ceb3  jz      loc_18003CB42
0x18003ceb9  mov     rcx, [rcx+10h]
0x18003cebd  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003cec4  mov     edx, 23h ; '#'
0x18003cec9  mov     r9d, edi
0x18003cecc  call    WPP_SF_d
0x18003ced1  jmp     loc_18003CB42
0x18003ced6  call    cs:__imp_GetLastError
0x18003cedc  mov     edi, eax
0x18003cede  test    eax, eax
0x18003cee0  jle     short loc_18003CEE8
0x18003cee2  movzx   edi, ax
0x18003cee5  or      edi, r12d
0x18003cee8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ceef  cmp     rcx, r14
0x18003cef2  jz      loc_18003CDCE
0x18003cef8  test    byte ptr [rcx+1Ch], 1
0x18003cefc  jz      loc_18003CDCE
0x18003cf02  mov     rcx, [rcx+10h]
0x18003cf06  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003cf0d  mov     edx, 26h ; '&'
0x18003cf12  mov     r9d, edi
0x18003cf15  call    WPP_SF_d
0x18003cf1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cf21  jmp     loc_18003CDCE
0x18003cf26  jle     short loc_18003CF2E
0x18003cf28  movzx   ebx, ax
0x18003cf2b  or      ebx, r12d
0x18003cf2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cf35  cmp     rcx, r14
0x18003cf38  jz      loc_18003CC68
0x18003cf3e  test    byte ptr [rcx+1Ch], 1
0x18003cf42  jz      loc_18003CC68
0x18003cf48  mov     rcx, [rcx+10h]
0x18003cf4c  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003cf53  mov     edx, 22h ; '"'
  ... truncated ...
```
