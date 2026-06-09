# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x18001aadc`
- end: `0x18001ad8b`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `687`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c1b8`
- `0x18001c560`

## callees

- `0x180002710`
- `0x180004b14`
- `0x1800061e8`
- `0x18000b0f4`
- `0x18001aadc`
- `0x18001e184`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001ac75`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001ac75`

## string_xrefs

- `0x18001aba6`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18001abcf`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18001ac27`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18001acb2`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64),
        DWORD a2,
        int a3,
        _BYTE *a4)
{
  void *v6; // rdi
  unsigned int v7; // ebx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v10; // eax
  HRESULT v11; // eax
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64); // rbx
  __int64 v13; // rax
  __int64 v14; // rcx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  int lpdwindexa; // [rsp+20h] [rbp-20h]
  HANDLE pHandles; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD dwindex; // [rsp+78h] [rbp+38h] BYREF
  int v20; // [rsp+80h] [rbp+40h] BYREF
  __int64 v21; // [rsp+88h] [rbp+48h] BYREF

  v20 = a3;
  dwindex = a2;
  if ( a4 )
    *a4 = 0;
  v6 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v6 )
  {
    v7 = -2147024882;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)v7,
      lpdwindex);
    return v7;
  }
  *(_QWORD *)v6 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>((_QWORD *)v6 + 1);
  *((_DWORD *)v6 + 11) = 1;
  *(_QWORD *)v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'};
  *((_QWORD *)v6 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>'::`2'::CompletionDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v6 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v6 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>'::`2'::CompletionDelegate::`vftable';
  *((_DWORD *)v6 + 12) = 0;
  *((_QWORD *)v6 + 7) = 0;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((void **)v6 + 7);
  v7 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      lpdwindex);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
    goto LABEL_9;
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 8LL))(v6);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
  v10 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), void *))(*a1)[6])(a1, v6);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x649,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v10,
      lpdwindex);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
    return v7;
  }
  pHandles = (HANDLE)*((_QWORD *)v6 + 7);
  dwindex = 0;
  v11 = CoWaitForMultipleHandles(8u, 0x7530u, 1u, &pHandles, &dwindex);
  v7 = v11;
  if ( a4 && v11 == -2147417835 )
  {
    *a4 = 1;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  else
  {
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x655,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
        (const char *)(unsigned int)v11,
        lpdwindexa);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
      return v7;
    }
    if ( *((_DWORD *)v6 + 12) != 1 )
    {
      v21 = 0;
      v12 = **a1;
      v13 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v21);
      v7 = v12(a1, &GUID_00000036_0000_0000_c000_000000000046, v13);
      if ( (v7 & 0x80000000) == 0 )
      {
        v20 = -2147418113;
        v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 64LL))(v21, &v20);
        if ( (v7 & 0x80000000) == 0 )
          v7 = v20;
      }
      v14 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
      return v7;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return 0;
}

```

## disassembly

```asm
0x18001aadc  mov     [rsp-28h+arg_10], r8d
0x18001aae1  mov     [rsp-28h+dwindex], edx
0x18001aae5  push    rbp
0x18001aae6  push    rbx
0x18001aae7  push    rsi
0x18001aae8  push    rdi
0x18001aae9  push    r14
0x18001aaeb  mov     rbp, rsp
0x18001aaee  sub     rsp, 40h
0x18001aaf2  mov     rsi, r9
0x18001aaf5  mov     r14, rcx
0x18001aaf8  test    r9, r9
0x18001aafb  jz      short loc_18001AB01
0x18001aafd  mov     byte ptr [r9], 0
0x18001ab01  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ab08  mov     ecx, 40h ; '@'; unsigned __int64
0x18001ab0d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001ab12  mov     rdi, rax
0x18001ab15  test    rax, rax
0x18001ab18  jnz     short loc_18001AB24
0x18001ab1a  mov     ebx, 8007000Eh
0x18001ab1f  jmp     loc_18001ABC8
0x18001ab24  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>::`vftable'
0x18001ab2b  mov     [rdi], rax
0x18001ab2e  lea     rbx, [rdi+8]
0x18001ab32  mov     rcx, rbx
0x18001ab35  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x18001ab3a  mov     dword ptr [rdi+2Ch], 1
0x18001ab41  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'}
0x18001ab48  mov     [rdi], rax
0x18001ab4b  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001ab52  mov     [rbx], rax
0x18001ab55  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001ab5c  test    rcx, rcx
0x18001ab5f  jz      short loc_18001AB6E
0x18001ab61  mov     rax, [rcx]
0x18001ab64  mov     rax, [rax+8]
0x18001ab68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab6d  nop
0x18001ab6e  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'}
0x18001ab75  mov     [rdi], rax
0x18001ab78  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001ab7f  mov     [rbx], rax
0x18001ab82  mov     dword ptr [rdi+30h], 0
0x18001ab89  lea     rcx, [rdi+38h]
0x18001ab8d  mov     qword ptr [rcx], 0
0x18001ab94  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001ab99  mov     ebx, eax
0x18001ab9b  test    eax, eax
0x18001ab9d  jns     short loc_18001ABE8
0x18001ab9f  mov     rcx, [rbp+28h]; this
0x18001aba3  mov     r9d, eax; char *
0x18001aba6  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001abad  mov     edx, 62Bh; void *
0x18001abb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001abb7  nop
0x18001abb8  mov     rax, [rdi]
0x18001abbb  mov     rcx, rdi
0x18001abbe  mov     rax, [rax+10h]
0x18001abc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abc7  nop
0x18001abc8  mov     rcx, [rbp+28h]; this
0x18001abcc  mov     r9d, ebx; char *
0x18001abcf  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001abd6  mov     edx, 648h; void *
0x18001abdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001abe0  nop
0x18001abe1  mov     eax, ebx
0x18001abe3  jmp     loc_18001AD7F
0x18001abe8  mov     rax, [rdi]
0x18001abeb  mov     rcx, rdi
0x18001abee  mov     rax, [rax+8]
0x18001abf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abf7  nop
0x18001abf8  mov     rax, [rdi]
0x18001abfb  mov     rcx, rdi
0x18001abfe  mov     rax, [rax+10h]
0x18001ac02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac07  nop
0x18001ac08  mov     rax, [r14]
0x18001ac0b  mov     rdx, rdi
0x18001ac0e  mov     rcx, r14
0x18001ac11  mov     rax, [rax+30h]
0x18001ac15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac1a  mov     ebx, eax
0x18001ac1c  test    eax, eax
0x18001ac1e  jns     short loc_18001AC4B
0x18001ac20  mov     rcx, [rbp+28h]; this
0x18001ac24  mov     r9d, eax; char *
0x18001ac27  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001ac2e  mov     edx, 649h; void *
0x18001ac33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ac38  nop
0x18001ac39  mov     rcx, [rdi]
0x18001ac3c  mov     rax, [rcx+10h]
0x18001ac40  mov     rcx, rdi
0x18001ac43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac48  nop
0x18001ac49  jmp     short loc_18001ABE1
0x18001ac4b  mov     rax, [rdi+38h]
0x18001ac4f  mov     [rbp+pHandles], rax
0x18001ac53  mov     [rbp+dwindex], 0
0x18001ac5a  lea     rax, [rbp+dwindex]
0x18001ac5e  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x18001ac63  lea     r9, [rbp+pHandles]; pHandles
0x18001ac67  mov     edx, 7530h; dwTimeout
0x18001ac6c  mov     ecx, 8; dwFlags
0x18001ac71  lea     r8d, [rcx-7]; cHandles
0x18001ac75  call    cs:__imp_CoWaitForMultipleHandles
0x18001ac7c  nop     dword ptr [rax+rax+00h]
0x18001ac81  mov     ebx, eax
0x18001ac83  test    rsi, rsi
0x18001ac86  jz      short loc_18001ACA7
0x18001ac88  cmp     eax, 80010115h
0x18001ac8d  jnz     short loc_18001ACA7
0x18001ac8f  mov     byte ptr [rsi], 1
0x18001ac92  mov     rax, [rdi]
0x18001ac95  mov     rcx, rdi
0x18001ac98  mov     rax, [rax+10h]
0x18001ac9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aca1  nop
0x18001aca2  jmp     loc_18001AD7D
0x18001aca7  test    ebx, ebx
0x18001aca9  jns     short loc_18001ACD9
0x18001acab  mov     rcx, [rbp+28h]; this
0x18001acaf  mov     r9d, ebx; char *
0x18001acb2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001acb9  mov     edx, 655h; void *
0x18001acbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001acc3  nop
0x18001acc4  mov     rax, [rdi]
0x18001acc7  mov     rcx, rdi
0x18001acca  mov     rax, [rax+10h]
0x18001acce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acd3  nop
0x18001acd4  jmp     loc_18001ABE1
0x18001acd9  mov     eax, [rdi+30h]
0x18001acdc  cmp     eax, 1
0x18001acdf  jz      loc_18001AD6D
0x18001ace5  mov     [rbp+arg_18], 0
0x18001aced  mov     rax, [r14]
0x18001acf0  mov     rbx, [rax]
0x18001acf3  lea     rcx, [rbp+arg_18]
0x18001acf7  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18001acfc  mov     r8, rax
0x18001acff  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18001ad06  mov     rcx, r14
0x18001ad09  mov     rax, rbx
0x18001ad0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad11  mov     ebx, eax
0x18001ad13  test    eax, eax
0x18001ad15  js      short loc_18001AD3A
0x18001ad17  mov     [rbp+arg_10], 8000FFFFh
0x18001ad1e  mov     rcx, [rbp+arg_18]
0x18001ad22  mov     rax, [rcx]
0x18001ad25  lea     rdx, [rbp+arg_10]
0x18001ad29  mov     rax, [rax+40h]
0x18001ad2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad32  mov     ebx, eax
0x18001ad34  test    eax, eax
0x18001ad36  cmovns  ebx, [rbp+arg_10]
0x18001ad3a  mov     rcx, [rbp+arg_18]
0x18001ad3e  test    rcx, rcx
0x18001ad41  jz      short loc_18001AD58
0x18001ad43  mov     [rbp+arg_18], 0
0x18001ad4b  mov     rax, [rcx]
0x18001ad4e  mov     rax, [rax+10h]
0x18001ad52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad57  nop
0x18001ad58  mov     rax, [rdi]
0x18001ad5b  mov     rcx, rdi
0x18001ad5e  mov     rax, [rax+10h]
0x18001ad62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad67  nop
0x18001ad68  jmp     loc_18001ABE1
0x18001ad6d  mov     rax, [rdi]
0x18001ad70  mov     rcx, rdi
0x18001ad73  mov     rax, [rax+10h]
0x18001ad77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad7c  nop
0x18001ad7d  xor     eax, eax
0x18001ad7f  add     rsp, 40h
0x18001ad83  pop     r14
0x18001ad85  pop     rdi
0x18001ad86  pop     rsi
0x18001ad87  pop     rbx
0x18001ad88  pop     rbp
0x18001ad89  retn
```
