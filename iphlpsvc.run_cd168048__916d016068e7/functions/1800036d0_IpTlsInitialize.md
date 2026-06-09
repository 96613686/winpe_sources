# IpTlsInitialize

- ea: `0x1800036d0`
- end: `0x180003ca6`
- name: `IpTlsInitialize`
- size: `1494`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001ad0`
- `0x180001d14`
- `0x180001e74`
- `0x180001ff0`
- `0x1800023e0`
- `0x1800028d4`
- `0x18000364c`
- `0x1800036d0`
- `0x180003cac`
- `0x180003ce4`
- `0x180004098`
- `0x1800041a0`
- `0x180004f50`
- `0x18000d7b0`
- `0x180012e20`
- `0x180013570`
- `0x180014098`
- `0x180033788`
- `0x18003f298`
- `0x180040dd0`
- `0x180042840`

## import_xrefs

- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x180003a77`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x180003a77`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180003ab5`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180003ab5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a0a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003c6b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003c6b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800038fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800038fd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800037f8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800037f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003afc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180003709`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180003709`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180003a22`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180003a22`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientConnectToServer` at `0x180003990`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientConnectToServer` at `0x180003990`
- `WINNSI!NsiConnectToServer` at `0x180003ada`
- `WINNSI!NsiConnectToServer` at `0x180003ada`
- `WINNSI!NsiRpcRegisterChangeNotification` at `0x180003b7a`
- `WINNSI!NsiRpcRegisterChangeNotification` at `0x180003b7a`
- `FirewallAPI!FWResetIndicatedPortInUse` at `0x180003830`
- `FirewallAPI!FWResetIndicatedPortInUse` at `0x180003846`
- `FirewallAPI!FWResetIndicatedPortInUse` at `0x180003830`
- `FirewallAPI!FWResetIndicatedPortInUse` at `0x180003846`

## string_xrefs

- `0x18000380d`: `IpTlsInitialize: g_IpTlsDisabledInDisabledComponents = %d`
- `0x18000396f`: `Failed to listen for DA registry state updates: 0x%x`
- `0x18000397d`: `DA is not enabled; listen for DA registry status changes`
- `0x180003c7d`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x18000375e`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180003a4b`: `IpTlsInitialize: CreateThreadpoolTimer failed:%d`

## pseudocode

