# DAS::DevnodeManagment::DevnodeFactory::DevnodeFactory(ushort const *,ushort const *,void *,std::shared_ptr<ProviderContext> &)

- ea: `0x18005bb14`
- end: `0x18005beae`
- name: `??0DevnodeFactory@DevnodeManagment@DAS@@QEAA@PEBG0PEAXAEAV?$shared_ptr@VProviderContext@@@std@@@Z`
- size: `922`
- prototype: `char *__fastcall(char *pv, __int64, const char *Src, HANDLE hSourceHandle, _QWORD *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004dac0`

## callees

- `0x180005770`
- `0x1800074c0`
- `0x1800186ac`
- `0x1800190f8`
- `0x18001a350`
- `0x18001eae0`
- `0x18002482c`
- `0x180024888`
- `0x180024d60`
- `0x1800290c4`
- `0x180033f14`
- `0x1800344e4`
- `0x180036e04`
- `0x18003bc80`
- `0x180044ce8`
- `0x18004f740`
- `0x18005baa8`
- `0x18005bb14`
- `0x18005c118`
- `0x18005cfe4`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18005bc86`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18005bc86`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005be00`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005be00`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005be39`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005be39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005bd9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005bda5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005bd9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005bda5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005bddb`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005bddb`

## string_xrefs

- `0x18005bce9`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x18005bd38`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`

## pseudocode

```c
char *__fastcall DAS::DevnodeManagment::DevnodeFactory::DevnodeFactory(
        char *pv,
        __int64 a2,
        const char *Src,
        HANDLE hSourceHandle,
        _QWORD *a5)
{
  __int64 v9; // rdx
  PTP_WORK *v10; // r15
  char *v11; // rbx
  const char *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  int PerUserSubKey; // eax
  PSRWLOCK v17; // rbx
  int Store; // eax
  Windows::Devices::Pnp::Internal::PnpObjectStore *v19; // rax
  HANDLE CurrentProcess; // rbx
  HANDLE v21; // rax
  unsigned int v22; // r8d
  const char *v23; // r9
  PTP_WORK ThreadpoolWork; // rax
  unsigned int v25; // r8d
  const char *v26; // r9
  int v27; // edx
  int v28; // r8d
  int dwDesiredAccess; // [rsp+20h] [rbp-A8h]
  unsigned __int16 *v31[2]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v32[32]; // [rsp+50h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v31[1] = (unsigned __int16 *)pv;
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAepDevnodeFactory,IServiceProvider,IAepDevnodeCreationCallback>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAepDevnodeFactory,IServiceProvider,IAepDevnodeCreationCallback>(pv);
  *(_QWORD *)pv = &DAS::DevnodeManagment::DevnodeFactory::`vftable';
  *((_QWORD *)pv + 1) = &DAS::DevnodeManagment::DevnodeFactory::`vftable'{for `IServiceProvider'};
  *((_QWORD *)pv + 2) = &DAS::DevnodeManagment::DevnodeFactory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAepDevnodeCreationCallback>'};
  std::wstring::wstring(pv + 32, a2);
  std::wstring::wstring(pv + 64);
  std::shared_ptr<ProviderContext>::shared_ptr<ProviderContext>((_QWORD *)pv + 12, a5);
  *((_QWORD *)pv + 14) = 0;
  *((_QWORD *)pv + 15) = 0;
  std::vector<std::wstring>::vector<std::wstring>(pv + 128);
  *((_QWORD *)pv + 19) = v9;
  *((_QWORD *)pv + 20) = v9;
  *((_QWORD *)pv + 21) = v9;
  *((_QWORD *)pv + 22) = v9;
  *((_QWORD *)pv + 23) = v9;
  *((_QWORD *)pv + 25) = v9;
  *((_QWORD *)pv + 26) = v9;
  *((_DWORD *)pv + 54) = v9;
  *((_QWORD *)pv + 28) = 0;
  pv[232] = 1;
  *((_QWORD *)pv + 30) = v9;
  v10 = (PTP_WORK *)(pv + 248);
  *((_QWORD *)pv + 31) = v9;
  v11 = pv + 256;
  *((_QWORD *)pv + 32) = v9;
  *((_QWORD *)pv + 33) = v9;
  *((_QWORD *)pv + 34) = v9;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v12 = Src;
    if ( !Src )
      v12 = L"-none passed-";
    WPP_RECORDER_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v9,
      (int)&WPP_f484a48a2ca63e117155ee67294b2084_Traceguids,
      v9 + 10,
      &WPP_f484a48a2ca63e117155ee67294b2084_Traceguids,
      a2,
      (__int64)v12);
  }
  *((_QWORD *)pv + 37) = pv + 288;
  *((_QWORD *)pv + 36) = pv + 288;
  InitializeSRWLock((PSRWLOCK)pv + 35);
  if ( Src )
  {
    v13 = std::wstring::wstring(v32, Src);
    std::wstring::operator=(pv + 64, v13);
    std::wstring::_Tidy_deallocate(v32, v14, v15);
    v31[0] = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v31,
      0);
    PerUserSubKey = DAS::DevnodeManagment::DevnodeManager::MakePerUserSubKey((const unsigned __int16 *)Src, v31);
    if ( PerUserSubKey < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
        (const char *)(unsigned int)PerUserSubKey,
        dwDesiredAccess);
    v17 = g_StoreManager;
    Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(pv + 112);
    Store = Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(v17, -2147483645, v31[0], 8);
    if ( Store < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
        (const char *)(unsigned int)Store,
        (_DWORD)pv + 112);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v31);
    v11 = pv + 256;
  }
  else
  {
    Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(pv + 112);
    v19 = g_AepStore;
    if ( g_AepStore )
    {
      (*(void (__fastcall **)(Windows::Devices::Pnp::Internal::PnpObjectStore *))(*(_QWORD *)g_AepStore + 8LL))(g_AepStore);
      v19 = g_AepStore;
    }
    *((_QWORD *)pv + 14) = v19;
  }
  if ( hSourceHandle )
  {
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v11,
      0);
    CurrentProcess = GetCurrentProcess();
    v21 = GetCurrentProcess();
    if ( !DuplicateHandle(v21, hSourceHandle, CurrentProcess, (LPHANDLE)pv + 32, 0, 0, 2u) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xA7, v22, v23);
  }
  ThreadpoolWork = CreateThreadpoolWork(DAS::DevnodeManagment::DevnodeFactory::SetupWorkCallback, pv, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
    pv + 248,
    ThreadpoolWork);
  if ( !*v10 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xAC, v25, v26);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(pv + 240);
  SubmitThreadpoolWork(*v10);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( !Src )
      Src = L"-none passed-";
    WPP_RECORDER_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v27,
      v28,
      11,
      &WPP_f484a48a2ca63e117155ee67294b2084_Traceguids,
      a2,
      (__int64)Src);
  }
  return pv;
}

