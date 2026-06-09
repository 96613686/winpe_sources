# ICSRpcServerInitialize(void)

- ea: `0x180022a90`
- end: `0x180023021`
- name: `?ICSRpcServerInitialize@@YAKXZ`
- size: `1425`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021fb8`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180022a90`
- `0x180023028`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022edb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022eee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022f01`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022edb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022eee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022f01`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022c45`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022c58`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022c6b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022c45`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022c58`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022c6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022bf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022bf0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180022f2f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180022f70`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180022f2f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180022f70`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180022f42`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180022f83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180022f42`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180022f83`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180022b83`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180022bd8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180022b83`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180022bd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022fb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022fb3`
- `RPCRT4!RpcBindingVectorFree` at `0x180022fd2`
- `RPCRT4!RpcBindingVectorFree` at `0x180022fd2`
- `RPCRT4!RpcServerUseProtseqW` at `0x180022c8f`
- `RPCRT4!RpcServerUseProtseqW` at `0x180022c8f`
- `RPCRT4!RpcServerUnregisterIf` at `0x180022e81`
- `RPCRT4!RpcServerUnregisterIf` at `0x180022e81`
- `RPCRT4!RpcServerRegisterIf3` at `0x180022cfc`
- `RPCRT4!RpcServerRegisterIf3` at `0x180022cfc`
- `RPCRT4!RpcEpUnregister` at `0x180022e1f`
- `RPCRT4!RpcEpUnregister` at `0x180022e1f`
- `RPCRT4!RpcServerInqBindings` at `0x180022d4e`
- `RPCRT4!RpcServerInqBindings` at `0x180022d4e`
- `RPCRT4!RpcEpRegisterW` at `0x180022dbc`
- `RPCRT4!RpcEpRegisterW` at `0x180022dbc`

## pseudocode

