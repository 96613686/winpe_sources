# NetworkListManager::Terminate(void)

- ea: `0x1800c61a4`
- end: `0x1800c6741`
- name: `?Terminate@NetworkListManager@@QEAAXXZ`
- size: `1437`
- prototype: `void __fastcall(NetworkListManager *__hidden this)`
- caller_count: `3`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18009eb98`
- `0x1800beb78`
- `0x1800c5620`

## callees

- `0x180009990`
- `0x18000fab0`
- `0x180035fec`
- `0x18004fbe4`
- `0x1800839d0`
- `0x180087130`
- `0x18009ab1c`
- `0x18009ced8`
- `0x1800bee38`
- `0x1800bf17c`
- `0x1800c61a4`
- `0x1800c80c0`
- `0x1800c81bc`
- `0x1800d1884`
- `0x1800d6098`
- `0x1800f281c`
- `0x1800f6af0`
- `0x1800fc680`
- `0x18010b728`
- `0x180111d00`
- `0x180116c84`
- `0x180125468`
- `0x18012b040`
- `0x18012bef4`
- `0x18012c4c4`
- `0x18012c634`
- `0x18012e504`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800c629d`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800c65a3`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800c629d`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800c65a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c645a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6729`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c645a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6729`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c6487`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c66b7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c6487`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c66b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c64aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c661e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c64aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c661e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c649c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c6608`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c649c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c6608`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800c62d8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800c65de`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800c62d8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800c65de`
- `api-ms-win-security-grouppolicy-l1-1-0!UnregisterGPNotificationInternal` at `0x1800c62f1`
- `api-ms-win-security-grouppolicy-l1-1-0!UnregisterGPNotificationInternal` at `0x1800c65f2`
- `api-ms-win-security-grouppolicy-l1-1-0!UnregisterGPNotificationInternal` at `0x1800c62f1`
- `api-ms-win-security-grouppolicy-l1-1-0!UnregisterGPNotificationInternal` at `0x1800c65f2`
- `WS2_32!__imp_WSACleanup` at `0x1800c64b5`
- `WS2_32!__imp_WSACleanup` at `0x1800c66c3`
- `WS2_32!__imp_WSACleanup` at `0x1800c64b5`
- `WS2_32!__imp_WSACleanup` at `0x1800c66c3`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800c62be`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800c65c4`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800c62be`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800c65c4`

## pseudocode

