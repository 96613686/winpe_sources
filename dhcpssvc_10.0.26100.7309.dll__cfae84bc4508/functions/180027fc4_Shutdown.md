# Shutdown

- ea: `0x180027fc4`
- end: `0x18002883e`
- name: `Shutdown`
- size: `2170`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180027ce0`
- `0x180034da0`

## callees

- `0x180002854`
- `0x18000323c`
- `0x180003864`
- `0x180003c9c`
- `0x180006310`
- `0x18000d274`
- `0x18000f144`
- `0x180019040`
- `0x18001d7a8`
- `0x18001f0f4`
- `0x18001f4b0`
- `0x1800254c4`
- `0x180025b4c`
- `0x180025b98`
- `0x1800277c4`
- `0x180027fc4`
- `0x180028844`
- `0x180034da0`
- `0x180053f60`
- `0x180062964`
- `0x180066260`
- `0x180067060`
- `0x1800676a4`
- `0x180069658`
- `0x180078b88`
- `0x1800794ec`
- `0x1800a0ff0`
- `0x1800cd010`

## import_xrefs

- `ADVAPI32!CryptReleaseContext` at `0x1800283bc`
- `ADVAPI32!CryptReleaseContext` at `0x1800283bc`
- `ADVAPI32!EventUnregister` at `0x1800287a3`
- `ADVAPI32!EventUnregister` at `0x1800287a3`
- `ADVAPI32!UnregisterTraceGuids` at `0x1800287de`
- `ADVAPI32!UnregisterTraceGuids` at `0x1800287de`
- `DNSAPI!DnsDhcpSrvRegisterTerm` at `0x180028376`
- `DNSAPI!DnsDhcpSrvRegisterTerm` at `0x180028376`
- `ESENT!JetCloseTable` at `0x1800283db`
- `ESENT!JetCloseTable` at `0x1800283db`
- `RPCRT4!RpcServerInqBindings` at `0x1800280a7`
- `RPCRT4!RpcServerInqBindings` at `0x1800280a7`
- `RPCRT4!RpcBindingVectorFree` at `0x18002814b`
- `RPCRT4!RpcBindingVectorFree` at `0x18002814b`
- `RPCRT4!RpcEpUnregister` at `0x1800280cf`
- `RPCRT4!RpcEpUnregister` at `0x180028112`
- `RPCRT4!RpcEpUnregister` at `0x1800280cf`
- `RPCRT4!RpcEpUnregister` at `0x180028112`
- `RPCRT4!RpcServerUnregisterIf` at `0x18002818a`
- `RPCRT4!RpcServerUnregisterIf` at `0x1800281c7`
- `RPCRT4!RpcServerUnregisterIf` at `0x18002818a`
- `RPCRT4!RpcServerUnregisterIf` at `0x1800281c7`
- `RPCRT4!RpcMgmtStopServerListening` at `0x1800281fa`
- `RPCRT4!RpcMgmtStopServerListening` at `0x1800281fa`
- `RPCRT4!RpcMgmtWaitServerListen` at `0x18002820a`
- `RPCRT4!RpcMgmtWaitServerListen` at `0x18002820a`
- `DSAUTH!DhcpDsCleanupDS` at `0x1800285e8`
- `DSAUTH!DhcpDsCleanupDS` at `0x1800286fb`
- `DSAUTH!DhcpDsCleanupDS` at `0x1800287bd`
- `DSAUTH!DhcpDsCleanupDS` at `0x1800285e8`
- `DSAUTH!DhcpDsCleanupDS` at `0x1800286fb`
- `DSAUTH!DhcpDsCleanupDS` at `0x1800287bd`
- `KERNEL32!DeleteTimerQueueEx` at `0x1800282f0`
- `KERNEL32!DeleteTimerQueueEx` at `0x1800282f0`
- `KERNEL32!SetEvent` at `0x180028290`
- `KERNEL32!SetEvent` at `0x180028290`
- `KERNEL32!DeleteCriticalSection` at `0x1800285d2`
- `KERNEL32!DeleteCriticalSection` at `0x180028647`
- `KERNEL32!DeleteCriticalSection` at `0x180028663`
- `KERNEL32!DeleteCriticalSection` at `0x18002867f`
- `KERNEL32!DeleteCriticalSection` at `0x18002869b`
- `KERNEL32!DeleteCriticalSection` at `0x1800286b7`
- `KERNEL32!DeleteCriticalSection` at `0x1800286d3`
- `KERNEL32!DeleteCriticalSection` at `0x1800286ef`
- `KERNEL32!DeleteCriticalSection` at `0x1800285d2`
- `KERNEL32!DeleteCriticalSection` at `0x180028647`
- `KERNEL32!DeleteCriticalSection` at `0x180028663`
- `KERNEL32!DeleteCriticalSection` at `0x18002867f`
- `KERNEL32!DeleteCriticalSection` at `0x18002869b`
- `KERNEL32!DeleteCriticalSection` at `0x1800286b7`
- `KERNEL32!DeleteCriticalSection` at `0x1800286d3`
- `KERNEL32!DeleteCriticalSection` at `0x1800286ef`
- `KERNEL32!CloseHandle` at `0x180028730`
- `KERNEL32!CloseHandle` at `0x180028730`
- `KERNEL32!LocalFree` at `0x180028316`
- `KERNEL32!LocalFree` at `0x180028316`
- `KERNEL32!EnterCriticalSection` at `0x180028718`
- `KERNEL32!EnterCriticalSection` at `0x180028718`
- `KERNEL32!LeaveCriticalSection` at `0x180028772`
- `KERNEL32!LeaveCriticalSection` at `0x180028772`
- `KERNEL32!HeapFree` at `0x180028590`
- `KERNEL32!HeapFree` at `0x1800285b8`
- `KERNEL32!HeapFree` at `0x180028758`
- `KERNEL32!HeapFree` at `0x180028590`
- `KERNEL32!HeapFree` at `0x1800285b8`
- `KERNEL32!HeapFree` at `0x180028758`
- `ole32!CoUninitialize` at `0x1800284af`
- `ole32!CoUninitialize` at `0x1800284af`

## pseudocode

```c
void __fastcall Shutdown(DWORD a1, __int64 a2, __int64 a3)
{
  char v3; // si
  char v4; // bp
  int String; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax
  int v17; // r10d
  unsigned int v18; // eax
  _QWORD *v19; // rcx
  int v20; // eax
  _UNKNOWN **v21; // rbx
  REGHANDLE v22; // rcx
  TRACEHANDLE v23; // rcx
  RPC_BINDING_VECTOR *BindingVector; // [rsp+88h] [rbp+20h] BYREF

  v3 = a3;
  v4 = a2;
  if ( !(_BYTE)a2 )
  {
    DhcpDsCleanupDS();
    v21 = (_UNKNOWN **)WPP_GLOBAL_Control;
    goto LABEL_91;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
  DhcpGlobalOkToService = 0;
  DhcpGlobalServiceStopping = 1;
  String = GetString(1077, a2, a3);
  DhcpUpdateAuditLog(1, String, 0, 0, 0, 0);
  if ( a1 )
    DhcpServerEventLog(1008, 1, a1);
  DhcpGlobalServiceStatus.dwCurrentState = 3;
  DhcpGlobalServiceStatus.dwCheckPoint = 1;
  UpdateStatus();
  if ( DhcpGlobalRpcStarted )
  {
    BindingVector = 0;
    v7 = RpcServerInqBindings(&BindingVector);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v7);
    }
    else
    {
      v8 = RpcEpUnregister(&unk_1800D2520, BindingVector, 0);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v8);
      v9 = RpcEpUnregister(&unk_1800D96F0, BindingVector, 0);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v9);
      RpcBindingVectorFree(&BindingVector);
    }
    v10 = RpcServerUnregisterIf(&unk_1800D2520, 0, 1u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v10);
    v11 = RpcServerUnregisterIf(&unk_1800D96F0, 0, 1u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v11);
    if ( !RpcMgmtStopServerListening(0) )
    {
      v12 = RpcMgmtWaitServerListen();
      if ( v12 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_31;
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v12);
      }
    }
    v13 = WPP_GLOBAL_Control;
