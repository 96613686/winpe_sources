# ICSRpcServerInitialize(void)

- ea: `0x18002fb44`
- end: `0x18003004c`
- name: `?ICSRpcServerInitialize@@YAKXZ`
- size: `1288`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002f0f8`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18002fb44`
- `0x180030054`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ff3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ff4a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ff57`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ff3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ff4a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ff57`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002fce1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002fcee`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002fcfb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002fce1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002fcee`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002fcfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc92`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002ff7f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002ffb4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002ff7f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002ffb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002ff8c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002ffc1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002ff8c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002ffc1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002fc37`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002fc80`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002fc37`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002fc80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ffeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ffeb`
- `RPCRT4!RpcBindingVectorFree` at `0x180030004`
- `RPCRT4!RpcBindingVectorFree` at `0x180030004`
- `RPCRT4!RpcServerUseProtseqW` at `0x18002fd19`
- `RPCRT4!RpcServerUseProtseqW` at `0x18002fd19`
- `RPCRT4!RpcServerUnregisterIf` at `0x18002fee9`
- `RPCRT4!RpcServerUnregisterIf` at `0x18002fee9`
- `RPCRT4!RpcServerRegisterIf3` at `0x18002fd80`
- `RPCRT4!RpcServerRegisterIf3` at `0x18002fd80`
- `RPCRT4!RpcEpUnregister` at `0x18002fe8d`
- `RPCRT4!RpcEpUnregister` at `0x18002fe8d`
- `RPCRT4!RpcServerInqBindings` at `0x18002fdcc`
- `RPCRT4!RpcServerInqBindings` at `0x18002fdcc`
- `RPCRT4!RpcEpRegisterW` at `0x18002fe30`
- `RPCRT4!RpcEpRegisterW` at `0x18002fe30`

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
    v6 = RpcServerRegisterIf3(qword_180092AC0, 0, 0, 41, 1234, 0, 0, SecurityDescriptor);
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
      v6 = RpcEpRegisterW(qword_180092AC0, BindingVector, 0, 0);
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
  v8 = RpcEpUnregister(qword_180092AC0, BindingVector, 0);
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
  RpcServerUnregisterIf(qword_180092AC0, 0, 1u);
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
0x18002fb44  mov     [rsp+arg_10], rbx
0x18002fb49  push    rbp
0x18002fb4a  push    rsi
0x18002fb4b  push    rdi
0x18002fb4c  push    r12
0x18002fb4e  push    r14
0x18002fb50  sub     rsp, 40h
0x18002fb54  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb5b  lea     r14, WPP_GLOBAL_Control
0x18002fb62  lea     r12, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x18002fb69  mov     bpl, 40h ; '@'
0x18002fb6c  cmp     rcx, r14
0x18002fb6f  jz      short loc_18002FB8E
0x18002fb71  test    [rcx+1Ch], bpl
0x18002fb75  jz      short loc_18002FB8E
0x18002fb77  cmp     byte ptr [rcx+19h], 6
0x18002fb7b  jb      short loc_18002FB8E
0x18002fb7d  mov     rcx, [rcx+10h]
0x18002fb81  mov     edx, 0Fh
0x18002fb86  mov     r8, r12
0x18002fb89  call    WPP_SF_
0x18002fb8e  xor     esi, esi
0x18002fb90  lea     rcx, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x18002fb95  mov     [rsp+68h+SecurityDescriptor], rsi
0x18002fb9a  mov     [rsp+68h+BindingVector], rsi
0x18002fb9f  call    ?Rpc_MakeLowboxSD@@YAKPEAPEAX@Z; Rpc_MakeLowboxSD(void * *)
0x18002fba4  test    eax, eax
0x18002fba6  jz      short loc_18002FBDC
0x18002fba8  mov     ebx, 53Ah
0x18002fbad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbb4  cmp     rcx, r14
0x18002fbb7  jz      loc_18002FE73
0x18002fbbd  test    [rcx+1Ch], bpl
0x18002fbc1  jz      loc_18002FE73
0x18002fbc7  cmp     byte ptr [rcx+19h], 2
0x18002fbcb  jb      loc_18002FE73
0x18002fbd1  lea     edx, [rsi+10h]
0x18002fbd4  mov     r9d, ebx
0x18002fbd7  jmp     loc_18002FE60
0x18002fbdc  xorps   xmm0, xmm0
0x18002fbdf  mov     cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x18002fbe9  lea     r8, ?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18002fbf0  movdqa  xmmword ptr cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x18002fbf8  xor     edx, edx; pv
0x18002fbfa  mov     cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rsi; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x18002fc01  lea     rcx, ?StartDhcpServerBackgroundProcessing@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002fc08  mov     cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rsi; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x18002fc0f  mov     cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rsi; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x18002fc16  mov     cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, rsi; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x18002fc1d  mov     dword ptr cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, esi; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x18002fc23  mov     cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x18002fc2d  mov     cs:?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 g_RpcEnvironment ...
0x18002fc37  call    cs:__imp_CreateThreadpoolWork
0x18002fc3d  mov     cs:?g_StartDhcpServerBackgroundWork@@3PEAU_TP_WORK@@EA, rax; _TP_WORK * g_StartDhcpServerBackgroundWork
0x18002fc44  test    rax, rax
0x18002fc47  jnz     short loc_18002FC70
0x18002fc49  call    cs:__imp_GetLastError
0x18002fc4f  mov     ebx, eax
0x18002fc51  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc58  cmp     rcx, r14
0x18002fc5b  jz      short loc_18002FCCD
0x18002fc5d  test    [rcx+1Ch], bpl
0x18002fc61  jz      short loc_18002FCCD
0x18002fc63  cmp     byte ptr [rcx+19h], 2
0x18002fc67  jb      short loc_18002FCCD
0x18002fc69  mov     edx, 11h
0x18002fc6e  jmp     short loc_18002FCB7
0x18002fc70  lea     r8, ?g_RpcEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18002fc77  xor     edx, edx; pv
0x18002fc79  lea     rcx, ?StartSharingBackgroundProcessing@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002fc80  call    cs:__imp_CreateThreadpoolWork
0x18002fc86  mov     cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA, rax; _TP_WORK * g_StartSharingBackgroundWork
0x18002fc8d  test    rax, rax
0x18002fc90  jnz     short loc_18002FCDA
0x18002fc92  call    cs:__imp_GetLastError
0x18002fc98  mov     ebx, eax
0x18002fc9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fca1  cmp     rcx, r14
0x18002fca4  jz      short loc_18002FCCD
0x18002fca6  test    [rcx+1Ch], bpl
0x18002fcaa  jz      short loc_18002FCCD
0x18002fcac  cmp     byte ptr [rcx+19h], 2
0x18002fcb0  jb      short loc_18002FCCD
0x18002fcb2  mov     edx, 12h
0x18002fcb7  mov     rcx, [rcx+10h]
0x18002fcbb  mov     r9d, eax
0x18002fcbe  mov     r8, r12
0x18002fcc1  call    WPP_SF_d
0x18002fcc6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fccd  test    ebx, ebx
0x18002fccf  jnz     loc_18002FE73
0x18002fcd5  jmp     loc_18002FFDE
0x18002fcda  lea     rcx, ?g_csOperationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002fce1  call    cs:__imp_InitializeCriticalSection
0x18002fce7  lea     rcx, ?g_csPolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002fcee  call    cs:__imp_InitializeCriticalSection
0x18002fcf4  lea     rcx, ?g_csDnsLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002fcfb  call    cs:__imp_InitializeCriticalSection
0x18002fd01  mov     r8, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x18002fd06  lea     rcx, Protseq; "ncalrpc"
0x18002fd0d  mov     edx, 0Ah; MaxCalls
0x18002fd12  mov     cs:?g_fRpcCsInitialized@@3_NA, 1; bool g_fRpcCsInitialized
0x18002fd19  call    cs:__imp_RpcServerUseProtseqW
0x18002fd1f  mov     ebx, eax
0x18002fd21  test    eax, eax
0x18002fd23  jz      short loc_18002FD53
0x18002fd25  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fd2c  cmp     rcx, r14
0x18002fd2f  jz      loc_18002FE73
0x18002fd35  test    [rcx+1Ch], bpl
0x18002fd39  jz      loc_18002FE73
0x18002fd3f  cmp     byte ptr [rcx+19h], 2
0x18002fd43  jb      loc_18002FE73
0x18002fd49  mov     edx, 13h
0x18002fd4e  jmp     loc_18002FE5D
0x18002fd53  mov     rax, [rsp+68h+SecurityDescriptor]
0x18002fd58  lea     rcx, qword_180092AC0
0x18002fd5f  mov     [rsp+68h+var_30], rax
0x18002fd64  mov     r9d, 29h ; ')'
0x18002fd6a  mov     [rsp+68h+var_38], rsi
0x18002fd6f  xor     r8d, r8d
0x18002fd72  mov     [rsp+68h+var_40], esi
0x18002fd76  xor     edx, edx
0x18002fd78  mov     [rsp+68h+var_48], 4D2h
0x18002fd80  call    cs:__imp_RpcServerRegisterIf3
0x18002fd86  mov     ebx, eax
0x18002fd88  test    eax, eax
0x18002fd8a  jz      short loc_18002FDC0
0x18002fd8c  mov     r9d, 6B1h
0x18002fd92  cmp     eax, r9d
0x18002fd95  jnz     short loc_18002FDFF
0x18002fd97  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fd9e  cmp     rcx, r14
0x18002fda1  jz      short loc_18002FDC0
0x18002fda3  test    [rcx+1Ch], bpl
0x18002fda7  jz      short loc_18002FDC0
0x18002fda9  cmp     byte ptr [rcx+19h], 3
0x18002fdad  jb      short loc_18002FDC0
0x18002fdaf  mov     rcx, [rcx+10h]
0x18002fdb3  mov     edx, 14h
0x18002fdb8  mov     r8, r12
0x18002fdbb  call    WPP_SF_d
0x18002fdc0  lea     rcx, [rsp+68h+BindingVector]; BindingVector
0x18002fdc5  mov     cs:?g_fRpcIfRegisgtered@@3_NA, 1; bool g_fRpcIfRegisgtered
0x18002fdcc  call    cs:__imp_RpcServerInqBindings
0x18002fdd2  mov     ebx, eax
0x18002fdd4  test    eax, eax
0x18002fdd6  jz      short loc_18002FE1E
0x18002fdd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fddf  cmp     rcx, r14
0x18002fde2  jz      loc_18002FE73
0x18002fde8  test    [rcx+1Ch], bpl
0x18002fdec  jz      loc_18002FE73
0x18002fdf2  cmp     byte ptr [rcx+19h], 2
0x18002fdf6  jb      short loc_18002FE73
0x18002fdf8  mov     edx, 16h
0x18002fdfd  jmp     short loc_18002FE5D
0x18002fdff  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe06  cmp     rcx, r14
0x18002fe09  jz      short loc_18002FE73
0x18002fe0b  test    [rcx+1Ch], bpl
0x18002fe0f  jz      short loc_18002FE73
0x18002fe11  cmp     byte ptr [rcx+19h], 2
0x18002fe15  jb      short loc_18002FE73
0x18002fe17  mov     edx, 15h
0x18002fe1c  jmp     short loc_18002FE5D
0x18002fe1e  mov     rdx, [rsp+68h+BindingVector]; BindingVector
0x18002fe23  lea     rcx, qword_180092AC0; IfSpec
0x18002fe2a  xor     r9d, r9d; Annotation
0x18002fe2d  xor     r8d, r8d; UuidVector
0x18002fe30  call    cs:__imp_RpcEpRegisterW
0x18002fe36  mov     ebx, eax
0x18002fe38  test    eax, eax
0x18002fe3a  jz      loc_18002FFD0
0x18002fe40  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe47  cmp     rcx, r14
0x18002fe4a  jz      short loc_18002FE73
0x18002fe4c  test    [rcx+1Ch], bpl
0x18002fe50  jz      short loc_18002FE73
0x18002fe52  cmp     byte ptr [rcx+19h], 2
0x18002fe56  jb      short loc_18002FE73
0x18002fe58  mov     edx, 17h
0x18002fe5d  mov     r9d, eax
0x18002fe60  mov     rcx, [rcx+10h]
0x18002fe64  mov     r8, r12
0x18002fe67  call    WPP_SF_d
0x18002fe6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe73  cmp     cs:?g_fRpcEndPointRegistered@@3_NA, sil; bool g_fRpcEndPointRegistered
0x18002fe7a  mov     edi, esi
0x18002fe7c  jz      short loc_18002FED3
0x18002fe7e  mov     rdx, [rsp+68h+BindingVector]; BindingVector
0x18002fe83  lea     rcx, qword_180092AC0; IfSpec
0x18002fe8a  xor     r8d, r8d; UuidVector
0x18002fe8d  call    cs:__imp_RpcEpUnregister
0x18002fe93  mov     edi, eax
0x18002fe95  test    eax, eax
0x18002fe97  jz      short loc_18002FEC5
0x18002fe99  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fea0  cmp     rcx, r14
0x18002fea3  jz      short loc_18002FECC
0x18002fea5  test    [rcx+1Ch], bpl
0x18002fea9  jz      short loc_18002FECC
0x18002feab  cmp     byte ptr [rcx+19h], 2
0x18002feaf  jb      short loc_18002FECC
0x18002feb1  mov     rcx, [rcx+10h]
0x18002feb5  mov     edx, 18h
0x18002feba  mov     r9d, eax
0x18002febd  mov     r8, r12
0x18002fec0  call    WPP_SF_d
0x18002fec5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fecc  mov     cs:?g_fRpcEndPointRegistered@@3_NA, sil; bool g_fRpcEndPointRegistered
0x18002fed3  cmp     cs:?g_fRpcIfRegisgtered@@3_NA, sil; bool g_fRpcIfRegisgtered
0x18002feda  jz      short loc_18002FF2D
0x18002fedc  xor     edx, edx; MgrTypeUuid
0x18002fede  lea     rcx, qword_180092AC0; IfSpec
0x18002fee5  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x18002fee9  call    cs:__imp_RpcServerUnregisterIf
0x18002feef  test    edi, edi
0x18002fef1  jz      short loc_18002FF1F
0x18002fef3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fefa  cmp     rcx, r14
0x18002fefd  jz      short loc_18002FF26
0x18002feff  test    [rcx+1Ch], bpl
0x18002ff03  jz      short loc_18002FF26
0x18002ff05  cmp     byte ptr [rcx+19h], 2
0x18002ff09  jb      short loc_18002FF26
0x18002ff0b  mov     rcx, [rcx+10h]
0x18002ff0f  mov     edx, 19h
0x18002ff14  mov     r9d, edi
0x18002ff17  mov     r8, r12
0x18002ff1a  call    WPP_SF_d
0x18002ff1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff26  mov     cs:?g_fRpcIfRegisgtered@@3_NA, sil; bool g_fRpcIfRegisgtered
0x18002ff2d  cmp     cs:?g_fRpcCsInitialized@@3_NA, sil; bool g_fRpcCsInitialized
0x18002ff34  jz      short loc_18002FF6B
0x18002ff36  lea     rcx, ?g_csOperationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002ff3d  call    cs:__imp_DeleteCriticalSection
0x18002ff43  lea     rcx, ?g_csPolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002ff4a  call    cs:__imp_DeleteCriticalSection
0x18002ff50  lea     rcx, ?g_csDnsLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002ff57  call    cs:__imp_DeleteCriticalSection
0x18002ff5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff64  mov     cs:?g_fRpcCsInitialized@@3_NA, sil; bool g_fRpcCsInitialized
0x18002ff6b  mov     rax, cs:?g_StartDhcpServerBackgroundWork@@3PEAU_TP_WORK@@EA; _TP_WORK * g_StartDhcpServerBackgroundWork
0x18002ff72  test    rax, rax
0x18002ff75  jz      short loc_18002FFA0
0x18002ff77  mov     edx, 1; fCancelPendingCallbacks
0x18002ff7c  mov     rcx, rax; pwk
0x18002ff7f  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18002ff85  mov     rcx, cs:?g_StartDhcpServerBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18002ff8c  call    cs:__imp_CloseThreadpoolWork
0x18002ff92  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff99  mov     cs:?g_StartDhcpServerBackgroundWork@@3PEAU_TP_WORK@@EA, rsi; _TP_WORK * g_StartDhcpServerBackgroundWork
0x18002ffa0  mov     rax, cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA; _TP_WORK * g_StartSharingBackgroundWork
0x18002ffa7  test    rax, rax
0x18002ffaa  jz      short loc_18002FFDE
0x18002ffac  mov     edx, 1; fCancelPendingCallbacks
0x18002ffb1  mov     rcx, rax; pwk
0x18002ffb4  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18002ffba  mov     rcx, cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18002ffc1  call    cs:__imp_CloseThreadpoolWork
0x18002ffc7  mov     cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA, rsi; _TP_WORK * g_StartSharingBackgroundWork
0x18002ffce  jmp     short loc_18002FFD7
0x18002ffd0  mov     cs:?g_fRpcEndPointRegistered@@3_NA, 1; bool g_fRpcEndPointRegistered
0x18002ffd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ffde  mov     rax, [rsp+68h+SecurityDescriptor]
0x18002ffe3  test    rax, rax
0x18002ffe6  jz      short loc_18002FFF8
0x18002ffe8  mov     rcx, rax; hMem
0x18002ffeb  call    cs:__imp_LocalFree
0x18002fff1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fff8  cmp     [rsp+68h+BindingVector], rsi
0x18002fffd  jz      short loc_180030011
0x18002ffff  lea     rcx, [rsp+68h+BindingVector]; BindingVector
0x180030004  call    cs:__imp_RpcBindingVectorFree
0x18003000a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030011  cmp     rcx, r14
0x180030014  jz      short loc_180030036
0x180030016  test    [rcx+1Ch], bpl
0x18003001a  jz      short loc_180030036
0x18003001c  cmp     byte ptr [rcx+19h], 6
0x180030020  jb      short loc_180030036
0x180030022  mov     rcx, [rcx+10h]
0x180030026  mov     edx, 1Ah
0x18003002b  mov     r9d, ebx
0x18003002e  mov     r8, r12
0x180030031  call    WPP_SF_d
0x180030036  mov     eax, ebx
0x180030038  mov     rbx, [rsp+68h+arg_10]
0x180030040  add     rsp, 40h
0x180030044  pop     r14
0x180030046  pop     r12
0x180030048  pop     rdi
0x180030049  pop     rsi
0x18003004a  pop     rbp
0x18003004b  retn
```
