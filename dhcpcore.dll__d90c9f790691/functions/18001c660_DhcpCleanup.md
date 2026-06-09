# DhcpCleanup

- ea: `0x18001c660`
- end: `0x18001ca68`
- name: `DhcpCleanup`
- size: `1032`
- prototype: `__int64 __fastcall(DWORD)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180025350`

## callees

- `0x1800057f0`
- `0x180008240`
- `0x180009038`
- `0x180009108`
- `0x18000a100`
- `0x18000b650`
- `0x18000eafc`
- `0x18001c05c`
- `0x18001c0f8`
- `0x18001c660`
- `0x18001ca70`
- `0x180020980`
- `0x180035c70`
- `0x180041224`
- `0x180045044`
- `0x180045168`
- `0x18004d1a0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c72e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c761`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c929`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c942`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c95b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c974`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c72e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c761`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c929`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c942`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c95b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c974`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18001c721`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18001c721`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c7fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c88f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c7fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c88f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c7c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c816`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c7c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c816`
- `DNSAPI!DnsDhcpRegisterTerm` at `0x18001c991`
- `DNSAPI!DnsDhcpRegisterTerm` at `0x18001c991`
- `SspiCli!LsaUnregisterPolicyChangeNotification` at `0x18001c754`
- `SspiCli!LsaUnregisterPolicyChangeNotification` at `0x18001c754`
- `WS2_32!__imp_WSACleanup` at `0x18001c9fd`
- `WS2_32!__imp_WSACleanup` at `0x18001c9fd`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001c9ce`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001c9ce`

## pseudocode

```c
__int64 __fastcall DhcpCleanup(DWORD a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  bool v4; // zf
  char *v5; // rax
  _QWORD *v6; // rbx
  _UNKNOWN **v7; // rsi
  _UNKNOWN **v8; // r8
  _QWORD *v9; // r9
  _QWORD *v10; // rdx
  _QWORD *v11; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 result; // rax
  _QWORD *v18; // [rsp+48h] [rbp+10h] BYREF

  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 111, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, a1);
  TraceLogErrorv4(0, a1, 12);
  if ( a1 )
  {
    if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 0x40) != 0 )
      McTemplateU0qq_EtwEventWriteTransfer(v2, ErrorServiceStop, a1, (unsigned int)DhcpGlobalIsShuttingDown);
  }
  else if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 0x20) != 0 )
  {
    McTemplateU0q_EtwEventWriteTransfer(v2, ServiceStop, (unsigned int)DhcpGlobalIsShuttingDown);
  }
  DhcpGlobalServiceStatus.dwCurrentState = 3;
  DhcpGlobalServiceStatus.dwCheckPoint = 0;
  UpdateStatus();
  if ( DhcpGlobalWinSockInitialized && DhcpCommonInitialized )
  {
    if ( DhcpGlobalWaitableTimerHandle )
    {
      CancelWaitableTimer(DhcpGlobalWaitableTimerHandle);
      CloseHandle(DhcpGlobalWaitableTimerHandle);
      DhcpGlobalWaitableTimerHandle = 0;
    }
    if ( !DhcpGlobalIsShuttingDown && DhcpLsaDnsDomChangeNotifyHandle )
    {
      LsaUnregisterPolicyChangeNotification(PolicyNotifyDnsDomainInformation, DhcpLsaDnsDomChangeNotifyHandle);
      CloseHandle(DhcpLsaDnsDomChangeNotifyHandle);
      DhcpLsaDnsDomChangeNotifyHandle = 0;
    }
    while ( DhcpGlobalForceBroadcastMediaList != (_UNKNOWN *)&DhcpGlobalForceBroadcastMediaList )
    {
      if ( *((_UNKNOWN ***)DhcpGlobalForceBroadcastMediaList + 1) != &DhcpGlobalForceBroadcastMediaList )
        goto LABEL_35;
      v3 = *(_QWORD *)DhcpGlobalForceBroadcastMediaList;
      if ( *(_UNKNOWN **)(*(_QWORD *)DhcpGlobalForceBroadcastMediaList + 8LL) != DhcpGlobalForceBroadcastMediaList )
        goto LABEL_35;
      v4 = DhcpGlobalForceBroadcastMediaList == (_UNKNOWN *)16;
      v5 = (char *)DhcpGlobalForceBroadcastMediaList - 16;
      DhcpGlobalForceBroadcastMediaList = *(_UNKNOWN **)DhcpGlobalForceBroadcastMediaList;
      v18 = v5;
      *(_QWORD *)(v3 + 8) = &DhcpGlobalForceBroadcastMediaList;
      if ( !v4 )
        DhcpPunycodeFree(&v18);
    }
    EnterCriticalSection(&DhcpGlobalNicListCritSect);
    CleanupNicList(&DhcpGlobalConnectedNICList, &DhcpGlobalAdaptersCount);
    CleanupNicList(&DhcpGlobalDisconnectedNICList, 0);
    CleanupNicList(&DhcpGlobalConnectPendingNICList, 0);
    LeaveCriticalSection(&DhcpGlobalNicListCritSect);
    if ( !DhcpGlobalIsShuttingDown )
    {
      EnterCriticalSection(&DhcpGlobalNotificationListCritSect);
      v6 = DhcpGlobalNotificationList;
      if ( DhcpGlobalNotificationList != (_UNKNOWN *)&DhcpGlobalNotificationList )
      {
        while ( 1 )
        {
          v7 = (_UNKNOWN **)*v6;
          v18 = v6;
          DhcpPunycodeFree(v6 + 3);
          DhcpPunycodeFree(v6 + 5);
          v8 = (_UNKNOWN **)*v6;
          if ( *(_QWORD **)(*v6 + 8LL) != v6 )
            break;
          v9 = v6 + 1;
          v10 = (_QWORD *)v6[1];
          if ( (_QWORD *)*v10 != v6 )
            break;
          v11 = v6;
          *v10 = v8;
          v8[1] = v10;
          v6 = v7;
          *v9 = v11;
          *v11 = v11;
          DhcpPunycodeFree(&v18);
          if ( v7 == &DhcpGlobalNotificationList )
            goto LABEL_25;
        }
LABEL_35:
        __fastfail(3u);
      }
LABEL_25:
      LeaveCriticalSection(&DhcpGlobalNotificationListCritSect);
    }
    if ( !(unsigned int)DhcpIsFSEGuestSystem() )
      DhcpCleanupRegistryOnServiceStop();
    if ( !DhcpGlobalIsShuttingDown )
    {
      while ( 1 )
      {
        v13 = DhcpGlobalParamChangeRequestList;
        if ( DhcpGlobalParamChangeRequestList == &DhcpGlobalParamChangeRequestList )
          break;
        if ( *((LPVOID **)DhcpGlobalParamChangeRequestList + 1) != &DhcpGlobalParamChangeRequestList )
          goto LABEL_35;
        v14 = *(_QWORD *)DhcpGlobalParamChangeRequestList;
        if ( *(LPVOID *)(*(_QWORD *)DhcpGlobalParamChangeRequestList + 8LL) != DhcpGlobalParamChangeRequestList )
          goto LABEL_35;
        DhcpGlobalParamChangeRequestList = *(LPVOID *)DhcpGlobalParamChangeRequestList;
        *(_QWORD *)(v14 + 8) = &DhcpGlobalParamChangeRequestList;
        v15 = *((unsigned int *)v13 + 8);
        v18 = v13;
        if ( (_DWORD)v15 )
          DhcpDelClass(v12, v13[3], v15);
        DhcpPunycodeFree(&v18);
      }
      if ( !(unsigned int)DhcpIsFSEGuestSystem() )
        DhcpCleanupRegistry();
    }
    DhcpFirewallCleanup();
    if ( !DhcpGlobalIsShuttingDown )
    {
      if ( DhcpGlobalTerminateEvent )
      {
        CloseHandle(DhcpGlobalTerminateEvent);
        DhcpGlobalTerminateEvent = 0;
      }
      if ( DhcpGlobalServiceSyncEvent )
      {
        CloseHandle(DhcpGlobalServiceSyncEvent);
        DhcpGlobalServiceSyncEvent = 0;
      }
      if ( DhcpGlobalRecomputeTimerEvent )
      {
        CloseHandle(DhcpGlobalRecomputeTimerEvent);
        DhcpGlobalRecomputeTimerEvent = 0;
      }
      if ( DhcpGlobalRefreshEvent )
      {
        CloseHandle(DhcpGlobalRefreshEvent);
        DhcpGlobalRefreshEvent = 0;
      }
    }
    if ( DhcpGlobalUseMHAsyncDns )
    {
      if ( !DhcpGlobalIsShuttingDown )
      {
        v16 = DnsDhcpRegisterTerm();
        if ( v16 )
        {
          if ( (xmmword_1800616A0 & 2) != 0 )
            WPP_SF_D(1025, 112, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v16);
        }
      }
    }
  }
  PdcUnInitialize();
  if ( DhcpGlobalCSNotificationHandle )
  {
    PowerSettingUnregisterNotification(DhcpGlobalCSNotificationHandle);
    DhcpGlobalCSNotificationHandle = 0;
  }
  DhcpCRMPowerUnregistrationAndClean(
    &DhcpGlobalCrmNotificationHandle,
    &DhcpGlobalCrmActivity,
    (unsigned int)DhcpGlobalIsCrmRegistered);
  if ( DhcpGlobalWinSockInitialized )
  {
    WSACleanup();
    DhcpGlobalWinSockInitialized = 0;
  }
  DhcpFreeAllOptionDefs();
  DhcpFreeAllClasses();
  DhcpGlobalServiceStatus.dwCurrentState = 1;
  DhcpGlobalServiceStatus.dwWin32ExitCode = a1;
  *(_QWORD *)&DhcpGlobalServiceStatus.dwServiceSpecificExitCode = 0;
  DhcpGlobalServiceStatus.dwWaitHint = 0;
  UpdateStatus();
  result = DhcpPunycodeFree(&DhcpGlobalTraceExArray);
  if ( g_fVelocityDhcpMainThreadSleepTracing )
    return DhcpPunycodeFree(&g_pDhcpMainThreadTraceArray);
  return result;
}