```

## disassembly

```asm
0x18005bb14  push    rbx
0x18005bb16  push    rbp
0x18005bb17  push    rsi
0x18005bb18  push    rdi
0x18005bb19  push    r12
0x18005bb1b  push    r13
0x18005bb1d  push    r14
0x18005bb1f  push    r15
0x18005bb21  sub     rsp, 88h
0x18005bb28  mov     rax, cs:__security_cookie
0x18005bb2f  xor     rax, rsp
0x18005bb32  mov     [rsp+0C8h+var_58], rax
0x18005bb37  mov     r13, r9
0x18005bb3a  mov     rsi, r8
0x18005bb3d  mov     r12, rdx
0x18005bb40  mov     rdi, rcx
0x18005bb43  mov     [rsp+0C8h+var_80], rcx
0x18005bb48  mov     rbx, [rsp+0C8h+arg_20]
0x18005bb50  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAepDevnodeFactory@@UIServiceProvider@@UIAepDevnodeCreationCallback@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAepDevnodeFactory,IServiceProvider,IAepDevnodeCreationCallback>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAepDevnodeFactory,IServiceProvider,IAepDevnodeCreationCallback>(void)
0x18005bb55  nop
0x18005bb56  lea     rax, ??_7DevnodeFactory@DevnodeManagment@DAS@@6B@; const DAS::DevnodeManagment::DevnodeFactory::`vftable'
0x18005bb5d  mov     [rdi], rax
0x18005bb60  lea     rax, ??_7DevnodeFactory@DevnodeManagment@DAS@@6BIServiceProvider@@@; const DAS::DevnodeManagment::DevnodeFactory::`vftable'{for `IServiceProvider'}
0x18005bb67  mov     [rdi+8], rax
0x18005bb6b  lea     rax, ??_7DevnodeFactory@DevnodeManagment@DAS@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAepDevnodeCreationCallback@@@Details@WRL@Microsoft@@@; const DAS::DevnodeManagment::DevnodeFactory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAepDevnodeCreationCallback>'}
0x18005bb72  mov     [rdi+10h], rax
0x18005bb76  lea     rcx, [rdi+20h]
0x18005bb7a  mov     rdx, r12
0x18005bb7d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005bb82  nop
0x18005bb83  lea     rcx, [rdi+40h]
0x18005bb87  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005bb8c  nop
0x18005bb8d  lea     rcx, [rdi+60h]
0x18005bb91  mov     rdx, rbx
0x18005bb94  call    ??0?$shared_ptr@VProviderContext@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ProviderContext>::shared_ptr<ProviderContext>(std::shared_ptr<ProviderContext> const &)
0x18005bb99  nop
0x18005bb9a  lea     r14, [rdi+70h]
0x18005bb9e  xor     edx, edx
0x18005bba0  mov     [r14], rdx
0x18005bba3  xor     eax, eax
0x18005bba5  mov     [rdi+78h], rax
0x18005bba9  lea     rcx, [rdi+80h]
0x18005bbb0  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x18005bbb5  nop
0x18005bbb6  mov     [rdi+98h], rdx
0x18005bbbd  mov     [rdi+0A0h], rdx
0x18005bbc4  mov     [rdi+0A8h], rdx
0x18005bbcb  mov     [rdi+0B0h], rdx
0x18005bbd2  mov     [rdi+0B8h], rdx
0x18005bbd9  mov     [rdi+0C8h], rdx
0x18005bbe0  mov     [rdi+0D0h], rdx
0x18005bbe7  mov     [rdi+0D8h], edx
0x18005bbed  xor     eax, eax
0x18005bbef  mov     [rdi+0E0h], rax
0x18005bbf6  mov     byte ptr [rdi+0E8h], 1
0x18005bbfd  mov     [rdi+0F0h], rdx
0x18005bc04  lea     r15, [rdi+0F8h]
0x18005bc0b  mov     [r15], rdx
0x18005bc0e  lea     rbx, [rdi+100h]
0x18005bc15  mov     [rbx], rdx
0x18005bc18  mov     [rdi+108h], rdx
0x18005bc1f  mov     [rdi+110h], rdx
0x18005bc26  lea     rax, WPP_RECORDER_INITIALIZED
0x18005bc2d  lea     rcx, aNonePassed; "-none passed-"
0x18005bc34  lea     r8, WPP_f484a48a2ca63e117155ee67294b2084_Traceguids; int
0x18005bc3b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005bc42  jz      short loc_18005BC71
0x18005bc44  mov     rax, rsi
0x18005bc47  test    rsi, rsi
0x18005bc4a  cmovz   rax, rcx
0x18005bc4e  lea     r9d, [rdx+0Ah]; int
0x18005bc52  mov     qword ptr [rsp+0C8h+dwOptions], rax; __int64
0x18005bc57  mov     qword ptr [rsp+0C8h+bInheritHandle], r12; __int64
0x18005bc5c  mov     qword ptr [rsp+0C8h+dwDesiredAccess], r8; int
0x18005bc61  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bc68  mov     rcx, [rcx+28h]; int
0x18005bc6c  call    WPP_RECORDER_SF_SS
0x18005bc71  lea     rax, [rdi+120h]
0x18005bc78  mov     [rax+8], rax
0x18005bc7c  mov     [rax], rax
0x18005bc7f  lea     rcx, [rdi+118h]; SRWLock
0x18005bc86  call    cs:__imp_InitializeSRWLock
0x18005bc8c  test    rsi, rsi
0x18005bc8f  jz      loc_18005BD5D
0x18005bc95  mov     rdx, rsi
0x18005bc98  lea     rcx, [rsp+0C8h+var_78]
0x18005bc9d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005bca2  mov     rdx, rax
0x18005bca5  lea     rcx, [rdi+40h]
0x18005bca9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005bcae  lea     rcx, [rsp+0C8h+var_78]
0x18005bcb3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005bcb8  mov     [rsp+0C8h+var_88], 0
0x18005bcc1  xor     edx, edx
0x18005bcc3  lea     rcx, [rsp+0C8h+var_88]
0x18005bcc8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005bccd  lea     rdx, [rsp+0C8h+var_88]; unsigned __int16 **
0x18005bcd2  mov     rcx, rsi; Src
0x18005bcd5  call    ?MakePerUserSubKey@DevnodeManager@DevnodeManagment@DAS@@SAJPEBGPEAPEAG@Z; DAS::DevnodeManagment::DevnodeManager::MakePerUserSubKey(ushort const *,ushort * *)
0x18005bcda  mov     rcx, [rsp+0C8h]; this
0x18005bce2  test    eax, eax
0x18005bce4  jns     short loc_18005BCFB
0x18005bce6  mov     r9d, eax; char *
0x18005bce9  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18005bcf0  mov     edx, 92h; void *
0x18005bcf5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18005bcfb  mov     rbx, cs:?g_StoreManager@@3V?$unique_ptr@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@U?$default_delete@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@@std@@@std@@A; std::unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager> g_StoreManager
0x18005bd02  mov     rcx, r14
0x18005bd05  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x18005bd0a  mov     qword ptr [rsp+0C8h+dwDesiredAccess], r14; int
0x18005bd0f  mov     r9d, 8
0x18005bd15  mov     r8, [rsp+0C8h+var_88]
0x18005bd1a  mov     rdx, 0FFFFFFFF80000003h
0x18005bd21  mov     rcx, rbx
0x18005bd24  call    ?GetStore@PnpObjectStoreManager@Internal@Pnp@Devices@Windows@@QEAAJPEAUHKEY__@@PEBGW4_PNP_OBJECT_TYPE@@PEAPEAVPnpObjectStore@2345@@Z; Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(HKEY__ *,ushort const *,_PNP_OBJECT_TYPE,Windows::Devices::Pnp::Internal::PnpObjectStore * *)
0x18005bd29  mov     rcx, [rsp+0C8h]; this
0x18005bd31  test    eax, eax
0x18005bd33  jns     short loc_18005BD4A
0x18005bd35  mov     r9d, eax; char *
0x18005bd38  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18005bd3f  mov     edx, 97h; void *
0x18005bd44  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18005bd4a  lea     rcx, [rsp+0C8h+var_88]
0x18005bd4f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005bd54  lea     rbx, [rdi+100h]
0x18005bd5b  jmp     short loc_18005BD8D
0x18005bd5d  mov     rcx, r14
0x18005bd60  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x18005bd65  mov     rax, cs:?g_AepStore@@3V?$ComPtr@VPnpObjectStore@Internal@Pnp@Devices@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Devices::Pnp::Internal::PnpObjectStore> g_AepStore
0x18005bd6c  test    rax, rax
0x18005bd6f  jz      short loc_18005BD8A
0x18005bd71  mov     rcx, [rax]
0x18005bd74  mov     rdx, [rcx+8]
0x18005bd78  mov     rcx, rax
0x18005bd7b  mov     rax, rdx
0x18005bd7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd83  mov     rax, cs:?g_AepStore@@3V?$ComPtr@VPnpObjectStore@Internal@Pnp@Devices@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Devices::Pnp::Internal::PnpObjectStore> g_AepStore
0x18005bd8a  mov     [r14], rax
0x18005bd8d  test    r13, r13
0x18005bd90  jz      short loc_18005BDF3
0x18005bd92  xor     edx, edx
0x18005bd94  mov     rcx, rbx
0x18005bd97  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18005bd9c  call    cs:__imp_GetCurrentProcess
0x18005bda2  mov     rbx, rax
0x18005bda5  call    cs:__imp_GetCurrentProcess
0x18005bdab  mov     rbp, [rsp+0C8h]
0x18005bdb3  mov     [rsp+0C8h+dwOptions], 2; dwOptions
0x18005bdbb  mov     [rsp+0C8h+bInheritHandle], 0; bInheritHandle
0x18005bdc3  mov     [rsp+0C8h+dwDesiredAccess], 0; dwDesiredAccess
0x18005bdcb  lea     r9, [rdi+100h]; lpTargetHandle
0x18005bdd2  mov     r8, rbx; hTargetProcessHandle
0x18005bdd5  mov     rdx, r13; hSourceHandle
0x18005bdd8  mov     rcx, rax; hSourceProcessHandle
0x18005bddb  call    cs:__imp_DuplicateHandle
0x18005bde1  test    eax, eax
0x18005bde3  jnz     short loc_18005BDF3
0x18005bde5  mov     edx, 0A7h; void *
0x18005bdea  mov     rcx, rbp; this
0x18005bded  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005bdf3  xor     r8d, r8d; pcbe
0x18005bdf6  mov     rdx, rdi; pv
0x18005bdf9  lea     rcx, ?SetupWorkCallback@DevnodeFactory@DevnodeManagment@DAS@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18005be00  call    cs:__imp_CreateThreadpoolWork
0x18005be06  mov     rdx, rax
0x18005be09  mov     rcx, r15
0x18005be0c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18005be11  mov     rcx, [rsp+0C8h]; this
0x18005be19  cmp     qword ptr [r15], 0
0x18005be1d  jnz     short loc_18005BE2A
0x18005be1f  mov     edx, 0ACh; void *
0x18005be24  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005be2a  lea     rcx, [rdi+0F0h]
0x18005be31  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18005be36  mov     rcx, [r15]; pwk
0x18005be39  call    cs:__imp_SubmitThreadpoolWork
0x18005be3f  lea     rax, WPP_RECORDER_INITIALIZED
0x18005be46  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005be4d  jz      short loc_18005BE8A
0x18005be4f  test    rsi, rsi
0x18005be52  lea     rax, aNonePassed; "-none passed-"
0x18005be59  cmovz   rsi, rax
0x18005be5d  mov     r9d, 0Bh; int
0x18005be63  mov     qword ptr [rsp+0C8h+dwOptions], rsi; __int64
0x18005be68  mov     qword ptr [rsp+0C8h+bInheritHandle], r12; __int64
0x18005be6d  lea     rax, WPP_f484a48a2ca63e117155ee67294b2084_Traceguids
0x18005be74  mov     qword ptr [rsp+0C8h+dwDesiredAccess], rax; MessageGuid
0x18005be79  mov     rcx, cs:WPP_GLOBAL_Control
0x18005be80  mov     rcx, [rcx+28h]; int
0x18005be84  call    WPP_RECORDER_SF_SS
0x18005be89  nop
0x18005be8a  mov     rax, rdi
0x18005be8d  mov     rcx, [rsp+0C8h+var_58]
0x18005be92  xor     rcx, rsp; StackCookie
0x18005be95  call    __security_check_cookie
0x18005be9a  add     rsp, 88h
0x18005bea1  pop     r15
0x18005bea3  pop     r14
0x18005bea5  pop     r13
0x18005bea7  pop     r12
0x18005bea9  pop     rdi
0x18005beaa  pop     rsi
0x18005beab  pop     rbp
0x18005beac  pop     rbx
0x18005bead  retn
```
