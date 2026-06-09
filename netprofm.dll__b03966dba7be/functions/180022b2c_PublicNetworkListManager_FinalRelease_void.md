# PublicNetworkListManager::FinalRelease(void)

- ea: `0x180022b2c`
- end: `0x180023087`
- name: `?FinalRelease@PublicNetworkListManager@@QEAAXXZ`
- size: `1371`
- prototype: `void __fastcall(PublicNetworkListManager *__hidden this)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015760`
- `0x18001587c`

## callees

- `0x180006770`
- `0x180006810`
- `0x1800074e0`
- `0x1800086b0`
- `0x180009184`
- `0x180009d08`
- `0x1800120d0`
- `0x18001f188`
- `0x18001ff00`
- `0x180021bcc`
- `0x180022b2c`
- `0x180026c04`
- `0x180028bb0`
- `0x18002a294`
- `0x18002a74c`
- `0x18002a84c`
- `0x18002a978`
- `0x18002a9b4`
- `0x18002ae28`
- `0x18002f390`
- `0x18002f4e0`
- `0x18002f630`
- `0x18002f780`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022f7f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022f9e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022fbd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022fdc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022ffb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023008`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023015`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023022`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002302f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022f7f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022f9e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022fbd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022fdc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022ffb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023008`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023015`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023022`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002302f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022e92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022eed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022f3f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022e92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022eed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022f3f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022d9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022ebc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022f2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022d9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022ebc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022f2e`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180022be5`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180022d6e`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180022be5`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180022d6e`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180022f51`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180022f51`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PublicNetworkListManager::FinalRelease(PublicNetworkListManager *this)
{
  __int64 v2; // rdx
  int v3; // eax
  __int64 v4; // r8
  int v5; // eax
  __int64 v6; // r8
  int PrivateNetworkListManager; // eax
  __int64 v8; // rcx
  void *v9; // rcx
  struct _RTL_CRITICAL_SECTION *v10; // [rsp+30h] [rbp-30h] BYREF
  __int64 v11; // [rsp+38h] [rbp-28h] BYREF
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+40h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
  ppv = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::GetImpl'::`2'::impl) )
  {
    v12 = 0;
    wil::EnterCriticalSection(&v12, (struct _RTL_CRITICAL_SECTION *)((char *)this + 232));
    *((_BYTE *)this + 276) = 1;
    v10 = 0;
    v11 = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>>::operator=(
      &v11,
      (_QWORD *)this + 25);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>>::operator=(
      (_QWORD *)this + 25,
      &v10);
    if ( v10 )
      UnsubscribeServiceChangeNotifications();
    v2 = *((unsigned int *)this + 68);
    if ( (_DWORD)v2 != -1 )
    {
      v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, LPVOID *))(**((_QWORD **)this + 28) + 40LL))(
             *((_QWORD *)this + 28),
             v2,
             &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b,
             &ppv);
      if ( v3 < 0 )
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xAC, v4, (const char *)(unsigned int)v3);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v12);
    wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(
      &v11,
      0);
    if ( *((_QWORD *)this + 27) )
    {
      v10 = 0;
      wil::EnterCriticalSection(&v10, (struct _RTL_CRITICAL_SECTION *)((char *)this + 616));
      PublicNetworkListManager::PrivateNetworkEventSync::Uninitialize(*((PublicNetworkListManager::PrivateNetworkEventSync **)this
                                                                      + 27));
      if ( *((_DWORD *)this + 164) )
      {
        if ( !ppv )
        {
          v5 = CoCreatePrivateNetworkListManagerInstance(&ppv);
          if ( v5 < 0 )
            wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xC0, v6, (const char *)(unsigned int)v5);
        }
        if ( ppv )
        {
          if ( (*((_BYTE *)this + 656) & 1) != 0
            && (int)PublicNetworkListManager::PrivateNetworkEventSync::UnadviseNotifyNetworkListManagerEvents(
                      *((PublicNetworkListManager::PrivateNetworkEventSync **)this + 27),
                      (struct INetworkListManagerPrivate *)ppv) >= 0 )
          {
            *((_DWORD *)this + 164) &= ~1u;
          }
          if ( (*((_BYTE *)this + 656) & 2) != 0
            && (int)PublicNetworkListManager::PrivateNetworkEventSync::UnadviseNotifyNetworkEvents(
                      *((PublicNetworkListManager::PrivateNetworkEventSync **)this + 27),
                      (struct INetworkListManagerPrivate *)ppv) >= 0 )
          {
            *((_DWORD *)this + 164) &= ~2u;
          }
          if ( (*((_BYTE *)this + 656) & 4) != 0
            && (int)PublicNetworkListManager::PrivateNetworkEventSync::UnadviseNotifyNetworkInterfaceEvents(
                      *((PublicNetworkListManager::PrivateNetworkEventSync **)this + 27),
                      (struct INetworkListManagerPrivate *)ppv) >= 0 )
          {
            *((_DWORD *)this + 164) &= ~4u;
          }
          if ( (*((_BYTE *)this + 656) & 8) != 0
            && (int)PublicNetworkListManager::PrivateNetworkEventSync::UnadviseNotifyNetworkGlobalCostEvents(
                      *((PublicNetworkListManager::PrivateNetworkEventSync **)this + 27),
                      (struct INetworkListManagerPrivate *)ppv) >= 0 )
          {
            *((_DWORD *)this + 164) &= ~8u;
          }
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
        &v10,
        0);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 27) + 16LL))(*((_QWORD *)this + 27));
      *((_QWORD *)this + 27) = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v10);
    }
    if ( v11 )
      UnsubscribeServiceChangeNotifications();
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(
      (char *)this + 200,
      0);
    if ( *((_QWORD *)this + 27) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 616));
      PublicNetworkListManager::PrivateNetworkEventSync::Uninitialize(*((PublicNetworkListManager::PrivateNetworkEventSync **)this
                                                                      + 27));
      if ( *((_DWORD *)this + 164) )
      {
        PrivateNetworkListManager = PublicNetworkListManager::GetPrivateNetworkListManager(
                                      this,
                                      (struct INetworkListManagerPrivate **)&ppv);
        if ( PrivateNetworkListManager < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
            (unsigned int)PrivateNetworkListManager);
        }
        if ( ppv )
        {
          if ( (*((_BYTE *)this + 656) & 1) != 0
            && (int)PublicNetworkListManager::PrivateNetworkEventSync::UnadviseNotifyNetworkListManagerEvents(
                      *((PublicNetworkListManager::PrivateNetworkEventSync **)this + 27),
                      (struct INetworkListManagerPrivate *)ppv) >= 0 )
          {
            *((_DWORD *)this + 164) &= ~1u;
          }
          if ( (*((_BYTE *)this + 656) & 2) != 0
            && (int)PublicNetworkListManager::PrivateNetworkEventSync::UnadviseNotifyNetworkEvents(
                      *((PublicNetworkListManager::PrivateNetworkEventSync **)this + 27),
                      (struct INetworkListManagerPrivate *)ppv) >= 0 )
          {
            *((_DWORD *)this + 164) &= ~2u;
          }
          if ( (*((_BYTE *)this + 656) & 4) != 0
            && (int)PublicNetworkListManager::PrivateNetworkEventSync::UnadviseNotifyNetworkInterfaceEvents(
                      *((PublicNetworkListManager::PrivateNetworkEventSync **)this + 27),
                      (struct INetworkListManagerPrivate *)ppv) >= 0 )
          {
            *((_DWORD *)this + 164) &= ~4u;
          }
          if ( (*((_BYTE *)this + 656) & 8) != 0
            && (int)PublicNetworkListManager::PrivateNetworkEventSync::UnadviseNotifyNetworkGlobalCostEvents(
                      *((PublicNetworkListManager::PrivateNetworkEventSync **)this + 27),
                      (struct INetworkListManagerPrivate *)ppv) >= 0 )
          {
            *((_DWORD *)this + 164) &= ~8u;
          }
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 616));
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 27) + 16LL))(*((_QWORD *)this + 27));
      *((_QWORD *)this + 27) = 0;
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  if ( *((_DWORD *)this + 68) != -1 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 28) + 32LL))(*((_QWORD *)this + 28));
    *((_DWORD *)this + 68) = -1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  v8 = *((_QWORD *)this + 28);
  if ( v8 )
  {
    *((_QWORD *)this + 28) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl'::`2'::impl) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)this + 14);
    PublicNetworkListManager::ClearAddressInterfaceListNoLock(this);
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 14);
  }
  v9 = (void *)*((_QWORD *)this + 97);
  if ( v9 )
  {
    CancelMibChangeNotify2(v9);
    *((_QWORD *)this + 97) = 0;
  }
  PublicNetworkListManager::TerminateIpHlpEventMgr(this);
  PublicNetworkListManager::RemoveGITAndRegistrationOnAllCookies((char *)this + 320, (char *)this + 280);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 7);
  PublicNetworkListManager::RemoveGITAndRegistrationOnAllCookies((char *)this + 376, (char *)this + 336);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  PublicNetworkListManager::RemoveGITAndRegistrationOnAllCookies((char *)this + 432, (char *)this + 392);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 392));
  PublicNetworkListManager::RemoveGITAndRegistrationOnAllCookies((char *)this + 544, (char *)this + 504);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 504));
  PublicNetworkListManager::RemoveGITAndRegistrationOnAllCookies((char *)this + 488, (char *)this + 448);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 448));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 14);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 664));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 616));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
}

