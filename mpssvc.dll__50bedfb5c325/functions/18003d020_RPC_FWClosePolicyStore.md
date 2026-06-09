# RPC_FWClosePolicyStore

- ea: `0x18003d020`
- end: `0x18003d700`
- name: `RPC_FWClosePolicyStore`
- size: `1760`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800089bc`
- `0x18000a710`
- `0x18003d020`
- `0x18003d708`
- `0x18006a710`
- `0x1800729c0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18003d06d`
- `ntdll!EtwEventWrite` at `0x18003d325`
- `ntdll!EtwEventWrite` at `0x18003d06d`
- `ntdll!EtwEventWrite` at `0x18003d325`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003d0c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003d210`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003d0c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003d210`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003d0df`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003d22a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003d0df`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003d22a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d4a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d4f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d5d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d4a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d4f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d5d7`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18003d189`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18003d2c2`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18003d189`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18003d2c2`
- `RPCRT4!RpcImpersonateClient` at `0x18003d0af`
- `RPCRT4!RpcImpersonateClient` at `0x18003d1fa`
- `RPCRT4!RpcImpersonateClient` at `0x18003d0af`
- `RPCRT4!RpcImpersonateClient` at `0x18003d1fa`
- `RPCRT4!RpcRevertToSelf` at `0x18003d110`
- `RPCRT4!RpcRevertToSelf` at `0x18003d24b`
- `RPCRT4!RpcRevertToSelf` at `0x18003d110`
- `RPCRT4!RpcRevertToSelf` at `0x18003d24b`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x18003d081`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x18003d1cf`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x18003d081`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x18003d1cf`
- `fwbase!FwHResultToWindowsError` at `0x18003d361`
- `fwbase!FwHResultToWindowsError` at `0x18003d361`
- `fwbase!FwCloseHandle` at `0x18003d1a6`
- `fwbase!FwCloseHandle` at `0x18003d2de`
- `fwbase!FwCloseHandle` at `0x18003d1a6`
- `fwbase!FwCloseHandle` at `0x18003d2de`

## string_xrefs

- `0x18003d63e`: `mpssvc.dll`
- `0x18003d6a9`: `mpssvc.dll`

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
  unsigned int v9; // eax
  __int64 v10; // rcx
  WINBOOL v11; // ebx
  PSECURITY_DESCRIPTOR v12; // rsi
  RPC_STATUS v13; // eax
  signed int v14; // ebx
  HANDLE v15; // rax
  unsigned int v16; // eax
  __int64 v17; // rcx
  WINBOOL v18; // esi
  unsigned int v19; // eax
  unsigned int v20; // ebx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  __int64 v25; // r9
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  signed int LastError; // eax
  signed int v31; // eax
  signed int v32; // eax
  signed int v33; // eax
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
    v4 = (PSECURITY_DESCRIPTOR)qword_180132A18;
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
        MicrosoftTelemetryAssertTriggeredNoArgs();
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
    v9 = RpcRevertToSelf();
    if ( v9 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v9, 0);
    goto LABEL_12;
  }
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  v10 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      34,
      WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
      (unsigned int)v7);
LABEL_12:
    v10 = WPP_GLOBAL_Control;
  }
  if ( v7 < 0 )
  {
    v11 = 0;
    if ( (_UNKNOWN *)v10 != &WPP_GLOBAL_Control && (*(_BYTE *)(v10 + 28) & 1) != 0 )
    {
      v28 = 36;
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
      v11 = AccessStatus;
      v7 = 0;
      goto LABEL_16;
    }
    v31 = GetLastError();
    v7 = v31;
    if ( v31 > 0 )
      v7 = (unsigned __int16)v31 | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        38,
        WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
        (unsigned int)v7);
      v10 = WPP_GLOBAL_Control;
    }
    v11 = 0;
    if ( v7 < 0 && (_UNKNOWN *)v10 != &WPP_GLOBAL_Control && (*(_BYTE *)(v10 + 28) & 1) != 0 )
    {
      v28 = 37;
LABEL_52:
      WPP_SF_d(*(_QWORD *)(v10 + 16), v28, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, (unsigned int)v7);
    }
  }
