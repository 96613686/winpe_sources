# NcbRegistrarUninitialize

- ea: `0x180021340`
- end: `0x180021431`
- name: `NcbRegistrarUninitialize`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001fce0`

## callees

- `0x18000a0a0`
- `0x18001c500`
- `0x180021340`
- `0x180022d28`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x1800213dd`
- `ntdll!RtlDeleteHashTable` at `0x1800213dd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800213ea`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800213ea`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x1800213af`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x1800213af`
- `RPCRT4!RpcServerInterfaceGroupDeactivate` at `0x180021386`
- `RPCRT4!RpcServerInterfaceGroupDeactivate` at `0x180021386`
- `WS2_32!__imp_closesocket` at `0x1800213fd`
- `WS2_32!__imp_closesocket` at `0x1800213fd`
- `WS2_32!__imp_WSACleanup` at `0x180021403`
- `WS2_32!__imp_WSACleanup` at `0x180021403`

## pseudocode

```c
void NcbRegistrarUninitialize()
{
  unsigned int v0; // eax
  __int64 v1; // rdx
  __int64 v2; // rcx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rdx
  SOCKET v7; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
  }
  if ( g_ncbRpcInterfaceGroup )
  {
    v0 = RpcServerInterfaceGroupDeactivate(g_ncbRpcInterfaceGroup, 0);
    if ( v0 && (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v2, v1, L"StopNcbRpcServer: RpcServerInterfaceGroupDeactivate failed", v0);
    v3 = RpcServerInterfaceGroupClose(g_ncbRpcInterfaceGroup);
    if ( v3 && (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v5, v4, L"StopNcbRpcServer: RpcServerInterfaceGroupClose failed", v3);
  }
  NcbPolicyUninitialize();
  RtlDeleteHashTable(g_ControlChannelTriggerContextTable);
  DeleteCriticalSection(&g_ControlChannelTriggerContextTableLock);
  v7 = g_NcbControlSocket;
  if ( g_NcbControlSocket != -1 )
  {
    closesocket(g_NcbControlSocket);
    WSACleanup();
    g_NcbControlSocket = -1;
  }
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v7, v6, L"NcbReg: Registrar uninitialized ended with", 0);
}

```

## disassembly

```asm
0x180021340  sub     rsp, 28h
0x180021344  mov     rcx, cs:WPP_GLOBAL_Control
0x18002134b  lea     rax, WPP_GLOBAL_Control
0x180021352  cmp     rcx, rax
0x180021355  jz      short loc_180021378
0x180021357  test    byte ptr [rcx+1Ch], 1
0x18002135b  jz      short loc_180021378
0x18002135d  cmp     byte ptr [rcx+19h], 6
0x180021361  jb      short loc_180021378
0x180021363  mov     rcx, [rcx+10h]
0x180021367  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18002136e  mov     edx, 55h ; 'U'
0x180021373  call    WPP_SF_
0x180021378  mov     rcx, cs:g_ncbRpcInterfaceGroup
0x18002137f  test    rcx, rcx
0x180021382  jz      short loc_1800213D1
0x180021384  xor     edx, edx
0x180021386  call    cs:__imp_RpcServerInterfaceGroupDeactivate
0x18002138c  test    eax, eax
0x18002138e  jz      short loc_1800213A8
0x180021390  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180021397  jz      short loc_1800213A8
0x180021399  mov     r9d, eax
0x18002139c  lea     r8, aStopncbrpcserv; "StopNcbRpcServer: RpcServerInterfaceGro"...
0x1800213a3  call    McTemplateU0zq_EventWriteTransfer
0x1800213a8  mov     rcx, cs:g_ncbRpcInterfaceGroup
0x1800213af  call    cs:__imp_RpcServerInterfaceGroupClose
0x1800213b5  test    eax, eax
0x1800213b7  jz      short loc_1800213D1
0x1800213b9  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800213c0  jz      short loc_1800213D1
0x1800213c2  mov     r9d, eax
0x1800213c5  lea     r8, aStopncbrpcserv_0; "StopNcbRpcServer: RpcServerInterfaceGro"...
0x1800213cc  call    McTemplateU0zq_EventWriteTransfer
0x1800213d1  call    NcbPolicyUninitialize
0x1800213d6  lea     rcx, g_ControlChannelTriggerContextTable
0x1800213dd  call    cs:__imp_RtlDeleteHashTable
0x1800213e3  lea     rcx, g_ControlChannelTriggerContextTableLock; lpCriticalSection
0x1800213ea  call    cs:__imp_DeleteCriticalSection
0x1800213f0  mov     rcx, cs:g_NcbControlSocket; s
0x1800213f7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800213fb  jz      short loc_180021414
0x1800213fd  call    cs:__imp_closesocket
0x180021403  call    cs:__imp_WSACleanup
0x180021409  mov     cs:g_NcbControlSocket, 0FFFFFFFFFFFFFFFFh
0x180021414  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18002141b  jz      short loc_18002142C
0x18002141d  xor     r9d, r9d
0x180021420  lea     r8, aNcbregRegistra_0; "NcbReg: Registrar uninitialized ended w"...
0x180021427  call    McTemplateU0zq_EventWriteTransfer
0x18002142c  add     rsp, 28h
0x180021430  retn
```
