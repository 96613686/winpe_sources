# Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)

- ea: `0x180014298`
- end: `0x1800143c3`
- name: `??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800148a0`

## callees

- `0x180001a30`
- `0x180004dcc`
- `0x1800058a4`
- `0x180013214`
- `0x1800132b4`
- `0x180014298`
- `0x180016b9c`
- `0x18001a010`

## string_xrefs

- `0x18001436a`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAUIPropertySet_Collections_Foundation_Windows_ABI___Foundation_Windows_ABI___details_wil__YAJPEAU__IAsyncOperation_PEAUIPropertySet_Collections_Foundation_Windows_ABI___Foundation_Windows_ABI__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAUIPropertySet_Collections_Foundation_Windows_ABI___Foundation_Windows_ABI___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAUIPropertySet_Collections_Foundation_Windows_ABI___Foundation_Windows_ABI___details_wil__YAJPEAU__IAsyncOperation_PEAUIPropertySet_Collections_Foundation_Windows_ABI___Foundation_Windows_ABI__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  unsigned int v3; // edi
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  _DWORD *v8; // [rsp+40h] [rbp+8h] BYREF
  _DWORD *v9; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::`vftable'{for `ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IPropertySet *>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *>'::`2'::CompletionDelegate::`vftable';
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v8 = v2;
    v9 = 0;
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)(v2 + 14));
    v3 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
    {
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
      *a1 = v2;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
      v3 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
        (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
        v6);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<ConsolePropertySheetHandler,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<ConsolePropertySheetHandler,0>>(&v9);
  return v3;
}

```

## disassembly

```asm
0x180014298  mov     [rsp+arg_10], rbx
0x18001429d  mov     [rsp+arg_18], rsi
0x1800142a2  push    rdi
0x1800142a3  sub     rsp, 30h
0x1800142a7  mov     rsi, rcx
0x1800142aa  mov     qword ptr [rcx], 0
0x1800142b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800142b8  mov     ecx, 40h ; '@'; unsigned __int64
0x1800142bd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800142c2  mov     rbx, rax
0x1800142c5  mov     [rsp+38h+arg_8], rax
0x1800142ca  test    rax, rax
0x1800142cd  jnz     short loc_1800142D9
0x1800142cf  mov     edi, 8007000Eh
0x1800142d4  jmp     loc_1800143A6
0x1800142d9  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@6B@; const ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *>::`vftable'
0x1800142e0  mov     [rbx], rax
0x1800142e3  lea     rdi, [rbx+8]
0x1800142e7  mov     rcx, rdi; this
0x1800142ea  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800142ef  mov     dword ptr [rbx+2Ch], 1
0x1800142f6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::`vftable'{for `ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IPropertySet *>'}
0x1800142fd  mov     [rbx], rax
0x180014300  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180014307  mov     [rdi], rax
0x18001430a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180014311  test    rcx, rcx
0x180014314  jz      short loc_180014323
0x180014316  mov     rax, [rcx]
0x180014319  mov     rax, [rax+8]
0x18001431d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014322  nop
0x180014323  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@456@@; const `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IPropertySet *>'}
0x18001432a  mov     [rbx], rax
0x18001432d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180014334  mov     [rdi], rax
0x180014337  mov     dword ptr [rbx+30h], 0
0x18001433e  lea     rcx, [rbx+38h]
0x180014342  mov     qword ptr [rcx], 0
0x180014349  mov     [rsp+38h+arg_0], rbx
0x18001434e  mov     [rsp+38h+arg_8], 0
0x180014357  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001435c  mov     edi, eax
0x18001435e  test    eax, eax
0x180014360  jns     short loc_180014387
0x180014362  mov     rcx, [rsp+38h]; this
0x180014367  mov     r9d, eax; char *
0x18001436a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180014371  mov     edx, 62Bh; void *
0x180014376  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001437b  lea     rcx, [rsp+38h+arg_0]
0x180014380  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014385  jmp     short loc_1800143A6
0x180014387  mov     rax, [rbx]
0x18001438a  mov     rcx, rbx
0x18001438d  mov     rax, [rax+8]
0x180014391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014396  nop
0x180014397  mov     [rsi], rbx
0x18001439a  lea     rcx, [rsp+38h+arg_0]
0x18001439f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800143a4  xor     edi, edi
0x1800143a6  lea     rcx, [rsp+38h+arg_8]
0x1800143ab  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VConsolePropertySheetHandler@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<ConsolePropertySheetHandler,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<ConsolePropertySheetHandler,0>>(void)
0x1800143b0  mov     eax, edi
0x1800143b2  mov     rbx, [rsp+38h+arg_10]
0x1800143b7  mov     rsi, [rsp+38h+arg_18]
0x1800143bc  add     rsp, 30h
0x1800143c0  pop     rdi
0x1800143c1  retn
```
