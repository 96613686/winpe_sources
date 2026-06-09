# ICSRpcServerUninitialize(void)

- ea: `0x180068a74`
- end: `0x180068cc3`
- name: `?ICSRpcServerUninitialize@@YAKXZ`
- size: `591`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003eee0`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180068a74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180068c28`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180068c35`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180068c42`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180068c28`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180068c35`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180068c42`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180068c73`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180068c73`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180068ad5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180068b04`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180068ad5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180068b04`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180068ae2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180068b11`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180068ae2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180068b11`
- `RPCRT4!RpcBindingVectorFree` at `0x180068c0b`
- `RPCRT4!RpcBindingVectorFree` at `0x180068c0b`
- `RPCRT4!RpcServerUnregisterIf` at `0x180068bbf`
- `RPCRT4!RpcServerUnregisterIf` at `0x180068bbf`
- `RPCRT4!RpcEpUnregister` at `0x180068b6a`
- `RPCRT4!RpcEpUnregister` at `0x180068b6a`
- `RPCRT4!RpcServerInqBindings` at `0x180068b27`
- `RPCRT4!RpcServerInqBindings` at `0x180068b27`

## pseudocode

```c
__int64 ICSRpcServerUninitialize(void)
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  PVOID *v2; // rcx
  __int64 v3; // rdx
  unsigned int v4; // eax
  RPC_BINDING_VECTOR *BindingVector; // [rsp+30h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids);
  }
  BindingVector = 0;
  if ( g_StartDhcpServerBackgroundWork )
  {
    WaitForThreadpoolWorkCallbacks(g_StartDhcpServerBackgroundWork, 1);
    CloseThreadpoolWork(g_StartDhcpServerBackgroundWork);
    g_StartDhcpServerBackgroundWork = 0;
  }
  if ( g_StartSharingBackgroundWork )
  {
    WaitForThreadpoolWorkCallbacks(g_StartSharingBackgroundWork, 1);
    CloseThreadpoolWork(g_StartSharingBackgroundWork);
    g_StartSharingBackgroundWork = 0;
  }
  v0 = RpcServerInqBindings(&BindingVector);
  v1 = v0;
  if ( v0 )
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = 30;
LABEL_20:
      WPP_SF_d(v2[2], v3, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids, v0);
LABEL_21:
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    if ( !g_fRpcEndPointRegistered )
      goto LABEL_21;
    v0 = RpcEpUnregister(qword_180092AC0, BindingVector, 0);
    v1 = v0;
    if ( !v0 )
      goto LABEL_21;
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = 31;
      goto LABEL_20;
    }
  }
  if ( !g_fRpcIfRegisgtered )
    goto LABEL_29;
  v4 = RpcServerUnregisterIf(qword_180092AC0, 0, 1u);
  v1 = v4;
  if ( !v4 )
    goto LABEL_28;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids, v4);
