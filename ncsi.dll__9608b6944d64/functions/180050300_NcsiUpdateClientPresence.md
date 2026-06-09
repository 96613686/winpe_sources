# NcsiUpdateClientPresence

- ea: `0x180050300`
- end: `0x18005079f`
- name: `NcsiUpdateClientPresence`
- size: `1183`
- prototype: ``
- caller_count: `0`
- callee_count: `49`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000e59c`
- `0x180010200`
- `0x180011a58`
- `0x180013e48`
- `0x18001572c`
- `0x180019dc4`
- `0x18001d590`
- `0x180021e7c`
- `0x1800257b8`
- `0x18002c1ec`
- `0x18002ced0`
- `0x180032280`
- `0x180041008`
- `0x1800430bc`
- `0x180043ce8`
- `0x180044350`
- `0x180044580`
- `0x180044958`
- `0x18004507c`
- `0x180046340`
- `0x180047240`
- `0x180047f78`
- `0x18004f6a0`
- `0x18004f86c`
- `0x180050300`
- `0x180054bec`
- `0x18005bb74`
- `0x18005bce0`
- `0x18005bd40`
- `0x18005beac`
- `0x18005c2bc`
- `0x18005c6e4`
- `0x18005cf94`
- `0x18005d53c`
- `0x18005d8a0`
- `0x18005da88`
- `0x18005e9d4`
- `0x18005ea40`
- `0x18005eb14`
- `0x180060528`
- `0x180060918`
- `0x180060c14`
- `0x180061050`
- `0x180064c70`
- `0x180069cb8`
- `0x18006bbe0`
- `0x18006d128`
- `0x18006d1d4`
- `0x18006d224`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800506a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005071f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800506a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005071f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005049f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005049f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005066f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800506ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005066f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800506ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005042f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005042f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180050657`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180050657`
- `WS2_32!__imp_WSAStartup` at `0x180050383`
- `WS2_32!__imp_WSAStartup` at `0x180050383`
- `WS2_32!__imp_WSACleanup` at `0x1800503f7`
- `WS2_32!__imp_WSACleanup` at `0x18005046f`
- `WS2_32!__imp_WSACleanup` at `0x18005073e`
- `WS2_32!__imp_WSACleanup` at `0x1800503f7`
- `WS2_32!__imp_WSACleanup` at `0x18005046f`
- `WS2_32!__imp_WSACleanup` at `0x18005073e`

## pseudocode

```c
void __fastcall NcsiUpdateClientPresence(unsigned __int32 a1)
{
  struct _TP_TIMER *ThreadpoolTimer; // rax
  __int64 v3; // rcx
  DWORD LastError; // eax
  DWORD v5; // esi
  __int64 v6; // rcx
  NcsiConfigData *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  NcsiIpsecEventMonitor *v10; // rcx
  NcsiProxyDetectedMonitor *v11; // rcx
  NcsiAuthProxyMonitor *v12; // rcx
  NcsiSuspectStateMonitor *v13; // rcx
  GroupPolicyMonitor *v14; // rcx
  unsigned __int32 v15; // edi
  Ncsi::Power *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  NcsiConfigData *v19; // rcx
  void (*v20)(void); // rdx
  MacResolver *v21; // rcx
  NHM::NhmNetReadyMonitor *v22; // rcx
  NcsiIpsecEventMonitor *v23; // rcx
  GroupPolicyMonitor *v24; // rcx
  __int64 v25; // rcx
  Ncsi::Proxy::Detector *v26; // rcx
  NcsiConfigData *v27; // rcx
  Ncsi::Power *v28; // rcx
  const char *v29; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v30[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v31[8]; // [rsp+80h] [rbp-80h] BYREF
  WSAData WSAData; // [rsp+C0h] [rbp-40h] BYREF

  if ( a1 > 1 )
    return;
  if ( a1 == 1 && !CheckIfClientPresent() )
  {
    memset_0(&WSAData, 0, sizeof(WSAData));
    if ( WSAStartup(0x202u, &WSAData) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_3ebc9b3a6d83394e3616c8f9597e5791_Traceguids);
      }
      return;
    }
    if ( !NcsiThreadPoolInitialize() )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 26, WPP_3ebc9b3a6d83394e3616c8f9597e5791_Traceguids);
      }
      WSACleanup();
      return;
    }
    if ( pti )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    ThreadpoolTimer = NcsiCreateThreadpoolTimer((PTP_TIMER_CALLBACK)HandleResponseToWpadOpportunityTimer, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&void CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      v3,
      ThreadpoolTimer);
    if ( !pti )
    {
      LastError = GetLastError();
      v5 = LastError;
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 27, WPP_3ebc9b3a6d83394e3616c8f9597e5791_Traceguids, LastError);
      }
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&void CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        v6,
        0);
      NcsiThreadPoolShutdown();
      WSACleanup();
      if ( v5 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
        {
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 29, WPP_3ebc9b3a6d83394e3616c8f9597e5791_Traceguids, v5);
        }
        return;
      }
    }
    if ( NCSI_CORP_LOCATION_PROBE::s_probeThreadCount )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    _InterlockedExchange(&NCSI_CORP_LOCATION_PROBE::s_probeThreadCount, 0);
    NCSI_CORP_LOCATION_PROBE::s_probesAllFinishedEvent = CreateEventW(0, 0, 0, 0);
    NcsiConfigData::QueryRegistry(v7);
    v31[0] = off_18007D510;
    v31[7] = v31;
    v30[0] = off_18007D540;
    v30[7] = v30;
    ServiceTracking::Init(v9, v8, (__int64)v30, (__int64)v31);
    std::_Func_class<void,>::_Tidy(v30);
    std::_Func_class<void,>::_Tidy(v31);
    NcsiIpsecEventMonitor::Initialize(v10);
    NcsiProxyDetectedMonitor::Initialize(v11);
    NcsiAuthProxyMonitor::Initialize(v12);
    NcsiSuspectStateMonitor::Initialize(v13);
    GroupPolicyMonitor::Start(v14);
  }
  v15 = _InterlockedExchange(&g_ncsiClientPresent, a1);
  if ( v15 != a1
    && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_dd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 28, WPP_3ebc9b3a6d83394e3616c8f9597e5791_Traceguids, v15, a1);
  }
  if ( _InterlockedCompareExchange(&details::g_userLoggedIn, 1, 1) != 1 && details::DoesActiveWTSSessionExist() )
    details::SetUsersLoggedIn(1);
  if ( a1 == 1 )
  {
    if ( !v15 )
    {
      if ( (int)ActiveProbeManager::Init() < 0 )
      {
        if ( (unsigned int)dword_18009A048 > 5 )
        {
          v29 = "ActiveProbeManager::Init failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (__int64)&dword_18009A048,
            (unsigned __int8 *)word_1800863E2,
            v17,
            v18,
            (const unsigned __int16 **)&v29);
        }
        return;
      }
      Ncsi::Power::Initialize(v16);
      NcsiConfigData::Initialize(v19);
      Ncsi::PassivePoll::PassivePollManager::Initialize();
      if ( CheckIfClientPresent() )
      {
        Ncsi::PassivePoll::PassivePollManager::NetworkEventHappened();
        MacResolver::RegisterCallback(v21, v20);
        NHM::NhmNetReadyMonitor::StartMonitor(v22);
      }
    }
    Ncsi::PassivePoll::PassivePollManager::UpdateClientPresence(1);
  }
  if ( v15 == 1 && !a1 )
  {
    StopMediaMonitor();
    NcsiIpsecEventMonitor::Uninitialize(v23);
    EtwListener::Uninitialize((EtwListener *)&g_ncsiHotspotAuthMonitor);
    NcsiProxyDetectedMonitor::Uninitialize((NcsiProxyDetectedMonitor *)&g_ncsiProxyDetectedMonitor);
    NcsiAuthProxyMonitor::Uninitialize((NcsiAuthProxyMonitor *)&g_ncsiAuthProxyMonitor);
    EtwListener::Uninitialize((EtwListener *)&g_ncsiWinInetProxySettingsMonitor);
    NcsiSuspectStateMonitor::Uninitialize((NcsiSuspectStateMonitor *)&g_ncsiSuspectStateMonitor);
    GroupPolicyMonitor::Stop(v24);
    Ncsi::PassivePoll::PassivePollManager::UpdateClientPresence(0);
    while ( g_ncsiNlaThreadCount > 0 )
      Sleep(0x32u);
    EnterCriticalSection(&g_ncsiNetHealthTracking);
    if ( qword_18009D7D8 != (_QWORD)xmmword_18009D7E0 )
    {
      std::_Destroy_range<std::allocator<std::unique_ptr<NetworkHealthTracking::NetworkHealthEvent>>>(
        qword_18009D7D8,
        xmmword_18009D7E0);
      *(_QWORD *)&xmmword_18009D7E0 = qword_18009D7D8;
    }
    LeaveCriticalSection(&g_ncsiNetHealthTracking);
    NCSI_CORP_LOCATION_PROBE::Cleanup();
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NCSI_Fix_ThreadPoolTimerCleanup>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NCSI_Fix_ThreadPoolTimerCleanup>::GetImpl'::`2'::impl) )
    {
      CancelResponseToWpadOpportunity();
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&void CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        v25,
        0);
      NcsiThreadPoolShutdown();
    }
    else
    {
      NcsiThreadPoolShutdown();
      pti = 0;
    }
    Ncsi::Proxy::Detector::Purge(v26);
    EnterCriticalSection(&g_ncsiLock);
    if ( g_ncsiInterfaceList != xmmword_18009DCC0 )
    {
      std::_Destroy_range<std::allocator<NCSI_INTERFACE_ATTRIBUTES>>(g_ncsiInterfaceList);
      xmmword_18009DCC0 = g_ncsiInterfaceList;
    }
    LeaveCriticalSection(&g_ncsiLock);
    NcsiConfigData::Uninitialize(v27);
    Ncsi::Power::Shutdown(v28);
    Ncsi::PassivePoll::PassivePollManager::Shutdown();
    ActiveProbeManager::Deinit();
    CleanupGlobalNsiData();
    WSACleanup();
  }
}

