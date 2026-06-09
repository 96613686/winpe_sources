# NetworkListManager::RuntimeClassInitialize(void)

- ea: `0x1800c5620`
- end: `0x1800c5ab5`
- name: `?RuntimeClassInitialize@NetworkListManager@@QEAAJXZ`
- size: `1173`
- prototype: `__int64 __fastcall(NetworkListManager *__hidden this)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800958d4`

## callees

- `0x18000fab0`
- `0x180010340`
- `0x180015628`
- `0x180018968`
- `0x18004fbe4`
- `0x18007f384`
- `0x18008285c`
- `0x180082958`
- `0x180082a48`
- `0x180088704`
- `0x180099b2c`
- `0x18009b248`
- `0x18009bc8c`
- `0x18009d2a0`
- `0x1800a1b54`
- `0x1800a25cc`
- `0x1800a3928`
- `0x1800a53b4`
- `0x1800a7f74`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800bcbfc`
- `0x1800c3f10`
- `0x1800c4fdc`
- `0x1800c5074`
- `0x1800c5180`
- `0x1800c5620`
- `0x1800c61a4`
- `0x1800c80c0`
- `0x1800c86f0`
- `0x1800cb214`
- `0x1800d1d98`
- `0x180116cfc`

## import_xrefs

- `ntdll!RtlQueryWnfStateData` at `0x1800c5911`
- `ntdll!RtlQueryWnfStateData` at `0x1800c5911`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800c5972`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800c5972`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800c56ac`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800c56ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c57be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c57be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5890`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800c5812`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800c58e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800c5812`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800c58e4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800c579d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800c586f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800c579d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800c586f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c56fd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c570a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c56fd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c570a`
- `WS2_32!__imp_WSAStartup` at `0x1800c5695`
- `WS2_32!__imp_WSAStartup` at `0x1800c5695`

## string_xrefs

- `0x1800c573f`: `onecore\net\netprofiles\service\src\standby\lib\standbymonitor.cpp`

## pseudocode

