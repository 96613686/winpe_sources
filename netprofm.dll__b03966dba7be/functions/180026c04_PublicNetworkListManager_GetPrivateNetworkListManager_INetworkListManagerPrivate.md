# PublicNetworkListManager::GetPrivateNetworkListManager(INetworkListManagerPrivate * *)

- ea: `0x180026c04`
- end: `0x180027166`
- name: `?GetPrivateNetworkListManager@PublicNetworkListManager@@QEAAJPEAPEAUINetworkListManagerPrivate@@@Z`
- size: `1378`
- prototype: `__int64 __fastcall(PublicNetworkListManager *__hidden this, struct INetworkListManagerPrivate **)`
- caller_count: `29`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180020120`
- `0x180022b2c`
- `0x180024410`
- `0x1800245a0`
- `0x1800251b0`
- `0x1800262d0`
- `0x180026460`
- `0x180026644`
- `0x1800268f0`
- `0x180026a80`
- `0x1800272f0`
- `0x180027630`
- `0x1800277e0`
- `0x180027900`
- `0x180027ab0`
- `0x180027bd0`
- `0x180027e10`
- `0x180027f80`
- `0x180028130`
- `0x180028250`
- `0x180028400`
- `0x180029678`
- `0x180029e70`
- `0x18002ab50`
- `0x18002acc0`
- `0x18002d580`
- `0x18002d6ec`
- `0x18002d858`
- `0x18002d9c4`

## callees

- `0x180001084`
- `0x1800011a0`
- `0x180006770`
- `0x180006810`
- `0x1800074e0`
- `0x180007540`
- `0x1800086b0`
- `0x1800086e0`
- `0x180008a7c`
- `0x180008b60`
- `0x180009184`
- `0x180009d08`
- `0x18000a078`
- `0x1800120d0`
- `0x18001f150`
- `0x180021bcc`
- `0x180026c04`
- `0x18002a9b4`
- `0x18002ae28`
- `0x18002aed0`
- `0x180033a1c`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027004`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027004`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026eb8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026eb8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180026e0b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180026f65`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180026e0b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180026f65`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180026ddb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180026f35`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180026ddb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180026f35`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180026e4c`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180026fa6`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180026e4c`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180026fa6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027095`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027095`

## string_xrefs

