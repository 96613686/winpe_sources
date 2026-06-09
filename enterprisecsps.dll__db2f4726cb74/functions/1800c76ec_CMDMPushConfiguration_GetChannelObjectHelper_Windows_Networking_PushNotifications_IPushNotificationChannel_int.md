# CMDMPushConfiguration::GetChannelObjectHelper(Windows::Networking::PushNotifications::IPushNotificationChannel * *,__int64)

- ea: `0x1800c76ec`
- end: `0x1800c7f11`
- name: `?GetChannelObjectHelper@CMDMPushConfiguration@@AEAAJPEAPEAUIPushNotificationChannel@PushNotifications@Networking@Windows@@_J@Z`
- size: `2085`
- prototype: `__int64 __fastcall(CMDMPushConfiguration *__hidden this, struct Windows::Networking::PushNotifications::IPushNotificationChannel **, __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c7580`

## callees

- `0x180008de0`
- `0x18000caf4`
- `0x18000d4d4`
- `0x180015804`
- `0x18001623c`
- `0x180022f08`
- `0x180024d8c`
- `0x180025a9c`
- `0x18002dc94`
- `0x180068954`
- `0x180083c04`
- `0x1800c11cc`
- `0x1800c1304`
- `0x1800c1510`
- `0x1800c1838`
- `0x1800c19e8`
- `0x1800c1ba0`
- `0x1800c1e0c`
- `0x1800c7340`
- `0x1800c76ec`
- `0x1800cac0c`
- `0x1800cb1a8`
- `0x1800cdc84`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800c79e2`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800c79e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c79fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c79fa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c77b6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c77b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c7797`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c7797`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c77e3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c7abd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c77e3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c7abd`

## string_xrefs

