# RPC_FWOpenPolicyStore

- ea: `0x18003b580`
- end: `0x18003bc26`
- name: `RPC_FWOpenPolicyStore`
- size: `1702`
- prototype: `__int64 __fastcall(void *, unsigned __int16, unsigned int, unsigned int, int, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800093b0`
- `0x18000af3c`
- `0x18003b580`
- `0x18003bc2c`
- `0x18003be24`
- `0x1800670c0`
- `0x18006f520`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18003b5db`
- `ntdll!EtwEventWrite` at `0x18003b87d`
- `ntdll!EtwEventWrite` at `0x18003b5db`
- `ntdll!EtwEventWrite` at `0x18003b87d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003b656`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003b781`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003b656`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003b781`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003b642`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003b76d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003b642`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003b76d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b9e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ba2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003babd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bb06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b9e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ba2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003babd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bb06`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18003b6ec`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18003b80a`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18003b6ec`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18003b80a`
- `RPCRT4!RpcRevertToSelf` at `0x18003b67e`
- `RPCRT4!RpcRevertToSelf` at `0x18003b79c`
- `RPCRT4!RpcRevertToSelf` at `0x18003b67e`
- `RPCRT4!RpcRevertToSelf` at `0x18003b79c`
- `RPCRT4!RpcImpersonateClient` at `0x18003b632`
- `RPCRT4!RpcImpersonateClient` at `0x18003b75d`
- `RPCRT4!RpcImpersonateClient` at `0x18003b632`
- `RPCRT4!RpcImpersonateClient` at `0x18003b75d`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x18003b5f8`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x18003b725`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x18003b5f8`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x18003b725`
- `fwbase!FwHResultToWindowsError` at `0x18003b8ab`
- `fwbase!FwHResultToWindowsError` at `0x18003b8ab`
- `fwbase!FwCloseHandle` at `0x18003b702`
- `fwbase!FwCloseHandle` at `0x18003b820`
- `fwbase!FwCloseHandle` at `0x18003b702`
- `fwbase!FwCloseHandle` at `0x18003b820`

## string_xrefs

- `0x18003bb67`: `mpssvc.dll`
- `0x18003bbcf`: `mpssvc.dll`

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
    v7 = (PSECURITY_DESCRIPTOR)qword_18012C848;
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
  if ( BCryptGetFipsAlgorithmMode(pfEnabled) < 0 || (v16 = qword_18012C870, !pfEnabled[0]) )
    v16 = (PSECURITY_DESCRIPTOR)qword_18012C858;
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
0x18003b580  push    rbp
0x18003b582  push    rbx
0x18003b583  push    rsi
0x18003b584  push    rdi
0x18003b585  push    r12
0x18003b587  push    r13
0x18003b589  push    r14
0x18003b58b  push    r15
0x18003b58d  lea     rbp, [rsp-0Fh]
0x18003b592  sub     rsp, 0B8h
0x18003b599  mov     rax, cs:__security_cookie
0x18003b5a0  xor     rax, rsp
0x18003b5a3  mov     [rbp+47h+var_50], rax
0x18003b5a7  mov     rax, [rbp+47h+arg_28]
0x18003b5ab  mov     rdi, rcx
0x18003b5ae  mov     [rbp+47h+BindingHandle], rcx
0x18003b5b2  mov     rcx, cs:g_Provider
0x18003b5b9  mov     [rbp+47h+var_AC], r9d
0x18003b5bd  mov     [rbp+47h+var_A8], r8d
0x18003b5c1  mov     [rbp+47h+var_B0], dx
0x18003b5c5  mov     [rbp+47h+var_98], rax
0x18003b5c9  test    rcx, rcx
0x18003b5cc  jz      short loc_18003B5E1
0x18003b5ce  xor     r9d, r9d
0x18003b5d1  lea     rdx, MPS_SVC_API_Enter_OpenPolicyStore
0x18003b5d8  xor     r8d, r8d
0x18003b5db  call    cs:__imp_EtwEventWrite
0x18003b5e1  mov     rcx, rdi; void *
0x18003b5e4  call    ?IsRPCClientNAPAgentService@@YAHPEAX@Z; IsRPCClientNAPAgentService(void *)
0x18003b5e9  test    eax, eax
0x18003b5eb  jnz     loc_18003B83E
0x18003b5f1  lea     rcx, [rbp+47h+pfEnabled]; pfEnabled
0x18003b5f5  mov     [rbp+47h+pfEnabled], al
0x18003b5f8  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x18003b5fe  test    eax, eax
0x18003b600  js      short loc_18003B60F
0x18003b602  cmp     [rbp+47h+pfEnabled], 0
0x18003b606  mov     rbx, cs:pSecurityDescriptor
0x18003b60d  jnz     short loc_18003B616
0x18003b60f  mov     rbx, cs:qword_18012C848
0x18003b616  movsxd  r12, [rbp+47h+var_AC]
0x18003b61a  lea     rax, ?AccessCheckAccessRights@@3PAKA; ulong near * AccessCheckAccessRights
0x18003b621  mov     rcx, rdi; BindingHandle
0x18003b624  mov     [rbp+47h+TokenHandle], 0
0x18003b62c  xor     esi, esi
0x18003b62e  mov     r15d, [rax+r12*4]
0x18003b632  call    cs:__imp_RpcImpersonateClient
0x18003b638  mov     edi, eax
0x18003b63a  test    eax, eax
0x18003b63c  jnz     loc_18003B999
0x18003b642  call    cs:__imp_GetCurrentThread
0x18003b648  mov     rcx, rax; ThreadHandle
0x18003b64b  lea     r9, [rbp+47h+TokenHandle]; TokenHandle
0x18003b64f  lea     edx, [rsi+8]; DesiredAccess
0x18003b652  lea     r8d, [rsi+1]; OpenAsSelf
0x18003b656  call    cs:__imp_OpenThreadToken
0x18003b65c  mov     r13d, 80070000h
0x18003b662  lea     r14, WPP_GLOBAL_Control
0x18003b669  test    eax, eax
0x18003b66b  jz      loc_18003B9E5
0x18003b671  mov     rsi, [rbp+47h+TokenHandle]
0x18003b675  test    rsi, rsi
0x18003b678  jz      loc_18003BB56
0x18003b67e  call    cs:__imp_RpcRevertToSelf
0x18003b684  test    eax, eax
0x18003b686  jnz     loc_18003BB64
0x18003b68c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b693  test    edi, edi
0x18003b695  js      loc_18003BB7A
0x18003b69b  xor     eax, eax
0x18003b69d  mov     [rbp+47h+var_7C], 14h
0x18003b6a4  mov     [rbp+47h+var_78.Privilege.Attributes], eax
0x18003b6a7  lea     r9, [rbp+47h+GenericMapping]; GenericMapping
0x18003b6ab  mov     [rbp+47h+var_80], eax
0x18003b6ae  xorps   xmm0, xmm0
0x18003b6b1  mov     [rbp+47h+var_84], eax
0x18003b6b4  xorps   xmm1, xmm1
0x18003b6b7  lea     rax, [rbp+47h+var_84]
0x18003b6bb  mov     r8d, r15d; DesiredAccess
0x18003b6be  mov     [rsp+0F0h+AccessStatus], rax; AccessStatus
0x18003b6c3  mov     rdx, rsi; ClientToken
0x18003b6c6  lea     rax, [rbp+47h+var_80]
0x18003b6ca  mov     rcx, rbx; pSecurityDescriptor
0x18003b6cd  mov     [rsp+0F0h+GrantedAccess], rax; GrantedAccess
0x18003b6d2  lea     rax, [rbp+47h+var_7C]
0x18003b6d6  mov     [rsp+0F0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18003b6db  lea     rax, [rbp+47h+var_78]
0x18003b6df  mov     [rsp+0F0h+PrivilegeSet], rax; PrivilegeSet
0x18003b6e4  movups  xmmword ptr [rbp+47h+GenericMapping.GenericRead], xmm0
0x18003b6e8  movups  xmmword ptr [rbp+47h+var_78.PrivilegeCount], xmm1
0x18003b6ec  call    cs:__imp_AccessCheck
0x18003b6f2  test    eax, eax
0x18003b6f4  jz      loc_18003BA2E
0x18003b6fa  mov     ebx, [rbp+47h+var_84]
0x18003b6fd  xor     edi, edi
0x18003b6ff  mov     rcx, rsi
0x18003b702  call    cs:__imp_FwCloseHandle
0x18003b708  mov     eax, 80070005h
0x18003b70d  test    edi, edi
0x18003b70f  js      loc_18003BB97
0x18003b715  test    ebx, ebx
0x18003b717  jz      loc_18003B8B3
0x18003b71d  lea     rcx, [rbp+47h+pfEnabled]; pfEnabled
0x18003b721  mov     [rbp+47h+pfEnabled], 0
0x18003b725  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x18003b72b  test    eax, eax
0x18003b72d  js      short loc_18003B73C
0x18003b72f  cmp     [rbp+47h+pfEnabled], 0
0x18003b733  mov     rsi, cs:qword_18012C870
0x18003b73a  jnz     short loc_18003B743
0x18003b73c  mov     rsi, cs:qword_18012C858
0x18003b743  mov     rcx, [rbp+47h+BindingHandle]; BindingHandle
0x18003b747  lea     rax, ?AccessCheckAccessRights@@3PAKA; ulong near * AccessCheckAccessRights
0x18003b74e  mov     r12d, [rax+r12*4]
0x18003b752  xor     r15d, r15d
0x18003b755  mov     [rbp+47h+TokenHandle], 0
0x18003b75d  call    cs:__imp_RpcImpersonateClient
0x18003b763  mov     ebx, eax
0x18003b765  test    eax, eax
0x18003b767  jnz     loc_18003BA7E
0x18003b76d  call    cs:__imp_GetCurrentThread
0x18003b773  mov     rcx, rax; ThreadHandle
0x18003b776  lea     r9, [rbp+47h+TokenHandle]; TokenHandle
0x18003b77a  lea     edx, [rbx+8]; DesiredAccess
0x18003b77d  lea     r8d, [r15+1]; OpenAsSelf
0x18003b781  call    cs:__imp_OpenThreadToken
0x18003b787  test    eax, eax
0x18003b789  jz      loc_18003BABD
0x18003b78f  mov     r15, [rbp+47h+TokenHandle]
0x18003b793  test    r15, r15
0x18003b796  jz      loc_18003BBBE
0x18003b79c  call    cs:__imp_RpcRevertToSelf
0x18003b7a2  test    eax, eax
0x18003b7a4  jnz     loc_18003BBCC
0x18003b7aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b7b1  test    ebx, ebx
0x18003b7b3  js      loc_18003BBE2
0x18003b7b9  xor     eax, eax
0x18003b7bb  mov     [rbp+47h+var_80], 14h
0x18003b7c2  mov     [rbp+47h+var_78.Privilege.Attributes], eax
0x18003b7c5  lea     r9, [rbp+47h+GenericMapping]; GenericMapping
0x18003b7c9  mov     [rbp+47h+var_7C], eax
0x18003b7cc  xorps   xmm0, xmm0
0x18003b7cf  mov     [rbp+47h+var_84], eax
0x18003b7d2  xorps   xmm1, xmm1
0x18003b7d5  lea     rax, [rbp+47h+var_84]
0x18003b7d9  mov     r8d, r12d; DesiredAccess
0x18003b7dc  mov     [rsp+0F0h+AccessStatus], rax; AccessStatus
0x18003b7e1  mov     rdx, r15; ClientToken
0x18003b7e4  lea     rax, [rbp+47h+var_7C]
0x18003b7e8  mov     rcx, rsi; pSecurityDescriptor
0x18003b7eb  mov     [rsp+0F0h+GrantedAccess], rax; GrantedAccess
0x18003b7f0  lea     rax, [rbp+47h+var_80]
0x18003b7f4  mov     [rsp+0F0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18003b7f9  lea     rax, [rbp+47h+var_78]
0x18003b7fd  mov     [rsp+0F0h+PrivilegeSet], rax; PrivilegeSet
0x18003b802  movups  xmmword ptr [rbp+47h+GenericMapping.GenericRead], xmm0
0x18003b806  movups  xmmword ptr [rbp+47h+var_78.PrivilegeCount], xmm1
0x18003b80a  call    cs:__imp_AccessCheck
0x18003b810  test    eax, eax
0x18003b812  jz      loc_18003BB06
0x18003b818  mov     esi, [rbp+47h+var_84]
0x18003b81b  xor     ebx, ebx
0x18003b81d  mov     rcx, r15
0x18003b820  call    cs:__imp_FwCloseHandle
0x18003b826  test    ebx, ebx
0x18003b828  js      loc_18003BBFF
0x18003b82e  test    esi, esi
0x18003b830  jz      loc_18003B8EC
0x18003b836  test    edi, edi
0x18003b838  js      short loc_18003B8A5
0x18003b83a  mov     rdi, [rbp+47h+BindingHandle]
0x18003b83e  mov     rax, [rbp+47h+var_98]
0x18003b842  mov     rcx, rdi
0x18003b845  mov     r9d, [rbp+47h+var_AC]
0x18003b849  mov     r8d, [rbp+47h+var_A8]
0x18003b84d  movzx   edx, [rbp+47h+var_B0]
0x18003b851  mov     [rsp+0F0h+PrivilegeSetLength], rax
0x18003b856  mov     eax, [rbp+47h+arg_20]
0x18003b859  mov     dword ptr [rsp+0F0h+PrivilegeSet], eax
0x18003b85d  call    ?SvrImpl_FWOpenPolicyStore@@YAKPEAXGW4_tag_FW_STORE_TYPE@@W4_tag_FW_POLICY_ACCESS_RIGHT@@KPEAPEAX@Z; SvrImpl_FWOpenPolicyStore(void *,ushort,_tag_FW_STORE_TYPE,_tag_FW_POLICY_ACCESS_RIGHT,ulong,void * *)
0x18003b862  mov     rcx, cs:g_Provider
0x18003b869  mov     ebx, eax
0x18003b86b  test    rcx, rcx
0x18003b86e  jz      short loc_18003B883
0x18003b870  xor     r9d, r9d
0x18003b873  lea     rdx, MPS_SVC_API_Exit_OpenPolicyStore
0x18003b87a  xor     r8d, r8d
0x18003b87d  call    cs:__imp_EtwEventWrite
0x18003b883  mov     eax, ebx
0x18003b885  mov     rcx, [rbp+47h+var_50]
0x18003b889  xor     rcx, rsp; StackCookie
0x18003b88c  call    __security_check_cookie
0x18003b891  add     rsp, 0B8h
0x18003b898  pop     r15
0x18003b89a  pop     r14
0x18003b89c  pop     r13
0x18003b89e  pop     r12
0x18003b8a0  pop     rdi
0x18003b8a1  pop     rsi
0x18003b8a2  pop     rbx
0x18003b8a3  pop     rbp
0x18003b8a4  retn
0x18003b8a5  test    ebx, ebx
0x18003b8a7  jns     short loc_18003B83A
0x18003b8a9  mov     ecx, edi
0x18003b8ab  call    cs:__imp_FwHResultToWindowsError
0x18003b8b1  jmp     short loc_18003B862
0x18003b8b3  mov     edi, eax
0x18003b8b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b8bc  cmp     rcx, r14
0x18003b8bf  jz      loc_18003B71D
0x18003b8c5  test    byte ptr [rcx+1Ch], 1
0x18003b8c9  jz      loc_18003B71D
0x18003b8cf  mov     edx, 11h
0x18003b8d4  mov     r9d, eax
0x18003b8d7  mov     rcx, [rcx+10h]
0x18003b8db  lea     r8, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x18003b8e2  call    WPP_SF_d
0x18003b8e7  jmp     loc_18003B71D
0x18003b8ec  mov     r9d, 80070005h
0x18003b8f2  mov     ebx, r9d
0x18003b8f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b8fc  cmp     rcx, r14
0x18003b8ff  jz      loc_18003B836
0x18003b905  test    byte ptr [rcx+1Ch], 1
0x18003b909  jz      loc_18003B836
0x18003b90f  mov     edx, 11h
0x18003b914  mov     rcx, [rcx+10h]
0x18003b918  lea     r8, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x18003b91f  call    WPP_SF_d
0x18003b924  jmp     loc_18003B836
0x18003b929  xor     ebx, ebx
0x18003b92b  test    edi, edi
0x18003b92d  jns     loc_18003B6FF
0x18003b933  cmp     rcx, r14
0x18003b936  jz      loc_18003B6FF
0x18003b93c  test    byte ptr [rcx+1Ch], 1
0x18003b940  jz      loc_18003B6FF
0x18003b946  lea     edx, [rbx+25h]
0x18003b949  mov     rcx, [rcx+10h]
0x18003b94d  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003b954  mov     r9d, edi
0x18003b957  call    WPP_SF_d
0x18003b95c  jmp     loc_18003B6FF
0x18003b961  xor     esi, esi
0x18003b963  test    ebx, ebx
0x18003b965  jns     loc_18003B81D
0x18003b96b  cmp     rcx, r14
0x18003b96e  jz      loc_18003B81D
0x18003b974  test    byte ptr [rcx+1Ch], 1
0x18003b978  jz      loc_18003B81D
0x18003b97e  lea     edx, [rsi+25h]
0x18003b981  mov     rcx, [rcx+10h]
0x18003b985  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003b98c  mov     r9d, ebx
0x18003b98f  call    WPP_SF_d
0x18003b994  jmp     loc_18003B81D
0x18003b999  mov     r13d, 80070000h
0x18003b99f  jle     short loc_18003B9A7
0x18003b9a1  movzx   edi, ax
0x18003b9a4  or      edi, r13d
0x18003b9a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b9ae  lea     r14, WPP_GLOBAL_Control
0x18003b9b5  cmp     rcx, r14
0x18003b9b8  jz      loc_18003B693
0x18003b9be  test    byte ptr [rcx+1Ch], 1
0x18003b9c2  jz      loc_18003B693
0x18003b9c8  mov     rcx, [rcx+10h]
0x18003b9cc  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003b9d3  mov     edx, 22h ; '"'
0x18003b9d8  mov     r9d, edi
0x18003b9db  call    WPP_SF_d
0x18003b9e0  jmp     loc_18003B68C
0x18003b9e5  call    cs:__imp_GetLastError
0x18003b9eb  mov     edi, eax
0x18003b9ed  test    eax, eax
0x18003b9ef  jle     short loc_18003B9F7
0x18003b9f1  movzx   edi, ax
0x18003b9f4  or      edi, r13d
0x18003b9f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b9fe  cmp     rcx, r14
0x18003ba01  jz      loc_18003B67E
0x18003ba07  test    byte ptr [rcx+1Ch], 1
0x18003ba0b  jz      loc_18003B67E
0x18003ba11  mov     rcx, [rcx+10h]
0x18003ba15  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003ba1c  mov     edx, 23h ; '#'
0x18003ba21  mov     r9d, edi
0x18003ba24  call    WPP_SF_d
0x18003ba29  jmp     loc_18003B67E
0x18003ba2e  call    cs:__imp_GetLastError
0x18003ba34  mov     edi, eax
0x18003ba36  test    eax, eax
0x18003ba38  jle     short loc_18003BA40
0x18003ba3a  movzx   edi, ax
0x18003ba3d  or      edi, r13d
0x18003ba40  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ba47  cmp     rcx, r14
0x18003ba4a  jz      loc_18003B929
  ... truncated ...
```