LABEL_31:
    DhcpGlobalRpcStarted = 0;
    goto LABEL_33;
  }
  v13 = WPP_GLOBAL_Control;
LABEL_33:
  if ( v13 != &WPP_GLOBAL_Control && (*((_DWORD *)v13 + 7) & 0x8000) != 0 )
  {
    WPP_SF_(v13[2], 98, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    v13 = WPP_GLOBAL_Control;
  }
  if ( DhcpGlobalProcessTerminationEvent )
  {
    SetEvent(DhcpGlobalProcessTerminationEvent);
    DhcpFSMCleanup();
    DhcpCleanupClientToServer();
    v16 = GetString(11011, v14, v15);
    DhcpV6UpdateAuditLog(v17, v16, 0, 0, 0, 0, 0);
    DhcpV6GlobalServiceStopping = 1;
    DhcpV6CleanupClientToServer();
    if ( hTimerQueue )
    {
      DeleteTimerQueueEx(hTimerQueue, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      hTimerQueue = 0;
    }
    DhcpRogueCleanup(0);
    if ( DhcpGlobalDSDomainAnsi )
    {
      LocalFree(DhcpGlobalDSDomainAnsi);
      DhcpGlobalDSDomainAnsi = 0;
    }
    v13 = WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)v13 + 7) & 0x8000) != 0 )
    {
      WPP_SF_(v13[2], 99, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != &WPP_GLOBAL_Control && (*((_DWORD *)v13 + 7) & 0x8000) != 0 )
      WPP_SF_(v13[2], 100, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
  }
  if ( !DhcpGlobalUseNoDns )
    DnsDhcpSrvRegisterTerm();
  DhcpCleanupDnsMemory();
  Dhcpv6CleanupDnsMemory();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
  if ( hCryptProv )
    CryptReleaseContext(hCryptProv, 0);
  if ( DhcpGlobalClientTableV6Handle )
  {
    v18 = JetCloseTable(DhcpGlobalJetServerSession, DhcpGlobalClientTableV6Handle);
    DhcpMapJetError(v18, "CloseTable");
    DhcpGlobalClientTableV6Handle = 0;
  }
  DhcpJetCleanupConfigTable6();
  DhcpCleanupDatabase();
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
      v19 = WPP_GLOBAL_Control;
    }
    if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 7) & 0x10000) != 0 )
    {
      WPP_SF_(v19[2], 36, &WPP_80e96922e6bf3bfb9ce3e5759cad305e_Traceguids);
      v19 = WPP_GLOBAL_Control;
    }
  }
  if ( dword_1800FB210 )
  {
    ((void (*)(void))qword_1800FB1F8)();
    v19 = WPP_GLOBAL_Control;
    dword_1800FB210 = 0;
  }
  if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 7) & 0x10000) != 0 )
  {
    WPP_SF_(v19[2], 19, &WPP_80e96922e6bf3bfb9ce3e5759cad305e_Traceguids);
    v19 = WPP_GLOBAL_Control;
  }
  if ( DhcpComNeedCleanUp )
  {
    CoUninitialize();
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_80e96922e6bf3bfb9ce3e5759cad305e_Traceguids);
      v19 = WPP_GLOBAL_Control;
    }
    DhcpComNeedCleanUp = 0;
    DhcpComInitialized = 0;
  }
  if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 7) & 0x8000) != 0 )
    WPP_SF_(v19[2], 103, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
  DhcpCleanupRegistry();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
  v20 = dword_1800FAE50;
  if ( dword_1800FAE50 )
  {
    --dword_1800FAE50;
    if ( v20 == 1 )
    {
      FreeTable();
      dword_1800FAE54 = 0;
    }
  }
  DhcpUALStop();
  if ( dword_1800FAE24 )
  {
    --dword_1800FAE24;
    AuditLogStop();
    if ( AuditLogFilePath )
    {
      HeapFree(gDhcpHeap, 0, (LPVOID)AuditLogFilePath);
      AuditLogFilePath = 0;
    }
    if ( AuditLogFileName )
    {
      HeapFree(gDhcpHeap, 0, AuditLogFileName);
      AuditLogFileName = 0;
    }
    DeleteCriticalSection(&AuditLogCritSect);
  }
  DhcpV6AuditLogCleanup();
  DhcpCleanupPerfCounters();
  DhcpDsCleanupDS();
  CleanupData();
  DhcpV6CleanupData();
  v21 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    v21 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
LABEL_91:
  if ( !v3 )
  {
    if ( fInProgressCritSectInit )
      DeleteCriticalSection(&DhcpGlobalInProgressCritSect);
    if ( fProcessMessageCritSectInit )
      DeleteCriticalSection(&g_ProcessMessageCritSect);
    if ( fMemoryCritSectInit )
      DeleteCriticalSection(&DhcpGlobalMemoryCritSect);
    if ( fRegCritSectInit )
      DeleteCriticalSection(&DhcpGlobalRegCritSect);
    if ( fQuarCritSectInit )
      DeleteCriticalSection(&DhcpGlobalQuarCritSect);
    if ( fJetDatabaseCritSectInit )
      DeleteCriticalSection(&DhcpGlobalJetDatabaseCritSect);
    if ( fStatelessCritSectInit )
      DeleteCriticalSection(&DhcpGlobalStatelessCritSect);
    DhcpDsCleanupDS();
    McGenEventUnregister_EventUnregister();
    FreeStrings();
    EnterCriticalSection(&DhcpGlobalDebugFileCritSect);
    if ( DhcpGlobalDebugFileHandle )
    {
      CloseHandle(DhcpGlobalDebugFileHandle);
      DhcpGlobalDebugFileHandle = 0;
    }
    if ( DhcpGlobalDebugSharePath )
    {
      HeapFree(gDhcpHeap, 0, DhcpGlobalDebugSharePath);
      DhcpGlobalDebugSharePath = 0;
    }
    LeaveCriticalSection(&DhcpGlobalDebugFileCritSect);
    v21 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( g_isRegisteredForUTC == 1 )
  {
    v22 = RegHandle;
    RegHandle = 0;
    dword_1800F6938 = 0;
    EventUnregister(v22);
    v21 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v21 != &WPP_GLOBAL_Control )
  {
    while ( v21 )
    {
      v23 = (TRACEHANDLE)v21[1];
      if ( v23 )
      {
        UnregisterTraceGuids(v23);
        v21[1] = 0;
      }
      v21 = (_UNKNOWN **)*v21;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    *(_QWORD *)&DhcpGlobalServiceStatus.dwCurrentState = 1;
    DhcpGlobalServiceStatus.dwWin32ExitCode = a1;
    *(_QWORD *)&DhcpGlobalServiceStatus.dwCheckPoint = 0;
    UpdateStatus();
  }
}

```

## disassembly

```asm
0x180027fc4  mov     [rsp+arg_0], rbx
0x180027fc9  mov     [rsp+arg_8], rbp
0x180027fce  mov     [rsp+arg_10], rsi
0x180027fd3  push    rdi
0x180027fd4  push    r12
0x180027fd6  push    r13
0x180027fd8  push    r14
0x180027fda  push    r15
0x180027fdc  sub     rsp, 40h
0x180027fe0  xor     r14d, r14d
0x180027fe3  lea     r15, WPP_GLOBAL_Control
0x180027fea  mov     sil, r8b
0x180027fed  mov     bpl, dl
0x180027ff0  mov     edi, ecx
0x180027ff2  mov     r13d, 1
0x180027ff8  test    dl, dl
0x180027ffa  jz      loc_1800287BD
0x180028000  mov     rcx, cs:WPP_GLOBAL_Control
0x180028007  lea     r12, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x18002800e  mov     ebx, 8000h
0x180028013  cmp     rcx, r15
0x180028016  jz      short loc_18002802D
0x180028018  test    [rcx+1Ch], ebx
0x18002801b  jz      short loc_18002802D
0x18002801d  mov     rcx, [rcx+10h]
0x180028021  lea     edx, [r13+5Ah]
0x180028025  mov     r8, r12
0x180028028  call    WPP_SF_
0x18002802d  mov     ecx, 435h
0x180028032  mov     cs:DhcpGlobalOkToService, r14d
0x180028039  mov     cs:DhcpGlobalServiceStopping, r13d
0x180028040  call    GetString
0x180028045  mov     rdx, rax
0x180028048  mov     [rsp+68h+var_40], r14
0x18002804d  mov     ecx, r13d
0x180028050  mov     [rsp+68h+var_48], r14d
0x180028055  xor     r9d, r9d
0x180028058  xor     r8d, r8d
0x18002805b  call    DhcpUpdateAuditLog
0x180028060  test    edi, edi
0x180028062  jz      short loc_180028074
0x180028064  mov     r8d, edi
0x180028067  mov     edx, r13d
0x18002806a  mov     ecx, 3F0h
0x18002806f  call    DhcpServerEventLog
0x180028074  mov     cs:DhcpGlobalServiceStatus.dwCurrentState, 3
0x18002807e  mov     cs:DhcpGlobalServiceStatus.dwCheckPoint, r13d
0x180028085  call    UpdateStatus
0x18002808a  cmp     cs:DhcpGlobalRpcStarted, r14d
0x180028091  jz      loc_180028254
0x180028097  lea     rcx, [rsp+68h+BindingVector]; BindingVector
0x18002809f  mov     [rsp+68h+BindingVector], r14
0x1800280a7  call    cs:__imp_RpcServerInqBindings
0x1800280ae  nop     dword ptr [rax+rax+00h]
0x1800280b3  mov     bl, 10h
0x1800280b5  test    eax, eax
0x1800280b7  jnz     loc_180028159
0x1800280bd  mov     rdx, [rsp+68h+BindingVector]; BindingVector
0x1800280c5  lea     rcx, unk_1800D2520; IfSpec
0x1800280cc  xor     r8d, r8d; UuidVector
0x1800280cf  call    cs:__imp_RpcEpUnregister
0x1800280d6  nop     dword ptr [rax+rax+00h]
0x1800280db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280e2  cmp     rcx, r15
0x1800280e5  jz      short loc_180028100
0x1800280e7  test    [rcx+1Ch], bl
0x1800280ea  jz      short loc_180028100
0x1800280ec  mov     rcx, [rcx+10h]
0x1800280f0  mov     edx, 5Ch ; '\'
0x1800280f5  mov     r9d, eax
0x1800280f8  mov     r8, r12
0x1800280fb  call    WPP_SF_D
0x180028100  mov     rdx, [rsp+68h+BindingVector]; BindingVector
0x180028108  lea     rcx, unk_1800D96F0; IfSpec
0x18002810f  xor     r8d, r8d; UuidVector
0x180028112  call    cs:__imp_RpcEpUnregister
0x180028119  nop     dword ptr [rax+rax+00h]
0x18002811e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028125  cmp     rcx, r15
0x180028128  jz      short loc_180028143
0x18002812a  test    [rcx+1Ch], bl
0x18002812d  jz      short loc_180028143
0x18002812f  mov     rcx, [rcx+10h]
0x180028133  mov     edx, 5Dh ; ']'
0x180028138  mov     r9d, eax
0x18002813b  mov     r8, r12
0x18002813e  call    WPP_SF_D
0x180028143  lea     rcx, [rsp+68h+BindingVector]; BindingVector
0x18002814b  call    cs:__imp_RpcBindingVectorFree
0x180028152  nop     dword ptr [rax+rax+00h]
0x180028157  jmp     short loc_18002817E
0x180028159  mov     rcx, cs:WPP_GLOBAL_Control
0x180028160  cmp     rcx, r15
0x180028163  jz      short loc_18002817E
0x180028165  test    [rcx+1Ch], bl
0x180028168  jz      short loc_18002817E
0x18002816a  mov     rcx, [rcx+10h]
0x18002816e  mov     edx, 5Eh ; '^'
0x180028173  mov     r9d, eax
0x180028176  mov     r8, r12
0x180028179  call    WPP_SF_D
0x18002817e  mov     r8d, r13d; WaitForCallsToComplete
0x180028181  lea     rcx, unk_1800D2520; IfSpec
0x180028188  xor     edx, edx; MgrTypeUuid
0x18002818a  call    cs:__imp_RpcServerUnregisterIf
0x180028191  nop     dword ptr [rax+rax+00h]
0x180028196  mov     rcx, cs:WPP_GLOBAL_Control
0x18002819d  cmp     rcx, r15
0x1800281a0  jz      short loc_1800281BB
0x1800281a2  test    [rcx+1Ch], bl
0x1800281a5  jz      short loc_1800281BB
0x1800281a7  mov     rcx, [rcx+10h]
0x1800281ab  mov     edx, 5Fh ; '_'
0x1800281b0  mov     r9d, eax
0x1800281b3  mov     r8, r12
0x1800281b6  call    WPP_SF_D
0x1800281bb  mov     r8d, r13d; WaitForCallsToComplete
0x1800281be  lea     rcx, unk_1800D96F0; IfSpec
0x1800281c5  xor     edx, edx; MgrTypeUuid
0x1800281c7  call    cs:__imp_RpcServerUnregisterIf
0x1800281ce  nop     dword ptr [rax+rax+00h]
0x1800281d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281da  cmp     rcx, r15
0x1800281dd  jz      short loc_1800281F8
0x1800281df  test    [rcx+1Ch], bl
0x1800281e2  jz      short loc_1800281F8
0x1800281e4  mov     rcx, [rcx+10h]
0x1800281e8  mov     edx, 60h ; '`'
0x1800281ed  mov     r9d, eax
0x1800281f0  mov     r8, r12
0x1800281f3  call    WPP_SF_D
0x1800281f8  xor     ecx, ecx; Binding
0x1800281fa  call    cs:__imp_RpcMgmtStopServerListening
0x180028201  nop     dword ptr [rax+rax+00h]
0x180028206  test    eax, eax
0x180028208  jnz     short loc_18002823F
0x18002820a  call    cs:__imp_RpcMgmtWaitServerListen
0x180028211  nop     dword ptr [rax+rax+00h]
0x180028216  test    eax, eax
0x180028218  jz      short loc_18002823F
0x18002821a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028221  cmp     rcx, r15
0x180028224  jz      short loc_180028246
0x180028226  test    [rcx+1Ch], bl
0x180028229  jz      short loc_180028246
0x18002822b  mov     rcx, [rcx+10h]
0x18002822f  mov     edx, 61h ; 'a'
0x180028234  mov     r9d, eax
0x180028237  mov     r8, r12
0x18002823a  call    WPP_SF_D
0x18002823f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028246  mov     cs:DhcpGlobalRpcStarted, r14d
0x18002824d  mov     ebx, 8000h
0x180028252  jmp     short loc_18002825B
0x180028254  mov     rcx, cs:WPP_GLOBAL_Control
0x18002825b  cmp     rcx, r15
0x18002825e  jz      short loc_18002827D
0x180028260  test    [rcx+1Ch], ebx
0x180028263  jz      short loc_18002827D
0x180028265  mov     rcx, [rcx+10h]
0x180028269  mov     edx, 62h ; 'b'
0x18002826e  mov     r8, r12
0x180028271  call    WPP_SF_
0x180028276  mov     rcx, cs:WPP_GLOBAL_Control
0x18002827d  mov     rax, cs:DhcpGlobalProcessTerminationEvent
0x180028284  test    rax, rax
0x180028287  jz      loc_180028330
0x18002828d  mov     rcx, rax; hEvent
0x180028290  call    cs:__imp_SetEvent
0x180028297  nop     dword ptr [rax+rax+00h]
0x18002829c  call    DhcpFSMCleanup
0x1800282a1  call    DhcpCleanupClientToServer
0x1800282a6  mov     r10d, 2B03h
0x1800282ac  mov     ecx, r10d
0x1800282af  call    GetString
0x1800282b4  mov     [rsp+68h+var_38], r14d
0x1800282b9  mov     rdx, rax
0x1800282bc  mov     [rsp+68h+var_40], r14
0x1800282c1  mov     ecx, r10d
0x1800282c4  xor     r9d, r9d
0x1800282c7  mov     [rsp+68h+var_48], r14d
0x1800282cc  xor     r8d, r8d
0x1800282cf  call    DhcpV6UpdateAuditLog
0x1800282d4  mov     cs:DhcpV6GlobalServiceStopping, r13d
0x1800282db  call    DhcpV6CleanupClientToServer
0x1800282e0  mov     rcx, cs:hTimerQueue; TimerQueue
0x1800282e7  test    rcx, rcx
0x1800282ea  jz      short loc_180028303
0x1800282ec  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800282f0  call    cs:__imp_DeleteTimerQueueEx
0x1800282f7  nop     dword ptr [rax+rax+00h]
0x1800282fc  mov     cs:hTimerQueue, r14
0x180028303  xor     ecx, ecx; void *
0x180028305  call    DhcpRogueCleanup
0x18002830a  mov     rcx, cs:DhcpGlobalDSDomainAnsi; hMem
0x180028311  test    rcx, rcx
0x180028314  jz      short loc_180028329
0x180028316  call    cs:__imp_LocalFree
0x18002831d  nop     dword ptr [rax+rax+00h]
0x180028322  mov     cs:DhcpGlobalDSDomainAnsi, r14
0x180028329  mov     rcx, cs:WPP_GLOBAL_Control
0x180028330  cmp     rcx, r15
0x180028333  jz      short loc_18002836D
0x180028335  test    [rcx+1Ch], ebx
0x180028338  jz      short loc_180028352
0x18002833a  mov     rcx, [rcx+10h]
0x18002833e  mov     edx, 63h ; 'c'
0x180028343  mov     r8, r12
0x180028346  call    WPP_SF_
0x18002834b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028352  cmp     rcx, r15
0x180028355  jz      short loc_18002836D
0x180028357  test    [rcx+1Ch], ebx
0x18002835a  jz      short loc_18002836D
0x18002835c  mov     rcx, [rcx+10h]
0x180028360  mov     edx, 64h ; 'd'
0x180028365  mov     r8, r12
0x180028368  call    WPP_SF_
0x18002836d  cmp     cs:DhcpGlobalUseNoDns, r14d
0x180028374  jnz     short loc_180028382
0x180028376  call    cs:__imp_DnsDhcpSrvRegisterTerm
0x18002837d  nop     dword ptr [rax+rax+00h]
0x180028382  call    DhcpCleanupDnsMemory
0x180028387  call    Dhcpv6CleanupDnsMemory
0x18002838c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028393  cmp     rcx, r15
0x180028396  jz      short loc_1800283AE
0x180028398  test    [rcx+1Ch], ebx
0x18002839b  jz      short loc_1800283AE
0x18002839d  mov     rcx, [rcx+10h]
0x1800283a1  mov     edx, 65h ; 'e'
0x1800283a6  mov     r8, r12
0x1800283a9  call    WPP_SF_
0x1800283ae  mov     rcx, cs:hCryptProv; hProv
0x1800283b5  test    rcx, rcx
0x1800283b8  jz      short loc_1800283C8
0x1800283ba  xor     edx, edx; dwFlags
0x1800283bc  call    cs:__imp_CryptReleaseContext
0x1800283c3  nop     dword ptr [rax+rax+00h]
0x1800283c8  mov     rdx, cs:DhcpGlobalClientTableV6Handle; tableid
0x1800283cf  test    rdx, rdx
0x1800283d2  jz      short loc_1800283FC
0x1800283d4  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800283db  call    cs:__imp_JetCloseTable
0x1800283e2  nop     dword ptr [rax+rax+00h]
0x1800283e7  mov     ecx, eax
0x1800283e9  lea     rdx, aClosetable; "CloseTable"
0x1800283f0  call    DhcpMapJetError
0x1800283f5  mov     cs:DhcpGlobalClientTableV6Handle, r14
0x1800283fc  call    DhcpJetCleanupConfigTable6
0x180028401  call    DhcpCleanupDatabase
0x180028406  mov     rcx, cs:WPP_GLOBAL_Control
0x18002840d  lea     r13, WPP_80e96922e6bf3bfb9ce3e5759cad305e_Traceguids
0x180028414  mov     ebx, 10000h
0x180028419  cmp     rcx, r15
0x18002841c  jz      short loc_180028461
0x18002841e  test    dword ptr [rcx+1Ch], 8000h
0x180028425  jz      short loc_18002843F
0x180028427  mov     rcx, [rcx+10h]
0x18002842b  mov     edx, 66h ; 'f'
0x180028430  mov     r8, r12
0x180028433  call    WPP_SF_
0x180028438  mov     rcx, cs:WPP_GLOBAL_Control
0x18002843f  cmp     rcx, r15
0x180028442  jz      short loc_180028461
0x180028444  test    [rcx+1Ch], ebx
0x180028447  jz      short loc_180028461
0x180028449  mov     rcx, [rcx+10h]
0x18002844d  mov     edx, 24h ; '$'
0x180028452  mov     r8, r13
0x180028455  call    WPP_SF_
0x18002845a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028461  cmp     cs:dword_1800FB210, r14d
0x180028468  jz      short loc_180028484
0x18002846a  mov     rax, cs:qword_1800FB1F8
0x180028471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028476  mov     rcx, cs:WPP_GLOBAL_Control
0x18002847d  mov     cs:dword_1800FB210, r14d
0x180028484  cmp     rcx, r15
0x180028487  jz      short loc_1800284A6
0x180028489  test    [rcx+1Ch], ebx
0x18002848c  jz      short loc_1800284A6
0x18002848e  mov     rcx, [rcx+10h]
0x180028492  mov     edx, 13h
0x180028497  mov     r8, r13
0x18002849a  call    WPP_SF_
0x18002849f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284a6  cmp     cs:DhcpComNeedCleanUp, r14d
0x1800284ad  jz      short loc_1800284F2
0x1800284af  call    cs:__imp_CoUninitialize
0x1800284b6  nop     dword ptr [rax+rax+00h]
0x1800284bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284c2  cmp     rcx, r15
0x1800284c5  jz      short loc_1800284E4
0x1800284c7  test    [rcx+1Ch], ebx
0x1800284ca  jz      short loc_1800284E4
0x1800284cc  mov     rcx, [rcx+10h]
0x1800284d0  mov     edx, 14h
0x1800284d5  mov     r8, r13
0x1800284d8  call    WPP_SF_
  ... truncated ...
```
