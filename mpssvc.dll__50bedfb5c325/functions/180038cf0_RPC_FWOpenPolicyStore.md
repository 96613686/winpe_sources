# RPC_FWOpenPolicyStore

- ea: `0x180038cf0`
- end: `0x180039415`
- name: `RPC_FWOpenPolicyStore`
- size: `1829`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, int, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800089bc`
- `0x18000a710`
- `0x180038cf0`
- `0x18003941c`
- `0x180039644`
- `0x18006a710`
- `0x1800729c0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180038d4b`
- `ntdll!EtwEventWrite` at `0x180039047`
- `ntdll!EtwEventWrite` at `0x180038d4b`
- `ntdll!EtwEventWrite` at `0x180039047`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038dc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038f19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038dc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038f19`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038dde`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038f33`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038dde`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003920b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800392a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800392ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003920b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800392a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800392ef`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180038e80`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180038fc8`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180038e80`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180038fc8`
- `RPCRT4!RpcImpersonateClient` at `0x180038dae`
- `RPCRT4!RpcImpersonateClient` at `0x180038f03`
- `RPCRT4!RpcImpersonateClient` at `0x180038dae`
- `RPCRT4!RpcImpersonateClient` at `0x180038f03`
- `RPCRT4!RpcRevertToSelf` at `0x180038e0c`
- `RPCRT4!RpcRevertToSelf` at `0x180038f54`
- `RPCRT4!RpcRevertToSelf` at `0x180038e0c`
- `RPCRT4!RpcRevertToSelf` at `0x180038f54`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x180038d6e`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x180038ec5`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x180038d6e`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x180038ec5`
- `fwbase!FwHResultToWindowsError` at `0x18003907c`
- `fwbase!FwHResultToWindowsError` at `0x18003907c`
- `fwbase!FwCloseHandle` at `0x180038e9c`
- `fwbase!FwCloseHandle` at `0x180038fe4`
- `fwbase!FwCloseHandle` at `0x180038e9c`
- `fwbase!FwCloseHandle` at `0x180038fe4`

## string_xrefs

- `0x180039356`: `mpssvc.dll`
- `0x1800393be`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall RPC_FWOpenPolicyStore(
        void *a1,
        unsigned __int16 a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        __int64 a6)
{
  void *v6; // rdi
  PSECURITY_DESCRIPTOR v7; // rbx
  void *v8; // rsi
  DWORD v9; // r15d
  RPC_STATUS v10; // eax
  signed int v11; // edi
  HANDLE CurrentThread; // rax
  unsigned int v13; // eax
  __int64 v14; // rcx
  WINBOOL v15; // ebx
  PSECURITY_DESCRIPTOR v16; // rsi
  DWORD v17; // r12d
  void *v18; // r15
  RPC_STATUS v19; // eax
  signed int v20; // ebx
  HANDLE v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rcx
  WINBOOL v24; // esi
  unsigned int v25; // eax
  unsigned int v26; // ebx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  __int64 v31; // r9
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rdx
  signed int LastError; // eax
  signed int v37; // eax
  signed int v38; // eax
  signed int v39; // eax
  void *TokenHandle; // [rsp+60h] [rbp-49h] BYREF
  BOOLEAN pfEnabled[4]; // [rsp+68h] [rbp-41h] BYREF
  WINBOOL AccessStatus; // [rsp+6Ch] [rbp-3Dh] BYREF
  DWORD GrantedAccess; // [rsp+70h] [rbp-39h] BYREF
  DWORD PrivilegeSetLength; // [rsp+74h] [rbp-35h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+78h] [rbp-31h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+90h] [rbp-19h] BYREF

  v6 = a1;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_API_Enter_OpenPolicyStore, 0, 0);
  if ( (unsigned int)IsRPCClientNAPAgentService(v6) )
    goto LABEL_36;
  pfEnabled[0] = 0;
  if ( BCryptGetFipsAlgorithmMode(pfEnabled) < 0 || (v7 = pSecurityDescriptor, !pfEnabled[0]) )
    v7 = (PSECURITY_DESCRIPTOR)qword_180132A18;
  TokenHandle = 0;
  v8 = 0;
  v9 = *((_DWORD *)&AccessCheckAccessRights + (int)a4);
  v10 = RpcImpersonateClient(v6);
  v11 = v10;
  if ( !v10 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v8 = TokenHandle;
      if ( !TokenHandle )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v8 = TokenHandle;
      }
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          35,
          WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
          (unsigned int)v11);
    }
    v13 = RpcRevertToSelf();
    if ( v13 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v13, 0);
    goto LABEL_13;
  }
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  v14 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      34,
      WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
      (unsigned int)v11);
