# PublicNetworkListManager::RetryStartPrivateNlm(void)

- ea: `0x180029678`
- end: `0x1800299ab`
- name: `?RetryStartPrivateNlm@PublicNetworkListManager@@AEAAJXZ`
- size: `819`
- prototype: `__int64 __fastcall(PublicNetworkListManager *__hidden this)`
- caller_count: `11`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020120`
- `0x180024410`
- `0x1800245a0`
- `0x1800251b0`
- `0x1800262d0`
- `0x1800268f0`
- `0x180026a80`
- `0x1800272f0`
- `0x180029e70`
- `0x18002ab50`
- `0x18002acc0`

## callees

- `0x180006810`
- `0x1800074e0`
- `0x1800086b0`
- `0x180008a7c`
- `0x180008b60`
- `0x180009184`
- `0x180009d08`
- `0x18000a078`
- `0x1800120d0`
- `0x18001f150`
- `0x18001f8d0`
- `0x18001ffd8`
- `0x180021bcc`
- `0x180026c04`
- `0x180029678`
- `0x18002a9b4`
- `0x18002ae28`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800298f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029956`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029980`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800298f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029956`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029980`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800298e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029916`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002996a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800298e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029916`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002996a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180029853`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180029853`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180029823`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180029823`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180029894`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180029894`

## string_xrefs

- `0x1800298a5`: `onecore\net\netprofiles\service\src\public\lib\networklistmanagerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PublicNetworkListManager::RetryStartPrivateNlm(PublicNetworkListManager *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // r15
  unsigned int *v3; // r14
  int PrivateNetworkListManager; // esi
  struct _RTL_CRITICAL_SECTION **v6; // rax
  SC_HANDLE v7; // rbx
  unsigned int v8; // r8d
  const char *v9; // r9
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  unsigned int v11; // r8d
  const char *v12; // r9
  unsigned int v13; // eax
  PublicNetworkListManager *v14; // rcx
  PublicNetworkListManager *v15; // rcx
  struct _RTL_CRITICAL_SECTION *v16; // [rsp+30h] [rbp-38h] BYREF
  struct _RTL_CRITICAL_SECTION *v17; // [rsp+38h] [rbp-30h] BYREF
  SC_HANDLE v18; // [rsp+40h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 232);
  v3 = (unsigned int *)((char *)this + 272);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::GetImpl'::`2'::impl) )
  {
    v16 = 0;
    wil::EnterCriticalSection(&v16, v2);
    if ( *((_BYTE *)v3 + 4) )
    {
LABEL_3:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v16);
      return 2147943515LL;
    }
    if ( *v3 != -1 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 28) + 32LL))(*((_QWORD *)this + 28), *v3);
      *v3 = -1;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
      &v16,
      0);
    ppv = 0;
    PrivateNetworkListManager = CoCreatePrivateNetworkListManagerInstance(&ppv);
    v6 = wil::EnterCriticalSection(&v17, v2);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(
      &v16,
      v6);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v17);
    if ( *((_BYTE *)this + 276) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
      goto LABEL_3;
    }
    if ( PrivateNetworkListManager < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
          (unsigned int)PrivateNetworkListManager);
    }
    else
    {
      *((_BYTE *)this + 208) = 1;
      if ( *v3 == -1 )
      {
        PrivateNetworkListManager = (*(__int64 (__fastcall **)(_QWORD, LPVOID, GUID *, unsigned int *))(**((_QWORD **)this + 28) + 24LL))(
                                      *((_QWORD *)this + 28),
                                      ppv,
                                      &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b,
                                      v3);
        if ( PrivateNetworkListManager < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
              (unsigned int)PrivateNetworkListManager);
          *((_DWORD *)this + 68) = -1;
        }
      }
    }
    if ( !*((_QWORD *)this + 25) )
    {
      v7 = OpenSCManagerW(0, 0, 5u);
      v18 = v7;
      if ( !v7 )
        wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x202, v8, v9);
      v10 = (struct _RTL_CRITICAL_SECTION *)OpenServiceW(v7, L"netprofm", 4u);
      v17 = v10;
      if ( !v10 )
        wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x205, v11, v12);
      wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(
        (char *)this + 200,
        0);
      v13 = SubscribeServiceChangeNotifications(v10, 2, PublicNetworkListManager::NLMServiceStateChangeCallback, this);
      if ( v13 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x208,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\networklistmanagerimpl.cpp",
          (const char *)v13,
          (_DWORD)this + 200);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>((SC_HANDLE *)&v17);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
      &v16,
      0);
    if ( PrivateNetworkListManager >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 616));
      PublicNetworkListManager::ClearCookieForExistingEventTypes(this);
      PublicNetworkListManager::AdviseForExistingEventTypes(v14);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 616));
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v16);
  }
  else
  {
    EnterCriticalSection(v2);
    if ( *v3 != -1 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 28) + 32LL))(*((_QWORD *)this + 28), *v3);
      *v3 = -1;
    }
    ppv = 0;
    PrivateNetworkListManager = PublicNetworkListManager::GetPrivateNetworkListManager(
                                  this,
                                  (struct INetworkListManagerPrivate **)&ppv);
    LeaveCriticalSection(v2);
    if ( PrivateNetworkListManager >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 616));
      PublicNetworkListManager::ClearCookieForExistingEventTypes(this);
      PublicNetworkListManager::AdviseForExistingEventTypes(v15);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 616));
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  }
  return (unsigned int)PrivateNetworkListManager;
}

