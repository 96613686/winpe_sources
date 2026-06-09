# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x140003e98`
- end: `0x140004108`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `624`
- prototype: `__int64(__int64, DWORD, int, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140004388`

## callees

- `0x1400025f8`
- `0x140003e98`
- `0x140004474`
- `0x14000ad94`
- `0x14000bef0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14000402a`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14000402a`

## string_xrefs

- `0x140003f5c`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x140003f85`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x140003fdd`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x14000403d`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *>(
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
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x140003e98  mov     rax, rsp
0x140003e9b  mov     [rax+8], rbx
0x140003e9f  mov     [rax+20h], r9
0x140003ea3  mov     [rax+18h], r8d
0x140003ea7  mov     [rax+10h], edx
0x140003eaa  push    rbp
0x140003eab  push    rsi
0x140003eac  push    rdi
0x140003ead  mov     rbp, rsp
0x140003eb0  sub     rsp, 40h
0x140003eb4  mov     rsi, rcx
0x140003eb7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140003ebe  mov     ecx, 40h ; '@'; unsigned __int64
0x140003ec3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140003ec8  mov     rbx, rax
0x140003ecb  test    rax, rax
0x140003ece  jnz     short loc_140003EDA
0x140003ed0  mov     edi, 8007000Eh
0x140003ed5  jmp     loc_140003F7E
0x140003eda  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable'
0x140003ee1  mov     [rbx], rax
0x140003ee4  lea     rdi, [rbx+8]
0x140003ee8  mov     rcx, rdi
0x140003eeb  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x140003ef0  mov     dword ptr [rbx+2Ch], 1
0x140003ef7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>'}
0x140003efe  mov     [rbx], rax
0x140003f01  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140003f08  mov     [rdi], rax
0x140003f0b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140003f12  test    rcx, rcx
0x140003f15  jz      short loc_140003F24
0x140003f17  mov     rax, [rcx]
0x140003f1a  mov     rax, [rax+8]
0x140003f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f23  nop
0x140003f24  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>'}
0x140003f2b  mov     [rbx], rax
0x140003f2e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140003f35  mov     [rdi], rax
0x140003f38  mov     dword ptr [rbx+30h], 0
0x140003f3f  lea     rcx, [rbx+38h]
0x140003f43  mov     qword ptr [rcx], 0
0x140003f4a  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140003f4f  mov     edi, eax
0x140003f51  test    eax, eax
0x140003f53  jns     short loc_140003F9E
0x140003f55  mov     rcx, [rbp+18h]; this
0x140003f59  mov     r9d, eax; char *
0x140003f5c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003f63  mov     edx, 62Bh; void *
0x140003f68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f6d  nop
0x140003f6e  mov     rax, [rbx]
0x140003f71  mov     rcx, rbx
0x140003f74  mov     rax, [rax+10h]
0x140003f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f7d  nop
0x140003f7e  mov     rcx, [rbp+18h]; this
0x140003f82  mov     r9d, edi; char *
0x140003f85  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003f8c  mov     edx, 648h; void *
0x140003f91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f96  nop
0x140003f97  mov     eax, edi
0x140003f99  jmp     loc_1400040FB
0x140003f9e  mov     rax, [rbx]
0x140003fa1  mov     rcx, rbx
0x140003fa4  mov     rax, [rax+8]
0x140003fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fad  nop
0x140003fae  mov     rax, [rbx]
0x140003fb1  mov     rcx, rbx
0x140003fb4  mov     rax, [rax+10h]
0x140003fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fbd  nop
0x140003fbe  mov     rax, [rsi]
0x140003fc1  mov     rdx, rbx
0x140003fc4  mov     rcx, rsi
0x140003fc7  mov     rax, [rax+30h]
0x140003fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fd0  mov     edi, eax
0x140003fd2  test    eax, eax
0x140003fd4  jns     short loc_140004001
0x140003fd6  mov     rcx, [rbp+18h]; this
0x140003fda  mov     r9d, eax; char *
0x140003fdd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003fe4  mov     edx, 649h; void *
0x140003fe9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003fee  nop
0x140003fef  mov     rcx, [rbx]
0x140003ff2  mov     rax, [rcx+10h]
0x140003ff6  mov     rcx, rbx
0x140003ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ffe  nop
0x140003fff  jmp     short loc_140003F97
0x140004001  mov     rax, [rbx+38h]
0x140004005  mov     [rbp+pHandles], rax
0x140004009  mov     [rbp+dwindex], 0
0x140004010  lea     rax, [rbp+dwindex]
0x140004014  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x140004019  lea     r9, [rbp+pHandles]; pHandles
0x14000401d  mov     r8d, 1; cHandles
0x140004023  or      edx, 0FFFFFFFFh; dwTimeout
0x140004026  lea     ecx, [r8+7]; dwFlags
0x14000402a  call    cs:__imp_CoWaitForMultipleHandles
0x140004030  mov     edi, eax
0x140004032  test    eax, eax
0x140004034  jns     short loc_140004064
0x140004036  mov     rcx, [rbp+18h]; this
0x14000403a  mov     r9d, eax; char *
0x14000403d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140004044  mov     edx, 655h; void *
0x140004049  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000404e  nop
0x14000404f  mov     rcx, [rbx]
0x140004052  mov     rax, [rcx+10h]
0x140004056  mov     rcx, rbx
0x140004059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000405e  nop
0x14000405f  jmp     loc_140003F97
0x140004064  mov     eax, [rbx+30h]
0x140004067  cmp     eax, 1
0x14000406a  jz      short loc_1400040E9
0x14000406c  mov     [rbp+arg_18], 0
0x140004074  mov     rax, [rsi]
0x140004077  lea     r8, [rbp+arg_18]
0x14000407b  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140004082  mov     rcx, rsi
0x140004085  mov     rax, [rax]
0x140004088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000408d  mov     edi, eax
0x14000408f  test    eax, eax
0x140004091  js      short loc_1400040B6
0x140004093  mov     [rbp+arg_10], 8000FFFFh
0x14000409a  mov     rcx, [rbp+arg_18]
0x14000409e  mov     rax, [rcx]
0x1400040a1  lea     rdx, [rbp+arg_10]
0x1400040a5  mov     rax, [rax+40h]
0x1400040a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040ae  mov     edi, eax
0x1400040b0  test    eax, eax
0x1400040b2  cmovns  edi, [rbp+arg_10]
0x1400040b6  mov     rcx, [rbp+arg_18]
0x1400040ba  test    rcx, rcx
0x1400040bd  jz      short loc_1400040D4
0x1400040bf  mov     [rbp+arg_18], 0
0x1400040c7  mov     rax, [rcx]
0x1400040ca  mov     rax, [rax+10h]
0x1400040ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040d3  nop
0x1400040d4  mov     rax, [rbx]
0x1400040d7  mov     rcx, rbx
0x1400040da  mov     rax, [rax+10h]
0x1400040de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040e3  nop
0x1400040e4  jmp     loc_140003F97
0x1400040e9  mov     rax, [rbx]
0x1400040ec  mov     rcx, rbx
0x1400040ef  mov     rax, [rax+10h]
0x1400040f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040f8  nop
0x1400040f9  xor     eax, eax
0x1400040fb  mov     rbx, [rsp+40h+arg_0]
0x140004100  add     rsp, 40h
0x140004104  pop     rdi
0x140004105  pop     rsi
0x140004106  pop     rbp
0x140004107  retn
```