```c
void __fastcall IpTlsInitialize(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  unsigned int v2; // edi
  __int64 v3; // r9
  int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  DWORD LastError; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int v15; // esi
  __int64 v16; // rcx
  DWORD v17; // eax
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rcx
  unsigned int v24; // eax
  int NotificationHandle; // [rsp+20h] [rbp-78h]
  __int64 *v26; // [rsp+30h] [rbp-68h]
  struct _SYSTEM_INFO v27; // [rsp+40h] [rbp-58h] BYREF
  NLM_CONNECTIVITY v28; // [rsp+B0h] [rbp+18h] BYREF
  int v29; // [rsp+B8h] [rbp+20h] BYREF

  v28 = NLM_CONNECTIVITY_DISCONNECTED;
  v29 = 0;
  memset(&v27, 0, sizeof(v27));
  v2 = 31;
  GetSystemInfo(&v27);
  g_IpTlsNumReceiveQueues = 2 * v27.dwNumberOfProcessors;
  g_IpTlsProtocolState = 0;
  xmmword_1800CC410 = 0;
  xmmword_1800CC420 = 0;
  if ( !(unsigned int)InitializeLock(&g_IpTlsDeletedInterfaceListLock) )
  {
    v3 = 3373;
LABEL_3:
    EventWrite0(
      0x10000000,
      L"IpTlsInitialize: Allocation failed:%S:%d",
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptls.c",
      v3);
    goto LABEL_39;
  }
  if ( !(unsigned int)InitializeLock(&g_IpTlsInterfaceListLock) )
  {
    UninitializeLock(&g_IpTlsDeletedInterfaceListLock);
    v3 = 3379;
    goto LABEL_3;
  }
  if ( !(unsigned int)InitializeLock(&g_IpTlsConfigChangeLock) )
  {
    UninitializeLock(&g_IpTlsDeletedInterfaceListLock);
    UninitializeLock(&g_IpTlsInterfaceListLock);
    v3 = 3385;
    goto LABEL_3;
  }
  if ( !(unsigned int)InitializeLock(&g_IpTlsNLMNotificationLock) )
  {
    UninitializeLock(&g_IpTlsDeletedInterfaceListLock);
    UninitializeLock(&g_IpTlsConfigChangeLock);
    UninitializeLock(&g_IpTlsInterfaceListLock);
    v3 = 3393;
    goto LABEL_3;
  }
  InitializeCriticalSection(&g_IpTlsConnectedNetworkListLock);
  g_IpTlsDisabledInDisabledComponents = IpTlsIsDisabledInDisabledComponents();
  EventWrite0(0x10000000, L"IpTlsInitialize: g_IpTlsDisabledInDisabledComponents = %d");
  v4 = FWResetIndicatedPortInUse(2);
  if ( v4 < 0 || (v4 = FWResetIndicatedPortInUse(3), v4 < 0) )
  {
    UninitializeLock(&g_IpTlsDeletedInterfaceListLock);
    UninitializeLock(&g_IpTlsNLMNotificationLock);
    UninitializeLock(&g_IpTlsConfigChangeLock);
    UninitializeLock(&g_IpTlsInterfaceListLock);
    EventWrite0(0x10000000, L"IpTlsInitialize: IpTlsResetFirewallExceptions failed:%X", (unsigned int)v4);
    goto LABEL_39;
  }
  if ( (unsigned __int8)IsOSServerSku(v6, v5, v7, v8) )
    g_IpTlsConfigureServerInterfaces = 1;
  qword_1800CC398 = (__int64)&g_IpTlsInterfaceListHead;
  g_IpTlsInterfaceListHead = (__int64)&g_IpTlsInterfaceListHead;
  qword_1800CC448 = (__int64)&g_IpTlsGlobalV6AddressList;
  g_IpTlsGlobalV6AddressList = &g_IpTlsGlobalV6AddressList;
  qword_1800CC3A8 = (__int64)&g_IpTlsDeletedInterfaceList;
  g_IpTlsDeletedInterfaceList = (__int64)&g_IpTlsDeletedInterfaceList;
  qword_1800CC4B8 = (__int64)&g_IpTlsConnectedNetworkList;
  g_IpTlsConnectedNetworkList = (__int64)&g_IpTlsConnectedNetworkList;
  g_IpTlsInterfaceListEmptyEvent = CreateEventW(0, 0, 0, 0);
  if ( g_IpTlsInterfaceListEmptyEvent == (HANDLE)-1LL )
  {
    UninitializeLock(&g_IpTlsDeletedInterfaceListLock);
    UninitializeLock(&g_IpTlsNLMNotificationLock);
    UninitializeLock(&g_IpTlsConfigChangeLock);
    UninitializeLock(&g_IpTlsInterfaceListLock);
    v3 = 3435;
    goto LABEL_3;
  }
  g_IpTlsInterfaceListReferenceObject = 2;
  g_IpTlsIsDaEnabled = IsDaEnabled();
  if ( !g_IpTlsIsDaEnabled )
  {
    v9 = NotifyDaEnabled();
    if ( v9 )
      EventWrite0(0x10000000, L"Failed to listen for DA registry state updates: 0x%x", v9);
    else
      EventWrite0(0x10000000, L"DA is not enabled; listen for DA registry status changes");
  }
  if ( (unsigned int)ProxyHelperClientConnectToServer(&g_IpTlsProxyMgrRpcHandle) )
  {
    IpTlsCleanup(v10);
    EventWrite0(0x10000000, L"IpTlsInitialize: ProxyHelperClientConnectToServerfailed");
    v2 = 110;
    goto LABEL_39;
  }
  IpTlsAcquireLock(g_IpTlsConfigChangeLock);
  IpTlsRemoveDeletedInterfaces();
  EventWrite0(0x10000000, L"IpTlsInitialize:Starting always on interfaces");
  IpTlsAddEligibleInterfaces(2, 2);
  IpTlsAddEligibleInterfaces(2, 1);
  IpTlsAddEligibleInterfaces(2, 0);
  IpTlsCheckOutsideEnabledInterfaces();
  ReleaseMutex(g_IpTlsConfigChangeLock);
  g_IpTlsCorpConnectivityTimer = CreateThreadpoolTimer(IpTlsCorpConnectivityTimeoutHandler, 0, 0);
  if ( !g_IpTlsCorpConnectivityTimer )
  {
    IpTlsCleanup(v11);
    LastError = GetLastError();
    EventWrite0(0x10000000, L"IpTlsInitialize: CreateThreadpoolTimer failed:%d", LastError);
    goto LABEL_45;
  }
  v2 = NotifyUnicastIpAddressChange(0x17u, IpTlsIpAddressChangeCallback, 0, 1u, &g_IpTlsIpv6AddressChangeNotification);
  if ( v2 )
  {
    IpTlsCleanup(v13);
    EventWrite0(0x10000000, L"IpTlsInitialize: NotifyUnicastIpAddressChange failed:%d", v2);
    goto LABEL_39;
  }
  v2 = NotifyIpInterfaceChange(
         0x17u,
         (PIPINTERFACE_CHANGE_CALLBACK)IpTlsIpInterfaceChangeCallback,
         0,
         0,
         &g_IpTlsIpInterfaceChangeNotification);
  if ( v2 )
  {
    IpTlsCleanup(v14);
    EventWrite0(0x10000000, L"IpTlsInitialize: NotifyIpInterfaceChange failed:%d", v2);
    goto LABEL_39;
  }
  v15 = 0;
  *(_QWORD *)&xmmword_1800CC420 = NsiConnectToServer(0);
  v16 = xmmword_1800CC420;
  if ( (_QWORD)xmmword_1800CC420 )
  {
    while ( 1 )
    {
      v19 = 32LL * v15;
      v26 = &qword_1800C8330[v19 / 8 + 1];
      v20 = *(__int64 *)((char *)&off_1800C8328 + v19 + 24);
      v21 = *(unsigned int *)((char *)&off_1800C8328 + v19 + 8);
      v22 = *(__int64 *)((char *)&off_1800C8328 + v19);
      *v26 = 0;
      LOBYTE(NotificationHandle) = 1;
      v2 = NsiRpcRegisterChangeNotification(v16, v22, v21, v20, NotificationHandle, 0, v26);
      if ( v2 )
        break;
      if ( ++v15 )
        break;
      v16 = xmmword_1800CC420;
    }
  }
  else
  {
    v2 = 1722;
    v17 = GetLastError();
    EventWrite0(0x10000, L"NsiConnectToServer got error %d", v17);
  }
  EventWrite0(0x40000, L"RegisterNotificationHandlers - Registered %d handlers status %d", v15, v2);
  if ( v2 )
  {
    IpTlsCleanup(v18);
    goto LABEL_39;
  }
  v2 = RegisterWmiEventNotification();
  if ( v2 )
  {
    IpTlsCleanup(v23);
    EventWrite0(0x10000000, L"IpTlsInitialize: RegisterWmiEventNotification failed:%d", v2);
LABEL_39:
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_IPHTTPS_INIT_FAILED,
        &word_180087660,
        v2);
    goto LABEL_45;
  }
  if ( !(unsigned int)IpTlsGetGlobalConnectivity(&v28, &v29) )
    IpTlsGlobalConnectivityChangeNotification(v28);
  RegisterForGlobalConnectivityNotification(
    &g_IpTlsNLMGlobalConnectivityChangeNotification,
    IpTlsGlobalConnectivityChangeNotification);
  RegisterForNetworkChangeNotification(
    &g_IpTlsNLMNetworkChangeNotification,
    IpTlsNetworkAddNotification,
    (void (*)(struct _GUID *, enum NLM_CONNECTIVITY))IpTlsNetworkChangeNotification,
    0,
    IpTlsNetworkDeleteNotification);
  v24 = IpTlsInitializeGlobalPerformanceCounters();
  if ( v24 )
    EventWrite0(0x10000000, L"IpTlsInitialize: IpTlsInitializeGlobalPerformanceCountersfailed:%d", v24);
LABEL_45:
  SetEvent(g_IpTlsStartCompleteEvent);
  DereferenceServiceEx("InitializeIpTls", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptls.c", 3610);
}

```