```c
__int64 ICSRpcServerInitialize(void)
{
  unsigned int v0; // ebx
  PVOID *v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // r9
  DWORD LastError; // eax
  __int64 v5; // rdx
  unsigned int v6; // eax
  unsigned int v7; // edi
  unsigned int v8; // eax
  RPC_BINDING_VECTOR *BindingVector; // [rsp+70h] [rbp+8h] BYREF
  void *SecurityDescriptor; // [rsp+78h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids);
  }
  SecurityDescriptor = 0;
  BindingVector = 0;
  if ( !Rpc_MakeLowboxSD(&SecurityDescriptor) )
  {
    g_RpcEnvironment.Version = 3;
    *(_OWORD *)&g_RpcEnvironment.RaceDll = 0;
    g_RpcEnvironment.Pool = 0;
    g_RpcEnvironment.CleanupGroup = 0;
    g_RpcEnvironment.CleanupGroupCancelCallback = 0;
    g_RpcEnvironment.FinalizationCallback = 0;
    g_RpcEnvironment.u.Flags = 0;
    g_RpcEnvironment.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
    g_RpcEnvironment.Size = 72;
    g_StartDhcpServerBackgroundWork = CreateThreadpoolWork(StartDhcpServerBackgroundProcessing, 0, &g_RpcEnvironment);
    if ( !g_StartDhcpServerBackgroundWork )
    {
      LastError = GetLastError();
      v0 = LastError;
      v1 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 17;
LABEL_20:
        WPP_SF_d(v1[2], v5, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids, LastError);
        v1 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_21;
      }
      goto LABEL_21;
    }
    g_StartSharingBackgroundWork = CreateThreadpoolWork(StartSharingBackgroundProcessing, 0, &g_RpcEnvironment);
    if ( !g_StartSharingBackgroundWork )
    {
      LastError = GetLastError();
      v0 = LastError;
      v1 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 18;
        goto LABEL_20;
      }
LABEL_21:
      if ( !v0 )
        goto LABEL_74;
      goto LABEL_50;
    }
    InitializeCriticalSection(&g_csOperationLock);
    InitializeCriticalSection(&g_csPolicyLock);
    InitializeCriticalSection(&g_csDnsLock);
    g_fRpcCsInitialized = 1;
    v6 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
    v0 = v6;
    if ( v6 )
    {
      v1 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_50;
      }
      v2 = 19;
      goto LABEL_48;
    }
    v6 = RpcServerRegisterIf3(qword_180099AB0, 0, 0, 41, 1234, 0, 0, SecurityDescriptor);
    v0 = v6;
    if ( v6 )
    {
      if ( v6 != 1713 )
      {
        v1 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_50;
        }
        v2 = 21;
        goto LABEL_48;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids, 1713);
      }
    }
    g_fRpcIfRegisgtered = 1;
    v6 = RpcServerInqBindings(&BindingVector);
    v0 = v6;
    if ( v6 )
    {
      v1 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_50;
      }
      v2 = 22;
    }
    else
    {
      v6 = RpcEpRegisterW(qword_180099AB0, BindingVector, 0, 0);
      v0 = v6;
      if ( !v6 )
      {
        g_fRpcEndPointRegistered = 1;
        goto LABEL_73;
      }
      v1 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_50;
      }
      v2 = 23;
    }
LABEL_48:
    v3 = v6;
    goto LABEL_49;
  }
  v0 = 1338;
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v2 = 16;
    v3 = 1338;
LABEL_49:
    WPP_SF_d(v1[2], v2, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids, v3);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_50:
  v7 = 0;
  if ( !g_fRpcEndPointRegistered )
    goto LABEL_58;
  v8 = RpcEpUnregister(qword_180099AB0, BindingVector, 0);
  v7 = v8;
  if ( v8 )
  {
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_57;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids, v8);
  }
  v1 = (PVOID *)WPP_GLOBAL_Control;
LABEL_57:
  g_fRpcEndPointRegistered = 0;
LABEL_58:
  if ( !g_fRpcIfRegisgtered )
    goto LABEL_66;
  RpcServerUnregisterIf(qword_180099AB0, 0, 1u);
  if ( v7 )
  {
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids, v7);
  }
  v1 = (PVOID *)WPP_GLOBAL_Control;
LABEL_65:
  g_fRpcIfRegisgtered = 0;
LABEL_66:
  if ( g_fRpcCsInitialized )
  {
    DeleteCriticalSection(&g_csOperationLock);
    DeleteCriticalSection(&g_csPolicyLock);
    DeleteCriticalSection(&g_csDnsLock);
    v1 = (PVOID *)WPP_GLOBAL_Control;
    g_fRpcCsInitialized = 0;
  }
  if ( g_StartDhcpServerBackgroundWork )
  {
    WaitForThreadpoolWorkCallbacks(g_StartDhcpServerBackgroundWork, 1);
    CloseThreadpoolWork(g_StartDhcpServerBackgroundWork);
    v1 = (PVOID *)WPP_GLOBAL_Control;
    g_StartDhcpServerBackgroundWork = 0;
  }
  if ( g_StartSharingBackgroundWork )
  {
    WaitForThreadpoolWorkCallbacks(g_StartSharingBackgroundWork, 1);
    CloseThreadpoolWork(g_StartSharingBackgroundWork);
    g_StartSharingBackgroundWork = 0;
LABEL_73:
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_74:
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( BindingVector )
  {
    RpcBindingVectorFree(&BindingVector);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 0x40) != 0 && *((_BYTE *)v1 + 25) >= 6u )
    WPP_SF_d(v1[2], 26, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x180022a90  mov     [rsp+arg_10], rbx
0x180022a95  push    rbp
0x180022a96  push    rsi
0x180022a97  push    rdi
0x180022a98  push    r12
0x180022a9a  push    r14
0x180022a9c  sub     rsp, 40h
0x180022aa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180022aa7  lea     r14, WPP_GLOBAL_Control
0x180022aae  lea     r12, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x180022ab5  mov     bpl, 40h ; '@'
0x180022ab8  cmp     rcx, r14
0x180022abb  jz      short loc_180022ADA
0x180022abd  test    [rcx+1Ch], bpl
0x180022ac1  jz      short loc_180022ADA
0x180022ac3  cmp     byte ptr [rcx+19h], 6
0x180022ac7  jb      short loc_180022ADA
0x180022ac9  mov     rcx, [rcx+10h]
0x180022acd  mov     edx, 0Fh
0x180022ad2  mov     r8, r12
0x180022ad5  call    WPP_SF_
0x180022ada  xor     esi, esi
0x180022adc  lea     rcx, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x180022ae1  mov     [rsp+68h+SecurityDescriptor], rsi
0x180022ae6  mov     [rsp+68h+BindingVector], rsi
0x180022aeb  call    ?Rpc_MakeLowboxSD@@YAKPEAPEAX@Z; Rpc_MakeLowboxSD(void * *)
0x180022af0  test    eax, eax
0x180022af2  jz      short loc_180022B28
0x180022af4  mov     ebx, 53Ah
0x180022af9  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b00  cmp     rcx, r14
0x180022b03  jz      loc_180022E05
0x180022b09  test    [rcx+1Ch], bpl
0x180022b0d  jz      loc_180022E05
0x180022b13  cmp     byte ptr [rcx+19h], 2
0x180022b17  jb      loc_180022E05
0x180022b1d  lea     edx, [rsi+10h]
0x180022b20  mov     r9d, ebx
0x180022b23  jmp     loc_180022DF2
0x180022b28  xorps   xmm0, xmm0
0x180022b2b  mov     cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x180022b35  lea     r8, ?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180022b3c  movdqa  xmmword ptr cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x180022b44  xor     edx, edx; pv
0x180022b46  mov     cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rsi; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x180022b4d  lea     rcx, ?StartDhcpServerBackgroundProcessing@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180022b54  mov     cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rsi; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x180022b5b  mov     cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rsi; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x180022b62  mov     cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, rsi; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x180022b69  mov     dword ptr cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, esi; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x180022b6f  mov     cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x180022b79  mov     cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x180022b83  call    cs:__imp_CreateThreadpoolWork
0x180022b8a  nop     dword ptr [rax+rax+00h]
0x180022b8f  mov     cs:?g_StartDhcpServerBackgroundWork@@3PEAU_TP_WORK@@EA, rax; _TP_WORK * g_StartDhcpServerBackgroundWork
0x180022b96  test    rax, rax
0x180022b99  jnz     short loc_180022BC8
0x180022b9b  call    cs:__imp_GetLastError
0x180022ba2  nop     dword ptr [rax+rax+00h]
0x180022ba7  mov     ebx, eax
0x180022ba9  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bb0  cmp     rcx, r14
0x180022bb3  jz      short loc_180022C31
0x180022bb5  test    [rcx+1Ch], bpl
0x180022bb9  jz      short loc_180022C31
0x180022bbb  cmp     byte ptr [rcx+19h], 2
0x180022bbf  jb      short loc_180022C31
0x180022bc1  mov     edx, 11h
0x180022bc6  jmp     short loc_180022C1B
0x180022bc8  lea     r8, ?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180022bcf  xor     edx, edx; pv
0x180022bd1  lea     rcx, ?StartSharingBackgroundProcessing@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180022bd8  call    cs:__imp_CreateThreadpoolWork
0x180022bdf  nop     dword ptr [rax+rax+00h]
0x180022be4  mov     cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA, rax; _TP_WORK * g_StartSharingBackgroundWork
0x180022beb  test    rax, rax
0x180022bee  jnz     short loc_180022C3E
0x180022bf0  call    cs:__imp_GetLastError
0x180022bf7  nop     dword ptr [rax+rax+00h]
0x180022bfc  mov     ebx, eax
0x180022bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c05  cmp     rcx, r14
0x180022c08  jz      short loc_180022C31
0x180022c0a  test    [rcx+1Ch], bpl
0x180022c0e  jz      short loc_180022C31
0x180022c10  cmp     byte ptr [rcx+19h], 2
0x180022c14  jb      short loc_180022C31
0x180022c16  mov     edx, 12h
0x180022c1b  mov     rcx, [rcx+10h]
0x180022c1f  mov     r9d, eax
0x180022c22  mov     r8, r12
0x180022c25  call    WPP_SF_d
0x180022c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c31  test    ebx, ebx
0x180022c33  jnz     loc_180022E05
0x180022c39  jmp     loc_180022FA6
0x180022c3e  lea     rcx, ?g_csOperationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180022c45  call    cs:__imp_InitializeCriticalSection
0x180022c4c  nop     dword ptr [rax+rax+00h]
0x180022c51  lea     rcx, ?g_csPolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180022c58  call    cs:__imp_InitializeCriticalSection
0x180022c5f  nop     dword ptr [rax+rax+00h]
0x180022c64  lea     rcx, ?g_csDnsLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180022c6b  call    cs:__imp_InitializeCriticalSection
0x180022c72  nop     dword ptr [rax+rax+00h]
0x180022c77  mov     r8, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x180022c7c  lea     rcx, Protseq; "ncalrpc"
0x180022c83  mov     edx, 0Ah; MaxCalls
0x180022c88  mov     cs:?g_fRpcCsInitialized@@3_NA, 1; bool g_fRpcCsInitialized
0x180022c8f  call    cs:__imp_RpcServerUseProtseqW
0x180022c96  nop     dword ptr [rax+rax+00h]
0x180022c9b  mov     ebx, eax
0x180022c9d  test    eax, eax
0x180022c9f  jz      short loc_180022CCF
0x180022ca1  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ca8  cmp     rcx, r14
0x180022cab  jz      loc_180022E05
0x180022cb1  test    [rcx+1Ch], bpl
0x180022cb5  jz      loc_180022E05
0x180022cbb  cmp     byte ptr [rcx+19h], 2
0x180022cbf  jb      loc_180022E05
0x180022cc5  mov     edx, 13h
0x180022cca  jmp     loc_180022DEF
0x180022ccf  mov     rax, [rsp+68h+SecurityDescriptor]
0x180022cd4  lea     rcx, qword_180099AB0
0x180022cdb  mov     [rsp+68h+var_30], rax
0x180022ce0  mov     r9d, 29h ; ')'
0x180022ce6  mov     [rsp+68h+var_38], rsi
0x180022ceb  xor     r8d, r8d
0x180022cee  mov     [rsp+68h+var_40], esi
0x180022cf2  xor     edx, edx
0x180022cf4  mov     [rsp+68h+var_48], 4D2h
0x180022cfc  call    cs:__imp_RpcServerRegisterIf3
0x180022d03  nop     dword ptr [rax+rax+00h]
0x180022d08  mov     ebx, eax
0x180022d0a  test    eax, eax
0x180022d0c  jz      short loc_180022D42
0x180022d0e  mov     r9d, 6B1h
0x180022d14  cmp     eax, r9d
0x180022d17  jnz     short loc_180022D8B
0x180022d19  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d20  cmp     rcx, r14
0x180022d23  jz      short loc_180022D42
0x180022d25  test    [rcx+1Ch], bpl
0x180022d29  jz      short loc_180022D42
0x180022d2b  cmp     byte ptr [rcx+19h], 3
0x180022d2f  jb      short loc_180022D42
0x180022d31  mov     rcx, [rcx+10h]
0x180022d35  mov     edx, 14h
0x180022d3a  mov     r8, r12
0x180022d3d  call    WPP_SF_d
0x180022d42  lea     rcx, [rsp+68h+BindingVector]; BindingVector
0x180022d47  mov     cs:?g_fRpcIfRegisgtered@@3_NA, 1; bool g_fRpcIfRegisgtered
0x180022d4e  call    cs:__imp_RpcServerInqBindings
0x180022d55  nop     dword ptr [rax+rax+00h]
0x180022d5a  mov     ebx, eax
0x180022d5c  test    eax, eax
0x180022d5e  jz      short loc_180022DAA
0x180022d60  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d67  cmp     rcx, r14
0x180022d6a  jz      loc_180022E05
0x180022d70  test    [rcx+1Ch], bpl
0x180022d74  jz      loc_180022E05
0x180022d7a  cmp     byte ptr [rcx+19h], 2
0x180022d7e  jb      loc_180022E05
0x180022d84  mov     edx, 16h
0x180022d89  jmp     short loc_180022DEF
0x180022d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d92  cmp     rcx, r14
0x180022d95  jz      short loc_180022E05
0x180022d97  test    [rcx+1Ch], bpl
0x180022d9b  jz      short loc_180022E05
0x180022d9d  cmp     byte ptr [rcx+19h], 2
0x180022da1  jb      short loc_180022E05
0x180022da3  mov     edx, 15h
0x180022da8  jmp     short loc_180022DEF
0x180022daa  mov     rdx, [rsp+68h+BindingVector]; BindingVector
0x180022daf  lea     rcx, qword_180099AB0; IfSpec
0x180022db6  xor     r9d, r9d; Annotation
0x180022db9  xor     r8d, r8d; UuidVector
0x180022dbc  call    cs:__imp_RpcEpRegisterW
0x180022dc3  nop     dword ptr [rax+rax+00h]
0x180022dc8  mov     ebx, eax
0x180022dca  test    eax, eax
0x180022dcc  jz      loc_180022F98
0x180022dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180022dd9  cmp     rcx, r14
0x180022ddc  jz      short loc_180022E05
0x180022dde  test    [rcx+1Ch], bpl
0x180022de2  jz      short loc_180022E05
0x180022de4  cmp     byte ptr [rcx+19h], 2
0x180022de8  jb      short loc_180022E05
0x180022dea  mov     edx, 17h
0x180022def  mov     r9d, eax
0x180022df2  mov     rcx, [rcx+10h]
0x180022df6  mov     r8, r12
0x180022df9  call    WPP_SF_d
0x180022dfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e05  cmp     cs:?g_fRpcEndPointRegistered@@3_NA, sil; bool g_fRpcEndPointRegistered
0x180022e0c  mov     edi, esi
0x180022e0e  jz      short loc_180022E6B
0x180022e10  mov     rdx, [rsp+68h+BindingVector]; BindingVector
0x180022e15  lea     rcx, qword_180099AB0; IfSpec
0x180022e1c  xor     r8d, r8d; UuidVector
0x180022e1f  call    cs:__imp_RpcEpUnregister
0x180022e26  nop     dword ptr [rax+rax+00h]
0x180022e2b  mov     edi, eax
0x180022e2d  test    eax, eax
0x180022e2f  jz      short loc_180022E5D
0x180022e31  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e38  cmp     rcx, r14
0x180022e3b  jz      short loc_180022E64
0x180022e3d  test    [rcx+1Ch], bpl
0x180022e41  jz      short loc_180022E64
0x180022e43  cmp     byte ptr [rcx+19h], 2
0x180022e47  jb      short loc_180022E64
0x180022e49  mov     rcx, [rcx+10h]
0x180022e4d  mov     edx, 18h
0x180022e52  mov     r9d, eax
0x180022e55  mov     r8, r12
0x180022e58  call    WPP_SF_d
0x180022e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e64  mov     cs:?g_fRpcEndPointRegistered@@3_NA, sil; bool g_fRpcEndPointRegistered
0x180022e6b  cmp     cs:?g_fRpcIfRegisgtered@@3_NA, sil; bool g_fRpcIfRegisgtered
0x180022e72  jz      short loc_180022ECB
0x180022e74  xor     edx, edx; MgrTypeUuid
0x180022e76  lea     rcx, qword_180099AB0; IfSpec
0x180022e7d  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x180022e81  call    cs:__imp_RpcServerUnregisterIf
0x180022e88  nop     dword ptr [rax+rax+00h]
0x180022e8d  test    edi, edi
0x180022e8f  jz      short loc_180022EBD
0x180022e91  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e98  cmp     rcx, r14
0x180022e9b  jz      short loc_180022EC4
0x180022e9d  test    [rcx+1Ch], bpl
0x180022ea1  jz      short loc_180022EC4
0x180022ea3  cmp     byte ptr [rcx+19h], 2
0x180022ea7  jb      short loc_180022EC4
0x180022ea9  mov     rcx, [rcx+10h]
0x180022ead  mov     edx, 19h
0x180022eb2  mov     r9d, edi
0x180022eb5  mov     r8, r12
0x180022eb8  call    WPP_SF_d
0x180022ebd  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ec4  mov     cs:?g_fRpcIfRegisgtered@@3_NA, sil; bool g_fRpcIfRegisgtered
0x180022ecb  cmp     cs:?g_fRpcCsInitialized@@3_NA, sil; bool g_fRpcCsInitialized
0x180022ed2  jz      short loc_180022F1B
0x180022ed4  lea     rcx, ?g_csOperationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180022edb  call    cs:__imp_DeleteCriticalSection
0x180022ee2  nop     dword ptr [rax+rax+00h]
0x180022ee7  lea     rcx, ?g_csPolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180022eee  call    cs:__imp_DeleteCriticalSection
0x180022ef5  nop     dword ptr [rax+rax+00h]
0x180022efa  lea     rcx, ?g_csDnsLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180022f01  call    cs:__imp_DeleteCriticalSection
0x180022f08  nop     dword ptr [rax+rax+00h]
0x180022f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f14  mov     cs:?g_fRpcCsInitialized@@3_NA, sil; bool g_fRpcCsInitialized
0x180022f1b  mov     rax, cs:?g_StartDhcpServerBackgroundWork@@3PEAU_TP_WORK@@EA; _TP_WORK * g_StartDhcpServerBackgroundWork
0x180022f22  test    rax, rax
0x180022f25  jz      short loc_180022F5C
0x180022f27  mov     edx, 1; fCancelPendingCallbacks
0x180022f2c  mov     rcx, rax; pwk
0x180022f2f  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180022f36  nop     dword ptr [rax+rax+00h]
0x180022f3b  mov     rcx, cs:?g_StartDhcpServerBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x180022f42  call    cs:__imp_CloseThreadpoolWork
0x180022f49  nop     dword ptr [rax+rax+00h]
0x180022f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f55  mov     cs:?g_StartDhcpServerBackgroundWork@@3PEAU_TP_WORK@@EA, rsi; _TP_WORK * g_StartDhcpServerBackgroundWork
0x180022f5c  mov     rax, cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA; _TP_WORK * g_StartSharingBackgroundWork
0x180022f63  test    rax, rax
0x180022f66  jz      short loc_180022FA6
0x180022f68  mov     edx, 1; fCancelPendingCallbacks
0x180022f6d  mov     rcx, rax; pwk
0x180022f70  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180022f77  nop     dword ptr [rax+rax+00h]
0x180022f7c  mov     rcx, cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x180022f83  call    cs:__imp_CloseThreadpoolWork
0x180022f8a  nop     dword ptr [rax+rax+00h]
0x180022f8f  mov     cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA, rsi; _TP_WORK * g_StartSharingBackgroundWork
0x180022f96  jmp     short loc_180022F9F
0x180022f98  mov     cs:?g_fRpcEndPointRegistered@@3_NA, 1; bool g_fRpcEndPointRegistered
0x180022f9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022fa6  mov     rax, [rsp+68h+SecurityDescriptor]
0x180022fab  test    rax, rax
0x180022fae  jz      short loc_180022FC6
0x180022fb0  mov     rcx, rax; hMem
0x180022fb3  call    cs:__imp_LocalFree
0x180022fba  nop     dword ptr [rax+rax+00h]
0x180022fbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180022fc6  cmp     [rsp+68h+BindingVector], rsi
0x180022fcb  jz      short loc_180022FE5
0x180022fcd  lea     rcx, [rsp+68h+BindingVector]; BindingVector
0x180022fd2  call    cs:__imp_RpcBindingVectorFree
0x180022fd9  nop     dword ptr [rax+rax+00h]
0x180022fde  mov     rcx, cs:WPP_GLOBAL_Control
0x180022fe5  cmp     rcx, r14
0x180022fe8  jz      short loc_18002300A
  ... truncated ...
```