- `0x180026e5d`: `onecore\net\netprofiles\service\src\public\lib\networklistmanagerimpl.cpp`
- `0x180026fb7`: `onecore\net\netprofiles\service\src\public\lib\networklistmanagerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PublicNetworkListManager::GetPrivateNetworkListManager(
        PublicNetworkListManager *this,
        struct INetworkListManagerPrivate **a2)
{
  HRESULT v4; // edi
  _DWORD *v5; // r14
  struct _RTL_CRITICAL_SECTION **v7; // rax
  SC_HANDLE v8; // rbx
  unsigned int v9; // r8d
  const char *v10; // r9
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  unsigned int v12; // r8d
  const char *v13; // r9
  unsigned int v14; // eax
  SC_HANDLE v15; // rbx
  unsigned int v16; // r8d
  const char *v17; // r9
  struct _RTL_CRITICAL_SECTION *v18; // rbx
  unsigned int v19; // r8d
  const char *v20; // r9
  unsigned int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // [rsp+30h] [rbp-40h] BYREF
  struct _RTL_CRITICAL_SECTION *v26; // [rsp+38h] [rbp-38h] BYREF
  struct INetworkListManagerPrivate **v27; // [rsp+40h] [rbp-30h]
  LPVOID ppv; // [rsp+48h] [rbp-28h] BYREF
  __int128 Parameter; // [rsp+50h] [rbp-20h] BYREF
  __int64 v30; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v27 = a2;
  v4 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
  *a2 = 0;
  v5 = (_DWORD *)((char *)this + 272);
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::GetImpl'::`2'::impl) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    if ( *v5 != -1 )
    {
LABEL_39:
      if ( !*((_QWORD *)this + 25) )
      {
        v15 = OpenSCManagerW(0, 0, 5u);
        ppv = v15;
        if ( !v15 )
          wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x336, v16, v17);
        v18 = (struct _RTL_CRITICAL_SECTION *)OpenServiceW(v15, L"netprofm", 4u);
        v25 = (__int64)v18;
        if ( !v18 )
          wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x339, v19, v20);
        wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(
          (char *)this + 200,
          0);
        v21 = SubscribeServiceChangeNotifications(v18, 2, PublicNetworkListManager::NLMServiceStateChangeCallback, this);
        if ( v21 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x33C,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\networklistmanagerimpl.cpp",
            (const char *)v21,
            (_DWORD)this + 200);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>((SC_HANDLE *)&v25);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>((SC_HANDLE *)&ppv);
      }
      if ( v4 >= 0 )
        v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, struct INetworkListManagerPrivate **))(**((_QWORD **)this + 28) + 40LL))(
               *((_QWORD *)this + 28),
               (unsigned int)*v5,
               &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b,
               v27);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
      goto LABEL_50;
    }
    ppv = 0;
    if ( (unsigned int)IsSystemSetupInProgress() )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v4 = -2147023834;
    }
    else
    {
      Parameter = 0;
      v30 = 0;
      CRPCTimeout::CRPCTimeout(&Parameter);
      v4 = CoCreateInstance(&CLSID_CNetworkListManager, 0, 4u, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, &ppv);
      if ( BYTE4(Parameter)
        && (unsigned int)dword_18005F140 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18005F140, 0x400000000000LL) )
      {
        v25 = 2048;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
          v22,
          (int)byte_180055E51,
          v23,
          v24,
          (__int64)&v25);
      }
      CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
      if ( v4 >= 0 )
      {
        *((_BYTE *)this + 208) = 1;
        v4 = (*(__int64 (__fastcall **)(_QWORD, LPVOID, GUID *, char *))(**((_QWORD **)this + 28) + 24LL))(
               *((_QWORD *)this + 28),
               ppv,
               &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b,
               (char *)this + 272);
        if ( v4 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              22,
              &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
              (unsigned int)v4);
          *v5 = -1;
        }
        goto LABEL_38;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
        (unsigned int)v4);
LABEL_38:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
    goto LABEL_39;
  }
  v26 = 0;
  wil::EnterCriticalSection(&v26, (struct _RTL_CRITICAL_SECTION *)((char *)this + 232));
  if ( *((_BYTE *)this + 276) )
  {
LABEL_6:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v26);
    return 2147943515LL;
  }
  if ( *v5 == -1 )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
      &v26,
      0);
    ppv = 0;
    v4 = CoCreatePrivateNetworkListManagerInstance(&ppv);
    v7 = wil::EnterCriticalSection(
           (struct _RTL_CRITICAL_SECTION **)&v25,
           (struct _RTL_CRITICAL_SECTION *)((char *)this + 232));
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(
      &v26,
      v7);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>((struct _RTL_CRITICAL_SECTION **)&v25);
    if ( *((_BYTE *)this + 276) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
      goto LABEL_6;
    }
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
          (unsigned int)v4);
    }
    else
    {
      *((_BYTE *)this + 208) = 1;
      if ( *v5 == -1 )
      {
        v4 = (*(__int64 (__fastcall **)(_QWORD, LPVOID, GUID *, char *))(**((_QWORD **)this + 28) + 24LL))(
               *((_QWORD *)this + 28),
               ppv,
               &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b,
               (char *)this + 272);
        if ( v4 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              20,
              &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
              (unsigned int)v4);
          *v5 = -1;
        }
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  }
  if ( !*((_QWORD *)this + 25) )
  {
    v8 = OpenSCManagerW(0, 0, 5u);
    ppv = v8;
    if ( !v8 )
      wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x2EF, v9, v10);
    v11 = (struct _RTL_CRITICAL_SECTION *)OpenServiceW(v8, L"netprofm", 4u);
    v25 = (__int64)v11;
    if ( !v11 )
      wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x2F2, v12, v13);
    wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(
      (char *)this + 200,
      0);
    v14 = SubscribeServiceChangeNotifications(v11, 2, PublicNetworkListManager::NLMServiceStateChangeCallback, this);
    if ( v14 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x2F5,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\networklistmanagerimpl.cpp",
        (const char *)v14,
        (_DWORD)this + 200);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>((SC_HANDLE *)&v25);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>((SC_HANDLE *)&ppv);
  }
  if ( v4 >= 0 )
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, struct INetworkListManagerPrivate **))(**((_QWORD **)this + 28)
                                                                                                 + 40LL))(
           *((_QWORD *)this + 28),
           (unsigned int)*v5,
           &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b,
           v27);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v26);