- `0x1800c7ec4`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800c7a88`: `Windows.System.Threading.ThreadPoolTimer`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CMDMPushConfiguration::GetChannelObjectHelper(
        CMDMPushConfiguration *this,
        struct Windows::Networking::PushNotifications::IPushNotificationChannel **a2)
{
  HSTRING v4; // rbx
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 result; // rax
  int AppId; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING, __int64 *); // rbx
  int v12; // eax
  unsigned int v13; // ebx
  const char *v14; // r9
  HANDLE Event; // rbx
  const char *v16; // r9
  __int64 v17; // rax
  char *v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rdi
  int v22; // eax
  unsigned int v23; // edi
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, __int64, __int64, HSTRING *); // rdi
  int v26; // eax
  unsigned int v27; // edi
  HSTRING v28; // rdi
  __int64 v29; // rdi
  __int64 v30; // rsi
  __int64 v31; // rdx
  int v32; // edi
  struct Windows::Networking::PushNotifications::IPushNotificationChannel *v33; // rax
  int v34; // [rsp+20h] [rbp-208h]
  struct Windows::Networking::PushNotifications::IPushNotificationChannel *v35; // [rsp+30h] [rbp-1F8h] BYREF
  HSTRING v36; // [rsp+38h] [rbp-1F0h] BYREF
  __int64 v37; // [rsp+40h] [rbp-1E8h] BYREF
  unsigned __int16 *v38; // [rsp+48h] [rbp-1E0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-1D8h] BYREF
  __int64 v40; // [rsp+58h] [rbp-1D0h] BYREF
  _QWORD v41[2]; // [rsp+60h] [rbp-1C8h] BYREF
  __int64 v42; // [rsp+70h] [rbp-1B8h] BYREF
  __int64 v43; // [rsp+78h] [rbp-1B0h]
  char v44; // [rsp+80h] [rbp-1A8h] BYREF
  HSTRING string; // [rsp+88h] [rbp-1A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-198h] BYREF
  _QWORD v47[42]; // [rsp+B0h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  wil::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v47);
  v47[0] = &MDMPushProvider::GetChannelObjectHelperActivity::`vftable';
  MDMPushProvider::GetChannelObjectHelperActivity::StartActivity((MDMPushProvider::GetChannelObjectHelperActivity *)v47);
  v40 = 0;
  v35 = 0;
  v39 = 0;
  v38 = 0;
  v37 = 0;
  v36 = 0;
  ____0__V___shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA_XZ(v41);
  v43 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Networking.PushNotifications.PushNotificationChannelManager",
         0x43u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = string;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v39);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_8baf9b65_77a1_4588_bd19_861529a9dcf0, &v39);
  v6 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v38,
      0);
    AppId = CMDMPushConfiguration::GetAppId(this, &v38);
    v9 = AppId;
    if ( AppId >= 0 )
    {
      v10 = v39;
      v11 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v39 + 56LL);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v40);
      Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)&string, v38);
      try
      {
        v12 = v11(v10, string, &v40);
        v13 = v12;
        if ( v12 >= 0 )
        {
          Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
          if ( !Event )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x1CC8,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
              v16);
          GetLastError();
          _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
            v41,
            Event);
          v17 = std::shared_ptr<CCertificateStore>::shared_ptr<CCertificateStore>(&string, v41);
          v18 = (char *)Microsoft::WRL::Callback_Windows::System::Threading::ITimerElapsedHandler__lambda_5c2cd178e30082c76c93240c01ceecaf___(
                          &v42,
                          v17);
          v19 = 0;
          if ( &v44 != v18 )
          {
            v19 = *(_QWORD *)v18;
            *(_QWORD *)v18 = 0;
          }
          v43 = v19;
          v20 = v42;
          if ( v42 )
          {
            v42 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
          lambda_5c2cd178e30082c76c93240c01ceecaf_::__lambda_5c2cd178e30082c76c93240c01ceecaf_(&string);
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            (HSTRING_HEADER *)&string,
            L"Windows.System.Threading.ThreadPoolTimer",
            0x29u,
            0x28u);
          v21 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[16];
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v37);
          v22 = RoGetActivationFactory(v21, &GUID_1a8a9d02_e482_461b_b8c7_8efad1cce590, &v37);
          v23 = v22;
          if ( v22 >= 0 )
          {
            v24 = v37;
            v25 = *(__int64 (__fastcall **)(__int64, __int64, __int64, HSTRING *))(*(_QWORD *)v37 + 56LL);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v36);
            v26 = v25(v24, v19, 400000000, &v36);
            v27 = v26;
            if ( v26 >= 0 )
            {
              v28 = v36;
              if ( v36 )
                (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v36 + 8LL))(v36);
              string = v28;
              v42 = 0;
              hstringHeader.Reserved.Reserved2[0] = 1;
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v42);
              if ( (unsigned __int8)std::operator!=<CCertificateLocation>(v41) )
                v29 = *(_QWORD *)v41[0];
              else
                v29 = 0;
              v30 = v40;
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
              v32 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(
                      v30,
                      v31,
                      v29);
              if ( v32 < 0
                || (v32 = (*(__int64 (__fastcall **)(__int64, struct Windows::Networking::PushNotifications::IPushNotificationChannel **))(*(_QWORD *)v30 + 64LL))(
                            v30,
                            &v35),
                    v32 < 0) )
              {
                if ( v32 == -2147023436
                  || (unsigned int)(v32 + 2147023674) <= 1
                  || v32 == -2147418110
                  || v32 == -2013002776 )
                {
                  wil::details::ScopeExitFn__lambda_1f618b4399afd11dd2cbe0ec8def606d___::_ScopeExitFn__lambda_1f618b4399afd11dd2cbe0ec8def606d___(&string);
                  if ( v19 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x1EB,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
                    (const char *)(unsigned int)v32,
                    v34);
                  wil::details::ScopeExitFn__lambda_1f618b4399afd11dd2cbe0ec8def606d___::_ScopeExitFn__lambda_1f618b4399afd11dd2cbe0ec8def606d___(&string);
                  if ( v19 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                }
                std::_Ptr_base<Dynamo::SyncmlPackProcessor>::_Decref(v41);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v36);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v37);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v39);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v40);
                MDMPushProvider::GetChannelObjectHelperActivity::~GetChannelObjectHelperActivity((MDMPushProvider::GetChannelObjectHelperActivity *)v47);
                result = (unsigned int)v32;
              }
              else
              {
                v33 = v35;
                v35 = 0;
                *a2 = v33;
                wil::details::ScopeExitFn__lambda_1f618b4399afd11dd2cbe0ec8def606d___::_ScopeExitFn__lambda_1f618b4399afd11dd2cbe0ec8def606d___(&string);
                if ( v19 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                std::_Ptr_base<Dynamo::SyncmlPackProcessor>::_Decref(v41);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v36);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v37);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v39);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v40);
                wil::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v47);
                MDMPushProvider::GetChannelObjectHelperActivity::~GetChannelObjectHelperActivity((MDMPushProvider::GetChannelObjectHelperActivity *)v47);
                result = 0;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1DD,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
                (const char *)(unsigned int)v26,
                v34);
              if ( v19 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
              std::_Ptr_base<Dynamo::SyncmlPackProcessor>::_Decref(v41);
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v36);
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v37);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v39);
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v40);
              MDMPushProvider::GetChannelObjectHelperActivity::~GetChannelObjectHelperActivity((MDMPushProvider::GetChannelObjectHelperActivity *)v47);
              result = v27;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1D9,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
              (const char *)(unsigned int)v22,
              v34);
            if ( v19 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
            std::_Ptr_base<Dynamo::SyncmlPackProcessor>::_Decref(v41);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v36);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v37);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v39);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v40);
            MDMPushProvider::GetChannelObjectHelperActivity::~GetChannelObjectHelperActivity((MDMPushProvider::GetChannelObjectHelperActivity *)v47);
            result = v23;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1CD,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
            (const char *)(unsigned int)v12,
            v34);
          std::_Ptr_base<Dynamo::SyncmlPackProcessor>::_Decref(v41);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v36);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v37);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v39);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v40);
          MDMPushProvider::GetChannelObjectHelperActivity::~GetChannelObjectHelperActivity((MDMPushProvider::GetChannelObjectHelperActivity *)v47);
          result = v13;
        }
      }
      catch ( ... )
      {
        LODWORD(v35) = wil::details::in1diag3::Return_CaughtException(
                         retaddr,
                         (void *)0x1F0,
                         (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
                         v14);
        MDMPushProvider::GetChannelObjectHelperActivity::~GetChannelObjectHelperActivity((MDMPushProvider::GetChannelObjectHelperActivity *)v47);
        return (unsigned int)v35;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C9,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
        (const char *)(unsigned int)AppId,
        v34);
      std::_Ptr_base<Dynamo::SyncmlPackProcessor>::_Decref(v41);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v36);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v37);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v39);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v40);
      MDMPushProvider::GetChannelObjectHelperActivity::~GetChannelObjectHelperActivity((MDMPushProvider::GetChannelObjectHelperActivity *)v47);
      return v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v34);
    std::_Ptr_base<Dynamo::SyncmlPackProcessor>::_Decref(v41);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v37);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v39);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v40);
    MDMPushProvider::GetChannelObjectHelperActivity::~GetChannelObjectHelperActivity((MDMPushProvider::GetChannelObjectHelperActivity *)v47);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x1800c76ec  mov     [rsp+arg_10], rbx
