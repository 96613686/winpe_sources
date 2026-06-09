# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x140004198`
- end: `0x14000440f`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000a3c4`

## callees

- `0x140002618`
- `0x140004198`
- `0x140004510`
- `0x14000b084`
- `0x14000c2a4`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14000432a`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14000432a`

## string_xrefs

- `0x14000425c`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x140004285`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x1400042dd`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x140004343`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>(
        __int64 a1,
        DWORD a2,
        int a3,
        ...)
{
  void *v4; // rbx
  unsigned int v5; // edi
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v8; // eax
  HRESULT v9; // eax
  __int64 v10; // rcx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  int lpdwindexa; // [rsp+20h] [rbp-20h]
  HANDLE pHandles; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD dwindex; // [rsp+68h] [rbp+28h] BYREF
  int v16; // [rsp+70h] [rbp+30h] BYREF
  __int64 v17; // [rsp+78h] [rbp+38h] BYREF
  va_list va; // [rsp+78h] [rbp+38h]
  va_list va1; // [rsp+80h] [rbp+40h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v17 = va_arg(va1, _QWORD);
  v16 = a3;
  dwindex = a2;
  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v5 = -2147024882;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)v5,
      lpdwindex);
    return v5;
  }
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>((_QWORD *)v4 + 1);
  *((_DWORD *)v4 + 11) = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>'};
  *((_QWORD *)v4 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>'::`2'::CompletionDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>'::`2'::CompletionDelegate::`vftable';
  *((_DWORD *)v4 + 12) = 0;
  *((_QWORD *)v4 + 7) = 0;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((void **)v4 + 7);
  v5 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      lpdwindex);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
    goto LABEL_7;
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 8LL))(v4);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
  v8 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)a1 + 48LL))(a1, v4);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x649,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v8,
      lpdwindex);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  pHandles = (HANDLE)*((_QWORD *)v4 + 7);
  dwindex = 0;
  v9 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  v5 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x655,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v9,
      lpdwindexa);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  if ( *((_DWORD *)v4 + 12) != 1 )
  {
    v17 = 0;
    v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
           a1,
           &GUID_00000036_0000_0000_c000_000000000046,
           (__int64 *)va);
    if ( (v5 & 0x80000000) == 0 )
    {
      v16 = -2147418113;
      v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 64LL))(v17, &v16);
      if ( (v5 & 0x80000000) == 0 )
        v5 = v16;
    }
    v10 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x140004198  mov     rax, rsp
0x14000419b  mov     [rax+8], rbx
0x14000419f  mov     [rax+20h], r9
0x1400041a3  mov     [rax+18h], r8d
0x1400041a7  mov     [rax+10h], edx
0x1400041aa  push    rbp
0x1400041ab  push    rsi
0x1400041ac  push    rdi
0x1400041ad  mov     rbp, rsp
0x1400041b0  sub     rsp, 40h
0x1400041b4  mov     rsi, rcx
0x1400041b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400041be  mov     ecx, 40h ; '@'; unsigned __int64
0x1400041c3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400041c8  mov     rbx, rax
0x1400041cb  test    rax, rax
0x1400041ce  jnz     short loc_1400041DA
0x1400041d0  mov     edi, 8007000Eh
0x1400041d5  jmp     loc_14000427E
0x1400041da  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable'
0x1400041e1  mov     [rbx], rax
0x1400041e4  lea     rdi, [rbx+8]
0x1400041e8  mov     rcx, rdi
0x1400041eb  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x1400041f0  mov     dword ptr [rbx+2Ch], 1
0x1400041f7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>'}
0x1400041fe  mov     [rbx], rax
0x140004201  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140004208  mov     [rdi], rax
0x14000420b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140004212  test    rcx, rcx
0x140004215  jz      short loc_140004224
0x140004217  mov     rax, [rcx]
0x14000421a  mov     rax, [rax+8]
0x14000421e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004223  nop
0x140004224  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>'}
0x14000422b  mov     [rbx], rax
0x14000422e  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140004235  mov     [rdi], rax
0x140004238  mov     dword ptr [rbx+30h], 0
0x14000423f  lea     rcx, [rbx+38h]
0x140004243  mov     qword ptr [rcx], 0
0x14000424a  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14000424f  mov     edi, eax
0x140004251  test    eax, eax
0x140004253  jns     short loc_14000429E
0x140004255  mov     rcx, [rbp+18h]; this
0x140004259  mov     r9d, eax; char *
0x14000425c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140004263  mov     edx, 62Bh; void *
0x140004268  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000426d  nop
0x14000426e  mov     rax, [rbx]
0x140004271  mov     rcx, rbx
0x140004274  mov     rax, [rax+10h]
0x140004278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000427d  nop
0x14000427e  mov     rcx, [rbp+18h]; this
0x140004282  mov     r9d, edi; char *
0x140004285  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000428c  mov     edx, 648h; void *
0x140004291  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004296  nop
0x140004297  mov     eax, edi
0x140004299  jmp     loc_140004401
0x14000429e  mov     rax, [rbx]
0x1400042a1  mov     rcx, rbx
0x1400042a4  mov     rax, [rax+8]
0x1400042a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042ad  nop
0x1400042ae  mov     rax, [rbx]
0x1400042b1  mov     rcx, rbx
0x1400042b4  mov     rax, [rax+10h]
0x1400042b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042bd  nop
0x1400042be  mov     rax, [rsi]
0x1400042c1  mov     rdx, rbx
0x1400042c4  mov     rcx, rsi
0x1400042c7  mov     rax, [rax+30h]
0x1400042cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042d0  mov     edi, eax
0x1400042d2  test    eax, eax
0x1400042d4  jns     short loc_140004301
0x1400042d6  mov     rcx, [rbp+18h]; this
0x1400042da  mov     r9d, eax; char *
0x1400042dd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400042e4  mov     edx, 649h; void *
0x1400042e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400042ee  nop
0x1400042ef  mov     rcx, [rbx]
0x1400042f2  mov     rax, [rcx+10h]
0x1400042f6  mov     rcx, rbx
0x1400042f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042fe  nop
0x1400042ff  jmp     short loc_140004297
0x140004301  mov     rax, [rbx+38h]
0x140004305  mov     [rbp+pHandles], rax
0x140004309  mov     [rbp+dwindex], 0
0x140004310  lea     rax, [rbp+dwindex]
0x140004314  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x140004319  lea     r9, [rbp+pHandles]; pHandles
0x14000431d  mov     r8d, 1; cHandles
0x140004323  or      edx, 0FFFFFFFFh; dwTimeout
0x140004326  lea     ecx, [r8+7]; dwFlags
0x14000432a  call    cs:__imp_CoWaitForMultipleHandles
0x140004331  nop     dword ptr [rax+rax+00h]
0x140004336  mov     edi, eax
0x140004338  test    eax, eax
0x14000433a  jns     short loc_14000436A
0x14000433c  mov     rcx, [rbp+18h]; this
0x140004340  mov     r9d, eax; char *
0x140004343  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000434a  mov     edx, 655h; void *
0x14000434f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004354  nop
0x140004355  mov     rcx, [rbx]
0x140004358  mov     rax, [rcx+10h]
0x14000435c  mov     rcx, rbx
0x14000435f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004364  nop
0x140004365  jmp     loc_140004297
0x14000436a  mov     eax, [rbx+30h]
0x14000436d  cmp     eax, 1
0x140004370  jz      short loc_1400043EF
0x140004372  mov     [rbp+arg_18], 0
0x14000437a  mov     rax, [rsi]
0x14000437d  lea     r8, [rbp+arg_18]
0x140004381  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140004388  mov     rcx, rsi
0x14000438b  mov     rax, [rax]
0x14000438e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004393  mov     edi, eax
0x140004395  test    eax, eax
0x140004397  js      short loc_1400043BC
0x140004399  mov     [rbp+arg_10], 8000FFFFh
0x1400043a0  mov     rcx, [rbp+arg_18]
0x1400043a4  mov     rax, [rcx]
0x1400043a7  lea     rdx, [rbp+arg_10]
0x1400043ab  mov     rax, [rax+40h]
0x1400043af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043b4  mov     edi, eax
0x1400043b6  test    eax, eax
0x1400043b8  cmovns  edi, [rbp+arg_10]
0x1400043bc  mov     rcx, [rbp+arg_18]
0x1400043c0  test    rcx, rcx
0x1400043c3  jz      short loc_1400043DA
0x1400043c5  mov     [rbp+arg_18], 0
0x1400043cd  mov     rax, [rcx]
0x1400043d0  mov     rax, [rax+10h]
0x1400043d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043d9  nop
0x1400043da  mov     rax, [rbx]
0x1400043dd  mov     rcx, rbx
0x1400043e0  mov     rax, [rax+10h]
0x1400043e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043e9  nop
0x1400043ea  jmp     loc_140004297
0x1400043ef  mov     rax, [rbx]
0x1400043f2  mov     rcx, rbx
0x1400043f5  mov     rax, [rax+10h]
0x1400043f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043fe  nop
0x1400043ff  xor     eax, eax
0x140004401  mov     rbx, [rsp+40h+arg_0]
0x140004406  add     rsp, 40h
0x14000440a  pop     rdi
0x14000440b  pop     rsi
0x14000440c  pop     rbp
0x14000440d  retn
```