```c
__int64 __fastcall NetworkListManager::RuntimeClassInitialize(NetworkListManager *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // ebx
  int v7; // eax
  bool v8; // cl
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *v10; // rcx
  signed int LastError; // eax
  PTP_WAIT v12; // rax
  struct _TP_WAIT *v13; // rcx
  signed int v14; // eax
  int WnfStateData; // eax
  int v16; // ebx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdx
  PVOID v21; // rcx
  bool v22; // al
  int v24; // [rsp+20h] [rbp-208h]
  unsigned int v25[4]; // [rsp+40h] [rbp-1E8h] BYREF
  WSAData WSAData; // [rsp+50h] [rbp-1D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
  if ( !*((_DWORD *)this + 22) )
  {
    memset_0(&WSAData, 0, sizeof(WSAData));
    *((_DWORD *)this + 22) = WSAStartup(0x202u, &WSAData) == 0;
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1192));
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_TerminateCleanupIsolation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_TerminateCleanupIsolation>::GetImpl'::`2'::impl) )
  {
    *((_BYTE *)this + 1232) = 1;
    byte_1801C7E60 = 0;
  }
  if ( g_pProfileManager )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2, v4, v5);
  g_pProfileManager = this;
  g_szRootDnsAddr = 0;
  NetworkListManager::LoadDefaultStrings(this);
  CoCreateGuid(&g_unidentifiedGuid);
  CoCreateGuid(&g_identifyingGuid);
  *(_QWORD *)v25 = this;
  v6 = wil::ResultFromException__NetworkListManager::RuntimeClassInitialize_::_2_::_lambda_1___(v25);
  if ( v6 >= 0 )
  {
    v7 = StandbyMonitor::details::Singleton<StandbyMonitor::StandbyMonitor>::Init<>();
    v6 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D4,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\standby\\lib\\standbymonitor.cpp",
        (const char *)(unsigned int)v7,
        v24);
      goto LABEL_56;
    }
    v6 = ConnectivityAggregator::Init();
    if ( v6 < 0 )
      goto LABEL_56;
    v6 = PairedWebProbe::Init();
    if ( v6 < 0 )
      goto LABEL_56;
    v6 = InterfaceIdentifier::Init();
    if ( v6 < 0 )
      goto LABEL_56;
    v6 = DiagnosticsManager::Init(v8);
    if ( v6 < 0 )
      goto LABEL_56;
    ThreadpoolWait = CreateThreadpoolWait(NetworkListManager::NetworkEventAggregatorCallback, 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
      &g_networkEventAggregator,
      ThreadpoolWait);
    v10 = g_networkEventAggregator;
    if ( !g_networkEventAggregator )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids,
          (unsigned int)v6);
      if ( v6 < 0 )
        goto LABEL_56;
      v10 = g_networkEventAggregator;
    }
    SetThreadpoolWait(v10, qword_1801C7BE8, 0);
    v6 = NlmSignatures::SignatureGenerator::Init();
    if ( v6 < 0 )
      goto LABEL_56;
    v6 = NlmDomain::Init();
    if ( v6 < 0 )
      goto LABEL_56;
    v6 = L2Manager::Init();
    if ( v6 < 0 )
      goto LABEL_56;
    v6 = L3Manager::Init();
    if ( v6 < 0 )
      goto LABEL_56;
    v6 = TlsAuthentication::Init();
    if ( v6 < 0 )
      goto LABEL_56;
    v12 = CreateThreadpoolWait(NetworkListManager::FirewallEventMgrCallback, 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
      &g_firewallEventMgr,
      v12);
    v13 = g_firewallEventMgr;
    if ( g_firewallEventMgr )
    {
LABEL_38:
      SetThreadpoolWait(v13, h, 0);
      v25[0] = 0;
      WnfStateData = RtlQueryWnfStateData(
                       v25,
                       WNF_WFAS_FIREWALL_NETWORK_CHANGE_READY,
                       NetworkListManager::FirewallNetworkChangeReadyCallback,
                       0,
                       0);
      v16 = WnfStateData;
      if ( WnfStateData >= 0 )
      {
        WnfStateData = RtlSubscribeWnfStateChangeNotification(
                         (char *)this + 1160,
                         WNF_WFAS_FIREWALL_NETWORK_CHANGE_READY,
                         v25[0],
                         NetworkListManager::FirewallNetworkChangeReadyCallback,
                         0,
                         0,
                         0,
                         1);
        v16 = WnfStateData;
        if ( WnfStateData < 0 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v18 = 14;
            goto LABEL_46;
          }
        }
      }
      else
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v18 = 13;
LABEL_46:
          WPP_SF_d(v17[2], v18, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids, (unsigned int)WnfStateData);
        }
      }
      v6 = v16 | 0x10000000;
      if ( v6 >= 0 )
      {
        NetworkListManager::RegisterVPNReconnectNotifications(this);
        HrGetDefaultCosts();
        v19 = NetworkListManager::RegisterWithIpHlp(this);
        v6 = v19;
        if ( v19 >= 0 )
        {
          v6 = IgdResolver::Init();
          if ( v6 >= 0 )
          {
            NetworkListManager::RegisterForPolicyChangeNotification(this);
            LoadPolicyData();
          }
        }
        else
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              15,
              &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids,
              (unsigned int)v19);
          if ( (Microsoft_Windows_NetworkProfileEnableBits & 0x20) != 0 )
            McTemplateU0dq_EtwEventWriteTransfer(v21, v20, (unsigned int)v6);
        }
      }
      goto LABEL_56;
    }
    v14 = GetLastError();
    v6 = v14;
    if ( v14 > 0 )
      v6 = (unsigned __int16)v14 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids,
        (unsigned int)v6);
    if ( v6 >= 0 )
    {
      v13 = g_firewallEventMgr;
      goto LABEL_38;
    }
  }