0x1800c76f1  mov     [rsp+arg_18], rsi
0x1800c76f6  push    rdi
0x1800c76f7  push    r14
0x1800c76f9  push    r15
0x1800c76fb  sub     rsp, 210h
0x1800c7702  mov     rax, cs:__security_cookie
0x1800c7709  xor     rax, rsp
0x1800c770c  mov     [rsp+228h+var_28], rax
0x1800c7714  mov     r14, rdx
0x1800c7717  mov     rdi, rcx
0x1800c771a  lea     rdx, aGetchannelobje_0; "GetChannelObjectHelperActivity"
0x1800c7721  lea     rcx, [rsp+228h+var_178]; struct wil::details::IFailureCallback *
0x1800c7729  call    ??0?$ActivityBase@VMDMPushProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800c772e  lea     rax, ??_7GetChannelObjectHelperActivity@MDMPushProvider@@6B@; const MDMPushProvider::GetChannelObjectHelperActivity::`vftable'
0x1800c7735  mov     [rsp+228h+var_178], rax
0x1800c773d  lea     rcx, [rsp+228h+var_178]; this
0x1800c7745  call    ?StartActivity@GetChannelObjectHelperActivity@MDMPushProvider@@QEAAXXZ; MDMPushProvider::GetChannelObjectHelperActivity::StartActivity(void)
0x1800c774a  nop
0x1800c774b  xor     r15d, r15d
0x1800c774e  mov     [rsp+228h+var_1D0], r15
0x1800c7753  mov     [rsp+228h+var_1F8], r15
0x1800c7758  mov     [rsp+228h+var_1D8], r15
0x1800c775d  mov     [rsp+228h+var_1E0], r15
0x1800c7762  mov     [rsp+228h+var_1E8], r15
0x1800c7767  mov     [rsp+228h+var_1F0], r15
0x1800c776c  lea     rcx, [rsp+228h+var_1C8]
0x1800c7771  call    ??$?0$$V@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@XZ
0x1800c7776  nop
0x1800c7777  mov     [rsp+228h+var_1B0], r15
0x1800c777c  lea     r9, [rsp+228h+string]; string
0x1800c7784  lea     r8, [rsp+228h+hstringHeader]; hstringHeader
0x1800c778c  lea     edx, [r15+43h]; length
0x1800c7790  lea     rcx, ?RuntimeClass_Windows_Networking_PushNotifications_PushNotificationChannelManager@@3QBGB; "Windows.Networking.PushNotifications.Pu"...
0x1800c7797  call    cs:__imp_WindowsCreateStringReference
0x1800c779e  nop     dword ptr [rax+rax+00h]
0x1800c77a3  test    eax, eax
0x1800c77a5  jns     short loc_1800C77C2
0x1800c77a7  xor     r9d, r9d; lpArguments
0x1800c77aa  xor     r8d, r8d; nNumberOfArguments
0x1800c77ad  lea     edx, [r15+1]; dwExceptionFlags
0x1800c77b1  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800c77b6  call    cs:__imp_RaiseException
0x1800c77bd  nop     dword ptr [rax+rax+00h]
0x1800c77c2  mov     rbx, [rsp+228h+string]
0x1800c77ca  lea     rcx, [rsp+228h+var_1D8]
0x1800c77cf  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c77d4  lea     r8, [rsp+228h+var_1D8]
0x1800c77d9  lea     rdx, _GUID_8baf9b65_77a1_4588_bd19_861529a9dcf0
0x1800c77e0  mov     rcx, rbx
0x1800c77e3  call    cs:__imp_RoGetActivationFactory
0x1800c77ea  nop     dword ptr [rax+rax+00h]
0x1800c77ef  mov     ebx, eax
0x1800c77f1  test    eax, eax
0x1800c77f3  jns     short loc_1800C7873
0x1800c77f5  mov     rcx, [rsp+228h]; this
0x1800c77fd  mov     r9d, eax; char *
0x1800c7800  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x1800c7807  mov     edx, 1C7h; void *
0x1800c780c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7811  nop
0x1800c7812  lea     rcx, [rsp+228h+var_1C8]
0x1800c7817  call    ?_Decref@?$_Ptr_base@VSyncmlPackProcessor@Dynamo@@@std@@IEAAXXZ; std::_Ptr_base<Dynamo::SyncmlPackProcessor>::_Decref(void)
0x1800c781c  nop
0x1800c781d  lea     rcx, [rsp+228h+var_1F0]
0x1800c7822  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c7827  nop
0x1800c7828  lea     rcx, [rsp+228h+var_1E8]
0x1800c782d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c7832  nop
0x1800c7833  lea     rcx, [rsp+228h+var_1E0]
0x1800c7838  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c783d  nop
0x1800c783e  lea     rcx, [rsp+228h+var_1D8]
0x1800c7843  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c7848  nop
0x1800c7849  lea     rcx, [rsp+228h+var_1F8]
0x1800c784e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c7853  nop
0x1800c7854  lea     rcx, [rsp+228h+var_1D0]
0x1800c7859  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c785e  nop
0x1800c785f  lea     rcx, [rsp+228h+var_178]; this
0x1800c7867  call    ??1GetChannelObjectHelperActivity@MDMPushProvider@@QEAA@XZ; MDMPushProvider::GetChannelObjectHelperActivity::~GetChannelObjectHelperActivity(void)
0x1800c786c  mov     eax, ebx
0x1800c786e  jmp     loc_1800C7EE7
0x1800c7873  xor     edx, edx
0x1800c7875  lea     rcx, [rsp+228h+var_1E0]
0x1800c787a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c787f  lea     rdx, [rsp+228h+var_1E0]; unsigned __int16 **
0x1800c7884  mov     rcx, rdi; this
0x1800c7887  call    ?GetAppId@CMDMPushConfiguration@@QEAAJPEAPEAG@Z; CMDMPushConfiguration::GetAppId(ushort * *)
0x1800c788c  mov     ebx, eax
0x1800c788e  test    eax, eax
0x1800c7890  jns     short loc_1800C7910
0x1800c7892  mov     rcx, [rsp+228h]; this
0x1800c789a  mov     r9d, eax; char *
0x1800c789d  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x1800c78a4  mov     edx, 1C9h; void *
0x1800c78a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c78ae  nop
0x1800c78af  lea     rcx, [rsp+228h+var_1C8]
0x1800c78b4  call    ?_Decref@?$_Ptr_base@VSyncmlPackProcessor@Dynamo@@@std@@IEAAXXZ; std::_Ptr_base<Dynamo::SyncmlPackProcessor>::_Decref(void)
0x1800c78b9  nop
0x1800c78ba  lea     rcx, [rsp+228h+var_1F0]
0x1800c78bf  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c78c4  nop
0x1800c78c5  lea     rcx, [rsp+228h+var_1E8]
0x1800c78ca  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c78cf  nop
0x1800c78d0  lea     rcx, [rsp+228h+var_1E0]
0x1800c78d5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c78da  nop
0x1800c78db  lea     rcx, [rsp+228h+var_1D8]
0x1800c78e0  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c78e5  nop
0x1800c78e6  lea     rcx, [rsp+228h+var_1F8]
0x1800c78eb  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c78f0  nop
0x1800c78f1  lea     rcx, [rsp+228h+var_1D0]
0x1800c78f6  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c78fb  nop
0x1800c78fc  lea     rcx, [rsp+228h+var_178]; this
0x1800c7904  call    ??1GetChannelObjectHelperActivity@MDMPushProvider@@QEAA@XZ; MDMPushProvider::GetChannelObjectHelperActivity::~GetChannelObjectHelperActivity(void)
0x1800c7909  mov     eax, ebx
0x1800c790b  jmp     loc_1800C7EE7
0x1800c7910  mov     rdi, [rsp+228h+var_1D8]
0x1800c7915  mov     rax, [rdi]
0x1800c7918  mov     rbx, [rax+38h]
0x1800c791c  lea     rcx, [rsp+228h+var_1D0]
0x1800c7921  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c7926  mov     rdx, [rsp+228h+var_1E0]; unsigned __int16 *
0x1800c792b  lea     rcx, [rsp+228h+string]; this
0x1800c7933  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800c7938  lea     r8, [rsp+228h+var_1D0]
0x1800c793d  mov     rdx, [rsp+228h+string]
0x1800c7945  mov     rcx, rdi
0x1800c7948  mov     rax, rbx
0x1800c794b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7950  mov     ebx, eax
0x1800c7952  test    eax, eax
0x1800c7954  jns     short loc_1800C79D4
0x1800c7956  mov     rcx, [rsp+228h]; this
0x1800c795e  mov     r9d, eax; char *
0x1800c7961  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x1800c7968  mov     edx, 1CDh; void *
0x1800c796d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7972  nop
0x1800c7973  lea     rcx, [rsp+228h+var_1C8]
0x1800c7978  call    ?_Decref@?$_Ptr_base@VSyncmlPackProcessor@Dynamo@@@std@@IEAAXXZ; std::_Ptr_base<Dynamo::SyncmlPackProcessor>::_Decref(void)
0x1800c797d  nop
0x1800c797e  lea     rcx, [rsp+228h+var_1F0]
0x1800c7983  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c7988  nop
0x1800c7989  lea     rcx, [rsp+228h+var_1E8]
0x1800c798e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c7993  nop
0x1800c7994  lea     rcx, [rsp+228h+var_1E0]
0x1800c7999  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c799e  nop
0x1800c799f  lea     rcx, [rsp+228h+var_1D8]
0x1800c79a4  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c79a9  nop
0x1800c79aa  lea     rcx, [rsp+228h+var_1F8]
0x1800c79af  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c79b4  nop
0x1800c79b5  lea     rcx, [rsp+228h+var_1D0]
0x1800c79ba  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c79bf  nop
0x1800c79c0  lea     rcx, [rsp+228h+var_178]; this
0x1800c79c8  call    ??1GetChannelObjectHelperActivity@MDMPushProvider@@QEAA@XZ; MDMPushProvider::GetChannelObjectHelperActivity::~GetChannelObjectHelperActivity(void)
0x1800c79cd  mov     eax, ebx
0x1800c79cf  jmp     loc_1800C7EE7
0x1800c79d4  xor     edx, edx; lpName
0x1800c79d6  xor     ecx, ecx; lpEventAttributes
0x1800c79d8  mov     r9d, 1F0003h; dwDesiredAccess
0x1800c79de  lea     r8d, [rdx+1]; dwFlags
0x1800c79e2  call    cs:__imp_CreateEventExW
0x1800c79e9  nop     dword ptr [rax+rax+00h]
0x1800c79ee  mov     rbx, rax
0x1800c79f1  test    rax, rax
0x1800c79f4  jz      loc_1800C7EBC
0x1800c79fa  call    cs:__imp_GetLastError
0x1800c7a01  nop     dword ptr [rax+rax+00h]
0x1800c7a06  mov     rdx, rbx
0x1800c7a09  lea     rcx, [rsp+228h+var_1C8]
0x1800c7a0e  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x1800c7a13  lea     rdx, [rsp+228h+var_1C8]
0x1800c7a18  lea     rcx, [rsp+228h+string]
0x1800c7a20  call    ??$?0VCMyStore@@$0A@@?$shared_ptr@VCCertificateStore@@@std@@QEAA@AEBV?$shared_ptr@VCMyStore@@@1@@Z; std::shared_ptr<CCertificateStore>::shared_ptr<CCertificateStore>(std::shared_ptr<CMyStore> const &)
0x1800c7a25  mov     rdx, rax
0x1800c7a28  lea     rcx, [rsp+228h+var_1B8]
0x1800c7a2d  call    Microsoft__WRL__Callback_Windows__System__Threading__ITimerElapsedHandler__lambda_5c2cd178e30082c76c93240c01ceecaf___
0x1800c7a32  mov     rbx, r15
0x1800c7a35  lea     rcx, [rsp+228h+var_1A8]
0x1800c7a3d  cmp     rcx, rax
0x1800c7a40  jz      short loc_1800C7A48
0x1800c7a42  mov     rbx, [rax]
0x1800c7a45  mov     [rax], r15
0x1800c7a48  mov     [rsp+228h+var_1B0], rbx
0x1800c7a4d  mov     rcx, [rsp+228h+var_1B8]
0x1800c7a52  test    rcx, rcx
0x1800c7a55  jz      short loc_1800C7A69
0x1800c7a57  mov     [rsp+228h+var_1B8], r15
0x1800c7a5c  mov     rax, [rcx]
0x1800c7a5f  mov     rax, [rax+10h]
0x1800c7a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7a68  nop
0x1800c7a69  lea     rcx, [rsp+228h+string]
0x1800c7a71  call    _lambda_5c2cd178e30082c76c93240c01ceecaf_____lambda_5c2cd178e30082c76c93240c01ceecaf_
0x1800c7a76  mov     qword ptr [rsp+228h+hstringHeader.Reserved+10h], r15
0x1800c7a7e  mov     r9d, 28h ; '('; unsigned int
0x1800c7a84  lea     r8d, [r9+1]; unsigned int
0x1800c7a88  lea     rdx, ?RuntimeClass_Windows_System_Threading_ThreadPoolTimer@@3QBGB; "Windows.System.Threading.ThreadPoolTime"...
0x1800c7a8f  lea     rcx, [rsp+228h+string]; hstringHeader
0x1800c7a97  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c7a9c  mov     rdi, qword ptr [rsp+228h+hstringHeader.Reserved+10h]
0x1800c7aa4  lea     rcx, [rsp+228h+var_1E8]
0x1800c7aa9  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c7aae  lea     r8, [rsp+228h+var_1E8]
0x1800c7ab3  lea     rdx, _GUID_1a8a9d02_e482_461b_b8c7_8efad1cce590
0x1800c7aba  mov     rcx, rdi
0x1800c7abd  call    cs:__imp_RoGetActivationFactory
0x1800c7ac4  nop     dword ptr [rax+rax+00h]
0x1800c7ac9  mov     edi, eax
0x1800c7acb  test    eax, eax
0x1800c7acd  jns     loc_1800C7B66
0x1800c7ad3  mov     rcx, [rsp+228h]; this
0x1800c7adb  mov     r9d, eax; char *
0x1800c7ade  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x1800c7ae5  mov     edx, 1D9h; void *
0x1800c7aea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7aef  nop
0x1800c7af0  test    rbx, rbx
0x1800c7af3  jz      short loc_1800C7B05
0x1800c7af5  mov     rax, [rbx]
0x1800c7af8  mov     rcx, rbx
0x1800c7afb  mov     rax, [rax+10h]
0x1800c7aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7b04  nop
0x1800c7b05  lea     rcx, [rsp+228h+var_1C8]
0x1800c7b0a  call    ?_Decref@?$_Ptr_base@VSyncmlPackProcessor@Dynamo@@@std@@IEAAXXZ; std::_Ptr_base<Dynamo::SyncmlPackProcessor>::_Decref(void)
0x1800c7b0f  nop
0x1800c7b10  lea     rcx, [rsp+228h+var_1F0]
0x1800c7b15  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c7b1a  nop
0x1800c7b1b  lea     rcx, [rsp+228h+var_1E8]
0x1800c7b20  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c7b25  nop
0x1800c7b26  lea     rcx, [rsp+228h+var_1E0]
0x1800c7b2b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c7b30  nop
0x1800c7b31  lea     rcx, [rsp+228h+var_1D8]
0x1800c7b36  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c7b3b  nop
0x1800c7b3c  lea     rcx, [rsp+228h+var_1F8]
0x1800c7b41  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c7b46  nop
0x1800c7b47  lea     rcx, [rsp+228h+var_1D0]
0x1800c7b4c  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c7b51  nop
0x1800c7b52  lea     rcx, [rsp+228h+var_178]; this
0x1800c7b5a  call    ??1GetChannelObjectHelperActivity@MDMPushProvider@@QEAA@XZ; MDMPushProvider::GetChannelObjectHelperActivity::~GetChannelObjectHelperActivity(void)
0x1800c7b5f  mov     eax, edi
0x1800c7b61  jmp     loc_1800C7EE7
0x1800c7b66  mov     rsi, [rsp+228h+var_1E8]
0x1800c7b6b  mov     rax, [rsi]
0x1800c7b6e  mov     rdi, [rax+38h]
0x1800c7b72  lea     rcx, [rsp+228h+var_1F0]
0x1800c7b77  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c7b7c  lea     r9, [rsp+228h+var_1F0]
0x1800c7b81  mov     r8d, 17D78400h
0x1800c7b87  mov     rdx, rbx
0x1800c7b8a  mov     rcx, rsi
0x1800c7b8d  mov     rax, rdi
0x1800c7b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7b95  mov     edi, eax
0x1800c7b97  test    eax, eax
0x1800c7b99  jns     loc_1800C7C32
0x1800c7b9f  mov     rcx, [rsp+228h]; this
0x1800c7ba7  mov     r9d, eax; char *
0x1800c7baa  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x1800c7bb1  mov     edx, 1DDh; void *
0x1800c7bb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7bbb  nop
0x1800c7bbc  test    rbx, rbx
0x1800c7bbf  jz      short loc_1800C7BD1
0x1800c7bc1  mov     rax, [rbx]
0x1800c7bc4  mov     rcx, rbx
0x1800c7bc7  mov     rax, [rax+10h]
0x1800c7bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7bd0  nop
0x1800c7bd1  lea     rcx, [rsp+228h+var_1C8]
0x1800c7bd6  call    ?_Decref@?$_Ptr_base@VSyncmlPackProcessor@Dynamo@@@std@@IEAAXXZ; std::_Ptr_base<Dynamo::SyncmlPackProcessor>::_Decref(void)
0x1800c7bdb  nop
0x1800c7bdc  lea     rcx, [rsp+228h+var_1F0]
0x1800c7be1  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c7be6  nop
0x1800c7be7  lea     rcx, [rsp+228h+var_1E8]
0x1800c7bec  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
  ... truncated ...
```