LABEL_16:
  FwCloseHandle(v5);
  if ( v7 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v23 = 16;
      v24 = (unsigned int)v7;
      goto LABEL_43;
    }
  }
  else if ( !v11 )
  {
    v7 = -2147024891;
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v23 = 17;
      v24 = 2147942405LL;
LABEL_43:
      WPP_SF_d(*(_QWORD *)(v22 + 16), v23, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids, v24);
    }
  }
  pfEnabled[0] = 0;
  if ( BCryptGetFipsAlgorithmMode(pfEnabled) < 0 || (v12 = qword_180132A40, !pfEnabled[0]) )
    v12 = (PSECURITY_DESCRIPTOR)qword_180132A28;
  TokenHandle = 0;
  v13 = RpcImpersonateClient(a1);
  v14 = v13;
  if ( !v13 )
  {
    v15 = GetCurrentThread();
    if ( OpenThreadToken(v15, 8u, 1, &TokenHandle) )
    {
      v3 = TokenHandle;
      if ( !TokenHandle )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v3 = TokenHandle;
      }
    }
    else
    {
      v32 = GetLastError();
      v14 = v32;
      if ( v32 > 0 )
        v14 = (unsigned __int16)v32 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          35,
          WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
          (unsigned int)v14);
    }
    v16 = RpcRevertToSelf();
    if ( v16 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v16, 0);
    goto LABEL_27;
  }
  if ( v13 > 0 )
    v14 = (unsigned __int16)v13 | 0x80070000;
  v17 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      34,
      WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
      (unsigned int)v14);
LABEL_27:
    v17 = WPP_GLOBAL_Control;
  }
  if ( v14 < 0 )
  {
    v18 = 0;
    if ( (_UNKNOWN *)v17 != &WPP_GLOBAL_Control && (*(_BYTE *)(v17 + 28) & 1) != 0 )
    {
      v29 = 36;
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
           v12,
           v3,
           0x20000u,
           &GenericMapping,
           &PrivilegeSet,
           &GrantedAccess,
           &PrivilegeSetLength,
           &AccessStatus) )
    {
      v18 = AccessStatus;
      v14 = 0;
      goto LABEL_31;
    }
    v33 = GetLastError();
    v14 = v33;
    if ( v33 > 0 )
      v14 = (unsigned __int16)v33 | 0x80070000;
    v17 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        38,
        WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
        (unsigned int)v14);
      v17 = WPP_GLOBAL_Control;
    }
    v18 = 0;
    if ( v14 < 0 && (_UNKNOWN *)v17 != &WPP_GLOBAL_Control && (*(_BYTE *)(v17 + 28) & 1) != 0 )
    {
      v29 = 37;
LABEL_57:
      WPP_SF_d(*(_QWORD *)(v17 + 16), v29, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, (unsigned int)v14);
    }
  }
LABEL_31:
  FwCloseHandle(v3);
  if ( v14 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v27 = 16;
      v25 = (unsigned int)v14;
      goto LABEL_47;
    }
  }
  else if ( !v18 )
  {
    v25 = 2147942405LL;
    v14 = -2147024891;
    v26 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v27 = 17;
LABEL_47:
      WPP_SF_d(*(_QWORD *)(v26 + 16), v27, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids, v25);
    }
  }
  if ( v7 >= 0 || v14 >= 0 )
    v19 = SvrImpl_FWClosePolicyStore(a1, a2);
  else
    v19 = FwHResultToWindowsError((unsigned int)v7);
  v20 = v19;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_API_Exit_ClosePolicyStore, 0, 0);
  return v20;
}