LABEL_50:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
      (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180026c04  mov     [rsp-28h+arg_10], rbx
0x180026c09  mov     [rsp-28h+arg_18], rsi
0x180026c0e  push    rbp
0x180026c0f  push    rdi
0x180026c10  push    r12
0x180026c12  push    r14
0x180026c14  push    r15
0x180026c16  mov     rbp, rsp
0x180026c19  sub     rsp, 70h
0x180026c1d  mov     rax, cs:__security_cookie
0x180026c24  xor     rax, rsp
0x180026c27  mov     [rbp+var_8], rax
0x180026c2b  mov     rbx, rdx
0x180026c2e  mov     [rbp+var_30], rdx
0x180026c32  mov     rsi, rcx
0x180026c35  xor     r15d, r15d
0x180026c38  mov     edi, r15d
0x180026c3b  lea     rax, WPP_GLOBAL_Control
0x180026c42  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c49  cmp     rcx, rax
0x180026c4c  jz      short loc_180026C68
0x180026c4e  test    byte ptr [rcx+1Ch], 8
0x180026c52  jz      short loc_180026C68
0x180026c54  lea     edx, [r15+13h]
0x180026c58  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180026c5f  mov     rcx, [rcx+10h]
0x180026c63  call    WPP_SF_
0x180026c68  mov     [rbx], r15
0x180026c6b  lea     r12, [rsi+0E8h]
0x180026c72  lea     r14, [rsi+110h]
0x180026c79  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::GetImpl(void)'::`2'::impl
0x180026c80  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::__private_IsEnabled(void)
0x180026c85  test    al, al
0x180026c87  jz      loc_180026EB5
0x180026c8d  mov     [rbp+var_38], r15
0x180026c91  mov     rdx, r12
0x180026c94  lea     rcx, [rbp+var_38]
0x180026c98  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180026c9d  nop
0x180026c9e  cmp     [r14+4], r15b
0x180026ca2  jz      short loc_180026CB7
0x180026ca4  lea     rcx, [rbp+var_38]
0x180026ca8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180026cad  mov     eax, 8007045Bh
0x180026cb2  jmp     loc_18002703D
0x180026cb7  or      ebx, 0FFFFFFFFh
0x180026cba  cmp     [r14], ebx
0x180026cbd  jnz     loc_180026DC2
0x180026cc3  xor     edx, edx
0x180026cc5  lea     rcx, [rbp+var_38]
0x180026cc9  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x180026cce  mov     [rbp+var_28], r15
0x180026cd2  lea     rcx, [rbp+var_28]; ppv
0x180026cd6  call    CoCreatePrivateNetworkListManagerInstance
0x180026cdb  mov     edi, eax
0x180026cdd  mov     rdx, r12
0x180026ce0  lea     rcx, [rbp+var_40]
0x180026ce4  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180026ce9  mov     rdx, rax
0x180026cec  lea     rcx, [rbp+var_38]
0x180026cf0  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> &&)
0x180026cf5  lea     rcx, [rbp+var_40]
0x180026cf9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180026cfe  cmp     [rsi+114h], r15b
0x180026d05  jz      short loc_180026D12
0x180026d07  lea     rcx, [rbp+var_28]
0x180026d0b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180026d10  jmp     short loc_180026CA4
0x180026d12  test    edi, edi
0x180026d14  js      short loc_180026D87
0x180026d16  mov     eax, 1
0x180026d1b  xchg    al, [rsi+0D0h]
0x180026d21  cmp     [r14], ebx
0x180026d24  jnz     loc_180026DB9
0x180026d2a  mov     rcx, [rsi+0E0h]
0x180026d31  mov     rax, [rcx]
0x180026d34  mov     r9, r14
0x180026d37  lea     r8, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b
0x180026d3e  mov     rdx, [rbp+var_28]
0x180026d42  mov     rax, [rax+18h]
0x180026d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d4b  mov     edi, eax
0x180026d4d  test    eax, eax
0x180026d4f  jns     short loc_180026DB9
0x180026d51  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d58  lea     rax, WPP_GLOBAL_Control
0x180026d5f  cmp     rcx, rax
0x180026d62  jz      short loc_180026D82
0x180026d64  test    byte ptr [rcx+1Ch], 1
0x180026d68  jz      short loc_180026D82
0x180026d6a  mov     edx, 14h
0x180026d6f  mov     r9d, edi
0x180026d72  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180026d79  mov     rcx, [rcx+10h]
0x180026d7d  call    WPP_SF_d
0x180026d82  mov     [r14], ebx
0x180026d85  jmp     short loc_180026DB9
0x180026d87  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d8e  lea     rax, WPP_GLOBAL_Control
0x180026d95  cmp     rcx, rax
0x180026d98  jz      short loc_180026DB9
0x180026d9a  test    byte ptr [rcx+1Ch], 1
0x180026d9e  jz      short loc_180026DB9
0x180026da0  mov     edx, 15h
0x180026da5  mov     r9d, edi
0x180026da8  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180026daf  mov     rcx, [rcx+10h]
0x180026db3  call    WPP_SF_d
0x180026db8  nop
0x180026db9  lea     rcx, [rbp+var_28]
0x180026dbd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180026dc2  lea     r15, [rsi+0C8h]
0x180026dc9  cmp     qword ptr [r15], 0
0x180026dcd  jnz     loc_180026E80
0x180026dd3  xor     edx, edx; lpDatabaseName
0x180026dd5  xor     ecx, ecx; lpMachineName
0x180026dd7  lea     r8d, [rdx+5]; dwDesiredAccess
0x180026ddb  call    cs:__imp_OpenSCManagerW
0x180026de1  mov     rbx, rax
0x180026de4  mov     [rbp+var_28], rax
0x180026de8  mov     rcx, [rbp+28h]; this
0x180026dec  test    rax, rax
0x180026def  jnz     short loc_180026DFB
0x180026df1  mov     edx, 2EFh; void *
0x180026df6  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180026dfb  mov     r8d, 4; dwDesiredAccess
0x180026e01  lea     rdx, ServiceName; "netprofm"
0x180026e08  mov     rcx, rbx; hSCManager
0x180026e0b  call    cs:__imp_OpenServiceW
0x180026e11  mov     rbx, rax
0x180026e14  mov     [rbp+var_40], rax
0x180026e18  mov     rcx, [rbp+28h]; this
0x180026e1c  test    rax, rax
0x180026e1f  jnz     short loc_180026E2B
0x180026e21  mov     edx, 2F2h; void *
0x180026e26  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180026e2b  xor     edx, edx
0x180026e2d  mov     rcx, r15
0x180026e30  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SC_NOTIFICATION_REGISTRATION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(_SC_NOTIFICATION_REGISTRATION *)
0x180026e35  mov     [rsp+70h+ppv], r15; unsigned int
0x180026e3a  mov     r9, rsi
0x180026e3d  lea     r8, ?NLMServiceStateChangeCallback@PublicNetworkListManager@@SAXKPEAX@Z; PublicNetworkListManager::NLMServiceStateChangeCallback(ulong,void *)
0x180026e44  mov     edx, 2
0x180026e49  mov     rcx, rbx
0x180026e4c  call    cs:__imp_SubscribeServiceChangeNotifications
0x180026e52  mov     rcx, [rbp+28h]; this
0x180026e56  test    eax, eax
0x180026e58  jz      short loc_180026E6E
0x180026e5a  mov     r9d, eax; char *
0x180026e5d  lea     r8, aOnecoreNetNetp_5; "onecore\\net\\netprofiles\\service\\src"...
0x180026e64  mov     edx, 2F5h; void *
0x180026e69  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180026e6e  lea     rcx, [rbp+var_40]
0x180026e72  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180026e77  lea     rcx, [rbp+var_28]
0x180026e7b  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180026e80  test    edi, edi
0x180026e82  js      short loc_180026EA7
0x180026e84  mov     rcx, [rsi+0E0h]
0x180026e8b  mov     rax, [rcx]
0x180026e8e  mov     r9, [rbp+var_30]
0x180026e92  lea     r8, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b
0x180026e99  mov     edx, [r14]
0x180026e9c  mov     rax, [rax+28h]
0x180026ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ea5  mov     edi, eax
0x180026ea7  lea     rcx, [rbp+var_38]
0x180026eab  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180026eb0  jmp     loc_18002700A
0x180026eb5  mov     rcx, r12; lpCriticalSection
0x180026eb8  call    cs:__imp_EnterCriticalSection
0x180026ebe  or      ebx, 0FFFFFFFFh
0x180026ec1  cmp     [r14], ebx
0x180026ec4  jnz     short loc_180026F1C
0x180026ec6  mov     [rbp+var_28], r15
0x180026eca  call    IsSystemSetupInProgress
0x180026ecf  test    eax, eax
0x180026ed1  jz      loc_180027062
0x180026ed7  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "false", "NetworkListManager API called during setup")
0x180026edc  mov     edi, 80070426h
0x180026ee1  mov     rcx, cs:WPP_GLOBAL_Control
0x180026ee8  lea     rax, WPP_GLOBAL_Control
0x180026eef  cmp     rcx, rax
0x180026ef2  jz      short loc_180026F13
0x180026ef4  test    byte ptr [rcx+1Ch], 1
0x180026ef8  jz      short loc_180026F13
0x180026efa  mov     edx, 17h
0x180026eff  mov     r9d, edi
0x180026f02  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180026f09  mov     rcx, [rcx+10h]
0x180026f0d  call    WPP_SF_d
0x180026f12  nop
0x180026f13  lea     rcx, [rbp+var_28]
0x180026f17  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180026f1c  lea     r15, [rsi+0C8h]
0x180026f23  cmp     qword ptr [r15], 0
0x180026f27  jnz     loc_180026FDA
0x180026f2d  xor     edx, edx; lpDatabaseName
0x180026f2f  xor     ecx, ecx; lpMachineName
0x180026f31  lea     r8d, [rdx+5]; dwDesiredAccess
0x180026f35  call    cs:__imp_OpenSCManagerW
0x180026f3b  mov     rbx, rax
0x180026f3e  mov     [rbp+var_28], rax
0x180026f42  test    rax, rax
0x180026f45  jnz     short loc_180026F55
0x180026f47  mov     rcx, [rbp+28h]; this
0x180026f4b  mov     edx, 336h; void *
0x180026f50  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180026f55  mov     r8d, 4; dwDesiredAccess
0x180026f5b  lea     rdx, ServiceName; "netprofm"
0x180026f62  mov     rcx, rbx; hSCManager
0x180026f65  call    cs:__imp_OpenServiceW
0x180026f6b  mov     rbx, rax
0x180026f6e  mov     [rbp+var_40], rax
0x180026f72  test    rax, rax
0x180026f75  jnz     short loc_180026F85
0x180026f77  mov     rcx, [rbp+28h]; this
0x180026f7b  mov     edx, 339h; void *
0x180026f80  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180026f85  xor     edx, edx
0x180026f87  mov     rcx, r15
0x180026f8a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SC_NOTIFICATION_REGISTRATION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(_SC_NOTIFICATION_REGISTRATION *)
0x180026f8f  mov     [rsp+70h+ppv], r15; unsigned int
0x180026f94  mov     r9, rsi
0x180026f97  lea     r8, ?NLMServiceStateChangeCallback@PublicNetworkListManager@@SAXKPEAX@Z; PublicNetworkListManager::NLMServiceStateChangeCallback(ulong,void *)
0x180026f9e  mov     edx, 2
0x180026fa3  mov     rcx, rbx
0x180026fa6  call    cs:__imp_SubscribeServiceChangeNotifications
0x180026fac  test    eax, eax
0x180026fae  jz      short loc_180026FC8
0x180026fb0  mov     rcx, [rbp+28h]; this
0x180026fb4  mov     r9d, eax; char *
0x180026fb7  lea     r8, aOnecoreNetNetp_5; "onecore\\net\\netprofiles\\service\\src"...
0x180026fbe  mov     edx, 33Ch; void *
0x180026fc3  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180026fc8  lea     rcx, [rbp+var_40]
0x180026fcc  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180026fd1  lea     rcx, [rbp+var_28]
0x180026fd5  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180026fda  test    edi, edi
0x180026fdc  js      short loc_180027001
0x180026fde  mov     rcx, [rsi+0E0h]
0x180026fe5  mov     rax, [rcx]
0x180026fe8  mov     r9, [rbp+var_30]
0x180026fec  lea     r8, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b
0x180026ff3  mov     edx, [r14]
0x180026ff6  mov     rax, [rax+28h]
0x180026ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fff  mov     edi, eax
0x180027001  mov     rcx, r12; lpCriticalSection
0x180027004  call    cs:__imp_LeaveCriticalSection
0x18002700a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027011  lea     rax, WPP_GLOBAL_Control
0x180027018  cmp     rcx, rax
0x18002701b  jz      short loc_18002703B
0x18002701d  test    byte ptr [rcx+1Ch], 8
0x180027021  jz      short loc_18002703B
0x180027023  mov     edx, 18h
0x180027028  mov     r9d, edi
0x18002702b  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180027032  mov     rcx, [rcx+10h]
0x180027036  call    WPP_SF_d
0x18002703b  mov     eax, edi
0x18002703d  mov     rcx, [rbp+var_8]
0x180027041  xor     rcx, rsp; StackCookie
0x180027044  call    __security_check_cookie
0x180027049  lea     r11, [rsp+70h+var_s0]
0x18002704e  mov     rbx, [r11+40h]
0x180027052  mov     rsi, [r11+48h]
0x180027056  mov     rsp, r11
0x180027059  pop     r15
0x18002705b  pop     r14
0x18002705d  pop     r12
0x18002705f  pop     rdi
0x180027060  pop     rbp
0x180027061  retn
0x180027062  xorps   xmm0, xmm0
0x180027065  xor     eax, eax
0x180027067  movups  [rbp+Parameter], xmm0
0x18002706b  mov     [rbp+var_10], rax
0x18002706f  lea     rcx, [rbp+Parameter]; Parameter
0x180027073  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x180027078  lea     rax, [rbp+var_28]
0x18002707c  mov     [rsp+70h+ppv], rax; ppv
0x180027081  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x180027088  xor     edx, edx; pUnkOuter
0x18002708a  lea     r8d, [rdx+4]; dwClsContext
0x18002708e  lea     rcx, CLSID_CNetworkListManager; rclsid
0x180027095  call    cs:__imp_CoCreateInstance
0x18002709b  mov     edi, eax
0x18002709d  cmp     byte ptr [rbp+Parameter+4], r15b
0x1800270a1  jz      short loc_1800270E5
0x1800270a3  mov     eax, cs:dword_18005F140
0x1800270a9  cmp     eax, 5
0x1800270ac  jbe     short loc_1800270E5
0x1800270ae  mov     rdx, 400000000000h
0x1800270b8  lea     rcx, dword_18005F140
0x1800270bf  call    _tlgKeywordOn
0x1800270c4  test    al, al
0x1800270c6  jz      short loc_1800270E5
  ... truncated ...
```