```

## disassembly

```asm
0x180050300  mov     [rsp-8+arg_8], rbx
0x180050305  mov     [rsp-8+arg_10], rsi
0x18005030a  push    rbp
0x18005030b  push    rdi
0x18005030c  push    r12
0x18005030e  push    r13
0x180050310  push    r15
0x180050312  lea     rbp, [rsp-170h]
0x18005031a  sub     rsp, 270h
0x180050321  mov     rax, cs:__security_cookie
0x180050328  xor     rax, rsp
0x18005032b  mov     [rbp+190h+var_30], rax
0x180050332  mov     r15d, 1
0x180050338  mov     ebx, ecx
0x18005033a  cmp     ecx, r15d
0x18005033d  ja      loc_180050774
0x180050343  xor     esi, esi
0x180050345  lea     r12, WPP_GLOBAL_Control
0x18005034c  lea     r13, WPP_3ebc9b3a6d83394e3616c8f9597e5791_Traceguids
0x180050353  cmp     ecx, r15d
0x180050356  jnz     loc_180050514
0x18005035c  call    ?CheckIfClientPresent@@YA_NXZ; CheckIfClientPresent(void)
0x180050361  test    al, al
0x180050363  jnz     loc_180050514
0x180050369  xor     edx, edx; Val
0x18005036b  lea     rcx, [rbp+190h+WSAData]; void *
0x18005036f  mov     r8d, 198h; Size
0x180050375  call    memset_0
0x18005037a  mov     ecx, 202h; wVersionRequested
0x18005037f  lea     rdx, [rbp+190h+WSAData]; lpWSAData
0x180050383  call    cs:__imp_WSAStartup
0x180050389  test    eax, eax
0x18005038b  jz      short loc_1800503C5
0x18005038d  mov     rcx, cs:WPP_GLOBAL_Control
0x180050394  cmp     rcx, r12
0x180050397  jz      loc_180050774
0x18005039d  test    [rcx+1Ch], r15b
0x1800503a1  jz      loc_180050774
0x1800503a7  cmp     byte ptr [rcx+19h], 2
0x1800503ab  jb      loc_180050774
0x1800503b1  mov     rcx, [rcx+10h]
0x1800503b5  lea     edx, [rsi+19h]
0x1800503b8  mov     r8, r13
0x1800503bb  call    WPP_SF_
0x1800503c0  jmp     loc_180050774
0x1800503c5  call    ?NcsiThreadPoolInitialize@@YA_NXZ; NcsiThreadPoolInitialize(void)
0x1800503ca  test    al, al
0x1800503cc  jnz     short loc_180050402
0x1800503ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800503d5  cmp     rcx, r12
0x1800503d8  jz      short loc_1800503F7
0x1800503da  test    [rcx+1Ch], r15b
0x1800503de  jz      short loc_1800503F7
0x1800503e0  cmp     byte ptr [rcx+19h], 2
0x1800503e4  jb      short loc_1800503F7
0x1800503e6  mov     rcx, [rcx+10h]
0x1800503ea  mov     edx, 1Ah
0x1800503ef  mov     r8, r13
0x1800503f2  call    WPP_SF_
0x1800503f7  call    cs:__imp_WSACleanup
0x1800503fd  jmp     loc_180050774
0x180050402  cmp     cs:pti, rsi
0x180050409  jz      short loc_180050410
0x18005040b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180050410  xor     edx, edx; pv
0x180050412  lea     rcx, ?HandleResponseToWpadOpportunityTimer@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180050419  call    ?NcsiCreateThreadpoolTimer@@YAPEAU_TP_TIMER@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU1@@Z1@Z; NcsiCreateThreadpoolTimer(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *),void *)
0x18005041e  mov     rdx, rax
0x180050421  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?CloseThreadpoolTimer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180050426  cmp     cs:pti, rsi
0x18005042d  jnz     short loc_18005047D
0x18005042f  call    cs:__imp_GetLastError
0x180050435  mov     esi, eax
0x180050437  mov     rcx, cs:WPP_GLOBAL_Control
0x18005043e  cmp     rcx, r12
0x180050441  jz      short loc_180050463
0x180050443  test    [rcx+1Ch], r15b
0x180050447  jz      short loc_180050463
0x180050449  cmp     byte ptr [rcx+19h], 2
0x18005044d  jb      short loc_180050463
0x18005044f  mov     rcx, [rcx+10h]
0x180050453  mov     edx, 1Bh
0x180050458  mov     r9d, eax
0x18005045b  mov     r8, r13
0x18005045e  call    WPP_SF_d
0x180050463  xor     edx, edx
0x180050465  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?CloseThreadpoolTimer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18005046a  call    ?NcsiThreadPoolShutdown@@YAXXZ; NcsiThreadPoolShutdown(void)
0x18005046f  call    cs:__imp_WSACleanup
0x180050475  test    esi, esi
0x180050477  jnz     loc_180050748
0x18005047d  mov     eax, cs:?s_probeThreadCount@NCSI_CORP_LOCATION_PROBE@@0U?$atomic@K@std@@A; std::atomic<ulong> NCSI_CORP_LOCATION_PROBE::s_probeThreadCount
0x180050483  nop
0x180050484  test    eax, eax
0x180050486  jz      short loc_18005048D
0x180050488  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005048d  xor     eax, eax
0x18005048f  xor     r9d, r9d; lpName
0x180050492  xchg    eax, cs:?s_probeThreadCount@NCSI_CORP_LOCATION_PROBE@@0U?$atomic@K@std@@A; std::atomic<ulong> NCSI_CORP_LOCATION_PROBE::s_probeThreadCount
0x180050498  xor     r8d, r8d; bInitialState
0x18005049b  xor     edx, edx; bManualReset
0x18005049d  xor     ecx, ecx; lpEventAttributes
0x18005049f  call    cs:__imp_CreateEventW
0x1800504a5  mov     cs:?s_probesAllFinishedEvent@NCSI_CORP_LOCATION_PROBE@@0PEAXEA, rax; void * NCSI_CORP_LOCATION_PROBE::s_probesAllFinishedEvent
0x1800504ac  call    ?QueryRegistry@NcsiConfigData@@QEAAXXZ; NcsiConfigData::QueryRegistry(void)
0x1800504b1  lea     rax, off_18007D510
0x1800504b8  mov     [rbp+190h+var_210], rax
0x1800504bc  lea     r9, [rbp+190h+var_210]
0x1800504c0  lea     rax, [rbp+190h+var_210]
0x1800504c4  mov     [rbp+190h+var_1D8], rax
0x1800504c8  lea     r8, [rsp+290h+var_250]
0x1800504cd  lea     rax, off_18007D540
0x1800504d4  mov     [rsp+290h+var_250], rax
0x1800504d9  lea     rax, [rsp+290h+var_250]
0x1800504de  mov     [rsp+290h+var_218], rax
0x1800504e3  call    ?Init@ServiceTracking@@QEAAJPEBG$$QEAV?$function@$$A6AXXZ@std@@1@Z; ServiceTracking::Init(ushort const *,std::function<void (void)> &&,std::function<void (void)> &&)
0x1800504e8  lea     rcx, [rsp+290h+var_250]
0x1800504ed  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x1800504f2  lea     rcx, [rbp+190h+var_210]
0x1800504f6  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x1800504fb  call    ?Initialize@NcsiIpsecEventMonitor@@QEAAXXZ; NcsiIpsecEventMonitor::Initialize(void)
0x180050500  call    ?Initialize@NcsiProxyDetectedMonitor@@QEAAXXZ; NcsiProxyDetectedMonitor::Initialize(void)
0x180050505  call    ?Initialize@NcsiAuthProxyMonitor@@QEAAXXZ; NcsiAuthProxyMonitor::Initialize(void)
0x18005050a  call    ?Initialize@NcsiSuspectStateMonitor@@QEAAKXZ; NcsiSuspectStateMonitor::Initialize(void)
0x18005050f  call    ?Start@GroupPolicyMonitor@@QEAAXXZ; GroupPolicyMonitor::Start(void)
0x180050514  mov     edi, ebx
0x180050516  xchg    edi, cs:?g_ncsiClientPresent@@3U?$atomic@W4_NCSI_CLIENT_PRESENCE@@@std@@A; std::atomic<_NCSI_CLIENT_PRESENCE> g_ncsiClientPresent
0x18005051c  cmp     edi, ebx
0x18005051e  jz      short loc_180050550
0x180050520  mov     rcx, cs:WPP_GLOBAL_Control
0x180050527  cmp     rcx, r12
0x18005052a  jz      short loc_180050550
0x18005052c  test    [rcx+1Ch], r15b
0x180050530  jz      short loc_180050550
0x180050532  cmp     byte ptr [rcx+19h], 5
0x180050536  jb      short loc_180050550
0x180050538  mov     rcx, [rcx+10h]
0x18005053c  mov     edx, 1Ch
0x180050541  mov     r9d, edi
0x180050544  mov     dword ptr [rsp+290h+var_270], ebx
0x180050548  mov     r8, r13
0x18005054b  call    WPP_SF_dd
0x180050550  mov     eax, r15d
0x180050553  lock cmpxchg cs:?g_userLoggedIn@details@@3JA, r15d; long details::g_userLoggedIn
0x18005055c  jz      short loc_18005056F
0x18005055e  call    ?DoesActiveWTSSessionExist@details@@YA_NXZ; details::DoesActiveWTSSessionExist(void)
0x180050563  test    al, al
0x180050565  jz      short loc_18005056F
0x180050567  mov     cl, r15b; bool
0x18005056a  call    ?SetUsersLoggedIn@details@@YAX_N@Z; details::SetUsersLoggedIn(bool)
0x18005056f  cmp     ebx, r15d
0x180050572  jnz     short loc_1800505ED
0x180050574  test    edi, edi
0x180050576  jnz     short loc_1800505E5
0x180050578  call    ?Init@ActiveProbeManager@@SAJXZ; ActiveProbeManager::Init(void)
0x18005057d  test    eax, eax
0x18005057f  jns     short loc_1800505BE
0x180050581  mov     eax, cs:dword_18009A048
0x180050587  cmp     eax, 5
0x18005058a  jbe     loc_180050774
0x180050590  lea     rax, aActiveprobeman_0; "ActiveProbeManager::Init failed"
0x180050597  mov     [rsp+290h+var_260], rax
0x18005059c  lea     rdx, word_1800863E2
0x1800505a3  lea     rax, [rsp+290h+var_260]
0x1800505a8  lea     rcx, dword_18009A048
0x1800505af  mov     [rsp+290h+var_270], rax
0x1800505b4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800505b9  jmp     loc_180050774
0x1800505be  call    ?Initialize@Power@Ncsi@@YAXXZ; Ncsi::Power::Initialize(void)
0x1800505c3  call    ?Initialize@NcsiConfigData@@QEAAXXZ; NcsiConfigData::Initialize(void)
0x1800505c8  call    ?Initialize@PassivePollManager@PassivePoll@Ncsi@@SAXXZ; Ncsi::PassivePoll::PassivePollManager::Initialize(void)
0x1800505cd  call    ?CheckIfClientPresent@@YA_NXZ; CheckIfClientPresent(void)
0x1800505d2  test    al, al
0x1800505d4  jz      short loc_1800505E5
0x1800505d6  call    ?NetworkEventHappened@PassivePollManager@PassivePoll@Ncsi@@SAXXZ; Ncsi::PassivePoll::PassivePollManager::NetworkEventHappened(void)
0x1800505db  call    ?RegisterCallback@MacResolver@@QEAAXP6AXXZ@Z; MacResolver::RegisterCallback(void (*)(void))
0x1800505e0  call    ?StartMonitor@NhmNetReadyMonitor@NHM@@QEAAXXZ; NHM::NhmNetReadyMonitor::StartMonitor(void)
0x1800505e5  mov     cl, r15b; bool
0x1800505e8  call    ?UpdateClientPresence@PassivePollManager@PassivePoll@Ncsi@@SAX_N@Z; Ncsi::PassivePoll::PassivePollManager::UpdateClientPresence(bool)
0x1800505ed  cmp     edi, r15d
0x1800505f0  jnz     loc_180050744
0x1800505f6  test    ebx, ebx
0x1800505f8  jnz     loc_180050744
0x1800505fe  call    ?StopMediaMonitor@@YAXXZ; StopMediaMonitor(void)
0x180050603  call    ?Uninitialize@NcsiIpsecEventMonitor@@QEAAXXZ; NcsiIpsecEventMonitor::Uninitialize(void)
0x180050608  lea     rcx, ?g_ncsiHotspotAuthMonitor@@3VNcsiHotspotAuthEventMonitor@@A; this
0x18005060f  call    ?Uninitialize@EtwListener@@QEAAXXZ; EtwListener::Uninitialize(void)
0x180050614  lea     rcx, ?g_ncsiProxyDetectedMonitor@@3VNcsiProxyDetectedMonitor@@A; this
0x18005061b  call    ?Uninitialize@NcsiProxyDetectedMonitor@@QEAAXXZ; NcsiProxyDetectedMonitor::Uninitialize(void)
0x180050620  lea     rcx, ?g_ncsiAuthProxyMonitor@@3VNcsiAuthProxyMonitor@@A; this
0x180050627  call    ?Uninitialize@NcsiAuthProxyMonitor@@QEAAXXZ; NcsiAuthProxyMonitor::Uninitialize(void)
0x18005062c  lea     rcx, ?g_ncsiWinInetProxySettingsMonitor@@3VNcsiWinINetProxySettingMonitor@@A; this
0x180050633  call    ?Uninitialize@EtwListener@@QEAAXXZ; EtwListener::Uninitialize(void)
0x180050638  lea     rcx, ?g_ncsiSuspectStateMonitor@@3VNcsiSuspectStateMonitor@@A; this
0x18005063f  call    ?Uninitialize@NcsiSuspectStateMonitor@@QEAAXXZ; NcsiSuspectStateMonitor::Uninitialize(void)
0x180050644  call    ?Stop@GroupPolicyMonitor@@QEAAXXZ; GroupPolicyMonitor::Stop(void)
0x180050649  xor     ecx, ecx; bool
0x18005064b  call    ?UpdateClientPresence@PassivePollManager@PassivePoll@Ncsi@@SAX_N@Z; Ncsi::PassivePoll::PassivePollManager::UpdateClientPresence(bool)
0x180050650  jmp     short loc_18005065D
0x180050652  mov     ecx, 32h ; '2'; dwMilliseconds
0x180050657  call    cs:__imp_Sleep
0x18005065d  mov     eax, cs:?g_ncsiNlaThreadCount@@3U?$atomic@J@std@@A; std::atomic<long> g_ncsiNlaThreadCount
0x180050663  nop
0x180050664  test    eax, eax
0x180050666  jg      short loc_180050652
0x180050668  lea     rcx, ?g_ncsiNetHealthTracking@@3VNetworkHealthTracking@@A; lpCriticalSection
0x18005066f  call    cs:__imp_EnterCriticalSection
0x180050675  mov     rdx, qword ptr cs:xmmword_18009D7E0
0x18005067c  mov     rcx, cs:qword_18009D7D8
0x180050683  cmp     rcx, rdx
0x180050686  jz      short loc_18005069B
0x180050688  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VNetworkHealthEvent@NetworkHealthTracking@@U?$default_delete@VNetworkHealthEvent@NetworkHealthTracking@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VNetworkHealthEvent@NetworkHealthTracking@@U?$default_delete@VNetworkHealthEvent@NetworkHealthTracking@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VNetworkHealthEvent@NetworkHealthTracking@@U?$default_delete@VNetworkHealthEvent@NetworkHealthTracking@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<NetworkHealthTracking::NetworkHealthEvent>>>(std::unique_ptr<NetworkHealthTracking::NetworkHealthEvent> *,std::unique_ptr<NetworkHealthTracking::NetworkHealthEvent> * const,std::allocator<std::unique_ptr<NetworkHealthTracking::NetworkHealthEvent>> &)
0x18005068d  mov     rax, cs:qword_18009D7D8
0x180050694  mov     qword ptr cs:xmmword_18009D7E0, rax
0x18005069b  lea     rcx, ?g_ncsiNetHealthTracking@@3VNetworkHealthTracking@@A; lpCriticalSection
0x1800506a2  call    cs:__imp_LeaveCriticalSection
0x1800506a8  call    ?Cleanup@NCSI_CORP_LOCATION_PROBE@@SAXXZ; NCSI_CORP_LOCATION_PROBE::Cleanup(void)
0x1800506ad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NCSI_Fix_ThreadPoolTimerCleanup@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NCSI_Fix_ThreadPoolTimerCleanup@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NCSI_Fix_ThreadPoolTimerCleanup> `wil::Feature<__WilFeatureTraits_Feature_NCSI_Fix_ThreadPoolTimerCleanup>::GetImpl(void)'::`2'::impl
0x1800506b4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NCSI_Fix_ThreadPoolTimerCleanup@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NCSI_Fix_ThreadPoolTimerCleanup>::__private_IsEnabled(void)
0x1800506b9  test    al, al
0x1800506bb  jz      short loc_1800506D0
0x1800506bd  call    ?CancelResponseToWpadOpportunity@@YAXXZ; CancelResponseToWpadOpportunity(void)
0x1800506c2  xor     edx, edx
0x1800506c4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?CloseThreadpoolTimer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&CloseThreadpoolTimer(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800506c9  call    ?NcsiThreadPoolShutdown@@YAXXZ; NcsiThreadPoolShutdown(void)
0x1800506ce  jmp     short loc_1800506E0
0x1800506d0  call    ?NcsiThreadPoolShutdown@@YAXXZ; NcsiThreadPoolShutdown(void)
0x1800506d5  mov     cs:pti, 0
0x1800506e0  call    ?Purge@Detector@Proxy@Ncsi@@QEAAXXZ; Ncsi::Proxy::Detector::Purge(void)
0x1800506e5  lea     rcx, ?g_ncsiLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x1800506ec  call    cs:__imp_EnterCriticalSection
0x1800506f2  mov     rdx, qword ptr cs:xmmword_18009DCC0
0x1800506f9  mov     rcx, cs:?g_ncsiInterfaceList@@3V?$vector@VNCSI_INTERFACE_ATTRIBUTES@@V?$allocator@VNCSI_INTERFACE_ATTRIBUTES@@@std@@@std@@A; this
0x180050700  cmp     rcx, rdx
0x180050703  jz      short loc_180050718
0x180050705  call    ??$_Destroy_range@V?$allocator@VNCSI_INTERFACE_ATTRIBUTES@@@std@@@std@@YAXPEAVNCSI_INTERFACE_ATTRIBUTES@@QEAV1@AEAV?$allocator@VNCSI_INTERFACE_ATTRIBUTES@@@0@@Z; std::_Destroy_range<std::allocator<NCSI_INTERFACE_ATTRIBUTES>>(NCSI_INTERFACE_ATTRIBUTES *,NCSI_INTERFACE_ATTRIBUTES * const,std::allocator<NCSI_INTERFACE_ATTRIBUTES> &)
0x18005070a  mov     rax, cs:?g_ncsiInterfaceList@@3V?$vector@VNCSI_INTERFACE_ATTRIBUTES@@V?$allocator@VNCSI_INTERFACE_ATTRIBUTES@@@std@@@std@@A; std::vector<NCSI_INTERFACE_ATTRIBUTES> g_ncsiInterfaceList
0x180050711  mov     qword ptr cs:xmmword_18009DCC0, rax
0x180050718  lea     rcx, ?g_ncsiLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x18005071f  call    cs:__imp_LeaveCriticalSection
0x180050725  call    ?Uninitialize@NcsiConfigData@@QEAAXXZ; NcsiConfigData::Uninitialize(void)
0x18005072a  call    ?Shutdown@Power@Ncsi@@YAXXZ; Ncsi::Power::Shutdown(void)
0x18005072f  call    ?Shutdown@PassivePollManager@PassivePoll@Ncsi@@SAXXZ; Ncsi::PassivePoll::PassivePollManager::Shutdown(void)
0x180050734  call    ?Deinit@ActiveProbeManager@@SAXXZ; ActiveProbeManager::Deinit(void)
0x180050739  call    ?CleanupGlobalNsiData@@YAXXZ; CleanupGlobalNsiData(void)
0x18005073e  call    cs:__imp_WSACleanup
0x180050744  test    esi, esi
0x180050746  jz      short loc_180050774
0x180050748  mov     rcx, cs:WPP_GLOBAL_Control
0x18005074f  cmp     rcx, r12
0x180050752  jz      short loc_180050774
0x180050754  test    [rcx+1Ch], r15b
0x180050758  jz      short loc_180050774
0x18005075a  cmp     byte ptr [rcx+19h], 5
0x18005075e  jb      short loc_180050774
0x180050760  mov     rcx, [rcx+10h]
0x180050764  mov     edx, 1Dh
0x180050769  mov     r9d, esi
0x18005076c  mov     r8, r13
0x18005076f  call    WPP_SF_d
0x180050774  mov     rcx, [rbp+190h+var_30]
0x18005077b  xor     rcx, rsp; StackCookie
0x18005077e  call    __security_check_cookie
0x180050783  lea     r11, [rsp+290h+var_20]
0x18005078b  mov     rbx, [r11+38h]
0x18005078f  mov     rsi, [r11+40h]
0x180050793  mov     rsp, r11
0x180050796  pop     r15
0x180050798  pop     r13
0x18005079a  pop     r12
0x18005079c  pop     rdi
0x18005079d  pop     rbp
0x18005079e  retn
```
