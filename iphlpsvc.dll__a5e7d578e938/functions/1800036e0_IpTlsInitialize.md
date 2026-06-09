# IpTlsInitialize

- ea: `0x1800036e0`
- end: `0x180003cb6`
- name: `IpTlsInitialize`
- size: `1494`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001ae0`
- `0x180001d24`
- `0x180001e84`
- `0x180002000`
- `0x1800023f0`
- `0x1800028e4`
- `0x18000365c`
- `0x1800036e0`
- `0x180003cbc`
- `0x180003cf4`
- `0x1800040a8`
- `0x1800041b0`
- `0x180004f60`
- `0x18000d7c0`
- `0x180012e30`
- `0x180013580`
- `0x1800140a8`
- `0x180033798`
- `0x18003f258`
- `0x180040d90`
- `0x180042800`

## import_xrefs

- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x180003a87`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x180003a87`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180003ac5`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180003ac5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a1a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003c7b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003c7b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000390d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000390d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180003808`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180003808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b0c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180003719`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180003719`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180003a32`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180003a32`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientConnectToServer` at `0x1800039a0`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientConnectToServer` at `0x1800039a0`
- `WINNSI!NsiConnectToServer` at `0x180003aea`
- `WINNSI!NsiConnectToServer` at `0x180003aea`
- `WINNSI!NsiRpcRegisterChangeNotification` at `0x180003b8a`
- `WINNSI!NsiRpcRegisterChangeNotification` at `0x180003b8a`
- `FirewallAPI!FWResetIndicatedPortInUse` at `0x180003840`
- `FirewallAPI!FWResetIndicatedPortInUse` at `0x180003856`
- `FirewallAPI!FWResetIndicatedPortInUse` at `0x180003840`
- `FirewallAPI!FWResetIndicatedPortInUse` at `0x180003856`

## string_xrefs

- `0x18000381d`: `IpTlsInitialize: g_IpTlsDisabledInDisabledComponents = %d`
- `0x18000397f`: `Failed to listen for DA registry state updates: 0x%x`
- `0x18000398d`: `DA is not enabled; listen for DA registry status changes`
- `0x180003c8d`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x18000376e`: `onecoreuap\net\netio\iphlpsvc\service\iptls.c`
- `0x180003a5b`: `IpTlsInitialize: CreateThreadpoolTimer failed:%d`

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
0x1800036e0  mov     rax, rsp
0x1800036e3  mov     [rax+8], rbx
0x1800036e7  push    rsi
0x1800036e8  push    rdi
0x1800036e9  push    r13
0x1800036eb  push    r14
0x1800036ed  push    r15
0x1800036ef  sub     rsp, 70h
0x1800036f3  xorps   xmm0, xmm0
0x1800036f6  mov     dword ptr [rax+18h], 0
0x1800036fd  lea     rcx, [rax-58h]; lpSystemInfo
0x180003701  mov     dword ptr [rax+20h], 0
0x180003708  movups  xmmword ptr [rax-58h], xmm0
0x18000370c  mov     edi, 1Fh
0x180003711  movups  xmmword ptr [rax-48h], xmm0
0x180003715  movups  xmmword ptr [rax-38h], xmm0
0x180003719  call    cs:__imp_GetSystemInfo
0x180003720  nop     dword ptr [rax+rax+00h]
0x180003725  mov     eax, [rsp+98h+var_38]
0x180003729  lea     r14, g_IpTlsDeletedInterfaceListLock
0x180003730  xorps   xmm0, xmm0
0x180003733  add     eax, eax
0x180003735  mov     rcx, r14
0x180003738  mov     cs:g_IpTlsNumReceiveQueues, eax
0x18000373e  movups  cs:g_IpTlsProtocolState, xmm0
0x180003745  movups  cs:xmmword_1800CC410, xmm0
0x18000374c  movups  cs:xmmword_1800CC420, xmm0
0x180003753  call    InitializeLock
0x180003758  test    eax, eax
0x18000375a  jnz     short loc_18000377F
0x18000375c  mov     r9d, 0D2Dh
0x180003762  mov     ecx, 10000000h
0x180003767  lea     rdx, aIptlsinitializ_1; "IpTlsInitialize: Allocation failed:%S:%"...
0x18000376e  lea     r8, aOnecoreuapNetN_42; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180003775  call    EventWrite0
0x18000377a  jmp     loc_180003BCD
0x18000377f  lea     r15, g_IpTlsInterfaceListLock
0x180003786  mov     rcx, r15
0x180003789  call    InitializeLock
0x18000378e  test    eax, eax
0x180003790  jnz     short loc_1800037A2
0x180003792  mov     rcx, r14
0x180003795  call    UninitializeLock
0x18000379a  mov     r9d, 0D33h
0x1800037a0  jmp     short loc_180003762
0x1800037a2  lea     rcx, g_IpTlsConfigChangeLock
0x1800037a9  call    InitializeLock
0x1800037ae  test    eax, eax
0x1800037b0  jnz     short loc_1800037CA
0x1800037b2  mov     rcx, r14
0x1800037b5  call    UninitializeLock
0x1800037ba  mov     rcx, r15
0x1800037bd  call    UninitializeLock
0x1800037c2  mov     r9d, 0D39h
0x1800037c8  jmp     short loc_180003762
0x1800037ca  lea     rcx, g_IpTlsNLMNotificationLock
0x1800037d1  call    InitializeLock
0x1800037d6  test    eax, eax
0x1800037d8  jnz     short loc_180003801
0x1800037da  mov     rcx, r14
0x1800037dd  call    UninitializeLock
0x1800037e2  lea     rcx, g_IpTlsConfigChangeLock
0x1800037e9  call    UninitializeLock
0x1800037ee  mov     rcx, r15
0x1800037f1  call    UninitializeLock
0x1800037f6  mov     r9d, 0D41h
0x1800037fc  jmp     loc_180003762
0x180003801  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x180003808  call    cs:__imp_InitializeCriticalSection
0x18000380f  nop     dword ptr [rax+rax+00h]
0x180003814  call    IpTlsIsDisabledInDisabledComponents
0x180003819  movzx   r8d, al
0x18000381d  lea     rdx, aIptlsinitializ_0; "IpTlsInitialize: g_IpTlsDisabledInDisab"...
0x180003824  mov     ebx, 10000000h
0x180003829  mov     cs:g_IpTlsDisabledInDisabledComponents, r8b
0x180003830  mov     ecx, ebx
0x180003832  call    EventWrite0
0x180003837  mov     r13d, 2
0x18000383d  mov     ecx, r13d
0x180003840  call    cs:__imp_FWResetIndicatedPortInUse
0x180003847  nop     dword ptr [rax+rax+00h]
0x18000384c  mov     esi, eax
0x18000384e  test    eax, eax
0x180003850  js      short loc_180003868
0x180003852  lea     ecx, [r13+1]
0x180003856  call    cs:__imp_FWResetIndicatedPortInUse
0x18000385d  nop     dword ptr [rax+rax+00h]
0x180003862  mov     esi, eax
0x180003864  test    eax, eax
0x180003866  jns     short loc_18000389F
0x180003868  mov     rcx, r14
0x18000386b  call    UninitializeLock
0x180003870  lea     rcx, g_IpTlsNLMNotificationLock
0x180003877  call    UninitializeLock
0x18000387c  lea     rcx, g_IpTlsConfigChangeLock
0x180003883  call    UninitializeLock
0x180003888  mov     rcx, r15
0x18000388b  call    UninitializeLock
0x180003890  mov     r8d, esi
0x180003893  lea     rdx, aIptlsinitializ_3; "IpTlsInitialize: IpTlsResetFirewallExce"...
0x18000389a  jmp     loc_180003BC6
0x18000389f  call    IsOSServerSku
0x1800038a4  test    al, al
0x1800038a6  jz      short loc_1800038AF
0x1800038a8  mov     cs:g_IpTlsConfigureServerInterfaces, 1
0x1800038af  lea     rax, g_IpTlsInterfaceListHead
0x1800038b6  xor     r9d, r9d; lpName
0x1800038b9  mov     cs:qword_1800CC398, rax
0x1800038c0  xor     r8d, r8d; bInitialState
0x1800038c3  mov     cs:g_IpTlsInterfaceListHead, rax
0x1800038ca  xor     edx, edx; bManualReset
0x1800038cc  lea     rax, g_IpTlsGlobalV6AddressList
0x1800038d3  xor     ecx, ecx; lpEventAttributes
0x1800038d5  mov     cs:qword_1800CC448, rax
0x1800038dc  mov     cs:g_IpTlsGlobalV6AddressList, rax
0x1800038e3  lea     rax, g_IpTlsDeletedInterfaceList
0x1800038ea  mov     cs:qword_1800CC3A8, rax
0x1800038f1  mov     cs:g_IpTlsDeletedInterfaceList, rax
0x1800038f8  lea     rax, g_IpTlsConnectedNetworkList
0x1800038ff  mov     cs:qword_1800CC4B8, rax
0x180003906  mov     cs:g_IpTlsConnectedNetworkList, rax
0x18000390d  call    cs:__imp_CreateEventW
0x180003914  nop     dword ptr [rax+rax+00h]
0x180003919  mov     cs:g_IpTlsInterfaceListEmptyEvent, rax
0x180003920  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003924  jnz     short loc_18000395B
0x180003926  mov     rcx, r14
0x180003929  call    UninitializeLock
0x18000392e  lea     rcx, g_IpTlsNLMNotificationLock
0x180003935  call    UninitializeLock
0x18000393a  lea     rcx, g_IpTlsConfigChangeLock
0x180003941  call    UninitializeLock
0x180003946  mov     rcx, r15
0x180003949  call    UninitializeLock
0x18000394e  mov     r9d, 0D6Bh
0x180003954  mov     ecx, ebx
0x180003956  jmp     loc_180003767
0x18000395b  mov     cs:g_IpTlsInterfaceListReferenceObject, r13d
0x180003962  call    IsDaEnabled
0x180003967  mov     cs:g_IpTlsIsDaEnabled, al
0x18000396d  test    al, al
0x18000396f  jnz     short loc_180003999
0x180003971  call    NotifyDaEnabled
0x180003976  mov     ecx, ebx
0x180003978  test    eax, eax
0x18000397a  jz      short loc_18000398D
0x18000397c  mov     r8d, eax
0x18000397f  lea     rdx, aFailedToListen; "Failed to listen for DA registry state "...
0x180003986  call    EventWrite0
0x18000398b  jmp     short loc_180003999
0x18000398d  lea     rdx, aDaIsNotEnabled; "DA is not enabled; listen for DA regist"...
0x180003994  call    EventWrite0
0x180003999  lea     rcx, g_IpTlsProxyMgrRpcHandle
0x1800039a0  call    cs:__imp_ProxyHelperClientConnectToServer
0x1800039a7  nop     dword ptr [rax+rax+00h]
0x1800039ac  test    eax, eax
0x1800039ae  jz      short loc_1800039CD
0x1800039b0  call    IpTlsCleanup
0x1800039b5  lea     rdx, aIptlsinitializ_6; "IpTlsInitialize: ProxyHelperClientConne"...
0x1800039bc  mov     ecx, ebx
0x1800039be  call    EventWrite0
0x1800039c3  mov     edi, 6Eh ; 'n'
0x1800039c8  jmp     loc_180003BCD
0x1800039cd  mov     rcx, cs:g_IpTlsConfigChangeLock
0x1800039d4  call    IpTlsAcquireLock
0x1800039d9  call    IpTlsRemoveDeletedInterfaces
0x1800039de  lea     rdx, aIptlsinitializ_8; "IpTlsInitialize:Starting always on inte"...
0x1800039e5  mov     ecx, ebx
0x1800039e7  call    EventWrite0
0x1800039ec  mov     edx, r13d
0x1800039ef  mov     ecx, r13d
0x1800039f2  call    IpTlsAddEligibleInterfaces
0x1800039f7  mov     edx, 1
0x1800039fc  mov     ecx, r13d
0x1800039ff  call    IpTlsAddEligibleInterfaces
0x180003a04  xor     edx, edx
0x180003a06  mov     ecx, r13d
0x180003a09  call    IpTlsAddEligibleInterfaces
0x180003a0e  call    IpTlsCheckOutsideEnabledInterfaces
0x180003a13  mov     rcx, cs:g_IpTlsConfigChangeLock; hMutex
0x180003a1a  call    cs:__imp_ReleaseMutex
0x180003a21  nop     dword ptr [rax+rax+00h]
0x180003a26  xor     r8d, r8d; pcbe
0x180003a29  lea     rcx, IpTlsCorpConnectivityTimeoutHandler; pfnti
0x180003a30  xor     edx, edx; pv
0x180003a32  call    cs:__imp_CreateThreadpoolTimer
0x180003a39  nop     dword ptr [rax+rax+00h]
0x180003a3e  mov     cs:g_IpTlsCorpConnectivityTimer, rax
0x180003a45  test    rax, rax
0x180003a48  jnz     short loc_180003A67
0x180003a4a  call    IpTlsCleanup
0x180003a4f  call    cs:__imp_GetLastError
0x180003a56  nop     dword ptr [rax+rax+00h]
0x180003a5b  lea     rdx, aIptlsinitializ_4; "IpTlsInitialize: CreateThreadpoolTimer "...
0x180003a62  jmp     loc_180003C6A
0x180003a67  lea     rax, g_IpTlsIpv6AddressChangeNotification
0x180003a6e  mov     esi, 17h
0x180003a73  mov     ecx, esi; Family
0x180003a75  mov     [rsp+98h+NotificationHandle], rax; NotificationHandle
0x180003a7a  mov     r9b, 1; InitialNotification
0x180003a7d  lea     rdx, IpTlsIpAddressChangeCallback; Callback
0x180003a84  xor     r8d, r8d; CallerContext
0x180003a87  call    cs:__imp_NotifyUnicastIpAddressChange
0x180003a8e  nop     dword ptr [rax+rax+00h]
0x180003a93  mov     edi, eax
0x180003a95  test    eax, eax
0x180003a97  jz      short loc_180003AAA
0x180003a99  call    IpTlsCleanup
0x180003a9e  lea     rdx, aIptlsinitializ_5; "IpTlsInitialize: NotifyUnicastIpAddress"...
0x180003aa5  jmp     loc_180003BC3
0x180003aaa  lea     rax, g_IpTlsIpInterfaceChangeNotification
0x180003ab1  mov     ecx, esi; Family
0x180003ab3  xor     r9d, r9d; InitialNotification
0x180003ab6  mov     [rsp+98h+NotificationHandle], rax; NotificationHandle
0x180003abb  xor     r8d, r8d; CallerContext
0x180003abe  lea     rdx, IpTlsIpInterfaceChangeCallback; Callback
0x180003ac5  call    cs:__imp_NotifyIpInterfaceChange
0x180003acc  nop     dword ptr [rax+rax+00h]
0x180003ad1  mov     edi, eax
0x180003ad3  test    eax, eax
0x180003ad5  jz      short loc_180003AE8
0x180003ad7  call    IpTlsCleanup
0x180003adc  lea     rdx, aIptlsinitializ_2; "IpTlsInitialize: NotifyIpInterfaceChang"...
0x180003ae3  jmp     loc_180003BC3
0x180003ae8  xor     ecx, ecx
0x180003aea  call    cs:__imp_NsiConnectToServer
0x180003af1  nop     dword ptr [rax+rax+00h]
0x180003af6  xor     esi, esi
0x180003af8  mov     qword ptr cs:xmmword_1800CC420, rax
0x180003aff  mov     rcx, rax
0x180003b02  test    rax, rax
0x180003b05  jnz     short loc_180003B4E
0x180003b07  mov     edi, 6BAh
0x180003b0c  call    cs:__imp_GetLastError
0x180003b13  nop     dword ptr [rax+rax+00h]
0x180003b18  lea     rdx, aNsiconnecttose_1; "NsiConnectToServer got error %d"
0x180003b1f  mov     ecx, 10000h
0x180003b24  mov     r8d, eax
0x180003b27  call    EventWrite0
0x180003b2c  mov     r9d, edi
0x180003b2f  lea     rdx, aRegisternotifi_0; "RegisterNotificationHandlers - Register"...
0x180003b36  mov     r8d, esi
0x180003b39  mov     ecx, 40000h
0x180003b3e  call    EventWrite0
0x180003b43  test    edi, edi
0x180003b45  jz      short loc_180003BAC
0x180003b47  call    IpTlsCleanup
0x180003b4c  jmp     short loc_180003BCD
0x180003b4e  lea     r14, off_1800C8328
0x180003b55  mov     edx, esi
0x180003b57  lea     rax, [r14+10h]
0x180003b5b  shl     rdx, 5
0x180003b5f  add     rax, rdx
0x180003b62  mov     [rsp+98h+var_68], rax
0x180003b67  mov     [rsp+98h+var_70], 0
0x180003b70  mov     r9, [rdx+r14+18h]
0x180003b75  mov     r8d, [rdx+r14+8]
0x180003b7a  mov     rdx, [rdx+r14]
0x180003b7e  mov     qword ptr [rax], 0
0x180003b85  mov     byte ptr [rsp+98h+NotificationHandle], 1
0x180003b8a  call    cs:__imp_NsiRpcRegisterChangeNotification
0x180003b91  nop     dword ptr [rax+rax+00h]
0x180003b96  mov     edi, eax
0x180003b98  test    eax, eax
0x180003b9a  jnz     short loc_180003B2C
0x180003b9c  inc     esi
0x180003b9e  cmp     esi, 1
0x180003ba1  jnb     short loc_180003B2C
0x180003ba3  mov     rcx, qword ptr cs:xmmword_1800CC420
0x180003baa  jmp     short loc_180003B55
0x180003bac  call    RegisterWmiEventNotification
0x180003bb1  mov     edi, eax
0x180003bb3  test    eax, eax
0x180003bb5  jz      short loc_180003BF9
0x180003bb7  call    IpTlsCleanup
0x180003bbc  lea     rdx, aIptlsinitializ; "IpTlsInitialize: RegisterWmiEventNotifi"...
0x180003bc3  mov     r8d, edi
0x180003bc6  mov     ecx, ebx
0x180003bc8  call    EventWrite0
0x180003bcd  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180003bd4  jz      loc_180003C74
0x180003bda  mov     r9d, edi
0x180003bdd  lea     r8, word_180087660
0x180003be4  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INIT_FAILED
0x180003beb  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180003bf2  call    McTemplateU0zq_EventWriteTransfer
0x180003bf7  jmp     short loc_180003C74
0x180003bf9  lea     rdx, [rsp+98h+arg_18]
0x180003c01  lea     rcx, [rsp+98h+arg_10]
0x180003c09  call    IpTlsGetGlobalConnectivity
0x180003c0e  test    eax, eax
0x180003c10  jnz     short loc_180003C1E
0x180003c12  mov     ecx, [rsp+98h+arg_10]; enum NLM_CONNECTIVITY
0x180003c19  call    IpTlsGlobalConnectivityChangeNotification
0x180003c1e  lea     rdx, IpTlsGlobalConnectivityChangeNotification; void (*)(enum NLM_CONNECTIVITY)
0x180003c25  lea     rcx, g_IpTlsNLMGlobalConnectivityChangeNotification; struct CNlmEventSink **
0x180003c2c  call    RegisterForGlobalConnectivityNotification
0x180003c31  lea     rax, IpTlsNetworkDeleteNotification
0x180003c38  xor     r9d, r9d; void (*)(struct _GUID *, enum NLM_NETWORK_PROPERTY_CHANGE)
0x180003c3b  lea     r8, IpTlsNetworkChangeNotification; void (*)(struct _GUID *, enum NLM_CONNECTIVITY)
  ... truncated ...
```