```

## disassembly

```asm
0x180029678  push    rbp
0x18002967a  push    rbx
0x18002967b  push    rsi
0x18002967c  push    rdi
0x18002967d  push    r14
0x18002967f  push    r15
0x180029681  mov     rbp, rsp
0x180029684  sub     rsp, 68h
0x180029688  mov     rax, cs:__security_cookie
0x18002968f  xor     rax, rsp
0x180029692  mov     [rbp+var_18], rax
0x180029696  mov     rdi, rcx
0x180029699  lea     r15, [rcx+0E8h]
0x1800296a0  lea     r14, [rcx+110h]
0x1800296a7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::GetImpl(void)'::`2'::impl
0x1800296ae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::__private_IsEnabled(void)
0x1800296b3  test    al, al
0x1800296b5  jz      loc_180029913
0x1800296bb  mov     [rbp+var_38], 0
0x1800296c3  mov     rdx, r15
0x1800296c6  lea     rcx, [rbp+var_38]
0x1800296ca  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800296cf  nop
0x1800296d0  cmp     byte ptr [r14+4], 0
0x1800296d5  jz      short loc_1800296EA
0x1800296d7  lea     rcx, [rbp+var_38]
0x1800296db  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800296e0  mov     eax, 8007045Bh
0x1800296e5  jmp     loc_180029992
0x1800296ea  or      ebx, 0FFFFFFFFh
0x1800296ed  cmp     [r14], ebx
0x1800296f0  jz      short loc_18002970B
0x1800296f2  mov     rcx, [rdi+0E0h]
0x1800296f9  mov     rax, [rcx]
0x1800296fc  mov     edx, [r14]
0x1800296ff  mov     rax, [rax+20h]
0x180029703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029708  mov     [r14], ebx
0x18002970b  xor     edx, edx
0x18002970d  lea     rcx, [rbp+var_38]
0x180029711  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x180029716  mov     [rbp+ppv], 0
0x18002971e  lea     rcx, [rbp+ppv]; ppv
0x180029722  call    CoCreatePrivateNetworkListManagerInstance
0x180029727  mov     esi, eax
0x180029729  mov     rdx, r15
0x18002972c  lea     rcx, [rbp+var_30]
0x180029730  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180029735  mov     rdx, rax
0x180029738  lea     rcx, [rbp+var_38]
0x18002973c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> &&)
0x180029741  lea     rcx, [rbp+var_30]
0x180029745  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18002974a  cmp     byte ptr [rdi+114h], 0
0x180029751  jz      short loc_180029761
0x180029753  lea     rcx, [rbp+ppv]
0x180029757  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002975c  jmp     loc_1800296D7
0x180029761  test    esi, esi
0x180029763  js      short loc_1800297D9
0x180029765  mov     eax, 1
0x18002976a  xchg    al, [rdi+0D0h]
0x180029770  cmp     [r14], ebx
0x180029773  jnz     loc_18002980A
0x180029779  mov     rcx, [rdi+0E0h]
0x180029780  mov     rax, [rcx]
0x180029783  mov     r9, r14
0x180029786  lea     r8, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b
0x18002978d  mov     rdx, [rbp+ppv]
0x180029791  mov     rax, [rax+18h]
0x180029795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002979a  mov     esi, eax
0x18002979c  test    eax, eax
0x18002979e  jns     short loc_18002980A
0x1800297a0  lea     rax, WPP_GLOBAL_Control
0x1800297a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297ae  cmp     rcx, rax
0x1800297b1  jz      short loc_1800297D1
0x1800297b3  test    byte ptr [rcx+1Ch], 1
0x1800297b7  jz      short loc_1800297D1
0x1800297b9  mov     edx, 11h
0x1800297be  mov     r9d, esi
0x1800297c1  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x1800297c8  mov     rcx, [rcx+10h]
0x1800297cc  call    WPP_SF_d
0x1800297d1  mov     [rdi+110h], ebx
0x1800297d7  jmp     short loc_18002980A
0x1800297d9  lea     rax, WPP_GLOBAL_Control
0x1800297e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297e7  cmp     rcx, rax
0x1800297ea  jz      short loc_18002980A
0x1800297ec  test    byte ptr [rcx+1Ch], 1
0x1800297f0  jz      short loc_18002980A
0x1800297f2  mov     edx, 12h
0x1800297f7  mov     r9d, esi
0x1800297fa  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180029801  mov     rcx, [rcx+10h]
0x180029805  call    WPP_SF_d
0x18002980a  lea     r14, [rdi+0C8h]
0x180029811  cmp     qword ptr [r14], 0
0x180029815  jnz     loc_1800298C8
0x18002981b  xor     edx, edx; lpDatabaseName
0x18002981d  xor     ecx, ecx; lpMachineName
0x18002981f  lea     r8d, [rdx+5]; dwDesiredAccess
0x180029823  call    cs:__imp_OpenSCManagerW
0x180029829  mov     rbx, rax
0x18002982c  mov     [rbp+var_28], rax
0x180029830  mov     rcx, [rbp+30h]; this
0x180029834  test    rax, rax
0x180029837  jnz     short loc_180029843
0x180029839  mov     edx, 202h; void *
0x18002983e  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180029843  mov     r8d, 4; dwDesiredAccess
0x180029849  lea     rdx, ServiceName; "netprofm"
0x180029850  mov     rcx, rbx; hSCManager
0x180029853  call    cs:__imp_OpenServiceW
0x180029859  mov     rbx, rax
0x18002985c  mov     [rbp+var_30], rax
0x180029860  mov     rcx, [rbp+30h]; this
0x180029864  test    rax, rax
0x180029867  jnz     short loc_180029873
0x180029869  mov     edx, 205h; void *
0x18002986e  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180029873  xor     edx, edx
0x180029875  mov     rcx, r14
0x180029878  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SC_NOTIFICATION_REGISTRATION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(_SC_NOTIFICATION_REGISTRATION *)
0x18002987d  mov     qword ptr [rsp+68h+var_48], r14; unsigned int
0x180029882  mov     r9, rdi
0x180029885  lea     r8, ?NLMServiceStateChangeCallback@PublicNetworkListManager@@SAXKPEAX@Z; PublicNetworkListManager::NLMServiceStateChangeCallback(ulong,void *)
0x18002988c  mov     edx, 2
0x180029891  mov     rcx, rbx
0x180029894  call    cs:__imp_SubscribeServiceChangeNotifications
0x18002989a  mov     rcx, [rbp+30h]; this
0x18002989e  test    eax, eax
0x1800298a0  jz      short loc_1800298B6
0x1800298a2  mov     r9d, eax; char *
0x1800298a5  lea     r8, aOnecoreNetNetp_5; "onecore\\net\\netprofiles\\service\\src"...
0x1800298ac  mov     edx, 208h; void *
0x1800298b1  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800298b6  lea     rcx, [rbp+var_30]
0x1800298ba  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800298bf  lea     rcx, [rbp+var_28]
0x1800298c3  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800298c8  xor     edx, edx
0x1800298ca  lea     rcx, [rbp+var_38]
0x1800298ce  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x1800298d3  test    esi, esi
0x1800298d5  js      short loc_1800298FE
0x1800298d7  lea     rbx, [rdi+268h]
0x1800298de  mov     rcx, rbx; lpCriticalSection
0x1800298e1  call    cs:__imp_EnterCriticalSection
0x1800298e7  mov     rcx, rdi; this
0x1800298ea  call    ?ClearCookieForExistingEventTypes@PublicNetworkListManager@@AEAAXXZ; PublicNetworkListManager::ClearCookieForExistingEventTypes(void)
0x1800298ef  call    ?AdviseForExistingEventTypes@PublicNetworkListManager@@AEAAXXZ; PublicNetworkListManager::AdviseForExistingEventTypes(void)
0x1800298f4  mov     rcx, rbx; lpCriticalSection
0x1800298f7  call    cs:__imp_LeaveCriticalSection
0x1800298fd  nop
0x1800298fe  lea     rcx, [rbp+ppv]
0x180029902  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180029907  nop
0x180029908  lea     rcx, [rbp+var_38]
0x18002990c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180029911  jmp     short loc_180029990
0x180029913  mov     rcx, r15; lpCriticalSection
0x180029916  call    cs:__imp_EnterCriticalSection
0x18002991c  or      ebx, 0FFFFFFFFh
0x18002991f  cmp     [r14], ebx
0x180029922  jz      short loc_18002993D
0x180029924  mov     rcx, [rdi+0E0h]
0x18002992b  mov     rax, [rcx]
0x18002992e  mov     edx, [r14]
0x180029931  mov     rax, [rax+20h]
0x180029935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002993a  mov     [r14], ebx
0x18002993d  mov     [rbp+ppv], 0
0x180029945  lea     rdx, [rbp+ppv]; struct INetworkListManagerPrivate **
0x180029949  mov     rcx, rdi; this
0x18002994c  call    ?GetPrivateNetworkListManager@PublicNetworkListManager@@QEAAJPEAPEAUINetworkListManagerPrivate@@@Z; PublicNetworkListManager::GetPrivateNetworkListManager(INetworkListManagerPrivate * *)
0x180029951  mov     esi, eax
0x180029953  mov     rcx, r15; lpCriticalSection
0x180029956  call    cs:__imp_LeaveCriticalSection
0x18002995c  test    esi, esi
0x18002995e  js      short loc_180029987
0x180029960  lea     rbx, [rdi+268h]
0x180029967  mov     rcx, rbx; lpCriticalSection
0x18002996a  call    cs:__imp_EnterCriticalSection
0x180029970  mov     rcx, rdi; this
0x180029973  call    ?ClearCookieForExistingEventTypes@PublicNetworkListManager@@AEAAXXZ; PublicNetworkListManager::ClearCookieForExistingEventTypes(void)
0x180029978  call    ?AdviseForExistingEventTypes@PublicNetworkListManager@@AEAAXXZ; PublicNetworkListManager::AdviseForExistingEventTypes(void)
0x18002997d  mov     rcx, rbx; lpCriticalSection
0x180029980  call    cs:__imp_LeaveCriticalSection
0x180029986  nop
0x180029987  lea     rcx, [rbp+ppv]
0x18002998b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180029990  mov     eax, esi
0x180029992  mov     rcx, [rbp+var_18]
0x180029996  xor     rcx, rsp; StackCookie
0x180029999  call    __security_check_cookie
0x18002999e  add     rsp, 68h
0x1800299a2  pop     r15
0x1800299a4  pop     r14
0x1800299a6  pop     rdi
0x1800299a7  pop     rsi
0x1800299a8  pop     rbx
0x1800299a9  pop     rbp
0x1800299aa  retn
```
