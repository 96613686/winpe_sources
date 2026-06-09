# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x180044f4c`
- end: `0x1800451d2`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `646`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180045ab8`

## callees

- `0x180002710`
- `0x180004b14`
- `0x1800061e8`
- `0x18000b0f4`
- `0x18001e184`
- `0x180044f4c`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800450de`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800450de`

## string_xrefs

- `0x180045010`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180045039`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180045091`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x1800450f7`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *>(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64),
        DWORD a2,
        int a3,
        ...)
{
  void *v4; // rdi
  unsigned int v5; // ebx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v8; // eax
  HRESULT v9; // eax
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64); // rbx
  __int64 v11; // rax
  __int64 v12; // rcx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  int lpdwindexa; // [rsp+20h] [rbp-20h]
  HANDLE pHandles; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD dwindex; // [rsp+68h] [rbp+28h] BYREF
  int v18; // [rsp+70h] [rbp+30h] BYREF
  __int64 v19; // [rsp+78h] [rbp+38h] BYREF
  va_list va; // [rsp+78h] [rbp+38h]
  va_list va1; // [rsp+80h] [rbp+40h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v19 = va_arg(va1, _QWORD);
  v18 = a3;
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
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>((_QWORD *)v4 + 1);
  *((_DWORD *)v4 + 11) = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>'};
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>'::`2'::FTMEventDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>'::`2'::FTMEventDelegate::`vftable';
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
  v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), void *))(*a1)[6])(a1, v4);
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
    v19 = 0;
    v10 = **a1;
    v11 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>((__int64 *)va);
    v5 = v10(a1, &GUID_00000036_0000_0000_c000_000000000046, v11);
    if ( (v5 & 0x80000000) == 0 )
    {
      v18 = -2147418113;
      v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 64LL))(v19, &v18);
      if ( (v5 & 0x80000000) == 0 )
        v5 = v18;
    }
    v12 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
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
0x180044f4c  mov     rax, rsp
0x180044f4f  mov     [rax+8], rbx
0x180044f53  mov     [rax+20h], r9
0x180044f57  mov     [rax+18h], r8d
0x180044f5b  mov     [rax+10h], edx
0x180044f5e  push    rbp
0x180044f5f  push    rsi
0x180044f60  push    rdi
0x180044f61  mov     rbp, rsp
0x180044f64  sub     rsp, 40h
0x180044f68  mov     rsi, rcx
0x180044f6b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180044f72  mov     ecx, 40h ; '@'; unsigned __int64
0x180044f77  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180044f7c  mov     rdi, rax
0x180044f7f  test    rax, rax
0x180044f82  jnz     short loc_180044F8E
0x180044f84  mov     ebx, 8007000Eh
0x180044f89  jmp     loc_180045032
0x180044f8e  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>::`vftable'
0x180044f95  mov     [rdi], rax
0x180044f98  lea     rbx, [rdi+8]
0x180044f9c  mov     rcx, rbx
0x180044f9f  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180044fa4  mov     dword ptr [rdi+2Ch], 1
0x180044fab  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>'}
0x180044fb2  mov     [rdi], rax
0x180044fb5  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180044fbc  mov     [rbx], rax
0x180044fbf  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180044fc6  test    rcx, rcx
0x180044fc9  jz      short loc_180044FD8
0x180044fcb  mov     rax, [rcx]
0x180044fce  mov     rax, [rax+8]
0x180044fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044fd7  nop
0x180044fd8  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>'}
0x180044fdf  mov     [rdi], rax
0x180044fe2  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180044fe9  mov     [rbx], rax
0x180044fec  mov     dword ptr [rdi+30h], 0
0x180044ff3  lea     rcx, [rdi+38h]
0x180044ff7  mov     qword ptr [rcx], 0
0x180044ffe  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180045003  mov     ebx, eax
0x180045005  test    eax, eax
0x180045007  jns     short loc_180045052
0x180045009  mov     rcx, [rbp+18h]; this
0x18004500d  mov     r9d, eax; char *
0x180045010  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180045017  mov     edx, 62Bh; void *
0x18004501c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045021  nop
0x180045022  mov     rax, [rdi]
0x180045025  mov     rcx, rdi
0x180045028  mov     rax, [rax+10h]
0x18004502c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045031  nop
0x180045032  mov     rcx, [rbp+18h]; this
0x180045036  mov     r9d, ebx; char *
0x180045039  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180045040  mov     edx, 648h; void *
0x180045045  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004504a  nop
0x18004504b  mov     eax, ebx
0x18004504d  jmp     loc_1800451C4
0x180045052  mov     rax, [rdi]
0x180045055  mov     rcx, rdi
0x180045058  mov     rax, [rax+8]
0x18004505c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045061  nop
0x180045062  mov     rax, [rdi]
0x180045065  mov     rcx, rdi
0x180045068  mov     rax, [rax+10h]
0x18004506c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045071  nop
0x180045072  mov     rax, [rsi]
0x180045075  mov     rdx, rdi
0x180045078  mov     rcx, rsi
0x18004507b  mov     rax, [rax+30h]
0x18004507f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045084  mov     ebx, eax
0x180045086  test    eax, eax
0x180045088  jns     short loc_1800450B5
0x18004508a  mov     rcx, [rbp+18h]; this
0x18004508e  mov     r9d, eax; char *
0x180045091  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180045098  mov     edx, 649h; void *
0x18004509d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800450a2  nop
0x1800450a3  mov     rcx, [rdi]
0x1800450a6  mov     rax, [rcx+10h]
0x1800450aa  mov     rcx, rdi
0x1800450ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450b2  nop
0x1800450b3  jmp     short loc_18004504B
0x1800450b5  mov     rax, [rdi+38h]
0x1800450b9  mov     [rbp+pHandles], rax
0x1800450bd  mov     [rbp+dwindex], 0
0x1800450c4  lea     rax, [rbp+dwindex]
0x1800450c8  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x1800450cd  lea     r9, [rbp+pHandles]; pHandles
0x1800450d1  mov     r8d, 1; cHandles
0x1800450d7  or      edx, 0FFFFFFFFh; dwTimeout
0x1800450da  lea     ecx, [r8+7]; dwFlags
0x1800450de  call    cs:__imp_CoWaitForMultipleHandles
0x1800450e5  nop     dword ptr [rax+rax+00h]
0x1800450ea  mov     ebx, eax
0x1800450ec  test    eax, eax
0x1800450ee  jns     short loc_18004511E
0x1800450f0  mov     rcx, [rbp+18h]; this
0x1800450f4  mov     r9d, eax; char *
0x1800450f7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800450fe  mov     edx, 655h; void *
0x180045103  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045108  nop
0x180045109  mov     rcx, [rdi]
0x18004510c  mov     rax, [rcx+10h]
0x180045110  mov     rcx, rdi
0x180045113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045118  nop
0x180045119  jmp     loc_18004504B
0x18004511e  mov     eax, [rdi+30h]
0x180045121  cmp     eax, 1
0x180045124  jz      loc_1800451B2
0x18004512a  mov     [rbp+arg_18], 0
0x180045132  mov     rax, [rsi]
0x180045135  mov     rbx, [rax]
0x180045138  lea     rcx, [rbp+arg_18]
0x18004513c  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180045141  mov     r8, rax
0x180045144  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18004514b  mov     rcx, rsi
0x18004514e  mov     rax, rbx
0x180045151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045156  mov     ebx, eax
0x180045158  test    eax, eax
0x18004515a  js      short loc_18004517F
0x18004515c  mov     [rbp+arg_10], 8000FFFFh
0x180045163  mov     rcx, [rbp+arg_18]
0x180045167  mov     rax, [rcx]
0x18004516a  lea     rdx, [rbp+arg_10]
0x18004516e  mov     rax, [rax+40h]
0x180045172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045177  mov     ebx, eax
0x180045179  test    eax, eax
0x18004517b  cmovns  ebx, [rbp+arg_10]
0x18004517f  mov     rcx, [rbp+arg_18]
0x180045183  test    rcx, rcx
0x180045186  jz      short loc_18004519D
0x180045188  mov     [rbp+arg_18], 0
0x180045190  mov     rax, [rcx]
0x180045193  mov     rax, [rax+10h]
0x180045197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004519c  nop
0x18004519d  mov     rax, [rdi]
0x1800451a0  mov     rcx, rdi
0x1800451a3  mov     rax, [rax+10h]
0x1800451a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451ac  nop
0x1800451ad  jmp     loc_18004504B
0x1800451b2  mov     rax, [rdi]
0x1800451b5  mov     rcx, rdi
0x1800451b8  mov     rax, [rax+10h]
0x1800451bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451c1  nop
0x1800451c2  xor     eax, eax
0x1800451c4  mov     rbx, [rsp+40h+arg_0]
0x1800451c9  add     rsp, 40h
0x1800451cd  pop     rdi
0x1800451ce  pop     rsi
0x1800451cf  pop     rbp
0x1800451d0  retn
```