LABEL_13:
    v14 = WPP_GLOBAL_Control;
  }
  if ( v11 < 0 )
  {
    v15 = 0;
    if ( (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 1) != 0 )
    {
      v34 = 36;
      goto LABEL_54;
    }
  }
  else
  {
    PrivilegeSetLength = 20;
    GrantedAccess = 0;
    AccessStatus = 0;
    GenericMapping = 0;
    memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
    if ( AccessCheck(v7, v8, v9, &GenericMapping, &PrivilegeSet, &PrivilegeSetLength, &GrantedAccess, &AccessStatus) )
    {
      v15 = AccessStatus;
      v11 = 0;
      goto LABEL_17;
    }
    v37 = GetLastError();
    v11 = v37;
    if ( v37 > 0 )
      v11 = (unsigned __int16)v37 | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        38,
        WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
        (unsigned int)v11);
      v14 = WPP_GLOBAL_Control;
    }
    v15 = 0;
    if ( v11 < 0 && (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 1) != 0 )
    {
      v34 = 37;
LABEL_54:
      WPP_SF_d(*(_QWORD *)(v14 + 16), v34, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, (unsigned int)v11);
    }
  }
LABEL_17:
  FwCloseHandle(v8);
  if ( v11 < 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v29 = 16;
      v30 = (unsigned int)v11;
      goto LABEL_45;
    }
  }
  else if ( !v15 )
  {
    v11 = -2147024891;
    v28 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v29 = 17;
      v30 = 2147942405LL;
LABEL_45:
      WPP_SF_d(*(_QWORD *)(v28 + 16), v29, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids, v30);
    }
  }
  pfEnabled[0] = 0;
  if ( BCryptGetFipsAlgorithmMode(pfEnabled) < 0 || (v16 = qword_180132A40, !pfEnabled[0]) )
    v16 = (PSECURITY_DESCRIPTOR)qword_180132A28;
  v17 = *((_DWORD *)&AccessCheckAccessRights + (int)a4);
  v18 = 0;
  TokenHandle = 0;
  v19 = RpcImpersonateClient(a1);
  v20 = v19;
  if ( !v19 )
  {
    v21 = GetCurrentThread();
    if ( OpenThreadToken(v21, 8u, 1, &TokenHandle) )
    {
      v18 = TokenHandle;
      if ( !TokenHandle )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v18 = TokenHandle;
      }
    }
    else
    {
      v38 = GetLastError();
      v20 = v38;
      if ( v38 > 0 )
        v20 = (unsigned __int16)v38 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          35,
          WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
          (unsigned int)v20);
    }
    v22 = RpcRevertToSelf();
    if ( v22 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v22, 0);
    goto LABEL_28;
  }
  if ( v19 > 0 )
    v20 = (unsigned __int16)v19 | 0x80070000;
  v23 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      34,
      WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
      (unsigned int)v20);