```

## disassembly

```asm
0x180022b2c  mov     [rsp-18h+arg_8], rbx
0x180022b31  mov     [rsp-18h+arg_10], rsi
0x180022b36  push    rbp
0x180022b37  push    rdi
0x180022b38  push    r13
0x180022b3a  mov     rbp, rsp
0x180022b3d  sub     rsp, 60h
0x180022b41  mov     rax, cs:__security_cookie
0x180022b48  xor     rax, rsp
0x180022b4b  mov     [rbp+var_10], rax
0x180022b4f  mov     rdi, rcx
0x180022b52  lea     r13, WPP_GLOBAL_Control
0x180022b59  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b60  cmp     rcx, r13
0x180022b63  jz      short loc_180022B80
0x180022b65  test    byte ptr [rcx+1Ch], 8
0x180022b69  jz      short loc_180022B80
0x180022b6b  mov     edx, 0Eh
0x180022b70  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180022b77  mov     rcx, [rcx+10h]
0x180022b7b  call    WPP_SF_
0x180022b80  xor     esi, esi
0x180022b82  mov     [rbp+ppv], rsi
0x180022b86  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::GetImpl(void)'::`2'::impl
0x180022b8d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::__private_IsEnabled(void)
0x180022b92  test    al, al
0x180022b94  jz      loc_180022D79
0x180022b9a  lea     rbx, [rdi+0C8h]
0x180022ba1  mov     [rbp+var_20], rsi
0x180022ba5  lea     rdx, [rdi+0E8h]
0x180022bac  lea     rcx, [rbp+var_20]
0x180022bb0  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180022bb5  mov     byte ptr [rdi+114h], 1
0x180022bbc  mov     [rbp+var_30], rsi
0x180022bc0  mov     [rbp+var_28], rsi
0x180022bc4  mov     rdx, rbx
0x180022bc7  lea     rcx, [rbp+var_28]
0x180022bcb  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>> &&)
0x180022bd0  lea     rdx, [rbp+var_30]
0x180022bd4  mov     rcx, rbx
0x180022bd7  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>> &&)
0x180022bdc  mov     rcx, [rbp+var_30]
0x180022be0  test    rcx, rcx
0x180022be3  jz      short loc_180022BEB
0x180022be5  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x180022beb  mov     edx, [rdi+110h]
0x180022bf1  cmp     edx, 0FFFFFFFFh
0x180022bf4  jz      short loc_180022C29
0x180022bf6  mov     rcx, [rdi+0E0h]
0x180022bfd  mov     rax, [rcx]
0x180022c00  lea     r9, [rbp+ppv]
0x180022c04  lea     r8, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b
0x180022c0b  mov     rax, [rax+28h]
0x180022c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c14  mov     rcx, [rbp+18h]; this
0x180022c18  test    eax, eax
0x180022c1a  jns     short loc_180022C29
0x180022c1c  mov     r9d, eax; char *
0x180022c1f  mov     edx, 0ACh; void *
0x180022c24  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022c29  lea     rcx, [rbp+var_20]
0x180022c2d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180022c32  xor     edx, edx
0x180022c34  lea     rcx, [rbp+var_28]
0x180022c38  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SC_NOTIFICATION_REGISTRATION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(_SC_NOTIFICATION_REGISTRATION *)
0x180022c3d  cmp     [rdi+0D8h], rsi
0x180022c44  jz      loc_180022D61
0x180022c4a  mov     [rbp+var_30], rsi
0x180022c4e  lea     rdx, [rdi+268h]
0x180022c55  lea     rcx, [rbp+var_30]
0x180022c59  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180022c5e  mov     rcx, [rdi+0D8h]; this
0x180022c65  call    ?Uninitialize@PrivateNetworkEventSync@PublicNetworkListManager@@QEAAXXZ; PublicNetworkListManager::PrivateNetworkEventSync::Uninitialize(void)
0x180022c6a  cmp     [rdi+290h], esi
0x180022c70  jz      loc_180022D33
0x180022c76  cmp     [rbp+ppv], rsi
0x180022c7a  jnz     short loc_180022C9A
0x180022c7c  lea     rcx, [rbp+ppv]; ppv
0x180022c80  call    CoCreatePrivateNetworkListManagerInstance
0x180022c85  mov     rcx, [rbp+18h]; this
0x180022c89  test    eax, eax
0x180022c8b  jns     short loc_180022C9A
0x180022c8d  mov     r9d, eax; char *
0x180022c90  mov     edx, 0C0h; void *
0x180022c95  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022c9a  mov     rdx, [rbp+ppv]; struct INetworkListManagerPrivate *
0x180022c9e  test    rdx, rdx
0x180022ca1  jz      loc_180022D33
0x180022ca7  test    byte ptr [rdi+290h], 1
0x180022cae  jz      short loc_180022CC7
0x180022cb0  mov     rcx, [rdi+0D8h]; this
0x180022cb7  call    ?UnadviseNotifyNetworkListManagerEvents@PrivateNetworkEventSync@PublicNetworkListManager@@QEAAJPEAUINetworkListManagerPrivate@@@Z; PublicNetworkListManager::PrivateNetworkEventSync::UnadviseNotifyNetworkListManagerEvents(INetworkListManagerPrivate *)
0x180022cbc  test    eax, eax
0x180022cbe  js      short loc_180022CC7
0x180022cc0  and     dword ptr [rdi+290h], 0FFFFFFFEh
0x180022cc7  test    byte ptr [rdi+290h], 2
0x180022cce  jz      short loc_180022CEB
0x180022cd0  mov     rdx, [rbp+ppv]; struct INetworkListManagerPrivate *
0x180022cd4  mov     rcx, [rdi+0D8h]; this
0x180022cdb  call    ?UnadviseNotifyNetworkEvents@PrivateNetworkEventSync@PublicNetworkListManager@@QEAAJPEAUINetworkListManagerPrivate@@@Z; PublicNetworkListManager::PrivateNetworkEventSync::UnadviseNotifyNetworkEvents(INetworkListManagerPrivate *)
0x180022ce0  test    eax, eax
0x180022ce2  js      short loc_180022CEB
0x180022ce4  and     dword ptr [rdi+290h], 0FFFFFFFDh
0x180022ceb  test    byte ptr [rdi+290h], 4
0x180022cf2  jz      short loc_180022D0F
0x180022cf4  mov     rdx, [rbp+ppv]; struct INetworkListManagerPrivate *
0x180022cf8  mov     rcx, [rdi+0D8h]; this
0x180022cff  call    ?UnadviseNotifyNetworkInterfaceEvents@PrivateNetworkEventSync@PublicNetworkListManager@@QEAAJPEAUINetworkListManagerPrivate@@@Z; PublicNetworkListManager::PrivateNetworkEventSync::UnadviseNotifyNetworkInterfaceEvents(INetworkListManagerPrivate *)
0x180022d04  test    eax, eax
0x180022d06  js      short loc_180022D0F
0x180022d08  and     dword ptr [rdi+290h], 0FFFFFFFBh
0x180022d0f  test    byte ptr [rdi+290h], 8
0x180022d16  jz      short loc_180022D33
0x180022d18  mov     rdx, [rbp+ppv]; struct INetworkListManagerPrivate *
0x180022d1c  mov     rcx, [rdi+0D8h]; this
0x180022d23  call    ?UnadviseNotifyNetworkGlobalCostEvents@PrivateNetworkEventSync@PublicNetworkListManager@@QEAAJPEAUINetworkListManagerPrivate@@@Z; PublicNetworkListManager::PrivateNetworkEventSync::UnadviseNotifyNetworkGlobalCostEvents(INetworkListManagerPrivate *)
0x180022d28  test    eax, eax
0x180022d2a  js      short loc_180022D33
0x180022d2c  and     dword ptr [rdi+290h], 0FFFFFFF7h
0x180022d33  xor     edx, edx
0x180022d35  lea     rcx, [rbp+var_30]
0x180022d39  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x180022d3e  mov     rcx, [rdi+0D8h]
0x180022d45  mov     rax, [rcx]
0x180022d48  mov     rax, [rax+10h]
0x180022d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d51  mov     [rdi+0D8h], rsi
0x180022d58  lea     rcx, [rbp+var_30]
0x180022d5c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180022d61  mov     rcx, [rbp+var_28]
0x180022d65  test    rcx, rcx
0x180022d68  jz      loc_180022EB2
0x180022d6e  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x180022d74  jmp     loc_180022EB2
0x180022d79  lea     rcx, [rdi+0C8h]
0x180022d80  xor     edx, edx
0x180022d82  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SC_NOTIFICATION_REGISTRATION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(_SC_NOTIFICATION_REGISTRATION *)
0x180022d87  cmp     [rdi+0D8h], rsi
0x180022d8e  jz      loc_180022EB2
0x180022d94  lea     rbx, [rdi+268h]
0x180022d9b  mov     rcx, rbx; lpCriticalSection
0x180022d9e  call    cs:__imp_EnterCriticalSection
0x180022da4  mov     rcx, [rdi+0D8h]; this
0x180022dab  call    ?Uninitialize@PrivateNetworkEventSync@PublicNetworkListManager@@QEAAXXZ; PublicNetworkListManager::PrivateNetworkEventSync::Uninitialize(void)
0x180022db0  cmp     [rdi+290h], esi
0x180022db6  jz      loc_180022E8F
0x180022dbc  lea     rdx, [rbp+ppv]; struct INetworkListManagerPrivate **
0x180022dc0  mov     rcx, rdi; this
0x180022dc3  call    ?GetPrivateNetworkListManager@PublicNetworkListManager@@QEAAJPEAPEAUINetworkListManagerPrivate@@@Z; PublicNetworkListManager::GetPrivateNetworkListManager(INetworkListManagerPrivate * *)
0x180022dc8  test    eax, eax
0x180022dca  jns     short loc_180022DF6
0x180022dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180022dd3  cmp     rcx, r13
0x180022dd6  jz      short loc_180022DF6
0x180022dd8  test    byte ptr [rcx+1Ch], 8
0x180022ddc  jz      short loc_180022DF6
0x180022dde  mov     edx, 0Fh
0x180022de3  mov     r9d, eax
0x180022de6  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180022ded  mov     rcx, [rcx+10h]
0x180022df1  call    WPP_SF_d
0x180022df6  mov     rdx, [rbp+ppv]; struct INetworkListManagerPrivate *
0x180022dfa  test    rdx, rdx
0x180022dfd  jz      loc_180022E8F
0x180022e03  test    byte ptr [rdi+290h], 1
0x180022e0a  jz      short loc_180022E23
0x180022e0c  mov     rcx, [rdi+0D8h]; this
0x180022e13  call    ?UnadviseNotifyNetworkListManagerEvents@PrivateNetworkEventSync@PublicNetworkListManager@@QEAAJPEAUINetworkListManagerPrivate@@@Z; PublicNetworkListManager::PrivateNetworkEventSync::UnadviseNotifyNetworkListManagerEvents(INetworkListManagerPrivate *)
0x180022e18  test    eax, eax
0x180022e1a  js      short loc_180022E23
0x180022e1c  and     dword ptr [rdi+290h], 0FFFFFFFEh
0x180022e23  test    byte ptr [rdi+290h], 2
0x180022e2a  jz      short loc_180022E47
0x180022e2c  mov     rdx, [rbp+ppv]; struct INetworkListManagerPrivate *
0x180022e30  mov     rcx, [rdi+0D8h]; this
0x180022e37  call    ?UnadviseNotifyNetworkEvents@PrivateNetworkEventSync@PublicNetworkListManager@@QEAAJPEAUINetworkListManagerPrivate@@@Z; PublicNetworkListManager::PrivateNetworkEventSync::UnadviseNotifyNetworkEvents(INetworkListManagerPrivate *)
0x180022e3c  test    eax, eax
0x180022e3e  js      short loc_180022E47
0x180022e40  and     dword ptr [rdi+290h], 0FFFFFFFDh
0x180022e47  test    byte ptr [rdi+290h], 4
0x180022e4e  jz      short loc_180022E6B
0x180022e50  mov     rdx, [rbp+ppv]; struct INetworkListManagerPrivate *
0x180022e54  mov     rcx, [rdi+0D8h]; this
0x180022e5b  call    ?UnadviseNotifyNetworkInterfaceEvents@PrivateNetworkEventSync@PublicNetworkListManager@@QEAAJPEAUINetworkListManagerPrivate@@@Z; PublicNetworkListManager::PrivateNetworkEventSync::UnadviseNotifyNetworkInterfaceEvents(INetworkListManagerPrivate *)
0x180022e60  test    eax, eax
0x180022e62  js      short loc_180022E6B
0x180022e64  and     dword ptr [rdi+290h], 0FFFFFFFBh
0x180022e6b  test    byte ptr [rdi+290h], 8
0x180022e72  jz      short loc_180022E8F
0x180022e74  mov     rdx, [rbp+ppv]; struct INetworkListManagerPrivate *
0x180022e78  mov     rcx, [rdi+0D8h]; this
0x180022e7f  call    ?UnadviseNotifyNetworkGlobalCostEvents@PrivateNetworkEventSync@PublicNetworkListManager@@QEAAJPEAUINetworkListManagerPrivate@@@Z; PublicNetworkListManager::PrivateNetworkEventSync::UnadviseNotifyNetworkGlobalCostEvents(INetworkListManagerPrivate *)
0x180022e84  test    eax, eax
0x180022e86  js      short loc_180022E8F
0x180022e88  and     dword ptr [rdi+290h], 0FFFFFFF7h
0x180022e8f  mov     rcx, rbx; lpCriticalSection
0x180022e92  call    cs:__imp_LeaveCriticalSection
0x180022e98  mov     rcx, [rdi+0D8h]
0x180022e9f  mov     rax, [rcx]
0x180022ea2  mov     rax, [rax+10h]
0x180022ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022eab  mov     [rdi+0D8h], rsi
0x180022eb2  lea     rbx, [rdi+0E8h]
0x180022eb9  mov     rcx, rbx; lpCriticalSection
0x180022ebc  call    cs:__imp_EnterCriticalSection
0x180022ec2  mov     edx, [rdi+110h]
0x180022ec8  cmp     edx, 0FFFFFFFFh
0x180022ecb  jz      short loc_180022EEA
0x180022ecd  mov     rcx, [rdi+0E0h]
0x180022ed4  mov     rax, [rcx]
0x180022ed7  mov     rax, [rax+20h]
0x180022edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ee0  mov     dword ptr [rdi+110h], 0FFFFFFFFh
0x180022eea  mov     rcx, rbx; lpCriticalSection
0x180022eed  call    cs:__imp_LeaveCriticalSection
0x180022ef3  nop
0x180022ef4  mov     rcx, [rdi+0E0h]
0x180022efb  test    rcx, rcx
0x180022efe  jz      short loc_180022F14
0x180022f00  mov     [rdi+0E0h], rsi
0x180022f07  mov     rax, [rcx]
0x180022f0a  mov     rax, [rax+10h]
0x180022f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f13  nop
0x180022f14  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl(void)'::`2'::impl
0x180022f1b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(void)
0x180022f20  test    al, al
0x180022f22  jnz     short loc_180022F45
0x180022f24  lea     rbx, [rdi+230h]
0x180022f2b  mov     rcx, rbx; lpCriticalSection
0x180022f2e  call    cs:__imp_EnterCriticalSection
0x180022f34  mov     rcx, rdi; this
0x180022f37  call    ?ClearAddressInterfaceListNoLock@PublicNetworkListManager@@AEAAXXZ; PublicNetworkListManager::ClearAddressInterfaceListNoLock(void)
0x180022f3c  mov     rcx, rbx; lpCriticalSection
0x180022f3f  call    cs:__imp_LeaveCriticalSection
0x180022f45  mov     rcx, [rdi+308h]; NotificationHandle
0x180022f4c  test    rcx, rcx
0x180022f4f  jz      short loc_180022F5E
0x180022f51  call    cs:__imp_CancelMibChangeNotify2
0x180022f57  mov     [rdi+308h], rsi
0x180022f5e  mov     rcx, rdi; this
0x180022f61  call    ?TerminateIpHlpEventMgr@PublicNetworkListManager@@AEAAXXZ; PublicNetworkListManager::TerminateIpHlpEventMgr(void)
0x180022f66  lea     rbx, [rdi+118h]
0x180022f6d  lea     rcx, [rdi+140h]
0x180022f74  mov     rdx, rbx
0x180022f77  call    ?RemoveGITAndRegistrationOnAllCookies@PublicNetworkListManager@@CAXPEAV?$map@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@@std@@PEAU_RTL_CRITICAL_SECTION@@@Z; PublicNetworkListManager::RemoveGITAndRegistrationOnAllCookies(std::map<ulong,CLIENT_CALLBACK_INTERFACE> *,_RTL_CRITICAL_SECTION *)
0x180022f7c  mov     rcx, rbx; lpCriticalSection
0x180022f7f  call    cs:__imp_DeleteCriticalSection
0x180022f85  lea     rbx, [rdi+150h]
0x180022f8c  lea     rcx, [rdi+178h]
0x180022f93  mov     rdx, rbx
0x180022f96  call    ?RemoveGITAndRegistrationOnAllCookies@PublicNetworkListManager@@CAXPEAV?$map@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@@std@@PEAU_RTL_CRITICAL_SECTION@@@Z; PublicNetworkListManager::RemoveGITAndRegistrationOnAllCookies(std::map<ulong,CLIENT_CALLBACK_INTERFACE> *,_RTL_CRITICAL_SECTION *)
0x180022f9b  mov     rcx, rbx; lpCriticalSection
0x180022f9e  call    cs:__imp_DeleteCriticalSection
0x180022fa4  lea     rbx, [rdi+188h]
0x180022fab  lea     rcx, [rdi+1B0h]
0x180022fb2  mov     rdx, rbx
0x180022fb5  call    ?RemoveGITAndRegistrationOnAllCookies@PublicNetworkListManager@@CAXPEAV?$map@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@@std@@PEAU_RTL_CRITICAL_SECTION@@@Z; PublicNetworkListManager::RemoveGITAndRegistrationOnAllCookies(std::map<ulong,CLIENT_CALLBACK_INTERFACE> *,_RTL_CRITICAL_SECTION *)
0x180022fba  mov     rcx, rbx; lpCriticalSection
0x180022fbd  call    cs:__imp_DeleteCriticalSection
0x180022fc3  lea     rbx, [rdi+1F8h]
0x180022fca  lea     rcx, [rdi+220h]
0x180022fd1  mov     rdx, rbx
0x180022fd4  call    ?RemoveGITAndRegistrationOnAllCookies@PublicNetworkListManager@@CAXPEAV?$map@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@@std@@PEAU_RTL_CRITICAL_SECTION@@@Z; PublicNetworkListManager::RemoveGITAndRegistrationOnAllCookies(std::map<ulong,CLIENT_CALLBACK_INTERFACE> *,_RTL_CRITICAL_SECTION *)
0x180022fd9  mov     rcx, rbx; lpCriticalSection
0x180022fdc  call    cs:__imp_DeleteCriticalSection
0x180022fe2  lea     rbx, [rdi+1C0h]
0x180022fe9  lea     rcx, [rdi+1E8h]
0x180022ff0  mov     rdx, rbx
0x180022ff3  call    ?RemoveGITAndRegistrationOnAllCookies@PublicNetworkListManager@@CAXPEAV?$map@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@@std@@PEAU_RTL_CRITICAL_SECTION@@@Z; PublicNetworkListManager::RemoveGITAndRegistrationOnAllCookies(std::map<ulong,CLIENT_CALLBACK_INTERFACE> *,_RTL_CRITICAL_SECTION *)
0x180022ff8  mov     rcx, rbx; lpCriticalSection
0x180022ffb  call    cs:__imp_DeleteCriticalSection
0x180023001  lea     rcx, [rdi+230h]; lpCriticalSection
0x180023008  call    cs:__imp_DeleteCriticalSection
0x18002300e  lea     rcx, [rdi+298h]; lpCriticalSection
0x180023015  call    cs:__imp_DeleteCriticalSection
0x18002301b  lea     rcx, [rdi+0E8h]; lpCriticalSection
0x180023022  call    cs:__imp_DeleteCriticalSection
0x180023028  lea     rcx, [rdi+268h]; lpCriticalSection
0x18002302f  call    cs:__imp_DeleteCriticalSection
0x180023035  mov     rcx, cs:WPP_GLOBAL_Control
0x18002303c  cmp     rcx, r13
0x18002303f  jz      short loc_18002305C
0x180023041  test    byte ptr [rcx+1Ch], 8
0x180023045  jz      short loc_18002305C
0x180023047  mov     edx, 10h
0x18002304c  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180023053  mov     rcx, [rcx+10h]
0x180023057  call    WPP_SF_
0x18002305c  lea     rcx, [rbp+ppv]
0x180023060  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180023065  nop
0x180023066  mov     rcx, [rbp+var_10]
0x18002306a  xor     rcx, rsp; StackCookie
0x18002306d  call    __security_check_cookie
0x180023072  lea     r11, [rsp+60h+var_s0]
0x180023077  mov     rbx, [r11+28h]
0x18002307b  mov     rsi, [r11+30h]
0x18002307f  mov     rsp, r11
0x180023082  pop     r13
  ... truncated ...
```
