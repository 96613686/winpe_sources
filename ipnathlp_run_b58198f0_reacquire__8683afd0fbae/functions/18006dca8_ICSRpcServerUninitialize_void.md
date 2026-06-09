# ICSRpcServerUninitialize(void)

- ea: `0x18006dca8`
- end: `0x18006df40`
- name: `?ICSRpcServerUninitialize@@YAKXZ`
- size: `664`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180042360`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18006dca8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006de8c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006de9f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006deb2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006de8c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006de9f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006deb2`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18006dee9`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18006dee9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18006dd09`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18006dd44`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18006dd09`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18006dd44`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006dd1c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006dd57`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006dd1c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006dd57`
- `RPCRT4!RpcBindingVectorFree` at `0x18006de69`
- `RPCRT4!RpcBindingVectorFree` at `0x18006de69`
- `RPCRT4!RpcServerUnregisterIf` at `0x18006de17`
- `RPCRT4!RpcServerUnregisterIf` at `0x18006de17`
- `RPCRT4!RpcEpUnregister` at `0x18006ddbc`
- `RPCRT4!RpcEpUnregister` at `0x18006ddbc`
- `RPCRT4!RpcServerInqBindings` at `0x18006dd73`
- `RPCRT4!RpcServerInqBindings` at `0x18006dd73`

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
    v0 = RpcEpUnregister(qword_180099AB0, BindingVector, 0);
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
  v4 = RpcServerUnregisterIf(qword_180099AB0, 0, 1u);
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
0x18006dca8  mov     [rsp+arg_8], rbx
0x18006dcad  mov     [rsp+arg_10], rbp
0x18006dcb2  push    r15
0x18006dcb4  sub     rsp, 20h
0x18006dcb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dcbf  lea     rbp, WPP_GLOBAL_Control
0x18006dcc6  lea     r15, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x18006dccd  cmp     rcx, rbp
0x18006dcd0  jz      short loc_18006DCEF
0x18006dcd2  test    byte ptr [rcx+1Ch], 40h
0x18006dcd6  jz      short loc_18006DCEF
0x18006dcd8  cmp     byte ptr [rcx+19h], 6
0x18006dcdc  jb      short loc_18006DCEF
0x18006dcde  mov     rcx, [rcx+10h]
0x18006dce2  mov     edx, 1Dh
0x18006dce7  mov     r8, r15
0x18006dcea  call    WPP_SF_
0x18006dcef  mov     rcx, cs:?g_StartDhcpServerBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18006dcf6  mov     [rsp+28h+BindingVector], 0
0x18006dcff  test    rcx, rcx
0x18006dd02  jz      short loc_18006DD33
0x18006dd04  mov     edx, 1; fCancelPendingCallbacks
0x18006dd09  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18006dd10  nop     dword ptr [rax+rax+00h]
0x18006dd15  mov     rcx, cs:?g_StartDhcpServerBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18006dd1c  call    cs:__imp_CloseThreadpoolWork
0x18006dd23  nop     dword ptr [rax+rax+00h]
0x18006dd28  mov     cs:?g_StartDhcpServerBackgroundWork@@3PEAU_TP_WORK@@EA, 0; _TP_WORK * g_StartDhcpServerBackgroundWork
0x18006dd33  mov     rcx, cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18006dd3a  test    rcx, rcx
0x18006dd3d  jz      short loc_18006DD6E
0x18006dd3f  mov     edx, 1; fCancelPendingCallbacks
0x18006dd44  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18006dd4b  nop     dword ptr [rax+rax+00h]
0x18006dd50  mov     rcx, cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18006dd57  call    cs:__imp_CloseThreadpoolWork
0x18006dd5e  nop     dword ptr [rax+rax+00h]
0x18006dd63  mov     cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA, 0; _TP_WORK * g_StartSharingBackgroundWork
0x18006dd6e  lea     rcx, [rsp+28h+BindingVector]; BindingVector
0x18006dd73  call    cs:__imp_RpcServerInqBindings
0x18006dd7a  nop     dword ptr [rax+rax+00h]
0x18006dd7f  mov     ebx, eax
0x18006dd81  test    eax, eax
0x18006dd83  jz      short loc_18006DDA4
0x18006dd85  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dd8c  cmp     rcx, rbp
0x18006dd8f  jz      short loc_18006DE01
0x18006dd91  test    byte ptr [rcx+1Ch], 40h
0x18006dd95  jz      short loc_18006DE01
0x18006dd97  cmp     byte ptr [rcx+19h], 2
0x18006dd9b  jb      short loc_18006DE01
0x18006dd9d  mov     edx, 1Eh
0x18006dda2  jmp     short loc_18006DDEB
0x18006dda4  cmp     cs:?g_fRpcEndPointRegistered@@3_NA, 0; bool g_fRpcEndPointRegistered
0x18006ddab  jz      short loc_18006DDFA
0x18006ddad  mov     rdx, [rsp+28h+BindingVector]; BindingVector
0x18006ddb2  lea     rcx, qword_180099AB0; IfSpec
0x18006ddb9  xor     r8d, r8d; UuidVector
0x18006ddbc  call    cs:__imp_RpcEpUnregister
0x18006ddc3  nop     dword ptr [rax+rax+00h]
0x18006ddc8  mov     ebx, eax
0x18006ddca  test    eax, eax
0x18006ddcc  jz      short loc_18006DDFA
0x18006ddce  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ddd5  cmp     rcx, rbp
0x18006ddd8  jz      short loc_18006DE01
0x18006ddda  test    byte ptr [rcx+1Ch], 40h
0x18006ddde  jz      short loc_18006DE01
0x18006dde0  cmp     byte ptr [rcx+19h], 2
0x18006dde4  jb      short loc_18006DE01
0x18006dde6  mov     edx, 1Fh
0x18006ddeb  mov     rcx, [rcx+10h]
0x18006ddef  mov     r9d, eax
0x18006ddf2  mov     r8, r15
0x18006ddf5  call    WPP_SF_d
0x18006ddfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18006de01  cmp     cs:?g_fRpcIfRegisgtered@@3_NA, 0; bool g_fRpcIfRegisgtered
0x18006de08  jz      short loc_18006DE5C
0x18006de0a  xor     edx, edx; MgrTypeUuid
0x18006de0c  lea     rcx, qword_180099AB0; IfSpec
0x18006de13  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x18006de17  call    cs:__imp_RpcServerUnregisterIf
0x18006de1e  nop     dword ptr [rax+rax+00h]
0x18006de23  mov     ebx, eax
0x18006de25  test    eax, eax
0x18006de27  jz      short loc_18006DE55
0x18006de29  mov     rcx, cs:WPP_GLOBAL_Control
0x18006de30  cmp     rcx, rbp
0x18006de33  jz      short loc_18006DE5C
0x18006de35  test    byte ptr [rcx+1Ch], 40h
0x18006de39  jz      short loc_18006DE5C
0x18006de3b  cmp     byte ptr [rcx+19h], 2
0x18006de3f  jb      short loc_18006DE5C
0x18006de41  mov     rcx, [rcx+10h]
0x18006de45  mov     edx, 20h ; ' '
0x18006de4a  mov     r9d, eax
0x18006de4d  mov     r8, r15
0x18006de50  call    WPP_SF_d
0x18006de55  mov     rcx, cs:WPP_GLOBAL_Control
0x18006de5c  cmp     [rsp+28h+BindingVector], 0
0x18006de62  jz      short loc_18006DE7C
0x18006de64  lea     rcx, [rsp+28h+BindingVector]; BindingVector
0x18006de69  call    cs:__imp_RpcBindingVectorFree
0x18006de70  nop     dword ptr [rax+rax+00h]
0x18006de75  mov     rcx, cs:WPP_GLOBAL_Control
0x18006de7c  cmp     cs:?g_fRpcCsInitialized@@3_NA, 0; bool g_fRpcCsInitialized
0x18006de83  jz      short loc_18006DEC5
0x18006de85  lea     rcx, ?g_csOperationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006de8c  call    cs:__imp_DeleteCriticalSection
0x18006de93  nop     dword ptr [rax+rax+00h]
0x18006de98  lea     rcx, ?g_csPolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006de9f  call    cs:__imp_DeleteCriticalSection
0x18006dea6  nop     dword ptr [rax+rax+00h]
0x18006deab  lea     rcx, ?g_csDnsLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006deb2  call    cs:__imp_DeleteCriticalSection
0x18006deb9  nop     dword ptr [rax+rax+00h]
0x18006debe  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dec5  mov     rax, cs:?g_hIpNotify@@3PEAXEA; void * g_hIpNotify
0x18006decc  mov     cs:?g_fRpcIfRegisgtered@@3_NA, 0; bool g_fRpcIfRegisgtered
0x18006ded3  mov     cs:?g_fRpcEndPointRegistered@@3_NA, 0; bool g_fRpcEndPointRegistered
0x18006deda  mov     cs:?g_fRpcCsInitialized@@3_NA, 0; bool g_fRpcCsInitialized
0x18006dee1  test    rax, rax
0x18006dee4  jz      short loc_18006DF07
0x18006dee6  mov     rcx, rax; NotificationHandle
0x18006dee9  call    cs:__imp_CancelMibChangeNotify2
0x18006def0  nop     dword ptr [rax+rax+00h]
0x18006def5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006defc  mov     cs:?g_hIpNotify@@3PEAXEA, 0; void * g_hIpNotify
0x18006df07  cmp     rcx, rbp
0x18006df0a  jz      short loc_18006DF2C
0x18006df0c  test    byte ptr [rcx+1Ch], 40h
0x18006df10  jz      short loc_18006DF2C
0x18006df12  cmp     byte ptr [rcx+19h], 6
0x18006df16  jb      short loc_18006DF2C
0x18006df18  mov     rcx, [rcx+10h]
0x18006df1c  mov     edx, 21h ; '!'
0x18006df21  mov     r9d, ebx
0x18006df24  mov     r8, r15
0x18006df27  call    WPP_SF_d
0x18006df2c  mov     rbp, [rsp+28h+arg_10]
0x18006df31  mov     eax, ebx
0x18006df33  mov     rbx, [rsp+28h+arg_8]
0x18006df38  add     rsp, 20h
0x18006df3c  pop     r15
0x18006df3e  retn
```
