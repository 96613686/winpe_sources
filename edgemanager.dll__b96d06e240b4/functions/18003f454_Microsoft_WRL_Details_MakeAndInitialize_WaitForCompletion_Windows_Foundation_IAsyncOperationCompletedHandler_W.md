# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18003f454`
- end: `0x18003f58c`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180016a50`

## callees

- `0x180002a90`
- `0x18000b0ec`
- `0x18000f5d4`
- `0x18002b5e4`
- `0x18003f454`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003f51d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003f51d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f52c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f52c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  signed int v3; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  _DWORD *v7; // [rsp+30h] [rbp+8h] BYREF
  _DWORD *v8; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Foundation::ITypedEventHandler<Windows::UI::WebUI::WebUIView *,Windows::ApplicationModel::Activation::IActivatedEventArgs *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v7 = v2;
    v8 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    *((_QWORD *)v2 + 7) = Event;
    if ( Event )
      goto LABEL_10;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_10:
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
      *a1 = v2;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v7);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v7);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003f454  mov     [rsp+arg_10], rbx
0x18003f459  mov     [rsp+arg_18], rsi
0x18003f45e  push    rdi
0x18003f45f  sub     rsp, 20h
0x18003f463  mov     rsi, rcx
0x18003f466  mov     qword ptr [rcx], 0
0x18003f46d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003f474  mov     ecx, 40h ; '@'; unsigned __int64
0x18003f479  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003f47e  mov     rbx, rax
0x18003f481  mov     [rsp+28h+arg_8], rax
0x18003f486  test    rax, rax
0x18003f489  jnz     short loc_18003F495
0x18003f48b  mov     edi, 8007000Eh
0x18003f490  jmp     loc_18003F570
0x18003f495  lea     rax, ??_7?$ITypedEventHandler@PEAVWebUIView@WebUI@UI@Windows@@PEAUIActivatedEventArgs@Activation@ApplicationModel@4@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::WebUI::WebUIView *,Windows::ApplicationModel::Activation::IActivatedEventArgs *>::`vftable'
0x18003f49c  mov     [rbx], rax
0x18003f49f  lea     rdi, [rbx+8]
0x18003f4a3  mov     rcx, rdi; this
0x18003f4a6  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18003f4ab  mov     dword ptr [rbx+2Ch], 1
0x18003f4b2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>'}
0x18003f4b9  mov     [rbx], rax
0x18003f4bc  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003f4c3  mov     [rdi], rax
0x18003f4c6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18003f4cd  test    rcx, rcx
0x18003f4d0  jz      short loc_18003F4DF
0x18003f4d2  mov     rax, [rcx]
0x18003f4d5  mov     rax, [rax+8]
0x18003f4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f4de  nop
0x18003f4df  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>'}
0x18003f4e6  mov     [rbx], rax
0x18003f4e9  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003f4f0  mov     [rdi], rax
0x18003f4f3  mov     dword ptr [rbx+30h], 0
0x18003f4fa  mov     qword ptr [rbx+38h], 0
0x18003f502  mov     [rsp+28h+arg_0], rbx
0x18003f507  mov     [rsp+28h+arg_8], 0
0x18003f510  mov     r9d, 1F0003h; dwDesiredAccess
0x18003f516  xor     r8d, r8d; dwFlags
0x18003f519  xor     edx, edx; lpName
0x18003f51b  xor     ecx, ecx; lpEventAttributes
0x18003f51d  call    cs:__imp_CreateEventExW
0x18003f523  mov     [rbx+38h], rax
0x18003f527  test    rax, rax
0x18003f52a  jnz     short loc_18003F551
0x18003f52c  call    cs:__imp_GetLastError
0x18003f532  mov     edi, eax
0x18003f534  test    eax, eax
0x18003f536  jle     short loc_18003F541
0x18003f538  movzx   edi, ax
0x18003f53b  or      edi, 80070000h
0x18003f541  test    edi, edi
0x18003f543  jns     short loc_18003F551
0x18003f545  lea     rcx, [rsp+28h+arg_0]
0x18003f54a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003f54f  jmp     short loc_18003F570
0x18003f551  mov     rax, [rbx]
0x18003f554  mov     rcx, rbx
0x18003f557  mov     rax, [rax+8]
0x18003f55b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f560  nop
0x18003f561  mov     [rsi], rbx
0x18003f564  lea     rcx, [rsp+28h+arg_0]
0x18003f569  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003f56e  xor     edi, edi
0x18003f570  lea     rcx, [rsp+28h+arg_8]
0x18003f575  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x18003f57a  mov     eax, edi
0x18003f57c  mov     rbx, [rsp+28h+arg_10]
0x18003f581  mov     rsi, [rsp+28h+arg_18]
0x18003f586  add     rsp, 20h
0x18003f58a  pop     rdi
0x18003f58b  retn
```
