# winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::SemanticSearchConfigManager(void)

- ea: `0x1800d4b50`
- end: `0x1800d4dcb`
- name: `??0SemanticSearchConfigManager@implementation@SemanticSearch@Indexer@Windows@winrt@@QEAA@XZ`
- size: `635`
- prototype: `__int64 __fastcall(winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180185c64`

## callees

- `0x180012318`
- `0x1800ce7c0`
- `0x1800d0914`
- `0x1800d3368`
- `0x1800d4b50`
- `0x1800d4de0`
- `0x1800d4dfc`
- `0x1800d4ebc`
- `0x1800d4f3c`
- `0x1800e2374`
- `0x1801884a8`
- `0x1801885c8`
- `0x18018950c`
- `0x180189618`
- `0x1801908d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d4c03`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d4c5d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d4cb7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d4c03`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d4c5d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d4cb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4cd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4cd6`

## string_xrefs

- `0x1800d4c40`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\semanticsearchconfigmanager.cpp`
- `0x1800d4c9a`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\semanticsearchconfigmanager.cpp`
- `0x1800d4cf4`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\semanticsearchconfigmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager *__fastcall winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::SemanticSearchConfigManager(
        winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager *this)
{
  signed int LastError; // eax
  signed int v3; // eax
  signed int v4; // eax
  __int64 *Instance; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  std::_Ref_count_base *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v12; // [rsp+20h] [rbp-10h] BYREF
  std::_Ref_count_base *v13; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  HANDLE EventW; // [rsp+68h] [rbp+38h] BYREF

  winrt::impl::producers_base<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager,std::tuple<winrt::Windows::Indexer::SemanticSearch::SemanticSearchConfigManager>>::producers_base<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager,std::tuple<winrt::Windows::Indexer::SemanticSearch::SemanticSearchConfigManager>>((char *)this + 16);
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)this + 1) = 1;
  *(_QWORD *)this = &winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::`vftable';
  *((_DWORD *)this + 6) = 17;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_WORD *)this + 32) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_BYTE *)this + 84) = 0;
  *((_DWORD *)this + 22) = 0;
  *((_BYTE *)this + 92) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_BYTE *)this + 104) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  EventW = CreateEventW(0, 1, 1, 0);
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
    (char *)this + 32,
    &EventW);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&EventW);
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( !*((_QWORD *)this + 4) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\semanticsearchconfigmanager.cpp",
      (const char *)(unsigned int)LastError,
      v12);
  EventW = CreateEventW(0, 1, 1, 0);
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
    (char *)this + 40,
    &EventW);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&EventW);
  v3 = GetLastError();
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  if ( !*((_QWORD *)this + 5) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\semanticsearchconfigmanager.cpp",
      (const char *)(unsigned int)v3,
      v12);
  EventW = CreateEventW(0, 1, 0, 0);
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
    (char *)this + 48,
    &EventW);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&EventW);
  v4 = GetLastError();
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  if ( !*((_QWORD *)this + 6) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\semanticsearchconfigmanager.cpp",
      (const char *)(unsigned int)v4,
      v12);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55122781>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55122781>::GetImpl'::`2'::impl) )
    *((_BYTE *)this + 81) = GetIsInitialIndexingComplete();
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56253827>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56253827>::GetImpl'::`2'::impl) )
  {
    Instance = (__int64 *)Windows::Indexer::SemanticSearch::SemanticIndexingHealthMonitor::GetInstance(&v12);
    v6 = *Instance;
    v7 = Instance[1];
    *Instance = 0;
    Instance[1] = 0;
    *((_QWORD *)this + 15) = v6;
    v8 = (std::_Ref_count_base *)*((_QWORD *)this + 16);
    *((_QWORD *)this + 16) = v7;
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::GetCachedVariantState(v9, &EventW);
LABEL_24:
    *((_DWORD *)this + 25) = HIDWORD(EventW);
    _InterlockedExchange((volatile __int32 *)this + 24, GetNumberOfFilesForSemanticIndexingOnBattery());
    return this;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56981110>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110>::GetCachedVariantState(v10, &EventW);
    goto LABEL_24;
  }
  return this;
}

