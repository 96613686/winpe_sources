# Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::~ApiSamplingHost(void)

- ea: `0x1800c8288`
- end: `0x1800c8442`
- name: `??1ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@UEAA@XZ`
- size: `442`
- prototype: `void __fastcall(Windows::Compat::Inventory::ApiSampling::ApiSamplingHost *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800c84d0`

## callees

- `0x1800074f0`
- `0x1800108d4`
- `0x1800152d0`
- `0x1800c8288`
- `0x1800c88d8`
- `0x1800ca29c`
- `0x1800ca33c`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c83dc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c83dc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c8374`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c8374`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c83cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c83cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c83a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c83a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c83f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c83f5`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800c82c2`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800c82fc`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800c82c2`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800c82fc`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800c833b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800c833b`

## string_xrefs

- `0x1800c841e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800c8430`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800c82e5`: `Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingUninitialize`
- `0x1800c831f`: `Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingUninitialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::~ApiSamplingHost(
        Windows::Compat::Inventory::ApiSampling::ApiSamplingHost *this)
{
  void *v2; // rcx
  DWORD v3; // eax
  void *v4; // rcx
  DWORD v5; // eax
  void *v6; // rdx
  void (*v7)(void); // rax
  const char *v8; // r9
  char *v9; // rdi
  struct _RTL_CRITICAL_SECTION *v10; // rsi
  HMODULE v11; // rcx
  void *v12; // rcx
  const char *v13; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)this = &Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::`vftable';
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_CompatApiSamplingNotificationCrash>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_CompatApiSamplingNotificationCrash>::GetImpl'::`2'::impl) )
  {
    v2 = (void *)*((_QWORD *)this + 3);
    if ( v2 )
    {
      v3 = PowerSettingUnregisterNotification(v2);
      *((_QWORD *)this + 3) = 0;
      if ( v3 )
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingUninitialize",
          846,
          "Failed to unregister GUID_POWER_SAVING_STATUS with error [%d]",
          v3);
    }
    v4 = (void *)*((_QWORD *)this + 4);
    if ( v4 )
    {
      v5 = PowerSettingUnregisterNotification(v4);
      *((_QWORD *)this + 4) = 0;
      if ( v5 )
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingUninitialize",
          857,
          "Failed to unregister GUID_POWERSCHEME_PERSONALITY with error [%d]",
          v5);
    }
  }
  v6 = (void *)*((_QWORD *)this + 2);
  if ( v6 )
  {
    DeleteTimerQueueTimer(0, v6, 0);
    *((_QWORD *)this + 2) = 0;
  }
  if ( *((_QWORD *)this + 11) && *((_BYTE *)this + 42) )
  {
    Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingStop(this);
    *((_BYTE *)this + 42) = 0;
  }
  v7 = (void (*)(void))*((_QWORD *)this + 13);
  if ( v7 )
    v7();
  if ( !SetEvent(*((HANDLE *)this + 1)) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v8);
  if ( tipTest )
  {
    v9 = (char *)tipTest + 8;
    v10 = (struct _RTL_CRITICAL_SECTION *)((char *)tipTest + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)tipTest + 5);
    *((_DWORD *)v9 + 16) |= 0x300u;
    if ( *((_QWORD *)v9 + 30) )
      tip2::details::shared_data<0,0,1>::complete_helper(v9, 2);
    if ( v10 )
      LeaveCriticalSection(v10);
  }
  v11 = (HMODULE)*((_QWORD *)this + 11);
  if ( v11 )
    FreeLibrary(v11);
  std::wstring::~wstring((char *)this + 56);
  v12 = (void *)*((_QWORD *)this + 1);
  if ( v12 && !CloseHandle(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v13);
  *(_QWORD *)this = &Windows::Compat::Inventory::Service::InvSvcTenant::`vftable';
}

```

## disassembly

```asm
0x1800c8288  mov     [rsp+arg_0], rbx
0x1800c828d  mov     [rsp+arg_8], rsi
0x1800c8292  push    rdi
0x1800c8293  sub     rsp, 30h
0x1800c8297  mov     rbx, rcx
0x1800c829a  lea     rax, ??_7ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::`vftable'
0x1800c82a1  mov     [rcx], rax
0x1800c82a4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_CompatApiSamplingNotificationCrash@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_CompatApiSamplingNotificationCrash@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_CompatApiSamplingNotificationCrash> `wil::Feature<__WilFeatureTraits_Feature_Servicing_CompatApiSamplingNotificationCrash>::GetImpl(void)'::`2'::impl
0x1800c82ab  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_CompatApiSamplingNotificationCrash@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_CompatApiSamplingNotificationCrash>::__private_IsEnabled(void)
0x1800c82b0  test    al, al
0x1800c82b2  jz      short loc_1800C832D
0x1800c82b4  mov     rcx, [rbx+18h]; RegistrationHandle
0x1800c82b8  mov     edi, 1
0x1800c82bd  test    rcx, rcx
0x1800c82c0  jz      short loc_1800C82F3
0x1800c82c2  call    cs:__imp_PowerSettingUnregisterNotification
0x1800c82c8  mov     qword ptr [rbx+18h], 0
0x1800c82d0  test    eax, eax
0x1800c82d2  jz      short loc_1800C82F3
0x1800c82d4  mov     [rsp+38h+var_18], eax
0x1800c82d8  lea     r9, aFailedToUnregi_0; "Failed to unregister GUID_POWER_SAVING_"...
0x1800c82df  mov     r8d, 34Eh
0x1800c82e5  lea     rdx, aWindowsCompatI_13; "Windows::Compat::Inventory::ApiSampling"...
0x1800c82ec  mov     ecx, edi
0x1800c82ee  call    AslLogCallPrintf
0x1800c82f3  mov     rcx, [rbx+20h]; RegistrationHandle
0x1800c82f7  test    rcx, rcx
0x1800c82fa  jz      short loc_1800C832D
0x1800c82fc  call    cs:__imp_PowerSettingUnregisterNotification
0x1800c8302  mov     qword ptr [rbx+20h], 0
0x1800c830a  test    eax, eax
0x1800c830c  jz      short loc_1800C832D
0x1800c830e  mov     [rsp+38h+var_18], eax
0x1800c8312  lea     r9, aFailedToUnregi; "Failed to unregister GUID_POWERSCHEME_P"...
0x1800c8319  mov     r8d, 359h
0x1800c831f  lea     rdx, aWindowsCompatI_13; "Windows::Compat::Inventory::ApiSampling"...
0x1800c8326  mov     ecx, edi
0x1800c8328  call    AslLogCallPrintf
0x1800c832d  mov     rdx, [rbx+10h]; Timer
0x1800c8331  test    rdx, rdx
0x1800c8334  jz      short loc_1800C8349
0x1800c8336  xor     r8d, r8d; CompletionEvent
0x1800c8339  xor     ecx, ecx; TimerQueue
0x1800c833b  call    cs:__imp_DeleteTimerQueueTimer
0x1800c8341  mov     qword ptr [rbx+10h], 0
0x1800c8349  cmp     qword ptr [rbx+58h], 0
0x1800c834e  jz      short loc_1800C8362
0x1800c8350  cmp     byte ptr [rbx+2Ah], 0
0x1800c8354  jz      short loc_1800C8362
0x1800c8356  mov     rcx, rbx; this
0x1800c8359  call    ?ApiSamplingStop@ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@AEAAXXZ; Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingStop(void)
0x1800c835e  mov     byte ptr [rbx+2Ah], 0
0x1800c8362  mov     rax, [rbx+68h]
0x1800c8366  test    rax, rax
0x1800c8369  jz      short loc_1800C8370
0x1800c836b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8370  mov     rcx, [rbx+8]; hEvent
0x1800c8374  call    cs:__imp_SetEvent
0x1800c837a  mov     rcx, [rsp+38h]; this
0x1800c837f  test    eax, eax
0x1800c8381  jz      loc_1800C8430
0x1800c8387  mov     rax, cs:?tipTest@@3V?$tip_test@V?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>> tipTest
0x1800c838e  test    rax, rax
0x1800c8391  jz      short loc_1800C83D3
0x1800c8393  lea     rdi, [rax+8]
0x1800c8397  lea     rsi, [rdi+0C0h]
0x1800c839e  mov     rcx, rsi; lpCriticalSection
0x1800c83a1  call    cs:__imp_EnterCriticalSection
0x1800c83a7  or      dword ptr [rdi+40h], 300h
0x1800c83ae  cmp     qword ptr [rdi+0F0h], 0
0x1800c83b6  jz      short loc_1800C83C5
0x1800c83b8  mov     edx, 2
0x1800c83bd  mov     rcx, rdi
0x1800c83c0  call    ?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)
0x1800c83c5  test    rsi, rsi
0x1800c83c8  jz      short loc_1800C83D3
0x1800c83ca  mov     rcx, rsi; lpCriticalSection
0x1800c83cd  call    cs:__imp_LeaveCriticalSection
0x1800c83d3  mov     rcx, [rbx+58h]; hLibModule
0x1800c83d7  test    rcx, rcx
0x1800c83da  jz      short loc_1800C83E3
0x1800c83dc  call    cs:__imp_FreeLibrary
0x1800c83e2  nop
0x1800c83e3  lea     rcx, [rbx+38h]; void *
0x1800c83e7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c83ec  mov     rcx, [rbx+8]; hObject
0x1800c83f0  test    rcx, rcx
0x1800c83f3  jz      short loc_1800C83FF
0x1800c83f5  call    cs:__imp_CloseHandle
0x1800c83fb  test    eax, eax
0x1800c83fd  jz      short loc_1800C8419
0x1800c83ff  lea     rax, ??_7InvSvcTenant@Service@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::Service::InvSvcTenant::`vftable'
0x1800c8406  mov     [rbx], rax
0x1800c8409  mov     rbx, [rsp+38h+arg_0]
0x1800c840e  mov     rsi, [rsp+38h+arg_8]
0x1800c8413  add     rsp, 30h
0x1800c8417  pop     rdi
0x1800c8418  retn
0x1800c8419  mov     rcx, [rsp+38h]; this
0x1800c841e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c8425  mov     edx, 0A0Bh; void *
0x1800c842a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800c8430  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c8437  mov     edx, 0A01h; void *
0x1800c843c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