```c
void __fastcall NetworkListManager::Terminate(NetworkListManager *this)
{
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  void *v10; // rbp
  void *v11; // rsi
  int v12; // r14d
  ConnectionPointContainer *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  LPCRITICAL_SECTION v18; // [rsp+28h] [rbp-60h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[11]; // [rsp+30h] [rbp-58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_TerminateCleanupIsolation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_TerminateCleanupIsolation>::GetImpl'::`2'::impl) )
  {
    if ( g_pProfileManager == this )
    {
      if ( _InterlockedCompareExchange8(&byte_1801C7E60, 1, 0) )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v3 = 27;
          goto LABEL_9;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
        if ( *((_QWORD *)this + 145) )
        {
          RtlUnsubscribeWnfNotificationWaitForCompletion();
          *((_QWORD *)this + 145) = 0;
        }
        NetworkListManager::CleanupVPNReconnectNotifications(this);
        v4 = (void *)*((_QWORD *)this + 144);
        if ( v4 )
        {
          CancelMibChangeNotify2(v4);
          *((_QWORD *)this + 144) = 0;
        }
        v5 = (void *)*((_QWORD *)this + 14);
        if ( v5 )
        {
          UnregisterWaitEx(v5, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
          *((_QWORD *)this + 14) = 0;
        }
        if ( *((_DWORD *)this + 26) )
        {
          v6 = *((_QWORD *)this + 12);
          if ( v6 )
          {
            UnregisterGPNotificationInternal(v6);
            *((_DWORD *)this + 26) = 0;
          }
        }
        if ( g_networkEventAggregator )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
          NetworkListManager::PostNetworkEventToAggregator(6);
          NetworkListManager::Terminate_::_5_::_lambda_1_::operator()(v7, &g_networkEventAggregator);
        }
        if ( g_firewallEventMgr )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
          NetworkListManager::PostFirewallEventToFirewallEventMgr(3);
          NetworkListManager::Terminate_::_5_::_lambda_1_::operator()(v8, &g_firewallEventMgr);
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
        NetworkClassifier::Deinit();
        if ( g_isInContainerGuestMode )
          KryptonHostSharedContainerManager::Deinit();
        else
          KryptonHostManager::Deinit();
        IgdResolver::Deinit();
        TlsAuthentication::Deinit();
        L3Manager::Deinit();
        L2Manager::Deinit();
        NlmDomain::Deinit();
        NlmSignatures::SignatureGenerator::Deinit();
        DiagnosticsManager::Deinit();
        InterfaceIdentifier::Deinit();
        PairedWebProbe::Deinit();
        ConnectivityAggregator::Deinit();
        StandbyMonitor::details::Singleton<StandbyMonitor::StandbyMonitor>::DeinitAndWait();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
        lpCriticalSection[0] = 0;
        wil::EnterCriticalSection(lpCriticalSection, (char *)this + 40);
        v9 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 10);
        v18 = v9;
        *((_QWORD *)this + 10) = 0;
        v10 = (void *)*((_QWORD *)this + 155);
        *((_QWORD *)this + 155) = 0;
        v11 = (void *)*((_QWORD *)this + 12);
        *((_QWORD *)this + 12) = 0;
        v12 = *((_DWORD *)this + 22);
        *((_DWORD *)this + 22) = 0;
        if ( lpCriticalSection[0] )
          LeaveCriticalSection(lpCriticalSection[0]);
        if ( v9 )
        {
          ConnectionPointContainer::Terminate((ConnectionPointContainer *)v9);
          wil::com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>::reset(&v18);
        }
        if ( *((_BYTE *)this + 1232) )
        {
          DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1192));
          *((_BYTE *)this + 1232) = 0;
        }
        if ( v10 )
          CoTaskMemFree(v10);
        if ( v11 )
          CloseHandle(v11);
        if ( v12 )
          WSACleanup();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
        NetworkPropertyMaps::DeleteAllNetworks();
        g_pProfileManager = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
        wil::com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>::~com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>(&v18);
      }
    }
    else
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v3 = 26;
LABEL_9:
        WPP_SF_(v2[2], v3, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
      }
    }
  }
  else
  {
    NetworkClassifier::Deinit();
    if ( g_isInContainerGuestMode )
      KryptonHostSharedContainerManager::Deinit();
    else
      KryptonHostManager::Deinit();
    TlsAuthentication::Deinit();
    InterfaceIdentifier::Deinit();
    IgdResolver::Deinit();
    L3Manager::Deinit();
    L2Manager::Deinit();
    NlmDomain::Deinit();
    NlmSignatures::SignatureGenerator::Deinit();
    PairedWebProbe::Deinit();
    ConnectivityAggregator::Deinit();
    DiagnosticsManager::Deinit();
    StandbyMonitor::details::Singleton<StandbyMonitor::StandbyMonitor>::DeinitAndWait();
    v18 = 0;
    wil::EnterCriticalSection(&v18, (char *)this + 40);
    v13 = (ConnectionPointContainer *)*((_QWORD *)this + 10);
    if ( v13 )
    {
      ConnectionPointContainer::Terminate(v13);
      wil::com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>::reset((char *)this + 80);
    }
    if ( *((_QWORD *)this + 145) )
    {
      RtlUnsubscribeWnfNotificationWaitForCompletion();
      *((_QWORD *)this + 145) = 0;
    }
    NetworkListManager::CleanupVPNReconnectNotifications(this);
    v14 = (void *)*((_QWORD *)this + 144);
    if ( v14 )
    {
      CancelMibChangeNotify2(v14);
      *((_QWORD *)this + 144) = 0;
    }
    v15 = (void *)*((_QWORD *)this + 14);
    if ( v15 )
    {
      UnregisterWaitEx(v15, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      *((_QWORD *)this + 14) = 0;
    }
    if ( *((_DWORD *)this + 26) )
    {
      UnregisterGPNotificationInternal(*((_QWORD *)this + 12));
      *((_DWORD *)this + 26) = 0;
    }
    v16 = (void *)*((_QWORD *)this + 155);
    if ( v16 )
    {
      CoTaskMemFree(v16);
      *((_QWORD *)this + 155) = 0;
    }
    v17 = (void *)*((_QWORD *)this + 12);
    if ( v17 )
    {
      CloseHandle(v17);
      *((_QWORD *)this + 12) = 0;
    }
    if ( g_networkEventAggregator )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
      NetworkListManager::PostNetworkEventToAggregator(6);
      wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
        &g_networkEventAggregator,
        0);
    }
    if ( g_firewallEventMgr )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
      NetworkListManager::PostFirewallEventToFirewallEventMgr(3);
      wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
        &g_firewallEventMgr,
        0);
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1192));
    }
    if ( *((_DWORD *)this + 22) )
    {
      WSACleanup();
      *((_DWORD *)this + 22) = 0;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
    NetworkPropertyMaps::DeleteAllNetworks();
    g_pProfileManager = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
    if ( v18 )
      LeaveCriticalSection(v18);
  }
}