LABEL_56:
  v22 = IsInContainerGuestMode();
  g_isInContainerGuestMode = v22;
  if ( v22 )
    KryptonHostSharedContainerManager::Init();
  else
    KryptonHostManager::Init();
  if ( v6 < 0 || (v6 = NetworkClassifier::Init(), v6 < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
    NetworkListManager::Terminate(this);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids,
      (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800c5620  push    rbx
0x1800c5622  push    rbp
0x1800c5623  push    rdi
0x1800c5624  push    r15
0x1800c5626  sub     rsp, 208h
0x1800c562d  mov     rax, cs:__security_cookie
0x1800c5634  xor     rax, rsp
0x1800c5637  mov     [rsp+228h+var_38], rax
0x1800c563f  mov     rdi, rcx
0x1800c5642  lea     rbp, WPP_GLOBAL_Control
0x1800c5649  lea     r15, WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids
0x1800c5650  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5657  cmp     rcx, rbp
0x1800c565a  jz      short loc_1800C5673
0x1800c565c  test    byte ptr [rcx+1Ch], 8
0x1800c5660  jz      short loc_1800C5673
0x1800c5662  mov     edx, 0Ah
0x1800c5667  mov     r8, r15
0x1800c566a  mov     rcx, [rcx+10h]
0x1800c566e  call    WPP_SF_
0x1800c5673  cmp     dword ptr [rdi+58h], 0
0x1800c5677  jnz     short loc_1800C56A5
0x1800c5679  xor     edx, edx; Val
0x1800c567b  mov     r8d, 198h; Size
0x1800c5681  lea     rcx, [rsp+228h+WSAData]; void *
0x1800c5686  call    memset_0
0x1800c568b  mov     ecx, 202h; wVersionRequested
0x1800c5690  lea     rdx, [rsp+228h+WSAData]; lpWSAData
0x1800c5695  call    cs:__imp_WSAStartup
0x1800c569b  xor     ecx, ecx
0x1800c569d  test    eax, eax
0x1800c569f  setz    cl
0x1800c56a2  mov     [rdi+58h], ecx
0x1800c56a5  lea     rcx, [rdi+4A8h]; lpCriticalSection
0x1800c56ac  call    cs:__imp_InitializeCriticalSection
0x1800c56b2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_TerminateCleanupIsolation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_TerminateCleanupIsolation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_TerminateCleanupIsolation> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_TerminateCleanupIsolation>::GetImpl(void)'::`2'::impl
0x1800c56b9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_TerminateCleanupIsolation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_TerminateCleanupIsolation>::__private_IsEnabled(void)
0x1800c56be  test    al, al
0x1800c56c0  jz      short loc_1800C56D1
0x1800c56c2  mov     byte ptr [rdi+4D0h], 1
0x1800c56c9  xor     eax, eax
0x1800c56cb  xchg    al, cs:byte_1801C7E60
0x1800c56d1  cmp     cs:?g_pProfileManager@@3PEAVNetworkListManager@@EA, 0; NetworkListManager * g_pProfileManager
0x1800c56d9  jz      short loc_1800C56E0
0x1800c56db  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800c56e0  mov     cs:?g_pProfileManager@@3PEAVNetworkListManager@@EA, rdi; NetworkListManager * g_pProfileManager
0x1800c56e7  mov     cs:?g_szRootDnsAddr@@3PADA, 0; char near * g_szRootDnsAddr
0x1800c56ee  mov     rcx, rdi; this
0x1800c56f1  call    ?LoadDefaultStrings@NetworkListManager@@AEAAXXZ; NetworkListManager::LoadDefaultStrings(void)
0x1800c56f6  lea     rcx, ?g_unidentifiedGuid@@3U_GUID@@A; pguid
0x1800c56fd  call    cs:__imp_CoCreateGuid
0x1800c5703  lea     rcx, ?g_identifyingGuid@@3U_GUID@@A; pguid
0x1800c570a  call    cs:__imp_CoCreateGuid
0x1800c5710  mov     qword ptr [rsp+228h+var_1E8], rdi
0x1800c5715  lea     rcx, [rsp+228h+var_1E8]
0x1800c571a  call    wil__ResultFromException__NetworkListManager__RuntimeClassInitialize____2____lambda_1___
0x1800c571f  mov     ebx, eax
0x1800c5721  test    eax, eax
0x1800c5723  js      loc_1800C5A18
0x1800c5729  call    ??$Init@$$V@?$Singleton@VStandbyMonitor@1@@details@StandbyMonitor@@SAJXZ; StandbyMonitor::details::Singleton<StandbyMonitor::StandbyMonitor>::Init<>(void)
0x1800c572e  mov     ebx, eax
0x1800c5730  test    eax, eax
0x1800c5732  jns     short loc_1800C5755
0x1800c5734  mov     rcx, [rsp+228h]; this
0x1800c573c  mov     r9d, eax; char *
0x1800c573f  lea     r8, aOnecoreNetNetp_10; "onecore\\net\\netprofiles\\service\\src"...
0x1800c5746  mov     edx, 1D4h; void *
0x1800c574b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c5750  jmp     loc_1800C5A18
0x1800c5755  call    ?Init@ConnectivityAggregator@@SAJXZ; ConnectivityAggregator::Init(void)
0x1800c575a  mov     ebx, eax
0x1800c575c  test    eax, eax
0x1800c575e  js      loc_1800C5A18
0x1800c5764  call    ?Init@PairedWebProbe@@SAJXZ; PairedWebProbe::Init(void)
0x1800c5769  mov     ebx, eax
0x1800c576b  test    eax, eax
0x1800c576d  js      loc_1800C5A18
0x1800c5773  call    ?Init@InterfaceIdentifier@@SAJXZ; InterfaceIdentifier::Init(void)
0x1800c5778  mov     ebx, eax
0x1800c577a  test    eax, eax
0x1800c577c  js      loc_1800C5A18
0x1800c5782  call    ?Init@DiagnosticsManager@@SAJ_N@Z; DiagnosticsManager::Init(bool)
0x1800c5787  mov     ebx, eax
0x1800c5789  test    eax, eax
0x1800c578b  js      loc_1800C5A18
0x1800c5791  xor     r8d, r8d; pcbe
0x1800c5794  xor     edx, edx; pv
0x1800c5796  lea     rcx, ?NetworkEventAggregatorCallback@NetworkListManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800c579d  call    cs:__imp_CreateThreadpoolWait
0x1800c57a3  mov     rdx, rax
0x1800c57a6  lea     rcx, ?g_networkEventAggregator@@3UAggregatorEventMgr@@A; AggregatorEventMgr g_networkEventAggregator
0x1800c57ad  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x1800c57b2  mov     rcx, cs:?g_networkEventAggregator@@3UAggregatorEventMgr@@A; AggregatorEventMgr g_networkEventAggregator
0x1800c57b9  test    rcx, rcx
0x1800c57bc  jnz     short loc_1800C5808
0x1800c57be  call    cs:__imp_GetLastError
0x1800c57c4  mov     ebx, eax
0x1800c57c6  test    eax, eax
0x1800c57c8  jle     short loc_1800C57D3
0x1800c57ca  movzx   ebx, ax
0x1800c57cd  or      ebx, 80070000h
0x1800c57d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c57da  cmp     rcx, rbp
0x1800c57dd  jz      short loc_1800C57F9
0x1800c57df  test    byte ptr [rcx+1Ch], 1
0x1800c57e3  jz      short loc_1800C57F9
0x1800c57e5  mov     edx, 0Bh
0x1800c57ea  mov     r9d, ebx
0x1800c57ed  mov     r8, r15
0x1800c57f0  mov     rcx, [rcx+10h]
0x1800c57f4  call    WPP_SF_d
0x1800c57f9  test    ebx, ebx
0x1800c57fb  js      loc_1800C5A18
0x1800c5801  mov     rcx, cs:?g_networkEventAggregator@@3UAggregatorEventMgr@@A; pwa
0x1800c5808  xor     r8d, r8d; pftTimeout
0x1800c580b  mov     rdx, cs:qword_1801C7BE8; h
0x1800c5812  call    cs:__imp_SetThreadpoolWait
0x1800c5818  call    ?Init@SignatureGenerator@NlmSignatures@@SAJXZ; NlmSignatures::SignatureGenerator::Init(void)
0x1800c581d  mov     ebx, eax
0x1800c581f  test    eax, eax
0x1800c5821  js      loc_1800C5A18
0x1800c5827  call    ?Init@NlmDomain@@SAJXZ; NlmDomain::Init(void)
0x1800c582c  mov     ebx, eax
0x1800c582e  test    eax, eax
0x1800c5830  js      loc_1800C5A18
0x1800c5836  call    ?Init@L2Manager@@SAJXZ; L2Manager::Init(void)
0x1800c583b  mov     ebx, eax
0x1800c583d  test    eax, eax
0x1800c583f  js      loc_1800C5A18
0x1800c5845  call    ?Init@L3Manager@@SAJXZ; L3Manager::Init(void)
0x1800c584a  mov     ebx, eax
0x1800c584c  test    eax, eax
0x1800c584e  js      loc_1800C5A18
0x1800c5854  call    ?Init@TlsAuthentication@@SAJXZ; TlsAuthentication::Init(void)
0x1800c5859  mov     ebx, eax
0x1800c585b  test    eax, eax
0x1800c585d  js      loc_1800C5A18
0x1800c5863  xor     r8d, r8d; pcbe
0x1800c5866  xor     edx, edx; pv
0x1800c5868  lea     rcx, ?FirewallEventMgrCallback@NetworkListManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800c586f  call    cs:__imp_CreateThreadpoolWait
0x1800c5875  mov     rdx, rax
0x1800c5878  lea     rcx, ?g_firewallEventMgr@@3UFirewallEventMgr@@A; FirewallEventMgr g_firewallEventMgr
0x1800c587f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x1800c5884  mov     rcx, cs:?g_firewallEventMgr@@3UFirewallEventMgr@@A; FirewallEventMgr g_firewallEventMgr
0x1800c588b  test    rcx, rcx
0x1800c588e  jnz     short loc_1800C58DA
0x1800c5890  call    cs:__imp_GetLastError
0x1800c5896  mov     ebx, eax
0x1800c5898  test    eax, eax
0x1800c589a  jle     short loc_1800C58A5
0x1800c589c  movzx   ebx, ax
0x1800c589f  or      ebx, 80070000h
0x1800c58a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c58ac  cmp     rcx, rbp
0x1800c58af  jz      short loc_1800C58CB
0x1800c58b1  test    byte ptr [rcx+1Ch], 1
0x1800c58b5  jz      short loc_1800C58CB
0x1800c58b7  mov     edx, 0Ch
0x1800c58bc  mov     r9d, ebx
0x1800c58bf  mov     r8, r15
0x1800c58c2  mov     rcx, [rcx+10h]
0x1800c58c6  call    WPP_SF_d
0x1800c58cb  test    ebx, ebx
0x1800c58cd  js      loc_1800C5A18
0x1800c58d3  mov     rcx, cs:?g_firewallEventMgr@@3UFirewallEventMgr@@A; pwa
0x1800c58da  xor     r8d, r8d; pftTimeout
0x1800c58dd  mov     rdx, cs:h; h
0x1800c58e4  call    cs:__imp_SetThreadpoolWait
0x1800c58ea  mov     [rsp+228h+var_1E8], 0
0x1800c58f2  mov     [rsp+228h+var_208], 0
0x1800c58fb  xor     r9d, r9d
0x1800c58fe  lea     r8, ?FirewallNetworkChangeReadyCallback@NetworkListManager@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; NetworkListManager::FirewallNetworkChangeReadyCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800c5905  mov     rdx, cs:WNF_WFAS_FIREWALL_NETWORK_CHANGE_READY
0x1800c590c  lea     rcx, [rsp+228h+var_1E8]
0x1800c5911  call    cs:__imp_RtlQueryWnfStateData
0x1800c5917  mov     ebx, eax
0x1800c5919  test    eax, eax
0x1800c591b  jns     short loc_1800C5936
0x1800c591d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5924  cmp     rcx, rbp
0x1800c5927  jz      short loc_1800C59A4
0x1800c5929  test    byte ptr [rcx+1Ch], 1
0x1800c592d  jz      short loc_1800C59A4
0x1800c592f  mov     edx, 0Dh
0x1800c5934  jmp     short loc_1800C5995
0x1800c5936  lea     rcx, [rdi+488h]
0x1800c593d  mov     [rsp+228h+var_1F0], 1
0x1800c5945  mov     [rsp+228h+var_1F8], 0
0x1800c594d  mov     [rsp+228h+var_200], 0
0x1800c5956  mov     [rsp+228h+var_208], 0
0x1800c595f  lea     r9, ?FirewallNetworkChangeReadyCallback@NetworkListManager@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; NetworkListManager::FirewallNetworkChangeReadyCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800c5966  mov     r8d, [rsp+228h+var_1E8]
0x1800c596b  mov     rdx, cs:WNF_WFAS_FIREWALL_NETWORK_CHANGE_READY
0x1800c5972  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800c5978  mov     ebx, eax
0x1800c597a  test    eax, eax
0x1800c597c  jns     short loc_1800C59A4
0x1800c597e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5985  cmp     rcx, rbp
0x1800c5988  jz      short loc_1800C59A4
0x1800c598a  test    byte ptr [rcx+1Ch], 1
0x1800c598e  jz      short loc_1800C59A4
0x1800c5990  mov     edx, 0Eh
0x1800c5995  mov     r9d, eax
0x1800c5998  mov     r8, r15
0x1800c599b  mov     rcx, [rcx+10h]
0x1800c599f  call    WPP_SF_d
0x1800c59a4  or      ebx, 10000000h
0x1800c59aa  jl      short loc_1800C5A18
0x1800c59ac  mov     rcx, rdi; this
0x1800c59af  call    ?RegisterVPNReconnectNotifications@NetworkListManager@@AEAAJXZ; NetworkListManager::RegisterVPNReconnectNotifications(void)
0x1800c59b4  call    ?HrGetDefaultCosts@@YAXXZ; HrGetDefaultCosts(void)
0x1800c59b9  mov     rcx, rdi; this
0x1800c59bc  call    ?RegisterWithIpHlp@NetworkListManager@@AEAAJXZ; NetworkListManager::RegisterWithIpHlp(void)
0x1800c59c1  mov     ebx, eax
0x1800c59c3  test    eax, eax
0x1800c59c5  jns     short loc_1800C5A00
0x1800c59c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c59ce  cmp     rcx, rbp
0x1800c59d1  jz      short loc_1800C59ED
0x1800c59d3  test    byte ptr [rcx+1Ch], 1
0x1800c59d7  jz      short loc_1800C59ED
0x1800c59d9  mov     edx, 0Fh
0x1800c59de  mov     r9d, eax
0x1800c59e1  mov     r8, r15
0x1800c59e4  mov     rcx, [rcx+10h]
0x1800c59e8  call    WPP_SF_d
0x1800c59ed  test    byte ptr cs:Microsoft_Windows_NetworkProfileEnableBits, 20h
0x1800c59f4  jz      short loc_1800C5A18
0x1800c59f6  mov     r8d, ebx
0x1800c59f9  call    McTemplateU0dq_EtwEventWriteTransfer
0x1800c59fe  jmp     short loc_1800C5A18
0x1800c5a00  call    ?Init@IgdResolver@@SAJXZ; IgdResolver::Init(void)
0x1800c5a05  mov     ebx, eax
0x1800c5a07  test    eax, eax
0x1800c5a09  js      short loc_1800C5A18
0x1800c5a0b  mov     rcx, rdi; this
0x1800c5a0e  call    ?RegisterForPolicyChangeNotification@NetworkListManager@@AEAAJXZ; NetworkListManager::RegisterForPolicyChangeNotification(void)
0x1800c5a13  call    ?LoadPolicyData@@YAXXZ; LoadPolicyData(void)
0x1800c5a18  call    ?IsInContainerGuestMode@@YA_NXZ; IsInContainerGuestMode(void)
0x1800c5a1d  movzx   eax, al
0x1800c5a20  mov     cs:?g_isInContainerGuestMode@@3HA, eax; int g_isInContainerGuestMode
0x1800c5a26  test    eax, eax
0x1800c5a28  jz      short loc_1800C5A31
0x1800c5a2a  call    ?Init@KryptonHostSharedContainerManager@@SAJXZ; KryptonHostSharedContainerManager::Init(void)
0x1800c5a2f  jmp     short loc_1800C5A36
0x1800c5a31  call    ?Init@KryptonHostManager@@SAXXZ; KryptonHostManager::Init(void)
0x1800c5a36  test    ebx, ebx
0x1800c5a38  js      short loc_1800C5A45
0x1800c5a3a  call    ?Init@NetworkClassifier@@SAJXZ; NetworkClassifier::Init(void)
0x1800c5a3f  mov     ebx, eax
0x1800c5a41  test    eax, eax
0x1800c5a43  jns     short loc_1800C5A70
0x1800c5a45  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5a4c  cmp     rcx, rbp
0x1800c5a4f  jz      short loc_1800C5A68
0x1800c5a51  test    byte ptr [rcx+1Ch], 8
0x1800c5a55  jz      short loc_1800C5A68
0x1800c5a57  mov     edx, 10h
0x1800c5a5c  mov     r8, r15
0x1800c5a5f  mov     rcx, [rcx+10h]
0x1800c5a63  call    WPP_SF_
0x1800c5a68  mov     rcx, rdi; this
0x1800c5a6b  call    ?Terminate@NetworkListManager@@QEAAXXZ; NetworkListManager::Terminate(void)
0x1800c5a70  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5a77  cmp     rcx, rbp
0x1800c5a7a  jz      short loc_1800C5A96
0x1800c5a7c  test    byte ptr [rcx+1Ch], 8
0x1800c5a80  jz      short loc_1800C5A96
0x1800c5a82  mov     edx, 11h
0x1800c5a87  mov     r9d, ebx
0x1800c5a8a  mov     r8, r15
0x1800c5a8d  mov     rcx, [rcx+10h]
0x1800c5a91  call    WPP_SF_d
0x1800c5a96  mov     eax, ebx
0x1800c5a98  mov     rcx, [rsp+228h+var_38]
0x1800c5aa0  xor     rcx, rsp; StackCookie
0x1800c5aa3  call    __security_check_cookie
0x1800c5aa8  add     rsp, 208h
0x1800c5aaf  pop     r15
0x1800c5ab1  pop     rdi
0x1800c5ab2  pop     rbp
0x1800c5ab3  pop     rbx
0x1800c5ab4  retn
```