```

## disassembly

```asm
0x18001c660  mov     [rsp+arg_0], rbx
0x18001c665  mov     [rsp+arg_10], rbp
0x18001c66a  push    rsi
0x18001c66b  push    rdi
0x18001c66c  push    r14
0x18001c66e  sub     rsp, 20h
0x18001c672  mov     edi, ecx
0x18001c674  test    byte ptr cs:xmmword_1800616A0, 2
0x18001c67b  jz      short loc_18001C696
0x18001c67d  mov     edx, 6Fh ; 'o'
0x18001c682  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18001c689  mov     ecx, 401h
0x18001c68e  mov     r9d, edi
0x18001c691  call    WPP_SF_D
0x18001c696  mov     r8d, 0Ch
0x18001c69c  mov     edx, edi
0x18001c69e  xor     ecx, ecx
0x18001c6a0  call    TraceLogErrorv4
0x18001c6a5  xor     ebp, ebp
0x18001c6a7  test    edi, edi
0x18001c6a9  jz      short loc_18001C6CC
0x18001c6ab  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 40h
0x18001c6b2  jz      short loc_18001C6E8
0x18001c6b4  mov     r9d, cs:DhcpGlobalIsShuttingDown
0x18001c6bb  lea     rdx, ErrorServiceStop
0x18001c6c2  mov     r8d, edi
0x18001c6c5  call    McTemplateU0qq_EtwEventWriteTransfer
0x18001c6ca  jmp     short loc_18001C6E8
0x18001c6cc  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 20h
0x18001c6d3  jz      short loc_18001C6E8
0x18001c6d5  mov     r8d, cs:DhcpGlobalIsShuttingDown
0x18001c6dc  lea     rdx, ServiceStop
0x18001c6e3  call    McTemplateU0q_EtwEventWriteTransfer
0x18001c6e8  mov     cs:DhcpGlobalServiceStatus.dwCurrentState, 3
0x18001c6f2  mov     cs:DhcpGlobalServiceStatus.dwCheckPoint, ebp
0x18001c6f8  call    UpdateStatus
0x18001c6fd  cmp     cs:DhcpGlobalWinSockInitialized, ebp
0x18001c703  jz      loc_18001C9BD
0x18001c709  cmp     cs:DhcpCommonInitialized, ebp
0x18001c70f  jz      loc_18001C9BD
0x18001c715  mov     rcx, cs:DhcpGlobalWaitableTimerHandle; hTimer
0x18001c71c  test    rcx, rcx
0x18001c71f  jz      short loc_18001C73B
0x18001c721  call    cs:__imp_CancelWaitableTimer
0x18001c727  mov     rcx, cs:DhcpGlobalWaitableTimerHandle; hObject
0x18001c72e  call    cs:__imp_CloseHandle
0x18001c734  mov     cs:DhcpGlobalWaitableTimerHandle, rbp
0x18001c73b  cmp     cs:DhcpGlobalIsShuttingDown, ebp
0x18001c741  jnz     short loc_18001C76E
0x18001c743  mov     rdx, cs:DhcpLsaDnsDomChangeNotifyHandle; NotificationEventHandle
0x18001c74a  test    rdx, rdx
0x18001c74d  jz      short loc_18001C76E
0x18001c74f  mov     ecx, 4; InformationClass
0x18001c754  call    cs:__imp_LsaUnregisterPolicyChangeNotification
0x18001c75a  mov     rcx, cs:DhcpLsaDnsDomChangeNotifyHandle; hObject
0x18001c761  call    cs:__imp_CloseHandle
0x18001c767  mov     cs:DhcpLsaDnsDomChangeNotifyHandle, rbp
0x18001c76e  lea     rbx, DhcpGlobalForceBroadcastMediaList
0x18001c775  mov     rax, cs:DhcpGlobalForceBroadcastMediaList
0x18001c77c  cmp     rax, rbx
0x18001c77f  jz      short loc_18001C7BA
0x18001c781  cmp     [rax+8], rbx
0x18001c785  jnz     loc_18001C8FB
0x18001c78b  mov     rcx, [rax]
0x18001c78e  cmp     [rcx+8], rax
0x18001c792  jnz     loc_18001C8FB
0x18001c798  add     rax, 0FFFFFFFFFFFFFFF0h
0x18001c79c  mov     cs:DhcpGlobalForceBroadcastMediaList, rcx
0x18001c7a3  mov     [rsp+38h+arg_8], rax
0x18001c7a8  mov     [rcx+8], rbx
0x18001c7ac  jz      short loc_18001C775
0x18001c7ae  lea     rcx, [rsp+38h+arg_8]
0x18001c7b3  call    DhcpPunycodeFree
0x18001c7b8  jmp     short loc_18001C775
0x18001c7ba  lea     rcx, DhcpGlobalNicListCritSect; lpCriticalSection
0x18001c7c1  call    cs:__imp_EnterCriticalSection
0x18001c7c7  lea     rdx, DhcpGlobalAdaptersCount
0x18001c7ce  lea     rcx, DhcpGlobalConnectedNICList
0x18001c7d5  call    CleanupNicList
0x18001c7da  xor     edx, edx
0x18001c7dc  lea     rcx, DhcpGlobalDisconnectedNICList
0x18001c7e3  call    CleanupNicList
0x18001c7e8  xor     edx, edx
0x18001c7ea  lea     rcx, DhcpGlobalConnectPendingNICList
0x18001c7f1  call    CleanupNicList
0x18001c7f6  lea     rcx, DhcpGlobalNicListCritSect; lpCriticalSection
0x18001c7fd  call    cs:__imp_LeaveCriticalSection
0x18001c803  cmp     cs:DhcpGlobalIsShuttingDown, ebp
0x18001c809  jnz     loc_18001C895
0x18001c80f  lea     rcx, DhcpGlobalNotificationListCritSect; lpCriticalSection
0x18001c816  call    cs:__imp_EnterCriticalSection
0x18001c81c  mov     rbx, cs:DhcpGlobalNotificationList
0x18001c823  lea     r14, DhcpGlobalNotificationList
0x18001c82a  cmp     rbx, r14
0x18001c82d  jz      short loc_18001C888
0x18001c82f  mov     rsi, [rbx]
0x18001c832  lea     rcx, [rbx+18h]
0x18001c836  mov     [rsp+38h+arg_8], rbx
0x18001c83b  call    DhcpPunycodeFree
0x18001c840  lea     rcx, [rbx+28h]
0x18001c844  call    DhcpPunycodeFree
0x18001c849  mov     r8, [rbx]
0x18001c84c  cmp     [r8+8], rbx
0x18001c850  jnz     loc_18001C8FB
0x18001c856  lea     r9, [rbx+8]
0x18001c85a  mov     rdx, [r9]
0x18001c85d  cmp     [rdx], rbx
0x18001c860  jnz     loc_18001C8FB
0x18001c866  mov     rax, rbx
0x18001c869  mov     [rdx], r8
0x18001c86c  mov     [r8+8], rdx
0x18001c870  lea     rcx, [rsp+38h+arg_8]
0x18001c875  mov     rbx, rsi
0x18001c878  mov     [r9], rax
0x18001c87b  mov     [rax], rax
0x18001c87e  call    DhcpPunycodeFree
0x18001c883  cmp     rsi, r14
0x18001c886  jnz     short loc_18001C82F
0x18001c888  lea     rcx, DhcpGlobalNotificationListCritSect; lpCriticalSection
0x18001c88f  call    cs:__imp_LeaveCriticalSection
0x18001c895  call    DhcpIsFSEGuestSystem
0x18001c89a  test    eax, eax
0x18001c89c  jnz     short loc_18001C8A3
0x18001c89e  call    DhcpCleanupRegistryOnServiceStop
0x18001c8a3  cmp     cs:DhcpGlobalIsShuttingDown, ebp
0x18001c8a9  jnz     short loc_18001C910
0x18001c8ab  lea     rbx, DhcpGlobalParamChangeRequestList
0x18001c8b2  mov     rdx, cs:DhcpGlobalParamChangeRequestList
0x18001c8b9  cmp     rdx, rbx
0x18001c8bc  jz      short loc_18001C902
0x18001c8be  cmp     [rdx+8], rbx
0x18001c8c2  jnz     short loc_18001C8FB
0x18001c8c4  mov     rax, [rdx]
0x18001c8c7  cmp     [rax+8], rdx
0x18001c8cb  jnz     short loc_18001C8FB
0x18001c8cd  mov     cs:DhcpGlobalParamChangeRequestList, rax
0x18001c8d4  mov     [rax+8], rbx
0x18001c8d8  mov     r8d, [rdx+20h]
0x18001c8dc  mov     [rsp+38h+arg_8], rdx
0x18001c8e1  test    r8d, r8d
0x18001c8e4  jz      short loc_18001C8EF
0x18001c8e6  mov     rdx, [rdx+18h]
0x18001c8ea  call    DhcpDelClass
0x18001c8ef  lea     rcx, [rsp+38h+arg_8]
0x18001c8f4  call    DhcpPunycodeFree
0x18001c8f9  jmp     short loc_18001C8B2
0x18001c8fb  mov     ecx, 3
0x18001c900  int     29h; Win8: RtlFailFast(ecx)
0x18001c902  call    DhcpIsFSEGuestSystem
0x18001c907  test    eax, eax
0x18001c909  jnz     short loc_18001C910
0x18001c90b  call    DhcpCleanupRegistry
0x18001c910  call    DhcpFirewallCleanup
0x18001c915  cmp     cs:DhcpGlobalIsShuttingDown, ebp
0x18001c91b  jnz     short loc_18001C981
0x18001c91d  mov     rcx, cs:DhcpGlobalTerminateEvent; hObject
0x18001c924  test    rcx, rcx
0x18001c927  jz      short loc_18001C936
0x18001c929  call    cs:__imp_CloseHandle
0x18001c92f  mov     cs:DhcpGlobalTerminateEvent, rbp
0x18001c936  mov     rcx, cs:DhcpGlobalServiceSyncEvent; hObject
0x18001c93d  test    rcx, rcx
0x18001c940  jz      short loc_18001C94F
0x18001c942  call    cs:__imp_CloseHandle
0x18001c948  mov     cs:DhcpGlobalServiceSyncEvent, rbp
0x18001c94f  mov     rcx, cs:DhcpGlobalRecomputeTimerEvent; hObject
0x18001c956  test    rcx, rcx
0x18001c959  jz      short loc_18001C968
0x18001c95b  call    cs:__imp_CloseHandle
0x18001c961  mov     cs:DhcpGlobalRecomputeTimerEvent, rbp
0x18001c968  mov     rcx, cs:DhcpGlobalRefreshEvent; hObject
0x18001c96f  test    rcx, rcx
0x18001c972  jz      short loc_18001C981
0x18001c974  call    cs:__imp_CloseHandle
0x18001c97a  mov     cs:DhcpGlobalRefreshEvent, rbp
0x18001c981  cmp     cs:DhcpGlobalUseMHAsyncDns, ebp
0x18001c987  jz      short loc_18001C9BD
0x18001c989  cmp     cs:DhcpGlobalIsShuttingDown, ebp
0x18001c98f  jnz     short loc_18001C9BD
0x18001c991  call    cs:__imp_DnsDhcpRegisterTerm
0x18001c997  test    eax, eax
0x18001c999  jz      short loc_18001C9BD
0x18001c99b  test    byte ptr cs:xmmword_1800616A0, 2
0x18001c9a2  jz      short loc_18001C9BD
0x18001c9a4  mov     edx, 70h ; 'p'
0x18001c9a9  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18001c9b0  mov     ecx, 401h
0x18001c9b5  mov     r9d, eax
0x18001c9b8  call    WPP_SF_D
0x18001c9bd  call    PdcUnInitialize
0x18001c9c2  mov     rcx, cs:DhcpGlobalCSNotificationHandle; RegistrationHandle
0x18001c9c9  test    rcx, rcx
0x18001c9cc  jz      short loc_18001C9DB
0x18001c9ce  call    cs:__imp_PowerSettingUnregisterNotification
0x18001c9d4  mov     cs:DhcpGlobalCSNotificationHandle, rbp
0x18001c9db  mov     r8d, cs:DhcpGlobalIsCrmRegistered
0x18001c9e2  lea     rdx, DhcpGlobalCrmActivity
0x18001c9e9  lea     rcx, DhcpGlobalCrmNotificationHandle
0x18001c9f0  call    DhcpCRMPowerUnregistrationAndClean
0x18001c9f5  cmp     cs:DhcpGlobalWinSockInitialized, ebp
0x18001c9fb  jz      short loc_18001CA09
0x18001c9fd  call    cs:__imp_WSACleanup
0x18001ca03  mov     cs:DhcpGlobalWinSockInitialized, ebp
0x18001ca09  call    DhcpFreeAllOptionDefs
0x18001ca0e  call    DhcpFreeAllClasses
0x18001ca13  mov     cs:DhcpGlobalServiceStatus.dwCurrentState, 1
0x18001ca1d  mov     cs:DhcpGlobalServiceStatus.dwWin32ExitCode, edi
0x18001ca23  mov     qword ptr cs:DhcpGlobalServiceStatus.dwServiceSpecificExitCode, rbp
0x18001ca2a  mov     cs:DhcpGlobalServiceStatus.dwWaitHint, ebp
0x18001ca30  call    UpdateStatus
0x18001ca35  lea     rcx, DhcpGlobalTraceExArray
0x18001ca3c  call    DhcpPunycodeFree
0x18001ca41  cmp     cs:g_fVelocityDhcpMainThreadSleepTracing, ebp
0x18001ca47  jz      short loc_18001CA55
0x18001ca49  lea     rcx, g_pDhcpMainThreadTraceArray
0x18001ca50  call    DhcpPunycodeFree
0x18001ca55  mov     rbx, [rsp+38h+arg_0]
0x18001ca5a  mov     rbp, [rsp+38h+arg_10]
0x18001ca5f  add     rsp, 20h
0x18001ca63  pop     r14
0x18001ca65  pop     rdi
0x18001ca66  pop     rsi
0x18001ca67  retn
```