## disassembly

```asm
0x1800036d0  mov     rax, rsp
0x1800036d3  mov     [rax+8], rbx
0x1800036d7  push    rsi
0x1800036d8  push    rdi
0x1800036d9  push    r13
0x1800036db  push    r14
0x1800036dd  push    r15
0x1800036df  sub     rsp, 70h
0x1800036e3  xorps   xmm0, xmm0
0x1800036e6  mov     dword ptr [rax+18h], 0
0x1800036ed  lea     rcx, [rax-58h]; lpSystemInfo
0x1800036f1  mov     dword ptr [rax+20h], 0
0x1800036f8  movups  xmmword ptr [rax-58h], xmm0
0x1800036fc  mov     edi, 1Fh
0x180003701  movups  xmmword ptr [rax-48h], xmm0
0x180003705  movups  xmmword ptr [rax-38h], xmm0
0x180003709  call    cs:__imp_GetSystemInfo
0x180003710  nop     dword ptr [rax+rax+00h]
0x180003715  mov     eax, [rsp+98h+var_38]
0x180003719  lea     r14, g_IpTlsDeletedInterfaceListLock
0x180003720  xorps   xmm0, xmm0
0x180003723  add     eax, eax
0x180003725  mov     rcx, r14
0x180003728  mov     cs:g_IpTlsNumReceiveQueues, eax
0x18000372e  movups  cs:g_IpTlsProtocolState, xmm0
0x180003735  movups  cs:xmmword_1800CC410, xmm0
0x18000373c  movups  cs:xmmword_1800CC420, xmm0
0x180003743  call    InitializeLock
0x180003748  test    eax, eax
0x18000374a  jnz     short loc_18000376F
0x18000374c  mov     r9d, 0D2Dh
0x180003752  mov     ecx, 10000000h
0x180003757  lea     rdx, aIptlsinitializ_1; "IpTlsInitialize: Allocation failed:%S:%"...
0x18000375e  lea     r8, aOnecoreuapNetN_42; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180003765  call    EventWrite0
0x18000376a  jmp     loc_180003BBD
0x18000376f  lea     r15, g_IpTlsInterfaceListLock
0x180003776  mov     rcx, r15
0x180003779  call    InitializeLock
0x18000377e  test    eax, eax
0x180003780  jnz     short loc_180003792
0x180003782  mov     rcx, r14
0x180003785  call    UninitializeLock
0x18000378a  mov     r9d, 0D33h
0x180003790  jmp     short loc_180003752
0x180003792  lea     rcx, g_IpTlsConfigChangeLock
0x180003799  call    InitializeLock
0x18000379e  test    eax, eax
0x1800037a0  jnz     short loc_1800037BA
0x1800037a2  mov     rcx, r14
0x1800037a5  call    UninitializeLock
0x1800037aa  mov     rcx, r15
0x1800037ad  call    UninitializeLock
0x1800037b2  mov     r9d, 0D39h
0x1800037b8  jmp     short loc_180003752
0x1800037ba  lea     rcx, g_IpTlsNLMNotificationLock
0x1800037c1  call    InitializeLock
0x1800037c6  test    eax, eax
0x1800037c8  jnz     short loc_1800037F1
0x1800037ca  mov     rcx, r14
0x1800037cd  call    UninitializeLock
0x1800037d2  lea     rcx, g_IpTlsConfigChangeLock
0x1800037d9  call    UninitializeLock
0x1800037de  mov     rcx, r15
0x1800037e1  call    UninitializeLock
0x1800037e6  mov     r9d, 0D41h
0x1800037ec  jmp     loc_180003752
0x1800037f1  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x1800037f8  call    cs:__imp_InitializeCriticalSection
0x1800037ff  nop     dword ptr [rax+rax+00h]
0x180003804  call    IpTlsIsDisabledInDisabledComponents
0x180003809  movzx   r8d, al
0x18000380d  lea     rdx, aIptlsinitializ_0; "IpTlsInitialize: g_IpTlsDisabledInDisab"...
0x180003814  mov     ebx, 10000000h
0x180003819  mov     cs:g_IpTlsDisabledInDisabledComponents, r8b
0x180003820  mov     ecx, ebx
0x180003822  call    EventWrite0
0x180003827  mov     r13d, 2
0x18000382d  mov     ecx, r13d
0x180003830  call    cs:__imp_FWResetIndicatedPortInUse
0x180003837  nop     dword ptr [rax+rax+00h]
0x18000383c  mov     esi, eax
0x18000383e  test    eax, eax
0x180003840  js      short loc_180003858
0x180003842  lea     ecx, [r13+1]
0x180003846  call    cs:__imp_FWResetIndicatedPortInUse
0x18000384d  nop     dword ptr [rax+rax+00h]
0x180003852  mov     esi, eax
0x180003854  test    eax, eax
0x180003856  jns     short loc_18000388F
0x180003858  mov     rcx, r14
0x18000385b  call    UninitializeLock
0x180003860  lea     rcx, g_IpTlsNLMNotificationLock
0x180003867  call    UninitializeLock
0x18000386c  lea     rcx, g_IpTlsConfigChangeLock
0x180003873  call    UninitializeLock
0x180003878  mov     rcx, r15
0x18000387b  call    UninitializeLock
0x180003880  mov     r8d, esi
0x180003883  lea     rdx, aIptlsinitializ_3; "IpTlsInitialize: IpTlsResetFirewallExce"...
0x18000388a  jmp     loc_180003BB6
0x18000388f  call    IsOSServerSku
0x180003894  test    al, al
0x180003896  jz      short loc_18000389F
0x180003898  mov     cs:g_IpTlsConfigureServerInterfaces, 1
0x18000389f  lea     rax, g_IpTlsInterfaceListHead
0x1800038a6  xor     r9d, r9d; lpName
0x1800038a9  mov     cs:qword_1800CC398, rax
0x1800038b0  xor     r8d, r8d; bInitialState
0x1800038b3  mov     cs:g_IpTlsInterfaceListHead, rax
0x1800038ba  xor     edx, edx; bManualReset
0x1800038bc  lea     rax, g_IpTlsGlobalV6AddressList
0x1800038c3  xor     ecx, ecx; lpEventAttributes
0x1800038c5  mov     cs:qword_1800CC448, rax
0x1800038cc  mov     cs:g_IpTlsGlobalV6AddressList, rax
0x1800038d3  lea     rax, g_IpTlsDeletedInterfaceList
0x1800038da  mov     cs:qword_1800CC3A8, rax
0x1800038e1  mov     cs:g_IpTlsDeletedInterfaceList, rax
0x1800038e8  lea     rax, g_IpTlsConnectedNetworkList
0x1800038ef  mov     cs:qword_1800CC4B8, rax
0x1800038f6  mov     cs:g_IpTlsConnectedNetworkList, rax
0x1800038fd  call    cs:__imp_CreateEventW
0x180003904  nop     dword ptr [rax+rax+00h]
0x180003909  mov     cs:g_IpTlsInterfaceListEmptyEvent, rax
0x180003910  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003914  jnz     short loc_18000394B
0x180003916  mov     rcx, r14
0x180003919  call    UninitializeLock
0x18000391e  lea     rcx, g_IpTlsNLMNotificationLock
0x180003925  call    UninitializeLock
0x18000392a  lea     rcx, g_IpTlsConfigChangeLock
0x180003931  call    UninitializeLock
0x180003936  mov     rcx, r15
0x180003939  call    UninitializeLock
0x18000393e  mov     r9d, 0D6Bh
0x180003944  mov     ecx, ebx
0x180003946  jmp     loc_180003757
0x18000394b  mov     cs:g_IpTlsInterfaceListReferenceObject, r13d
0x180003952  call    IsDaEnabled
0x180003957  mov     cs:g_IpTlsIsDaEnabled, al
0x18000395d  test    al, al
0x18000395f  jnz     short loc_180003989
0x180003961  call    NotifyDaEnabled
0x180003966  mov     ecx, ebx
0x180003968  test    eax, eax
0x18000396a  jz      short loc_18000397D
0x18000396c  mov     r8d, eax
0x18000396f  lea     rdx, aFailedToListen; "Failed to listen for DA registry state "...
0x180003976  call    EventWrite0
0x18000397b  jmp     short loc_180003989
0x18000397d  lea     rdx, aDaIsNotEnabled; "DA is not enabled; listen for DA regist"...
0x180003984  call    EventWrite0
0x180003989  lea     rcx, g_IpTlsProxyMgrRpcHandle
0x180003990  call    cs:__imp_ProxyHelperClientConnectToServer
0x180003997  nop     dword ptr [rax+rax+00h]
0x18000399c  test    eax, eax
0x18000399e  jz      short loc_1800039BD
0x1800039a0  call    IpTlsCleanup
0x1800039a5  lea     rdx, aIptlsinitializ_6; "IpTlsInitialize: ProxyHelperClientConne"...
0x1800039ac  mov     ecx, ebx
0x1800039ae  call    EventWrite0
0x1800039b3  mov     edi, 6Eh ; 'n'
0x1800039b8  jmp     loc_180003BBD
0x1800039bd  mov     rcx, cs:g_IpTlsConfigChangeLock
0x1800039c4  call    IpTlsAcquireLock
0x1800039c9  call    IpTlsRemoveDeletedInterfaces
0x1800039ce  lea     rdx, aIptlsinitializ_8; "IpTlsInitialize:Starting always on inte"...
0x1800039d5  mov     ecx, ebx
0x1800039d7  call    EventWrite0
0x1800039dc  mov     edx, r13d
0x1800039df  mov     ecx, r13d
0x1800039e2  call    IpTlsAddEligibleInterfaces
0x1800039e7  mov     edx, 1
0x1800039ec  mov     ecx, r13d
0x1800039ef  call    IpTlsAddEligibleInterfaces
0x1800039f4  xor     edx, edx
0x1800039f6  mov     ecx, r13d
0x1800039f9  call    IpTlsAddEligibleInterfaces
0x1800039fe  call    IpTlsCheckOutsideEnabledInterfaces
0x180003a03  mov     rcx, cs:g_IpTlsConfigChangeLock; hMutex
0x180003a0a  call    cs:__imp_ReleaseMutex
0x180003a11  nop     dword ptr [rax+rax+00h]
0x180003a16  xor     r8d, r8d; pcbe
0x180003a19  lea     rcx, IpTlsCorpConnectivityTimeoutHandler; pfnti
0x180003a20  xor     edx, edx; pv
0x180003a22  call    cs:__imp_CreateThreadpoolTimer
0x180003a29  nop     dword ptr [rax+rax+00h]
0x180003a2e  mov     cs:g_IpTlsCorpConnectivityTimer, rax
0x180003a35  test    rax, rax
0x180003a38  jnz     short loc_180003A57
0x180003a3a  call    IpTlsCleanup
0x180003a3f  call    cs:__imp_GetLastError
0x180003a46  nop     dword ptr [rax+rax+00h]
0x180003a4b  lea     rdx, aIptlsinitializ_4; "IpTlsInitialize: CreateThreadpoolTimer "...
0x180003a52  jmp     loc_180003C5A
0x180003a57  lea     rax, g_IpTlsIpv6AddressChangeNotification
0x180003a5e  mov     esi, 17h
0x180003a63  mov     ecx, esi; Family
0x180003a65  mov     [rsp+98h+NotificationHandle], rax; NotificationHandle
0x180003a6a  mov     r9b, 1; InitialNotification
0x180003a6d  lea     rdx, IpTlsIpAddressChangeCallback; Callback
0x180003a74  xor     r8d, r8d; CallerContext
0x180003a77  call    cs:__imp_NotifyUnicastIpAddressChange
0x180003a7e  nop     dword ptr [rax+rax+00h]
0x180003a83  mov     edi, eax
0x180003a85  test    eax, eax
0x180003a87  jz      short loc_180003A9A
0x180003a89  call    IpTlsCleanup
0x180003a8e  lea     rdx, aIptlsinitializ_5; "IpTlsInitialize: NotifyUnicastIpAddress"...
0x180003a95  jmp     loc_180003BB3
0x180003a9a  lea     rax, g_IpTlsIpInterfaceChangeNotification
0x180003aa1  mov     ecx, esi; Family
0x180003aa3  xor     r9d, r9d; InitialNotification
0x180003aa6  mov     [rsp+98h+NotificationHandle], rax; NotificationHandle
0x180003aab  xor     r8d, r8d; CallerContext
0x180003aae  lea     rdx, IpTlsIpInterfaceChangeCallback; Callback
0x180003ab5  call    cs:__imp_NotifyIpInterfaceChange
0x180003abc  nop     dword ptr [rax+rax+00h]
0x180003ac1  mov     edi, eax
0x180003ac3  test    eax, eax
0x180003ac5  jz      short loc_180003AD8
0x180003ac7  call    IpTlsCleanup
0x180003acc  lea     rdx, aIptlsinitializ_2; "IpTlsInitialize: NotifyIpInterfaceChang"...
0x180003ad3  jmp     loc_180003BB3
0x180003ad8  xor     ecx, ecx
0x180003ada  call    cs:__imp_NsiConnectToServer
0x180003ae1  nop     dword ptr [rax+rax+00h]
0x180003ae6  xor     esi, esi
0x180003ae8  mov     qword ptr cs:xmmword_1800CC420, rax
0x180003aef  mov     rcx, rax
0x180003af2  test    rax, rax
0x180003af5  jnz     short loc_180003B3E
0x180003af7  mov     edi, 6BAh
0x180003afc  call    cs:__imp_GetLastError
0x180003b03  nop     dword ptr [rax+rax+00h]
0x180003b08  lea     rdx, aNsiconnecttose_1; "NsiConnectToServer got error %d"
0x180003b0f  mov     ecx, 10000h
0x180003b14  mov     r8d, eax
0x180003b17  call    EventWrite0
0x180003b1c  mov     r9d, edi
0x180003b1f  lea     rdx, aRegisternotifi_0; "RegisterNotificationHandlers - Register"...
0x180003b26  mov     r8d, esi
0x180003b29  mov     ecx, 40000h
0x180003b2e  call    EventWrite0
0x180003b33  test    edi, edi
0x180003b35  jz      short loc_180003B9C
0x180003b37  call    IpTlsCleanup
0x180003b3c  jmp     short loc_180003BBD
0x180003b3e  lea     r14, off_1800C8328
0x180003b45  mov     edx, esi
0x180003b47  lea     rax, [r14+10h]
0x180003b4b  shl     rdx, 5
0x180003b4f  add     rax, rdx
0x180003b52  mov     [rsp+98h+var_68], rax
0x180003b57  mov     [rsp+98h+var_70], 0
0x180003b60  mov     r9, [rdx+r14+18h]
0x180003b65  mov     r8d, [rdx+r14+8]
0x180003b6a  mov     rdx, [rdx+r14]
0x180003b6e  mov     qword ptr [rax], 0
0x180003b75  mov     byte ptr [rsp+98h+NotificationHandle], 1
0x180003b7a  call    cs:__imp_NsiRpcRegisterChangeNotification
0x180003b81  nop     dword ptr [rax+rax+00h]
0x180003b86  mov     edi, eax
0x180003b88  test    eax, eax
0x180003b8a  jnz     short loc_180003B1C
0x180003b8c  inc     esi
0x180003b8e  cmp     esi, 1
0x180003b91  jnb     short loc_180003B1C
0x180003b93  mov     rcx, qword ptr cs:xmmword_1800CC420
0x180003b9a  jmp     short loc_180003B45
0x180003b9c  call    RegisterWmiEventNotification
0x180003ba1  mov     edi, eax
0x180003ba3  test    eax, eax
0x180003ba5  jz      short loc_180003BE9
0x180003ba7  call    IpTlsCleanup
0x180003bac  lea     rdx, aIptlsinitializ; "IpTlsInitialize: RegisterWmiEventNotifi"...
0x180003bb3  mov     r8d, edi
0x180003bb6  mov     ecx, ebx
0x180003bb8  call    EventWrite0
0x180003bbd  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180003bc4  jz      loc_180003C64
0x180003bca  mov     r9d, edi
0x180003bcd  lea     r8, word_180087660
0x180003bd4  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INIT_FAILED
0x180003bdb  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180003be2  call    McTemplateU0zq_EventWriteTransfer
0x180003be7  jmp     short loc_180003C64
0x180003be9  lea     rdx, [rsp+98h+arg_18]
0x180003bf1  lea     rcx, [rsp+98h+arg_10]
0x180003bf9  call    IpTlsGetGlobalConnectivity
0x180003bfe  test    eax, eax
0x180003c00  jnz     short loc_180003C0E
0x180003c02  mov     ecx, [rsp+98h+arg_10]; enum NLM_CONNECTIVITY
0x180003c09  call    IpTlsGlobalConnectivityChangeNotification
0x180003c0e  lea     rdx, IpTlsGlobalConnectivityChangeNotification; void (*)(enum NLM_CONNECTIVITY)
0x180003c15  lea     rcx, g_IpTlsNLMGlobalConnectivityChangeNotification; struct CNlmEventSink **
0x180003c1c  call    RegisterForGlobalConnectivityNotification
0x180003c21  lea     rax, IpTlsNetworkDeleteNotification
0x180003c28  xor     r9d, r9d; void (*)(struct _GUID *, enum NLM_NETWORK_PROPERTY_CHANGE)
0x180003c2b  lea     r8, IpTlsNetworkChangeNotification; void (*)(struct _GUID *, enum NLM_CONNECTIVITY)
  ... truncated ...
```