LABEL_28:
    v23 = WPP_GLOBAL_Control;
  }
  if ( v20 < 0 )
  {
    v24 = 0;
    if ( (_UNKNOWN *)v23 != &WPP_GLOBAL_Control && (*(_BYTE *)(v23 + 28) & 1) != 0 )
    {
      v35 = 36;
      goto LABEL_59;
    }
  }
  else
  {
    GrantedAccess = 20;
    PrivilegeSetLength = 0;
    AccessStatus = 0;
    GenericMapping = 0;
    memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
    if ( AccessCheck(v16, v18, v17, &GenericMapping, &PrivilegeSet, &GrantedAccess, &PrivilegeSetLength, &AccessStatus) )
    {
      v24 = AccessStatus;
      v20 = 0;
      goto LABEL_32;
    }
    v39 = GetLastError();
    v20 = v39;
    if ( v39 > 0 )
      v20 = (unsigned __int16)v39 | 0x80070000;
    v23 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        38,
        WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
        (unsigned int)v20);
      v23 = WPP_GLOBAL_Control;
    }
    v24 = 0;
    if ( v20 < 0 && (_UNKNOWN *)v23 != &WPP_GLOBAL_Control && (*(_BYTE *)(v23 + 28) & 1) != 0 )
    {
      v35 = 37;
LABEL_59:
      WPP_SF_d(*(_QWORD *)(v23 + 16), v35, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, (unsigned int)v20);
    }
  }
LABEL_32:
  FwCloseHandle(v18);
  if ( v20 < 0 )
  {
    v32 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v33 = 16;
      v31 = (unsigned int)v20;
      goto LABEL_49;
    }
  }
  else if ( !v24 )
  {
    v31 = 2147942405LL;
    v20 = -2147024891;
    v32 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v33 = 17;
LABEL_49:
      WPP_SF_d(*(_QWORD *)(v32 + 16), v33, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids, v31);
    }
  }
  if ( v11 >= 0 || v20 >= 0 )
  {
    v6 = a1;
LABEL_36:
    v25 = SvrImpl_FWOpenPolicyStore(v6, a2, a3, a4, a5, a6);
    goto LABEL_37;
  }
  v25 = FwHResultToWindowsError((unsigned int)v11);
LABEL_37:
  v26 = v25;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_API_Exit_OpenPolicyStore, 0, 0);
  return v26;
}