```

## disassembly

```asm
0x1800d4b50  mov     [rsp-28h+arg_10], rbx
0x1800d4b55  mov     [rsp-28h+arg_18], rsi
0x1800d4b5a  mov     [rsp-28h+arg_0], rcx
0x1800d4b5f  push    rbp
0x1800d4b60  push    rdi
0x1800d4b61  push    r13
0x1800d4b63  push    r14
0x1800d4b65  push    r15
0x1800d4b67  mov     rbp, rsp
0x1800d4b6a  sub     rsp, 30h
0x1800d4b6e  mov     rbx, rcx
0x1800d4b71  add     rcx, 10h
0x1800d4b75  call    ??0?$producers_base@USemanticSearchConfigManager@implementation@SemanticSearch@Indexer@Windows@winrt@@V?$tuple@USemanticSearchConfigManager@SemanticSearch@Indexer@Windows@winrt@@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager,std::tuple<winrt::Windows::Indexer::SemanticSearch::SemanticSearchConfigManager>>::producers_base<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager,std::tuple<winrt::Windows::Indexer::SemanticSearch::SemanticSearchConfigManager>>(void)
0x1800d4b7a  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800d4b81  mov     r13d, 1
0x1800d4b87  mov     [rbx+8], r13
0x1800d4b8b  lea     rax, ??_7SemanticSearchConfigManager@implementation@SemanticSearch@Indexer@Windows@winrt@@6B@; const winrt::Windows::Indexer::SemanticSearch::implementation::SemanticSearchConfigManager::`vftable'
0x1800d4b92  mov     [rbx], rax
0x1800d4b95  mov     dword ptr [rbx+18h], 11h
0x1800d4b9c  lea     rsi, [rbx+20h]
0x1800d4ba0  xor     r15d, r15d
0x1800d4ba3  mov     [rsi], r15
0x1800d4ba6  lea     rdi, [rbx+28h]
0x1800d4baa  mov     [rdi], r15
0x1800d4bad  lea     r14, [rbx+30h]
0x1800d4bb1  mov     [r14], r15
0x1800d4bb4  xor     eax, eax
0x1800d4bb6  mov     [rbx+38h], rax
0x1800d4bba  mov     [rbx+40h], r15w
0x1800d4bbf  mov     [rbx+48h], r15
0x1800d4bc3  mov     [rbx+50h], r15d
0x1800d4bc7  mov     [rbx+54h], r15b
0x1800d4bcb  mov     [rbx+58h], r15d
0x1800d4bcf  mov     [rbx+5Ch], r15b
0x1800d4bd3  mov     [rbx+60h], r15
0x1800d4bd7  mov     [rbx+68h], r15b
0x1800d4bdb  mov     [rbx+70h], r15
0x1800d4bdf  mov     [rbx+78h], r15
0x1800d4be3  mov     [rbx+80h], r15
0x1800d4bea  mov     [rbx+88h], r15
0x1800d4bf1  mov     [rbx+90h], r15
0x1800d4bf8  xor     r9d, r9d; lpName
0x1800d4bfb  mov     r8d, r13d; bInitialState
0x1800d4bfe  mov     edx, r13d; bManualReset
0x1800d4c01  xor     ecx, ecx; lpEventAttributes
0x1800d4c03  call    cs:__imp_CreateEventW
0x1800d4c09  mov     [rbp+arg_8], rax
0x1800d4c0d  lea     rdx, [rbp+arg_8]
0x1800d4c11  mov     rcx, rsi
0x1800d4c14  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x1800d4c19  lea     rcx, [rbp+arg_8]
0x1800d4c1d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800d4c22  call    cs:__imp_GetLastError
0x1800d4c28  test    eax, eax
0x1800d4c2a  jle     short loc_1800D4C34
0x1800d4c2c  movzx   eax, ax
0x1800d4c2f  or      eax, 80070000h
0x1800d4c34  mov     rcx, [rbp+28h]; this
0x1800d4c38  cmp     [rsi], r15
0x1800d4c3b  jnz     short loc_1800D4C52
0x1800d4c3d  mov     r9d, eax; char *
0x1800d4c40  lea     r8, aOnecoreuapBase_159; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800d4c47  mov     edx, 2Bh ; '+'; void *
0x1800d4c4c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d4c52  xor     r9d, r9d; lpName
0x1800d4c55  mov     r8d, r13d; bInitialState
0x1800d4c58  mov     edx, r13d; bManualReset
0x1800d4c5b  xor     ecx, ecx; lpEventAttributes
0x1800d4c5d  call    cs:__imp_CreateEventW
0x1800d4c63  mov     [rbp+arg_8], rax
0x1800d4c67  lea     rdx, [rbp+arg_8]
0x1800d4c6b  mov     rcx, rdi
0x1800d4c6e  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x1800d4c73  lea     rcx, [rbp+arg_8]
0x1800d4c77  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800d4c7c  call    cs:__imp_GetLastError
0x1800d4c82  test    eax, eax
0x1800d4c84  jle     short loc_1800D4C8E
0x1800d4c86  movzx   eax, ax
0x1800d4c89  or      eax, 80070000h
0x1800d4c8e  mov     rcx, [rbp+28h]; this
0x1800d4c92  cmp     [rdi], r15
0x1800d4c95  jnz     short loc_1800D4CAC
0x1800d4c97  mov     r9d, eax; char *
0x1800d4c9a  lea     r8, aOnecoreuapBase_159; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800d4ca1  mov     edx, 2Dh ; '-'; void *
0x1800d4ca6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d4cac  xor     r9d, r9d; lpName
0x1800d4caf  xor     r8d, r8d; bInitialState
0x1800d4cb2  mov     edx, r13d; bManualReset
0x1800d4cb5  xor     ecx, ecx; lpEventAttributes
0x1800d4cb7  call    cs:__imp_CreateEventW
0x1800d4cbd  mov     [rbp+arg_8], rax
0x1800d4cc1  lea     rdx, [rbp+arg_8]
0x1800d4cc5  mov     rcx, r14
0x1800d4cc8  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x1800d4ccd  lea     rcx, [rbp+arg_8]
0x1800d4cd1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800d4cd6  call    cs:__imp_GetLastError
0x1800d4cdc  test    eax, eax
0x1800d4cde  jle     short loc_1800D4CE8
0x1800d4ce0  movzx   eax, ax
0x1800d4ce3  or      eax, 80070000h
0x1800d4ce8  mov     rcx, [rbp+28h]; this
0x1800d4cec  cmp     [r14], r15
0x1800d4cef  jnz     short loc_1800D4D06
0x1800d4cf1  mov     r9d, eax; char *
0x1800d4cf4  lea     r8, aOnecoreuapBase_159; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800d4cfb  mov     edx, 2Fh ; '/'; void *
0x1800d4d00  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d4d06  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55122781@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55122781@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55122781> `wil::Feature<__WilFeatureTraits_Feature_55122781>::GetImpl(void)'::`2'::impl
0x1800d4d0d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55122781@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55122781>::__private_IsEnabled(void)
0x1800d4d12  test    al, al
0x1800d4d14  jz      short loc_1800D4D1E
0x1800d4d16  call    ?GetIsInitialIndexingComplete@@YA_NXZ; GetIsInitialIndexingComplete(void)
0x1800d4d1b  mov     [rbx+51h], al
0x1800d4d1e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56253827@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56253827@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56253827> `wil::Feature<__WilFeatureTraits_Feature_56253827>::GetImpl(void)'::`2'::impl
0x1800d4d25  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56253827@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56253827>::__private_IsEnabled(void)
0x1800d4d2a  test    al, al
0x1800d4d2c  jz      short loc_1800D4D6F
0x1800d4d2e  lea     rcx, [rbp+var_10]
0x1800d4d32  call    ?GetInstance@SemanticIndexingHealthMonitor@SemanticSearch@Indexer@Windows@@SA?AV?$shared_ptr@USemanticIndexingHealthMonitor@SemanticSearch@Indexer@Windows@@@std@@XZ; Windows::Indexer::SemanticSearch::SemanticIndexingHealthMonitor::GetInstance(void)
0x1800d4d37  mov     rcx, [rax]
0x1800d4d3a  mov     rdx, [rax+8]
0x1800d4d3e  mov     [rax], r15
0x1800d4d41  mov     [rax+8], r15
0x1800d4d45  mov     [rbx+78h], rcx
0x1800d4d49  mov     rcx, [rbx+80h]; this
0x1800d4d50  mov     [rbx+80h], rdx
0x1800d4d57  test    rcx, rcx
0x1800d4d5a  jz      short loc_1800D4D61
0x1800d4d5c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d4d61  mov     rcx, [rbp+var_8]; this
0x1800d4d65  test    rcx, rcx
0x1800d4d68  jz      short loc_1800D4D6F
0x1800d4d6a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d4d6f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55904201@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55904201@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201> `wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl(void)'::`2'::impl
0x1800d4d76  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55904201@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(void)
0x1800d4d7b  test    al, al
0x1800d4d7d  jz      short loc_1800D4D8A
0x1800d4d7f  lea     rdx, [rbp+arg_8]
0x1800d4d83  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_55904201@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::GetCachedVariantState(void)
0x1800d4d88  jmp     short loc_1800D4DA3
0x1800d4d8a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56981110@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56981110@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110> `wil::Feature<__WilFeatureTraits_Feature_56981110>::GetImpl(void)'::`2'::impl
0x1800d4d91  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56981110@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110>::__private_IsEnabled(void)
0x1800d4d96  test    al, al
0x1800d4d98  jz      short loc_1800D4DB1
0x1800d4d9a  lea     rdx, [rbp+arg_8]
0x1800d4d9e  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_56981110@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110>::GetCachedVariantState(void)
0x1800d4da3  mov     eax, dword ptr [rbp+arg_8+4]
0x1800d4da6  mov     [rbx+64h], eax
0x1800d4da9  call    ?GetNumberOfFilesForSemanticIndexingOnBattery@@YAKXZ; GetNumberOfFilesForSemanticIndexingOnBattery(void)
0x1800d4dae  xchg    eax, [rbx+60h]
0x1800d4db1  mov     rax, rbx
0x1800d4db4  mov     rbx, [rsp+30h+arg_10]
0x1800d4db9  mov     rsi, [rsp+30h+arg_18]
0x1800d4dbe  add     rsp, 30h
0x1800d4dc2  pop     r15
0x1800d4dc4  pop     r14
0x1800d4dc6  pop     r13
0x1800d4dc8  pop     rdi
0x1800d4dc9  pop     rbp
0x1800d4dca  retn
```