```

## disassembly

```asm
0x18003d020  mov     [rsp-8+arg_10], rbx
0x18003d025  push    rbp
0x18003d026  push    rsi
0x18003d027  push    rdi
0x18003d028  push    r12
0x18003d02a  push    r13
0x18003d02c  push    r14
0x18003d02e  push    r15
0x18003d030  lea     rbp, [rsp-27h]
0x18003d035  sub     rsp, 90h
0x18003d03c  mov     rax, cs:__security_cookie
0x18003d043  xor     rax, rsp
0x18003d046  mov     [rbp+57h+var_38], rax
0x18003d04a  mov     r13, rcx
0x18003d04d  mov     [rbp+57h+var_80], rdx
0x18003d051  mov     rcx, cs:g_Provider
0x18003d058  xor     r15d, r15d
0x18003d05b  test    rcx, rcx
0x18003d05e  jz      short loc_18003D079
0x18003d060  xor     r9d, r9d
0x18003d063  lea     rdx, MPS_SVC_API_Enter_ClosePolicyStore
0x18003d06a  xor     r8d, r8d
0x18003d06d  call    cs:__imp_EtwEventWrite
0x18003d074  nop     dword ptr [rax+rax+00h]
0x18003d079  lea     rcx, [rbp+57h+pfEnabled]; pfEnabled
0x18003d07d  mov     [rbp+57h+pfEnabled], r15b
0x18003d081  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x18003d088  nop     dword ptr [rax+rax+00h]
0x18003d08d  test    eax, eax
0x18003d08f  js      short loc_18003D09E
0x18003d091  mov     rbx, cs:pSecurityDescriptor
0x18003d098  cmp     [rbp+57h+pfEnabled], r15b
0x18003d09c  jnz     short loc_18003D0A5
0x18003d09e  mov     rbx, cs:qword_180132A18
0x18003d0a5  mov     rcx, r13; BindingHandle
0x18003d0a8  mov     [rbp+57h+TokenHandle], r15
0x18003d0ac  mov     rsi, r15
0x18003d0af  call    cs:__imp_RpcImpersonateClient
0x18003d0b6  nop     dword ptr [rax+rax+00h]
0x18003d0bb  mov     edi, eax
0x18003d0bd  test    eax, eax
0x18003d0bf  jnz     loc_18003D458
0x18003d0c5  call    cs:__imp_GetCurrentThread
0x18003d0cc  nop     dword ptr [rax+rax+00h]
0x18003d0d1  mov     rcx, rax; ThreadHandle
0x18003d0d4  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18003d0d8  lea     edx, [rdi+8]; DesiredAccess
0x18003d0db  lea     r8d, [rdi+1]; OpenAsSelf
0x18003d0df  call    cs:__imp_OpenThreadToken
0x18003d0e6  nop     dword ptr [rax+rax+00h]
0x18003d0eb  mov     r12d, 80070000h
0x18003d0f1  lea     r14, WPP_GLOBAL_Control
0x18003d0f8  test    eax, eax
0x18003d0fa  jz      loc_18003D4A4
0x18003d100  mov     rsi, [rbp+57h+TokenHandle]
0x18003d104  mov     edi, r15d
0x18003d107  test    rsi, rsi
0x18003d10a  jz      loc_18003D62D
0x18003d110  call    cs:__imp_RpcRevertToSelf
0x18003d117  nop     dword ptr [rax+rax+00h]
0x18003d11c  test    eax, eax
0x18003d11e  jnz     loc_18003D63B
0x18003d124  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d12b  test    edi, edi
0x18003d12d  js      loc_18003D651
0x18003d133  xor     eax, eax
0x18003d135  mov     [rbp+57h+var_64], 14h
0x18003d13c  mov     [rbp+57h+var_60.Privilege.Attributes], eax
0x18003d13f  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18003d143  lea     rax, [rbp+57h+var_6C]
0x18003d147  mov     [rbp+57h+var_68], r15d
0x18003d14b  mov     [rsp+0C0h+AccessStatus], rax; AccessStatus
0x18003d150  xorps   xmm0, xmm0
0x18003d153  lea     rax, [rbp+57h+var_68]
0x18003d157  mov     [rbp+57h+var_6C], r15d
0x18003d15b  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x18003d160  xorps   xmm1, xmm1
0x18003d163  lea     rax, [rbp+57h+var_64]
0x18003d167  mov     r8d, 20000h; DesiredAccess
0x18003d16d  mov     [rsp+0C0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18003d172  mov     rdx, rsi; ClientToken
0x18003d175  lea     rax, [rbp+57h+var_60]
0x18003d179  mov     rcx, rbx; pSecurityDescriptor
0x18003d17c  mov     [rsp+0C0h+PrivilegeSet], rax; PrivilegeSet
0x18003d181  movups  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x18003d185  movups  xmmword ptr [rbp+57h+var_60.PrivilegeCount], xmm1
0x18003d189  call    cs:__imp_AccessCheck
0x18003d190  nop     dword ptr [rax+rax+00h]
0x18003d195  test    eax, eax
0x18003d197  jz      loc_18003D4F3
0x18003d19d  mov     ebx, [rbp+57h+var_6C]
0x18003d1a0  mov     edi, r15d
0x18003d1a3  mov     rcx, rsi
0x18003d1a6  call    cs:__imp_FwCloseHandle
0x18003d1ad  nop     dword ptr [rax+rax+00h]
0x18003d1b2  mov     eax, 80070005h
0x18003d1b7  test    edi, edi
0x18003d1b9  js      loc_18003D671
0x18003d1bf  test    ebx, ebx
0x18003d1c1  jz      loc_18003D36F
0x18003d1c7  lea     rcx, [rbp+57h+pfEnabled]; pfEnabled
0x18003d1cb  mov     [rbp+57h+pfEnabled], r15b
0x18003d1cf  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x18003d1d6  nop     dword ptr [rax+rax+00h]
0x18003d1db  test    eax, eax
0x18003d1dd  js      short loc_18003D1EC
0x18003d1df  mov     rsi, cs:qword_180132A40
0x18003d1e6  cmp     [rbp+57h+pfEnabled], r15b
0x18003d1ea  jnz     short loc_18003D1F3
0x18003d1ec  mov     rsi, cs:qword_180132A28
0x18003d1f3  mov     rcx, r13; BindingHandle
0x18003d1f6  mov     [rbp+57h+TokenHandle], r15
0x18003d1fa  call    cs:__imp_RpcImpersonateClient
0x18003d201  nop     dword ptr [rax+rax+00h]
0x18003d206  mov     ebx, eax
0x18003d208  test    eax, eax
0x18003d20a  jnz     loc_18003D549
0x18003d210  call    cs:__imp_GetCurrentThread
0x18003d217  nop     dword ptr [rax+rax+00h]
0x18003d21c  mov     rcx, rax; ThreadHandle
0x18003d21f  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18003d223  lea     edx, [rbx+8]; DesiredAccess
0x18003d226  lea     r8d, [rbx+1]; OpenAsSelf
0x18003d22a  call    cs:__imp_OpenThreadToken
0x18003d231  nop     dword ptr [rax+rax+00h]
0x18003d236  test    eax, eax
0x18003d238  jz      loc_18003D588
0x18003d23e  mov     r15, [rbp+57h+TokenHandle]
0x18003d242  test    r15, r15
0x18003d245  jz      loc_18003D698
0x18003d24b  call    cs:__imp_RpcRevertToSelf
0x18003d252  nop     dword ptr [rax+rax+00h]
0x18003d257  test    eax, eax
0x18003d259  jnz     loc_18003D6A6
0x18003d25f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d266  test    ebx, ebx
0x18003d268  js      loc_18003D6BC
0x18003d26e  xor     eax, eax
0x18003d270  mov     [rbp+57h+var_68], 14h
0x18003d277  mov     [rbp+57h+var_60.Privilege.Attributes], eax
0x18003d27a  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18003d27e  mov     [rbp+57h+var_64], eax
0x18003d281  xorps   xmm0, xmm0
0x18003d284  mov     [rbp+57h+var_6C], eax
0x18003d287  xorps   xmm1, xmm1
0x18003d28a  lea     rax, [rbp+57h+var_6C]
0x18003d28e  mov     r8d, 20000h; DesiredAccess
0x18003d294  mov     [rsp+0C0h+AccessStatus], rax; AccessStatus
0x18003d299  mov     rdx, r15; ClientToken
0x18003d29c  lea     rax, [rbp+57h+var_64]
0x18003d2a0  mov     rcx, rsi; pSecurityDescriptor
0x18003d2a3  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x18003d2a8  lea     rax, [rbp+57h+var_68]
0x18003d2ac  mov     [rsp+0C0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18003d2b1  lea     rax, [rbp+57h+var_60]
0x18003d2b5  mov     [rsp+0C0h+PrivilegeSet], rax; PrivilegeSet
0x18003d2ba  movups  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x18003d2be  movups  xmmword ptr [rbp+57h+var_60.PrivilegeCount], xmm1
0x18003d2c2  call    cs:__imp_AccessCheck
0x18003d2c9  nop     dword ptr [rax+rax+00h]
0x18003d2ce  test    eax, eax
0x18003d2d0  jz      loc_18003D5D7
0x18003d2d6  mov     esi, [rbp+57h+var_6C]
0x18003d2d9  xor     ebx, ebx
0x18003d2db  mov     rcx, r15
0x18003d2de  call    cs:__imp_FwCloseHandle
0x18003d2e5  nop     dword ptr [rax+rax+00h]
0x18003d2ea  test    ebx, ebx
0x18003d2ec  js      loc_18003D6D9
0x18003d2f2  test    esi, esi
0x18003d2f4  jz      loc_18003D3A8
0x18003d2fa  test    edi, edi
0x18003d2fc  js      short loc_18003D35B
0x18003d2fe  mov     rdx, [rbp+57h+var_80]; void **
0x18003d302  mov     rcx, r13; void *
0x18003d305  call    ?SvrImpl_FWClosePolicyStore@@YAKPEAXPEAPEAX@Z; SvrImpl_FWClosePolicyStore(void *,void * *)
0x18003d30a  mov     rcx, cs:g_Provider
0x18003d311  mov     ebx, eax
0x18003d313  test    rcx, rcx
0x18003d316  jz      short loc_18003D331
0x18003d318  xor     r9d, r9d
0x18003d31b  lea     rdx, MPS_SVC_API_Exit_ClosePolicyStore
0x18003d322  xor     r8d, r8d
0x18003d325  call    cs:__imp_EtwEventWrite
0x18003d32c  nop     dword ptr [rax+rax+00h]
0x18003d331  mov     eax, ebx
0x18003d333  mov     rcx, [rbp+57h+var_38]
0x18003d337  xor     rcx, rsp; StackCookie
0x18003d33a  call    __security_check_cookie
0x18003d33f  mov     rbx, [rsp+0C0h+arg_10]
0x18003d347  add     rsp, 90h
0x18003d34e  pop     r15
0x18003d350  pop     r14
0x18003d352  pop     r13
0x18003d354  pop     r12
0x18003d356  pop     rdi
0x18003d357  pop     rsi
0x18003d358  pop     rbp
0x18003d359  retn
0x18003d35b  test    ebx, ebx
0x18003d35d  jns     short loc_18003D2FE
0x18003d35f  mov     ecx, edi
0x18003d361  call    cs:__imp_FwHResultToWindowsError
0x18003d368  nop     dword ptr [rax+rax+00h]
0x18003d36d  jmp     short loc_18003D30A
0x18003d36f  mov     edi, eax
0x18003d371  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d378  cmp     rcx, r14
0x18003d37b  jz      loc_18003D1C7
0x18003d381  test    byte ptr [rcx+1Ch], 1
0x18003d385  jz      loc_18003D1C7
0x18003d38b  mov     edx, 11h
0x18003d390  mov     r9d, eax
0x18003d393  mov     rcx, [rcx+10h]
0x18003d397  lea     r8, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x18003d39e  call    WPP_SF_d
0x18003d3a3  jmp     loc_18003D1C7
0x18003d3a8  mov     r9d, 80070005h
0x18003d3ae  mov     ebx, r9d
0x18003d3b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d3b8  cmp     rcx, r14
0x18003d3bb  jz      loc_18003D2FA
0x18003d3c1  test    byte ptr [rcx+1Ch], 1
0x18003d3c5  jz      loc_18003D2FA
0x18003d3cb  mov     edx, 11h
0x18003d3d0  mov     rcx, [rcx+10h]
0x18003d3d4  lea     r8, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x18003d3db  call    WPP_SF_d
0x18003d3e0  jmp     loc_18003D2FA
0x18003d3e5  mov     ebx, r15d
0x18003d3e8  test    edi, edi
0x18003d3ea  jns     loc_18003D1A3
0x18003d3f0  cmp     rcx, r14
0x18003d3f3  jz      loc_18003D1A3
0x18003d3f9  test    byte ptr [rcx+1Ch], 1
0x18003d3fd  jz      loc_18003D1A3
0x18003d403  mov     edx, 25h ; '%'
0x18003d408  mov     rcx, [rcx+10h]
0x18003d40c  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003d413  mov     r9d, edi
0x18003d416  call    WPP_SF_d
0x18003d41b  jmp     loc_18003D1A3
0x18003d420  xor     esi, esi
0x18003d422  test    ebx, ebx
0x18003d424  jns     loc_18003D2DB
0x18003d42a  cmp     rcx, r14
0x18003d42d  jz      loc_18003D2DB
0x18003d433  test    byte ptr [rcx+1Ch], 1
0x18003d437  jz      loc_18003D2DB
0x18003d43d  lea     edx, [rsi+25h]
0x18003d440  mov     rcx, [rcx+10h]
0x18003d444  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003d44b  mov     r9d, ebx
0x18003d44e  call    WPP_SF_d
0x18003d453  jmp     loc_18003D2DB
0x18003d458  mov     r12d, 80070000h
0x18003d45e  jle     short loc_18003D466
0x18003d460  movzx   edi, ax
0x18003d463  or      edi, r12d
0x18003d466  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d46d  lea     r14, WPP_GLOBAL_Control
0x18003d474  cmp     rcx, r14
0x18003d477  jz      loc_18003D12B
0x18003d47d  test    byte ptr [rcx+1Ch], 1
0x18003d481  jz      loc_18003D12B
0x18003d487  mov     rcx, [rcx+10h]
0x18003d48b  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003d492  mov     edx, 22h ; '"'
0x18003d497  mov     r9d, edi
0x18003d49a  call    WPP_SF_d
0x18003d49f  jmp     loc_18003D124
0x18003d4a4  call    cs:__imp_GetLastError
0x18003d4ab  nop     dword ptr [rax+rax+00h]
0x18003d4b0  mov     edi, eax
0x18003d4b2  test    eax, eax
0x18003d4b4  jle     short loc_18003D4BC
0x18003d4b6  movzx   edi, ax
0x18003d4b9  or      edi, r12d
0x18003d4bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d4c3  cmp     rcx, r14
0x18003d4c6  jz      loc_18003D110
0x18003d4cc  test    byte ptr [rcx+1Ch], 1
0x18003d4d0  jz      loc_18003D110
0x18003d4d6  mov     rcx, [rcx+10h]
0x18003d4da  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003d4e1  mov     edx, 23h ; '#'
0x18003d4e6  mov     r9d, edi
0x18003d4e9  call    WPP_SF_d
0x18003d4ee  jmp     loc_18003D110
0x18003d4f3  call    cs:__imp_GetLastError
0x18003d4fa  nop     dword ptr [rax+rax+00h]
0x18003d4ff  mov     edi, eax
0x18003d501  test    eax, eax
0x18003d503  jle     short loc_18003D50B
0x18003d505  movzx   edi, ax
0x18003d508  or      edi, r12d
0x18003d50b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d512  cmp     rcx, r14
0x18003d515  jz      loc_18003D3E5
0x18003d51b  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