```

## disassembly

```asm
0x180038cf0  push    rbp
0x180038cf2  push    rbx
0x180038cf3  push    rsi
0x180038cf4  push    rdi
0x180038cf5  push    r12
0x180038cf7  push    r13
0x180038cf9  push    r14
0x180038cfb  push    r15
0x180038cfd  lea     rbp, [rsp-0Fh]
0x180038d02  sub     rsp, 0B8h
0x180038d09  mov     rax, cs:__security_cookie
0x180038d10  xor     rax, rsp
0x180038d13  mov     [rbp+47h+var_50], rax
0x180038d17  mov     rax, [rbp+47h+arg_28]
0x180038d1b  mov     rdi, rcx
0x180038d1e  mov     [rbp+47h+BindingHandle], rcx
0x180038d22  mov     rcx, cs:g_Provider
0x180038d29  mov     [rbp+47h+var_AC], r9d
0x180038d2d  mov     [rbp+47h+var_A8], r8d
0x180038d31  mov     [rbp+47h+var_B0], dx
0x180038d35  mov     [rbp+47h+var_98], rax
0x180038d39  test    rcx, rcx
0x180038d3c  jz      short loc_180038D57
0x180038d3e  xor     r9d, r9d
0x180038d41  lea     rdx, MPS_SVC_API_Enter_OpenPolicyStore
0x180038d48  xor     r8d, r8d
0x180038d4b  call    cs:__imp_EtwEventWrite
0x180038d52  nop     dword ptr [rax+rax+00h]
0x180038d57  mov     rcx, rdi; void *
0x180038d5a  call    ?IsRPCClientNAPAgentService@@YAHPEAX@Z; IsRPCClientNAPAgentService(void *)
0x180038d5f  test    eax, eax
0x180038d61  jnz     loc_180039008
0x180038d67  lea     rcx, [rbp+47h+pfEnabled]; pfEnabled
0x180038d6b  mov     [rbp+47h+pfEnabled], al
0x180038d6e  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x180038d75  nop     dword ptr [rax+rax+00h]
0x180038d7a  test    eax, eax
0x180038d7c  js      short loc_180038D8B
0x180038d7e  cmp     [rbp+47h+pfEnabled], 0
0x180038d82  mov     rbx, cs:pSecurityDescriptor
0x180038d89  jnz     short loc_180038D92
0x180038d8b  mov     rbx, cs:qword_180132A18
0x180038d92  movsxd  r12, [rbp+47h+var_AC]
0x180038d96  lea     rax, ?AccessCheckAccessRights@@3PAKA; ulong near * AccessCheckAccessRights
0x180038d9d  mov     rcx, rdi; BindingHandle
0x180038da0  mov     [rbp+47h+TokenHandle], 0
0x180038da8  xor     esi, esi
0x180038daa  mov     r15d, [rax+r12*4]
0x180038dae  call    cs:__imp_RpcImpersonateClient
0x180038db5  nop     dword ptr [rax+rax+00h]
0x180038dba  mov     edi, eax
0x180038dbc  test    eax, eax
0x180038dbe  jnz     loc_180039170
0x180038dc4  call    cs:__imp_GetCurrentThread
0x180038dcb  nop     dword ptr [rax+rax+00h]
0x180038dd0  mov     rcx, rax; ThreadHandle
0x180038dd3  lea     r9, [rbp+47h+TokenHandle]; TokenHandle
0x180038dd7  lea     edx, [rsi+8]; DesiredAccess
0x180038dda  lea     r8d, [rsi+1]; OpenAsSelf
0x180038dde  call    cs:__imp_OpenThreadToken
0x180038de5  nop     dword ptr [rax+rax+00h]
0x180038dea  mov     r13d, 80070000h
0x180038df0  lea     r14, WPP_GLOBAL_Control
0x180038df7  test    eax, eax
0x180038df9  jz      loc_1800391BC
0x180038dff  mov     rsi, [rbp+47h+TokenHandle]
0x180038e03  test    rsi, rsi
0x180038e06  jz      loc_180039345
0x180038e0c  call    cs:__imp_RpcRevertToSelf
0x180038e13  nop     dword ptr [rax+rax+00h]
0x180038e18  test    eax, eax
0x180038e1a  jnz     loc_180039353
0x180038e20  mov     rcx, cs:WPP_GLOBAL_Control
0x180038e27  test    edi, edi
0x180038e29  js      loc_180039369
0x180038e2f  xor     eax, eax
0x180038e31  mov     [rbp+47h+var_7C], 14h
0x180038e38  mov     [rbp+47h+var_78.Privilege.Attributes], eax
0x180038e3b  lea     r9, [rbp+47h+GenericMapping]; GenericMapping
0x180038e3f  mov     [rbp+47h+var_80], eax
0x180038e42  xorps   xmm0, xmm0
0x180038e45  mov     [rbp+47h+var_84], eax
0x180038e48  xorps   xmm1, xmm1
0x180038e4b  lea     rax, [rbp+47h+var_84]
0x180038e4f  mov     r8d, r15d; DesiredAccess
0x180038e52  mov     [rsp+0F0h+AccessStatus], rax; AccessStatus
0x180038e57  mov     rdx, rsi; ClientToken
0x180038e5a  lea     rax, [rbp+47h+var_80]
0x180038e5e  mov     rcx, rbx; pSecurityDescriptor
0x180038e61  mov     [rsp+0F0h+GrantedAccess], rax; GrantedAccess
0x180038e66  lea     rax, [rbp+47h+var_7C]
0x180038e6a  mov     [rsp+0F0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180038e6f  lea     rax, [rbp+47h+var_78]
0x180038e73  mov     [rsp+0F0h+PrivilegeSet], rax; PrivilegeSet
0x180038e78  movups  xmmword ptr [rbp+47h+GenericMapping.GenericRead], xmm0
0x180038e7c  movups  xmmword ptr [rbp+47h+var_78.PrivilegeCount], xmm1
0x180038e80  call    cs:__imp_AccessCheck
0x180038e87  nop     dword ptr [rax+rax+00h]
0x180038e8c  test    eax, eax
0x180038e8e  jz      loc_18003920B
0x180038e94  mov     ebx, [rbp+47h+var_84]
0x180038e97  xor     edi, edi
0x180038e99  mov     rcx, rsi
0x180038e9c  call    cs:__imp_FwCloseHandle
0x180038ea3  nop     dword ptr [rax+rax+00h]
0x180038ea8  mov     eax, 80070005h
0x180038ead  test    edi, edi
0x180038eaf  js      loc_180039386
0x180038eb5  test    ebx, ebx
0x180038eb7  jz      loc_18003908A
0x180038ebd  lea     rcx, [rbp+47h+pfEnabled]; pfEnabled
0x180038ec1  mov     [rbp+47h+pfEnabled], 0
0x180038ec5  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x180038ecc  nop     dword ptr [rax+rax+00h]
0x180038ed1  test    eax, eax
0x180038ed3  js      short loc_180038EE2
0x180038ed5  cmp     [rbp+47h+pfEnabled], 0
0x180038ed9  mov     rsi, cs:qword_180132A40
0x180038ee0  jnz     short loc_180038EE9
0x180038ee2  mov     rsi, cs:qword_180132A28
0x180038ee9  mov     rcx, [rbp+47h+BindingHandle]; BindingHandle
0x180038eed  lea     rax, ?AccessCheckAccessRights@@3PAKA; ulong near * AccessCheckAccessRights
0x180038ef4  mov     r12d, [rax+r12*4]
0x180038ef8  xor     r15d, r15d
0x180038efb  mov     [rbp+47h+TokenHandle], 0
0x180038f03  call    cs:__imp_RpcImpersonateClient
0x180038f0a  nop     dword ptr [rax+rax+00h]
0x180038f0f  mov     ebx, eax
0x180038f11  test    eax, eax
0x180038f13  jnz     loc_180039261
0x180038f19  call    cs:__imp_GetCurrentThread
0x180038f20  nop     dword ptr [rax+rax+00h]
0x180038f25  mov     rcx, rax; ThreadHandle
0x180038f28  lea     r9, [rbp+47h+TokenHandle]; TokenHandle
0x180038f2c  lea     edx, [rbx+8]; DesiredAccess
0x180038f2f  lea     r8d, [r15+1]; OpenAsSelf
0x180038f33  call    cs:__imp_OpenThreadToken
0x180038f3a  nop     dword ptr [rax+rax+00h]
0x180038f3f  test    eax, eax
0x180038f41  jz      loc_1800392A0
0x180038f47  mov     r15, [rbp+47h+TokenHandle]
0x180038f4b  test    r15, r15
0x180038f4e  jz      loc_1800393AD
0x180038f54  call    cs:__imp_RpcRevertToSelf
0x180038f5b  nop     dword ptr [rax+rax+00h]
0x180038f60  test    eax, eax
0x180038f62  jnz     loc_1800393BB
0x180038f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180038f6f  test    ebx, ebx
0x180038f71  js      loc_1800393D1
0x180038f77  xor     eax, eax
0x180038f79  mov     [rbp+47h+var_80], 14h
0x180038f80  mov     [rbp+47h+var_78.Privilege.Attributes], eax
0x180038f83  lea     r9, [rbp+47h+GenericMapping]; GenericMapping
0x180038f87  mov     [rbp+47h+var_7C], eax
0x180038f8a  xorps   xmm0, xmm0
0x180038f8d  mov     [rbp+47h+var_84], eax
0x180038f90  xorps   xmm1, xmm1
0x180038f93  lea     rax, [rbp+47h+var_84]
0x180038f97  mov     r8d, r12d; DesiredAccess
0x180038f9a  mov     [rsp+0F0h+AccessStatus], rax; AccessStatus
0x180038f9f  mov     rdx, r15; ClientToken
0x180038fa2  lea     rax, [rbp+47h+var_7C]
0x180038fa6  mov     rcx, rsi; pSecurityDescriptor
0x180038fa9  mov     [rsp+0F0h+GrantedAccess], rax; GrantedAccess
0x180038fae  lea     rax, [rbp+47h+var_80]
0x180038fb2  mov     [rsp+0F0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180038fb7  lea     rax, [rbp+47h+var_78]
0x180038fbb  mov     [rsp+0F0h+PrivilegeSet], rax; PrivilegeSet
0x180038fc0  movups  xmmword ptr [rbp+47h+GenericMapping.GenericRead], xmm0
0x180038fc4  movups  xmmword ptr [rbp+47h+var_78.PrivilegeCount], xmm1
0x180038fc8  call    cs:__imp_AccessCheck
0x180038fcf  nop     dword ptr [rax+rax+00h]
0x180038fd4  test    eax, eax
0x180038fd6  jz      loc_1800392EF
0x180038fdc  mov     esi, [rbp+47h+var_84]
0x180038fdf  xor     ebx, ebx
0x180038fe1  mov     rcx, r15
0x180038fe4  call    cs:__imp_FwCloseHandle
0x180038feb  nop     dword ptr [rax+rax+00h]
0x180038ff0  test    ebx, ebx
0x180038ff2  js      loc_1800393EE
0x180038ff8  test    esi, esi
0x180038ffa  jz      loc_1800390C3
0x180039000  test    edi, edi
0x180039002  js      short loc_180039076
0x180039004  mov     rdi, [rbp+47h+BindingHandle]
0x180039008  mov     rax, [rbp+47h+var_98]
0x18003900c  mov     rcx, rdi
0x18003900f  mov     r9d, [rbp+47h+var_AC]
0x180039013  mov     r8d, [rbp+47h+var_A8]
0x180039017  movzx   edx, [rbp+47h+var_B0]
0x18003901b  mov     [rsp+0F0h+PrivilegeSetLength], rax
0x180039020  mov     eax, [rbp+47h+arg_20]
0x180039023  mov     dword ptr [rsp+0F0h+PrivilegeSet], eax
0x180039027  call    ?SvrImpl_FWOpenPolicyStore@@YAKPEAXGW4_tag_FW_STORE_TYPE@@W4_tag_FW_POLICY_ACCESS_RIGHT@@KPEAPEAX@Z; SvrImpl_FWOpenPolicyStore(void *,ushort,_tag_FW_STORE_TYPE,_tag_FW_POLICY_ACCESS_RIGHT,ulong,void * *)
0x18003902c  mov     rcx, cs:g_Provider
0x180039033  mov     ebx, eax
0x180039035  test    rcx, rcx
0x180039038  jz      short loc_180039053
0x18003903a  xor     r9d, r9d
0x18003903d  lea     rdx, MPS_SVC_API_Exit_OpenPolicyStore
0x180039044  xor     r8d, r8d
0x180039047  call    cs:__imp_EtwEventWrite
0x18003904e  nop     dword ptr [rax+rax+00h]
0x180039053  mov     eax, ebx
0x180039055  mov     rcx, [rbp+47h+var_50]
0x180039059  xor     rcx, rsp; StackCookie
0x18003905c  call    __security_check_cookie
0x180039061  add     rsp, 0B8h
0x180039068  pop     r15
0x18003906a  pop     r14
0x18003906c  pop     r13
0x18003906e  pop     r12
0x180039070  pop     rdi
0x180039071  pop     rsi
0x180039072  pop     rbx
0x180039073  pop     rbp
0x180039074  retn
0x180039076  test    ebx, ebx
0x180039078  jns     short loc_180039004
0x18003907a  mov     ecx, edi
0x18003907c  call    cs:__imp_FwHResultToWindowsError
0x180039083  nop     dword ptr [rax+rax+00h]
0x180039088  jmp     short loc_18003902C
0x18003908a  mov     edi, eax
0x18003908c  mov     rcx, cs:WPP_GLOBAL_Control
0x180039093  cmp     rcx, r14
0x180039096  jz      loc_180038EBD
0x18003909c  test    byte ptr [rcx+1Ch], 1
0x1800390a0  jz      loc_180038EBD
0x1800390a6  mov     edx, 11h
0x1800390ab  mov     r9d, eax
0x1800390ae  mov     rcx, [rcx+10h]
0x1800390b2  lea     r8, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x1800390b9  call    WPP_SF_d
0x1800390be  jmp     loc_180038EBD
0x1800390c3  mov     r9d, 80070005h
0x1800390c9  mov     ebx, r9d
0x1800390cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800390d3  cmp     rcx, r14
0x1800390d6  jz      loc_180039000
0x1800390dc  test    byte ptr [rcx+1Ch], 1
0x1800390e0  jz      loc_180039000
0x1800390e6  mov     edx, 11h
0x1800390eb  mov     rcx, [rcx+10h]
0x1800390ef  lea     r8, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x1800390f6  call    WPP_SF_d
0x1800390fb  jmp     loc_180039000
0x180039100  xor     ebx, ebx
0x180039102  test    edi, edi
0x180039104  jns     loc_180038E99
0x18003910a  cmp     rcx, r14
0x18003910d  jz      loc_180038E99
0x180039113  test    byte ptr [rcx+1Ch], 1
0x180039117  jz      loc_180038E99
0x18003911d  lea     edx, [rbx+25h]
0x180039120  mov     rcx, [rcx+10h]
0x180039124  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003912b  mov     r9d, edi
0x18003912e  call    WPP_SF_d
0x180039133  jmp     loc_180038E99
0x180039138  xor     esi, esi
0x18003913a  test    ebx, ebx
0x18003913c  jns     loc_180038FE1
0x180039142  cmp     rcx, r14
0x180039145  jz      loc_180038FE1
0x18003914b  test    byte ptr [rcx+1Ch], 1
0x18003914f  jz      loc_180038FE1
0x180039155  lea     edx, [rsi+25h]
0x180039158  mov     rcx, [rcx+10h]
0x18003915c  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180039163  mov     r9d, ebx
0x180039166  call    WPP_SF_d
0x18003916b  jmp     loc_180038FE1
0x180039170  mov     r13d, 80070000h
0x180039176  jle     short loc_18003917E
0x180039178  movzx   edi, ax
0x18003917b  or      edi, r13d
0x18003917e  mov     rcx, cs:WPP_GLOBAL_Control
0x180039185  lea     r14, WPP_GLOBAL_Control
0x18003918c  cmp     rcx, r14
0x18003918f  jz      loc_180038E27
0x180039195  test    byte ptr [rcx+1Ch], 1
0x180039199  jz      loc_180038E27
0x18003919f  mov     rcx, [rcx+10h]
0x1800391a3  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x1800391aa  mov     edx, 22h ; '"'
0x1800391af  mov     r9d, edi
0x1800391b2  call    WPP_SF_d
0x1800391b7  jmp     loc_180038E20
0x1800391bc  call    cs:__imp_GetLastError
0x1800391c3  nop     dword ptr [rax+rax+00h]
0x1800391c8  mov     edi, eax
0x1800391ca  test    eax, eax
0x1800391cc  jle     short loc_1800391D4
0x1800391ce  movzx   edi, ax
0x1800391d1  or      edi, r13d
0x1800391d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391db  cmp     rcx, r14
  ... truncated ...
```
