# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x140003f18`
- end: `0x14000418f`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140004418`

## callees

- `0x140002618`
- `0x140003f18`
- `0x140004510`
- `0x14000b084`
- `0x14000c2a4`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1400040aa`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1400040aa`

## string_xrefs

- `0x140003fdc`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x140004005`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x14000405d`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x1400040c3`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *>(
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
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x140003f18  mov     rax, rsp
0x140003f1b  mov     [rax+8], rbx
0x140003f1f  mov     [rax+20h], r9
0x140003f23  mov     [rax+18h], r8d
0x140003f27  mov     [rax+10h], edx
0x140003f2a  push    rbp
0x140003f2b  push    rsi
0x140003f2c  push    rdi
0x140003f2d  mov     rbp, rsp
0x140003f30  sub     rsp, 40h
0x140003f34  mov     rsi, rcx
0x140003f37  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140003f3e  mov     ecx, 40h ; '@'; unsigned __int64
0x140003f43  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140003f48  mov     rbx, rax
0x140003f4b  test    rax, rax
0x140003f4e  jnz     short loc_140003F5A
0x140003f50  mov     edi, 8007000Eh
0x140003f55  jmp     loc_140003FFE
0x140003f5a  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable'
0x140003f61  mov     [rbx], rax
0x140003f64  lea     rdi, [rbx+8]
0x140003f68  mov     rcx, rdi
0x140003f6b  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x140003f70  mov     dword ptr [rbx+2Ch], 1
0x140003f77  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>'}
0x140003f7e  mov     [rbx], rax
0x140003f81  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140003f88  mov     [rdi], rax
0x140003f8b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140003f92  test    rcx, rcx
0x140003f95  jz      short loc_140003FA4
0x140003f97  mov     rax, [rcx]
0x140003f9a  mov     rax, [rax+8]
0x140003f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fa3  nop
0x140003fa4  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>'}
0x140003fab  mov     [rbx], rax
0x140003fae  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140003fb5  mov     [rdi], rax
0x140003fb8  mov     dword ptr [rbx+30h], 0
0x140003fbf  lea     rcx, [rbx+38h]
0x140003fc3  mov     qword ptr [rcx], 0
0x140003fca  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140003fcf  mov     edi, eax
0x140003fd1  test    eax, eax
0x140003fd3  jns     short loc_14000401E
0x140003fd5  mov     rcx, [rbp+18h]; this
0x140003fd9  mov     r9d, eax; char *
0x140003fdc  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003fe3  mov     edx, 62Bh; void *
0x140003fe8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003fed  nop
0x140003fee  mov     rax, [rbx]
0x140003ff1  mov     rcx, rbx
0x140003ff4  mov     rax, [rax+10h]
0x140003ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ffd  nop
0x140003ffe  mov     rcx, [rbp+18h]; this
0x140004002  mov     r9d, edi; char *
0x140004005  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000400c  mov     edx, 648h; void *
0x140004011  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004016  nop
0x140004017  mov     eax, edi
0x140004019  jmp     loc_140004181
0x14000401e  mov     rax, [rbx]
0x140004021  mov     rcx, rbx
0x140004024  mov     rax, [rax+8]
0x140004028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000402d  nop
0x14000402e  mov     rax, [rbx]
0x140004031  mov     rcx, rbx
0x140004034  mov     rax, [rax+10h]
0x140004038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000403d  nop
0x14000403e  mov     rax, [rsi]
0x140004041  mov     rdx, rbx
0x140004044  mov     rcx, rsi
0x140004047  mov     rax, [rax+30h]
0x14000404b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004050  mov     edi, eax
0x140004052  test    eax, eax
0x140004054  jns     short loc_140004081
0x140004056  mov     rcx, [rbp+18h]; this
0x14000405a  mov     r9d, eax; char *
0x14000405d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140004064  mov     edx, 649h; void *
0x140004069  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000406e  nop
0x14000406f  mov     rcx, [rbx]
0x140004072  mov     rax, [rcx+10h]
0x140004076  mov     rcx, rbx
0x140004079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000407e  nop
0x14000407f  jmp     short loc_140004017
0x140004081  mov     rax, [rbx+38h]
0x140004085  mov     [rbp+pHandles], rax
0x140004089  mov     [rbp+dwindex], 0
0x140004090  lea     rax, [rbp+dwindex]
0x140004094  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x140004099  lea     r9, [rbp+pHandles]; pHandles
0x14000409d  mov     r8d, 1; cHandles
0x1400040a3  or      edx, 0FFFFFFFFh; dwTimeout
0x1400040a6  lea     ecx, [r8+7]; dwFlags
0x1400040aa  call    cs:__imp_CoWaitForMultipleHandles
0x1400040b1  nop     dword ptr [rax+rax+00h]
0x1400040b6  mov     edi, eax
0x1400040b8  test    eax, eax
0x1400040ba  jns     short loc_1400040EA
0x1400040bc  mov     rcx, [rbp+18h]; this
0x1400040c0  mov     r9d, eax; char *
0x1400040c3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400040ca  mov     edx, 655h; void *
0x1400040cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400040d4  nop
0x1400040d5  mov     rcx, [rbx]
0x1400040d8  mov     rax, [rcx+10h]
0x1400040dc  mov     rcx, rbx
0x1400040df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040e4  nop
0x1400040e5  jmp     loc_140004017
0x1400040ea  mov     eax, [rbx+30h]
0x1400040ed  cmp     eax, 1
0x1400040f0  jz      short loc_14000416F
0x1400040f2  mov     [rbp+arg_18], 0
0x1400040fa  mov     rax, [rsi]
0x1400040fd  lea     r8, [rbp+arg_18]
0x140004101  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140004108  mov     rcx, rsi
0x14000410b  mov     rax, [rax]
0x14000410e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004113  mov     edi, eax
0x140004115  test    eax, eax
0x140004117  js      short loc_14000413C
0x140004119  mov     [rbp+arg_10], 8000FFFFh
0x140004120  mov     rcx, [rbp+arg_18]
0x140004124  mov     rax, [rcx]
0x140004127  lea     rdx, [rbp+arg_10]
0x14000412b  mov     rax, [rax+40h]
0x14000412f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004134  mov     edi, eax
0x140004136  test    eax, eax
0x140004138  cmovns  edi, [rbp+arg_10]
0x14000413c  mov     rcx, [rbp+arg_18]
0x140004140  test    rcx, rcx
0x140004143  jz      short loc_14000415A
0x140004145  mov     [rbp+arg_18], 0
0x14000414d  mov     rax, [rcx]
0x140004150  mov     rax, [rax+10h]
0x140004154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004159  nop
0x14000415a  mov     rax, [rbx]
0x14000415d  mov     rcx, rbx
0x140004160  mov     rax, [rax+10h]
0x140004164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004169  nop
0x14000416a  jmp     loc_140004017
0x14000416f  mov     rax, [rbx]
0x140004172  mov     rcx, rbx
0x140004175  mov     rax, [rax+10h]
0x140004179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000417e  nop
0x14000417f  xor     eax, eax
0x140004181  mov     rbx, [rsp+40h+arg_0]
0x140004186  add     rsp, 40h
0x14000418a  pop     rdi
0x14000418b  pop     rsi
0x14000418c  pop     rbp
0x14000418d  retn
```
