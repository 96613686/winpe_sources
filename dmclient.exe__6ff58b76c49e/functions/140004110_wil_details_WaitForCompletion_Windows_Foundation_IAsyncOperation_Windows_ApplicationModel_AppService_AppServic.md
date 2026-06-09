# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x140004110`
- end: `0x140004380`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `624`
- prototype: `__int64(__int64, DWORD, int, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000a19c`

## callees

- `0x1400025f8`
- `0x140004110`
- `0x140004474`
- `0x14000ad94`
- `0x14000bef0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1400042a2`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1400042a2`

## string_xrefs

- `0x1400041d4`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x1400041fd`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x140004255`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x1400042b5`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>(
        __int64 a1,
        DWORD a2,
        int a3,
        ...)
{
  char *v4; // rbx
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
  v4 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v4 + 8);
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
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z();
  v5 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      lpdwindex);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    goto LABEL_7;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
  v8 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)a1 + 48LL))(a1, v4);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x649,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v8,
      lpdwindex);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
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
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
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
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x140004110  mov     rax, rsp
0x140004113  mov     [rax+8], rbx
0x140004117  mov     [rax+20h], r9
0x14000411b  mov     [rax+18h], r8d
0x14000411f  mov     [rax+10h], edx
0x140004122  push    rbp
0x140004123  push    rsi
0x140004124  push    rdi
0x140004125  mov     rbp, rsp
0x140004128  sub     rsp, 40h
0x14000412c  mov     rsi, rcx
0x14000412f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140004136  mov     ecx, 40h ; '@'; unsigned __int64
0x14000413b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140004140  mov     rbx, rax
0x140004143  test    rax, rax
0x140004146  jnz     short loc_140004152
0x140004148  mov     edi, 8007000Eh
0x14000414d  jmp     loc_1400041F6
0x140004152  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable'
0x140004159  mov     [rbx], rax
0x14000415c  lea     rdi, [rbx+8]
0x140004160  mov     rcx, rdi
0x140004163  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x140004168  mov     dword ptr [rbx+2Ch], 1
0x14000416f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>'}
0x140004176  mov     [rbx], rax
0x140004179  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140004180  mov     [rdi], rax
0x140004183  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000418a  test    rcx, rcx
0x14000418d  jz      short loc_14000419C
0x14000418f  mov     rax, [rcx]
0x140004192  mov     rax, [rax+8]
0x140004196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000419b  nop
0x14000419c  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>'}
0x1400041a3  mov     [rbx], rax
0x1400041a6  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1400041ad  mov     [rdi], rax
0x1400041b0  mov     dword ptr [rbx+30h], 0
0x1400041b7  lea     rcx, [rbx+38h]
0x1400041bb  mov     qword ptr [rcx], 0
0x1400041c2  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400041c7  mov     edi, eax
0x1400041c9  test    eax, eax
0x1400041cb  jns     short loc_140004216
0x1400041cd  mov     rcx, [rbp+18h]; this
0x1400041d1  mov     r9d, eax; char *
0x1400041d4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400041db  mov     edx, 62Bh; void *
0x1400041e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400041e5  nop
0x1400041e6  mov     rax, [rbx]
0x1400041e9  mov     rcx, rbx
0x1400041ec  mov     rax, [rax+10h]
0x1400041f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041f5  nop
0x1400041f6  mov     rcx, [rbp+18h]; this
0x1400041fa  mov     r9d, edi; char *
0x1400041fd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140004204  mov     edx, 648h; void *
0x140004209  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000420e  nop
0x14000420f  mov     eax, edi
0x140004211  jmp     loc_140004373
0x140004216  mov     rax, [rbx]
0x140004219  mov     rcx, rbx
0x14000421c  mov     rax, [rax+8]
0x140004220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004225  nop
0x140004226  mov     rax, [rbx]
0x140004229  mov     rcx, rbx
0x14000422c  mov     rax, [rax+10h]
0x140004230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004235  nop
0x140004236  mov     rax, [rsi]
0x140004239  mov     rdx, rbx
0x14000423c  mov     rcx, rsi
0x14000423f  mov     rax, [rax+30h]
0x140004243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004248  mov     edi, eax
0x14000424a  test    eax, eax
0x14000424c  jns     short loc_140004279
0x14000424e  mov     rcx, [rbp+18h]; this
0x140004252  mov     r9d, eax; char *
0x140004255  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000425c  mov     edx, 649h; void *
0x140004261  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004266  nop
0x140004267  mov     rcx, [rbx]
0x14000426a  mov     rax, [rcx+10h]
0x14000426e  mov     rcx, rbx
0x140004271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004276  nop
0x140004277  jmp     short loc_14000420F
0x140004279  mov     rax, [rbx+38h]
0x14000427d  mov     [rbp+pHandles], rax
0x140004281  mov     [rbp+dwindex], 0
0x140004288  lea     rax, [rbp+dwindex]
0x14000428c  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x140004291  lea     r9, [rbp+pHandles]; pHandles
0x140004295  mov     r8d, 1; cHandles
0x14000429b  or      edx, 0FFFFFFFFh; dwTimeout
0x14000429e  lea     ecx, [r8+7]; dwFlags
0x1400042a2  call    cs:__imp_CoWaitForMultipleHandles
0x1400042a8  mov     edi, eax
0x1400042aa  test    eax, eax
0x1400042ac  jns     short loc_1400042DC
0x1400042ae  mov     rcx, [rbp+18h]; this
0x1400042b2  mov     r9d, eax; char *
0x1400042b5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400042bc  mov     edx, 655h; void *
0x1400042c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400042c6  nop
0x1400042c7  mov     rcx, [rbx]
0x1400042ca  mov     rax, [rcx+10h]
0x1400042ce  mov     rcx, rbx
0x1400042d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042d6  nop
0x1400042d7  jmp     loc_14000420F
0x1400042dc  mov     eax, [rbx+30h]
0x1400042df  cmp     eax, 1
0x1400042e2  jz      short loc_140004361
0x1400042e4  mov     [rbp+arg_18], 0
0x1400042ec  mov     rax, [rsi]
0x1400042ef  lea     r8, [rbp+arg_18]
0x1400042f3  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1400042fa  mov     rcx, rsi
0x1400042fd  mov     rax, [rax]
0x140004300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004305  mov     edi, eax
0x140004307  test    eax, eax
0x140004309  js      short loc_14000432E
0x14000430b  mov     [rbp+arg_10], 8000FFFFh
0x140004312  mov     rcx, [rbp+arg_18]
0x140004316  mov     rax, [rcx]
0x140004319  lea     rdx, [rbp+arg_10]
0x14000431d  mov     rax, [rax+40h]
0x140004321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004326  mov     edi, eax
0x140004328  test    eax, eax
0x14000432a  cmovns  edi, [rbp+arg_10]
0x14000432e  mov     rcx, [rbp+arg_18]
0x140004332  test    rcx, rcx
0x140004335  jz      short loc_14000434C
0x140004337  mov     [rbp+arg_18], 0
0x14000433f  mov     rax, [rcx]
0x140004342  mov     rax, [rax+10h]
0x140004346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000434b  nop
0x14000434c  mov     rax, [rbx]
0x14000434f  mov     rcx, rbx
0x140004352  mov     rax, [rax+10h]
0x140004356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000435b  nop
0x14000435c  jmp     loc_14000420F
0x140004361  mov     rax, [rbx]
0x140004364  mov     rcx, rbx
0x140004367  mov     rax, [rax+10h]
0x14000436b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004370  nop
0x140004371  xor     eax, eax
0x140004373  mov     rbx, [rsp+40h+arg_0]
0x140004378  add     rsp, 40h
0x14000437c  pop     rdi
0x14000437d  pop     rsi
0x14000437e  pop     rbp
0x14000437f  retn
```