```

## disassembly

```asm
0x1800c61a4  push    rbx
0x1800c61a6  push    rbp
0x1800c61a7  push    rsi
0x1800c61a8  push    rdi
0x1800c61a9  push    r12
0x1800c61ab  push    r13
0x1800c61ad  push    r14
0x1800c61af  push    r15
0x1800c61b1  sub     rsp, 48h
0x1800c61b5  mov     rdi, rcx
0x1800c61b8  lea     r12, WPP_GLOBAL_Control
0x1800c61bf  mov     sil, 8
0x1800c61c2  lea     r13, WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids
0x1800c61c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c61d0  cmp     rcx, r12
0x1800c61d3  jz      short loc_1800C61EC
0x1800c61d5  test    [rcx+1Ch], sil
0x1800c61d9  jz      short loc_1800C61EC
0x1800c61db  mov     edx, 19h
0x1800c61e0  mov     r8, r13
0x1800c61e3  mov     rcx, [rcx+10h]
0x1800c61e7  call    WPP_SF_
0x1800c61ec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_TerminateCleanupIsolation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_TerminateCleanupIsolation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_TerminateCleanupIsolation> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_TerminateCleanupIsolation>::GetImpl(void)'::`2'::impl
0x1800c61f3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_TerminateCleanupIsolation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_TerminateCleanupIsolation>::__private_IsEnabled(void)
0x1800c61f8  xor     r15d, r15d
0x1800c61fb  test    al, al
0x1800c61fd  jz      loc_1800C651C
0x1800c6203  cmp     cs:?g_pProfileManager@@3PEAVNetworkListManager@@EA, rdi; NetworkListManager * g_pProfileManager
0x1800c620a  jz      short loc_1800C623B
0x1800c620c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6213  cmp     rcx, r12
0x1800c6216  jz      loc_1800C6730
0x1800c621c  test    [rcx+1Ch], sil
0x1800c6220  jz      loc_1800C6730
0x1800c6226  lea     edx, [r15+1Ah]
0x1800c622a  mov     r8, r13
0x1800c622d  mov     rcx, [rcx+10h]
0x1800c6231  call    WPP_SF_
0x1800c6236  jmp     loc_1800C6730
0x1800c623b  mov     ecx, 1
0x1800c6240  xor     eax, eax
0x1800c6242  lock cmpxchg cs:byte_1801C7E60, cl
0x1800c624a  jz      short loc_1800C626D
0x1800c624c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6253  cmp     rcx, r12
0x1800c6256  jz      loc_1800C6730
0x1800c625c  test    [rcx+1Ch], sil
0x1800c6260  jz      loc_1800C6730
0x1800c6266  mov     edx, 1Bh
0x1800c626b  jmp     short loc_1800C622A
0x1800c626d  mov     bl, 4
0x1800c626f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6276  cmp     rcx, r12
0x1800c6279  jz      short loc_1800C6291
0x1800c627b  test    [rcx+1Ch], bl
0x1800c627e  jz      short loc_1800C6291
0x1800c6280  mov     edx, 1Ch
0x1800c6285  mov     r8, r13
0x1800c6288  mov     rcx, [rcx+10h]
0x1800c628c  call    WPP_SF_
0x1800c6291  mov     rcx, [rdi+488h]
0x1800c6298  test    rcx, rcx
0x1800c629b  jz      short loc_1800C62AA
0x1800c629d  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800c62a3  mov     [rdi+488h], r15
0x1800c62aa  mov     rcx, rdi; this
0x1800c62ad  call    ?CleanupVPNReconnectNotifications@NetworkListManager@@AEAAXXZ; NetworkListManager::CleanupVPNReconnectNotifications(void)
0x1800c62b2  mov     rcx, [rdi+480h]; NotificationHandle
0x1800c62b9  test    rcx, rcx
0x1800c62bc  jz      short loc_1800C62CB
0x1800c62be  call    cs:__imp_CancelMibChangeNotify2
0x1800c62c4  mov     [rdi+480h], r15
0x1800c62cb  mov     rcx, [rdi+70h]; WaitHandle
0x1800c62cf  test    rcx, rcx
0x1800c62d2  jz      short loc_1800C62E2
0x1800c62d4  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800c62d8  call    cs:__imp_UnregisterWaitEx
0x1800c62de  mov     [rdi+70h], r15
0x1800c62e2  cmp     [rdi+68h], r15d
0x1800c62e6  jz      short loc_1800C62FB
0x1800c62e8  mov     rcx, [rdi+60h]
0x1800c62ec  test    rcx, rcx
0x1800c62ef  jz      short loc_1800C62FB
0x1800c62f1  call    cs:__imp_UnregisterGPNotificationInternal
0x1800c62f7  mov     [rdi+68h], r15d
0x1800c62fb  cmp     cs:?g_networkEventAggregator@@3UAggregatorEventMgr@@A, r15; AggregatorEventMgr g_networkEventAggregator
0x1800c6302  jz      short loc_1800C633C
0x1800c6304  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c630b  cmp     rcx, r12
0x1800c630e  jz      short loc_1800C6326
0x1800c6310  test    [rcx+1Ch], bl
0x1800c6313  jz      short loc_1800C6326
0x1800c6315  mov     edx, 1Dh
0x1800c631a  mov     r8, r13
0x1800c631d  mov     rcx, [rcx+10h]
0x1800c6321  call    WPP_SF_
0x1800c6326  mov     ecx, 6
0x1800c632b  call    ?PostNetworkEventToAggregator@NetworkListManager@@SAJW4NpAggregatorEventType@@@Z; NetworkListManager::PostNetworkEventToAggregator(NpAggregatorEventType)
0x1800c6330  lea     rdx, ?g_networkEventAggregator@@3UAggregatorEventMgr@@A; AggregatorEventMgr g_networkEventAggregator
0x1800c6337  call    _NetworkListManager__Terminate____5____lambda_1___operator__
0x1800c633c  cmp     cs:?g_firewallEventMgr@@3UFirewallEventMgr@@A, r15; FirewallEventMgr g_firewallEventMgr
0x1800c6343  jz      short loc_1800C637D
0x1800c6345  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c634c  cmp     rcx, r12
0x1800c634f  jz      short loc_1800C6367
0x1800c6351  test    [rcx+1Ch], bl
0x1800c6354  jz      short loc_1800C6367
0x1800c6356  mov     edx, 1Eh
0x1800c635b  mov     r8, r13
0x1800c635e  mov     rcx, [rcx+10h]
0x1800c6362  call    WPP_SF_
0x1800c6367  mov     ecx, 3
0x1800c636c  call    ?PostFirewallEventToFirewallEventMgr@NetworkListManager@@CAJW4NpFirewallEventType@@@Z; NetworkListManager::PostFirewallEventToFirewallEventMgr(NpFirewallEventType)
0x1800c6371  lea     rdx, ?g_firewallEventMgr@@3UFirewallEventMgr@@A; FirewallEventMgr g_firewallEventMgr
0x1800c6378  call    _NetworkListManager__Terminate____5____lambda_1___operator__
0x1800c637d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6384  cmp     rcx, r12
0x1800c6387  jz      short loc_1800C639F
0x1800c6389  test    [rcx+1Ch], bl
0x1800c638c  jz      short loc_1800C639F
0x1800c638e  mov     edx, 1Fh
0x1800c6393  mov     r8, r13
0x1800c6396  mov     rcx, [rcx+10h]
0x1800c639a  call    WPP_SF_
0x1800c639f  call    ?Deinit@NetworkClassifier@@SAXXZ; NetworkClassifier::Deinit(void)
0x1800c63a4  cmp     cs:?g_isInContainerGuestMode@@3HA, r15d; int g_isInContainerGuestMode
0x1800c63ab  jz      short loc_1800C63B4
0x1800c63ad  call    ?Deinit@KryptonHostSharedContainerManager@@SAXXZ; KryptonHostSharedContainerManager::Deinit(void)
0x1800c63b2  jmp     short loc_1800C63B9
0x1800c63b4  call    ?Deinit@KryptonHostManager@@SAXXZ; KryptonHostManager::Deinit(void)
0x1800c63b9  call    ?Deinit@IgdResolver@@SAXXZ; IgdResolver::Deinit(void)
0x1800c63be  call    ?Deinit@TlsAuthentication@@SAXXZ; TlsAuthentication::Deinit(void)
0x1800c63c3  call    ?Deinit@L3Manager@@SAXXZ; L3Manager::Deinit(void)
0x1800c63c8  call    ?Deinit@L2Manager@@SAXXZ; L2Manager::Deinit(void)
0x1800c63cd  call    ?Deinit@NlmDomain@@SAXXZ; NlmDomain::Deinit(void)
0x1800c63d2  call    ?Deinit@SignatureGenerator@NlmSignatures@@SAXXZ; NlmSignatures::SignatureGenerator::Deinit(void)
0x1800c63d7  call    ?Deinit@DiagnosticsManager@@SAXXZ; DiagnosticsManager::Deinit(void)
0x1800c63dc  call    ?Deinit@InterfaceIdentifier@@SAXXZ; InterfaceIdentifier::Deinit(void)
0x1800c63e1  call    ?Deinit@PairedWebProbe@@SAXXZ; PairedWebProbe::Deinit(void)
0x1800c63e6  call    ?Deinit@ConnectivityAggregator@@SAXXZ; ConnectivityAggregator::Deinit(void)
0x1800c63eb  call    ?DeinitAndWait@?$Singleton@VStandbyMonitor@1@@details@StandbyMonitor@@SAXXZ; StandbyMonitor::details::Singleton<StandbyMonitor::StandbyMonitor>::DeinitAndWait(void)
0x1800c63f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c63f7  cmp     rcx, r12
0x1800c63fa  jz      short loc_1800C6412
0x1800c63fc  test    [rcx+1Ch], bl
0x1800c63ff  jz      short loc_1800C6412
0x1800c6401  mov     edx, 20h ; ' '
0x1800c6406  mov     r8, r13
0x1800c6409  mov     rcx, [rcx+10h]
0x1800c640d  call    WPP_SF_
0x1800c6412  mov     [rsp+88h+lpCriticalSection], r15
0x1800c6417  lea     rdx, [rdi+28h]
0x1800c641b  lea     rcx, [rsp+88h+lpCriticalSection]
0x1800c6420  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800c6425  mov     rbx, [rdi+50h]
0x1800c6429  mov     [rsp+88h+var_60], rbx
0x1800c642e  mov     [rdi+50h], r15
0x1800c6432  mov     rbp, [rdi+4D8h]
0x1800c6439  mov     [rdi+4D8h], r15
0x1800c6440  mov     rsi, [rdi+60h]
0x1800c6444  mov     [rdi+60h], r15
0x1800c6448  mov     r14d, [rdi+58h]
0x1800c644c  mov     [rdi+58h], r15d
0x1800c6450  mov     rcx, [rsp+88h+lpCriticalSection]; lpCriticalSection
0x1800c6455  test    rcx, rcx
0x1800c6458  jz      short loc_1800C6460
0x1800c645a  call    cs:__imp_LeaveCriticalSection
0x1800c6460  test    rbx, rbx
0x1800c6463  jz      short loc_1800C6477
0x1800c6465  mov     rcx, rbx; this
0x1800c6468  call    ?Terminate@ConnectionPointContainer@@QEAAXXZ; ConnectionPointContainer::Terminate(void)
0x1800c646d  lea     rcx, [rsp+88h+var_60]
0x1800c6472  call    ?reset@?$com_ptr_t@VConnectionPointContainer@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>::reset(void)
0x1800c6477  cmp     [rdi+4D0h], r15b
0x1800c647e  jz      short loc_1800C6494
0x1800c6480  lea     rcx, [rdi+4A8h]; lpCriticalSection
0x1800c6487  call    cs:__imp_DeleteCriticalSection
0x1800c648d  mov     [rdi+4D0h], r15b
0x1800c6494  test    rbp, rbp
0x1800c6497  jz      short loc_1800C64A2
0x1800c6499  mov     rcx, rbp; pv
0x1800c649c  call    cs:__imp_CoTaskMemFree
0x1800c64a2  test    rsi, rsi
0x1800c64a5  jz      short loc_1800C64B0
0x1800c64a7  mov     rcx, rsi; hObject
0x1800c64aa  call    cs:__imp_CloseHandle
0x1800c64b0  test    r14d, r14d
0x1800c64b3  jz      short loc_1800C64BB
0x1800c64b5  call    cs:__imp_WSACleanup
0x1800c64bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c64c2  cmp     rcx, r12
0x1800c64c5  jz      short loc_1800C64DE
0x1800c64c7  test    byte ptr [rcx+1Ch], 8
0x1800c64cb  jz      short loc_1800C64DE
0x1800c64cd  mov     edx, 21h ; '!'
0x1800c64d2  mov     r8, r13
0x1800c64d5  mov     rcx, [rcx+10h]
0x1800c64d9  call    WPP_SF_
0x1800c64de  call    ?DeleteAllNetworks@NetworkPropertyMaps@@SAXXZ; NetworkPropertyMaps::DeleteAllNetworks(void)
0x1800c64e3  mov     cs:?g_pProfileManager@@3PEAVNetworkListManager@@EA, r15; NetworkListManager * g_pProfileManager
0x1800c64ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c64f1  cmp     rcx, r12
0x1800c64f4  jz      short loc_1800C650D
0x1800c64f6  test    byte ptr [rcx+1Ch], 8
0x1800c64fa  jz      short loc_1800C650D
0x1800c64fc  mov     edx, 22h ; '"'
0x1800c6501  mov     r8, r13
0x1800c6504  mov     rcx, [rcx+10h]
0x1800c6508  call    WPP_SF_
0x1800c650d  lea     rcx, [rsp+88h+var_60]
0x1800c6512  call    ??1?$com_ptr_t@VConnectionPointContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>::~com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>(void)
0x1800c6517  jmp     loc_1800C6730
0x1800c651c  call    ?Deinit@NetworkClassifier@@SAXXZ; NetworkClassifier::Deinit(void)
0x1800c6521  cmp     cs:?g_isInContainerGuestMode@@3HA, r15d; int g_isInContainerGuestMode
0x1800c6528  jz      short loc_1800C6531
0x1800c652a  call    ?Deinit@KryptonHostSharedContainerManager@@SAXXZ; KryptonHostSharedContainerManager::Deinit(void)
0x1800c652f  jmp     short loc_1800C6536
0x1800c6531  call    ?Deinit@KryptonHostManager@@SAXXZ; KryptonHostManager::Deinit(void)
0x1800c6536  call    ?Deinit@TlsAuthentication@@SAXXZ; TlsAuthentication::Deinit(void)
0x1800c653b  call    ?Deinit@InterfaceIdentifier@@SAXXZ; InterfaceIdentifier::Deinit(void)
0x1800c6540  call    ?Deinit@IgdResolver@@SAXXZ; IgdResolver::Deinit(void)
0x1800c6545  call    ?Deinit@L3Manager@@SAXXZ; L3Manager::Deinit(void)
0x1800c654a  call    ?Deinit@L2Manager@@SAXXZ; L2Manager::Deinit(void)
0x1800c654f  call    ?Deinit@NlmDomain@@SAXXZ; NlmDomain::Deinit(void)
0x1800c6554  call    ?Deinit@SignatureGenerator@NlmSignatures@@SAXXZ; NlmSignatures::SignatureGenerator::Deinit(void)
0x1800c6559  call    ?Deinit@PairedWebProbe@@SAXXZ; PairedWebProbe::Deinit(void)
0x1800c655e  call    ?Deinit@ConnectivityAggregator@@SAXXZ; ConnectivityAggregator::Deinit(void)
0x1800c6563  call    ?Deinit@DiagnosticsManager@@SAXXZ; DiagnosticsManager::Deinit(void)
0x1800c6568  call    ?DeinitAndWait@?$Singleton@VStandbyMonitor@1@@details@StandbyMonitor@@SAXXZ; StandbyMonitor::details::Singleton<StandbyMonitor::StandbyMonitor>::DeinitAndWait(void)
0x1800c656d  mov     [rsp+88h+var_60], r15
0x1800c6572  lea     rdx, [rdi+28h]
0x1800c6576  lea     rcx, [rsp+88h+var_60]
0x1800c657b  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800c6580  mov     rcx, [rdi+50h]; this
0x1800c6584  test    rcx, rcx
0x1800c6587  jz      short loc_1800C6597
0x1800c6589  call    ?Terminate@ConnectionPointContainer@@QEAAXXZ; ConnectionPointContainer::Terminate(void)
0x1800c658e  lea     rcx, [rdi+50h]
0x1800c6592  call    ?reset@?$com_ptr_t@VConnectionPointContainer@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>::reset(void)
0x1800c6597  mov     rcx, [rdi+488h]
0x1800c659e  test    rcx, rcx
0x1800c65a1  jz      short loc_1800C65B0
0x1800c65a3  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800c65a9  mov     [rdi+488h], r15
0x1800c65b0  mov     rcx, rdi; this
0x1800c65b3  call    ?CleanupVPNReconnectNotifications@NetworkListManager@@AEAAXXZ; NetworkListManager::CleanupVPNReconnectNotifications(void)
0x1800c65b8  mov     rcx, [rdi+480h]; NotificationHandle
0x1800c65bf  test    rcx, rcx
0x1800c65c2  jz      short loc_1800C65D1
0x1800c65c4  call    cs:__imp_CancelMibChangeNotify2
0x1800c65ca  mov     [rdi+480h], r15
0x1800c65d1  mov     rcx, [rdi+70h]; WaitHandle
0x1800c65d5  test    rcx, rcx
0x1800c65d8  jz      short loc_1800C65E8
0x1800c65da  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800c65de  call    cs:__imp_UnregisterWaitEx
0x1800c65e4  mov     [rdi+70h], r15
0x1800c65e8  cmp     [rdi+68h], r15d
0x1800c65ec  jz      short loc_1800C65FC
0x1800c65ee  mov     rcx, [rdi+60h]
0x1800c65f2  call    cs:__imp_UnregisterGPNotificationInternal
0x1800c65f8  mov     [rdi+68h], r15d
0x1800c65fc  mov     rcx, [rdi+4D8h]; pv
0x1800c6603  test    rcx, rcx
0x1800c6606  jz      short loc_1800C6615
0x1800c6608  call    cs:__imp_CoTaskMemFree
0x1800c660e  mov     [rdi+4D8h], r15
0x1800c6615  mov     rcx, [rdi+60h]; hObject
0x1800c6619  test    rcx, rcx
0x1800c661c  jz      short loc_1800C6628
0x1800c661e  call    cs:__imp_CloseHandle
0x1800c6624  mov     [rdi+60h], r15
0x1800c6628  mov     bl, 4
0x1800c662a  cmp     cs:?g_networkEventAggregator@@3UAggregatorEventMgr@@A, r15; AggregatorEventMgr g_networkEventAggregator
0x1800c6631  jz      short loc_1800C666D
0x1800c6633  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c663a  cmp     rcx, r12
0x1800c663d  jz      short loc_1800C6655
0x1800c663f  test    [rcx+1Ch], bl
0x1800c6642  jz      short loc_1800C6655
0x1800c6644  mov     edx, 23h ; '#'
0x1800c6649  mov     r8, r13
0x1800c664c  mov     rcx, [rcx+10h]
0x1800c6650  call    WPP_SF_
0x1800c6655  mov     ecx, 6
0x1800c665a  call    ?PostNetworkEventToAggregator@NetworkListManager@@SAJW4NpAggregatorEventType@@@Z; NetworkListManager::PostNetworkEventToAggregator(NpAggregatorEventType)
0x1800c665f  xor     edx, edx
0x1800c6661  lea     rcx, ?g_networkEventAggregator@@3UAggregatorEventMgr@@A; AggregatorEventMgr g_networkEventAggregator
0x1800c6668  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x1800c666d  cmp     cs:?g_firewallEventMgr@@3UFirewallEventMgr@@A, r15; FirewallEventMgr g_firewallEventMgr
0x1800c6674  jz      short loc_1800C66BD
0x1800c6676  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c667d  cmp     rcx, r12
0x1800c6680  jz      short loc_1800C6698
0x1800c6682  test    [rcx+1Ch], bl
0x1800c6685  jz      short loc_1800C6698
0x1800c6687  mov     edx, 24h ; '$'
0x1800c668c  mov     r8, r13
0x1800c668f  mov     rcx, [rcx+10h]
0x1800c6693  call    WPP_SF_
  ... truncated ...
```