LABEL_28:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_29:
  if ( BindingVector )
  {
    RpcBindingVectorFree(&BindingVector);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( g_fRpcCsInitialized )
  {
    DeleteCriticalSection(&g_csOperationLock);
    DeleteCriticalSection(&g_csPolicyLock);
    DeleteCriticalSection(&g_csDnsLock);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  g_fRpcIfRegisgtered = 0;
  g_fRpcEndPointRegistered = 0;
  g_fRpcCsInitialized = 0;
  if ( g_hIpNotify )
  {
    CancelMibChangeNotify2(g_hIpNotify);
    v2 = (PVOID *)WPP_GLOBAL_Control;
    g_hIpNotify = 0;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_d(v2[2], 33, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x180068a74  mov     [rsp+arg_8], rbx
0x180068a79  mov     [rsp+arg_10], rbp
0x180068a7e  push    r15
0x180068a80  sub     rsp, 20h
0x180068a84  mov     rcx, cs:WPP_GLOBAL_Control
0x180068a8b  lea     rbp, WPP_GLOBAL_Control
0x180068a92  lea     r15, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x180068a99  cmp     rcx, rbp
0x180068a9c  jz      short loc_180068ABB
0x180068a9e  test    byte ptr [rcx+1Ch], 40h
0x180068aa2  jz      short loc_180068ABB
0x180068aa4  cmp     byte ptr [rcx+19h], 6
0x180068aa8  jb      short loc_180068ABB
0x180068aaa  mov     rcx, [rcx+10h]
0x180068aae  mov     edx, 1Dh
0x180068ab3  mov     r8, r15
0x180068ab6  call    WPP_SF_
0x180068abb  mov     rcx, cs:?g_StartDhcpServerBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x180068ac2  mov     [rsp+28h+BindingVector], 0
0x180068acb  test    rcx, rcx
0x180068ace  jz      short loc_180068AF3
0x180068ad0  mov     edx, 1; fCancelPendingCallbacks
0x180068ad5  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180068adb  mov     rcx, cs:?g_StartDhcpServerBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x180068ae2  call    cs:__imp_CloseThreadpoolWork
0x180068ae8  mov     cs:?g_StartDhcpServerBackgroundWork@@3PEAU_TP_WORK@@EA, 0; _TP_WORK * g_StartDhcpServerBackgroundWork
0x180068af3  mov     rcx, cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x180068afa  test    rcx, rcx
0x180068afd  jz      short loc_180068B22
0x180068aff  mov     edx, 1; fCancelPendingCallbacks
0x180068b04  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180068b0a  mov     rcx, cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x180068b11  call    cs:__imp_CloseThreadpoolWork
0x180068b17  mov     cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA, 0; _TP_WORK * g_StartSharingBackgroundWork
0x180068b22  lea     rcx, [rsp+28h+BindingVector]; BindingVector
0x180068b27  call    cs:__imp_RpcServerInqBindings
0x180068b2d  mov     ebx, eax
0x180068b2f  test    eax, eax
0x180068b31  jz      short loc_180068B52
0x180068b33  mov     rcx, cs:WPP_GLOBAL_Control
0x180068b3a  cmp     rcx, rbp
0x180068b3d  jz      short loc_180068BA9
0x180068b3f  test    byte ptr [rcx+1Ch], 40h
0x180068b43  jz      short loc_180068BA9
0x180068b45  cmp     byte ptr [rcx+19h], 2
0x180068b49  jb      short loc_180068BA9
0x180068b4b  mov     edx, 1Eh
0x180068b50  jmp     short loc_180068B93
0x180068b52  cmp     cs:?g_fRpcEndPointRegistered@@3_NA, 0; bool g_fRpcEndPointRegistered
0x180068b59  jz      short loc_180068BA2
0x180068b5b  mov     rdx, [rsp+28h+BindingVector]; BindingVector
0x180068b60  lea     rcx, qword_180092AC0; IfSpec
0x180068b67  xor     r8d, r8d; UuidVector
0x180068b6a  call    cs:__imp_RpcEpUnregister
0x180068b70  mov     ebx, eax
0x180068b72  test    eax, eax
0x180068b74  jz      short loc_180068BA2
0x180068b76  mov     rcx, cs:WPP_GLOBAL_Control
0x180068b7d  cmp     rcx, rbp
0x180068b80  jz      short loc_180068BA9
0x180068b82  test    byte ptr [rcx+1Ch], 40h
0x180068b86  jz      short loc_180068BA9
0x180068b88  cmp     byte ptr [rcx+19h], 2
0x180068b8c  jb      short loc_180068BA9
0x180068b8e  mov     edx, 1Fh
0x180068b93  mov     rcx, [rcx+10h]
0x180068b97  mov     r9d, eax
0x180068b9a  mov     r8, r15
0x180068b9d  call    WPP_SF_d
0x180068ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x180068ba9  cmp     cs:?g_fRpcIfRegisgtered@@3_NA, 0; bool g_fRpcIfRegisgtered
0x180068bb0  jz      short loc_180068BFE
0x180068bb2  xor     edx, edx; MgrTypeUuid
0x180068bb4  lea     rcx, qword_180092AC0; IfSpec
0x180068bbb  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x180068bbf  call    cs:__imp_RpcServerUnregisterIf
0x180068bc5  mov     ebx, eax
0x180068bc7  test    eax, eax
0x180068bc9  jz      short loc_180068BF7
0x180068bcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180068bd2  cmp     rcx, rbp
0x180068bd5  jz      short loc_180068BFE
0x180068bd7  test    byte ptr [rcx+1Ch], 40h
0x180068bdb  jz      short loc_180068BFE
0x180068bdd  cmp     byte ptr [rcx+19h], 2
0x180068be1  jb      short loc_180068BFE
0x180068be3  mov     rcx, [rcx+10h]
0x180068be7  mov     edx, 20h ; ' '
0x180068bec  mov     r9d, eax
0x180068bef  mov     r8, r15
0x180068bf2  call    WPP_SF_d
0x180068bf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180068bfe  cmp     [rsp+28h+BindingVector], 0
0x180068c04  jz      short loc_180068C18
0x180068c06  lea     rcx, [rsp+28h+BindingVector]; BindingVector
0x180068c0b  call    cs:__imp_RpcBindingVectorFree
0x180068c11  mov     rcx, cs:WPP_GLOBAL_Control
0x180068c18  cmp     cs:?g_fRpcCsInitialized@@3_NA, 0; bool g_fRpcCsInitialized
0x180068c1f  jz      short loc_180068C4F
0x180068c21  lea     rcx, ?g_csOperationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180068c28  call    cs:__imp_DeleteCriticalSection
0x180068c2e  lea     rcx, ?g_csPolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180068c35  call    cs:__imp_DeleteCriticalSection
0x180068c3b  lea     rcx, ?g_csDnsLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180068c42  call    cs:__imp_DeleteCriticalSection
0x180068c48  mov     rcx, cs:WPP_GLOBAL_Control
0x180068c4f  mov     rax, cs:?g_hIpNotify@@3PEAXEA; void * g_hIpNotify
0x180068c56  mov     cs:?g_fRpcIfRegisgtered@@3_NA, 0; bool g_fRpcIfRegisgtered
0x180068c5d  mov     cs:?g_fRpcEndPointRegistered@@3_NA, 0; bool g_fRpcEndPointRegistered
0x180068c64  mov     cs:?g_fRpcCsInitialized@@3_NA, 0; bool g_fRpcCsInitialized
0x180068c6b  test    rax, rax
0x180068c6e  jz      short loc_180068C8B
0x180068c70  mov     rcx, rax; NotificationHandle
0x180068c73  call    cs:__imp_CancelMibChangeNotify2
0x180068c79  mov     rcx, cs:WPP_GLOBAL_Control
0x180068c80  mov     cs:?g_hIpNotify@@3PEAXEA, 0; void * g_hIpNotify
0x180068c8b  cmp     rcx, rbp
0x180068c8e  jz      short loc_180068CB0
0x180068c90  test    byte ptr [rcx+1Ch], 40h
0x180068c94  jz      short loc_180068CB0
0x180068c96  cmp     byte ptr [rcx+19h], 6
0x180068c9a  jb      short loc_180068CB0
0x180068c9c  mov     rcx, [rcx+10h]
0x180068ca0  mov     edx, 21h ; '!'
0x180068ca5  mov     r9d, ebx
0x180068ca8  mov     r8, r15
0x180068cab  call    WPP_SF_d
0x180068cb0  mov     rbp, [rsp+28h+arg_10]
0x180068cb5  mov     eax, ebx
0x180068cb7  mov     rbx, [rsp+28h+arg_8]
0x180068cbc  add     rsp, 20h
0x180068cc0  pop     r15
0x180068cc2  retn
```
