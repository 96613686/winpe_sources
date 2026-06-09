# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x1800645c0`
- end: `0x1800646f8`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: `__int64 __fastcall(WaitForCompletion::__l2::FTMEventDelegate **result)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180064700`

## callees

- `0x180002be0`
- `0x18003f688`
- `0x18005b4a4`
- `0x1800645c0`
- `0x180064890`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180064689`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180064689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064698`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUIUICommand_Popups_UI_Windows___Foundation_Windows__U__IAsyncOperation_PEAUIUICommand_Popups_UI_Windows___23___YAJPEAU__IAsyncOperation_PEAUIUICommand_Popups_UI_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUIUICommand_Popups_UI_Windows___Foundation_Windows__U__IAsyncOperation_PEAUIUICommand_Popups_UI_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUIUICommand_Popups_UI_Windows___Foundation_Windows__U__IAsyncOperation_PEAUIUICommand_Popups_UI_Windows___23___YAJPEAU__IAsyncOperation_PEAUIUICommand_Popups_UI_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        WaitForCompletion::__l2::FTMEventDelegate **result)
{
  WaitForCompletion::__l2::FTMEventDelegate *v2; // rbx
  signed int v3; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> object; // [rsp+20h] [rbp-18h] BYREF
  Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> allocator; // [rsp+28h] [rbp-10h] BYREF

  *result = 0;
  v2 = (WaitForCompletion::__l2::FTMEventDelegate *)operator new(0x40u, &std::nothrow);
  allocator.buffer_ = v2;
  if ( v2 )
  {
    v2->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Windows::Foundation::IAsyncActionCompletedHandler::IUnknown::__vftable = (WaitForCompletion::__l2::FTMEventDelegate_vtbl *)Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase(&v2->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >);
    v2->refcount_ = 1;
    v2->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Windows::Foundation::IAsyncActionCompletedHandler::IUnknown::__vftable = (WaitForCompletion::__l2::FTMEventDelegate_vtbl *)Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>'};
    v2->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >_vtbl *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      Microsoft::WRL::Details::ModuleBase::module_->IncrementObjectCount(Microsoft::WRL::Details::ModuleBase::module_);
    v2->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Windows::Foundation::IAsyncActionCompletedHandler::IUnknown::__vftable = (WaitForCompletion::__l2::FTMEventDelegate_vtbl *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>'::`2'::FTMEventDelegate::`vftable';
    v2->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >_vtbl *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>'::`2'::FTMEventDelegate::`vftable';
    v2->_status = Started;
    v2->_hEventCompleted = 0;
    object.ptr_ = v2;
    allocator.buffer_ = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    v2->_hEventCompleted = Event;
    if ( Event )
      goto LABEL_10;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_10:
      v2->AddRef(v2);
      *result = v2;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&object);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&object);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Networking::NetworkOperators::ProvisionedProfile>::~MakeAllocator<Windows::Networking::NetworkOperators::ProvisionedProfile>(&allocator);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800645c0  mov     [rsp+arg_8], rbx
0x1800645c5  mov     [rsp+arg_10], rsi
0x1800645ca  push    rdi
0x1800645cb  sub     rsp, 30h
0x1800645cf  mov     rsi, result
0x1800645d2  mov     qword ptr [result], 0
0x1800645d9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; __formal
0x1800645e0  mov     ecx, 40h ; '@'; size
0x1800645e5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800645ea  mov     rbx, rax
0x1800645ed  mov     [rsp+38h+allocator.buffer_], rax
0x1800645f2  test    rax, rax
0x1800645f5  jnz     short loc_180064601
0x1800645f7  mov     edi, 8007000Eh
0x1800645fc  jmp     loc_1800646DC
0x180064601  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>::`vftable'
0x180064608  mov     [rbx], rax
0x18006460b  lea     rdi, [rbx+8]
0x18006460f  mov     result, rdi; this
0x180064612  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180064617  mov     dword ptr [rbx+2Ch], 1
0x18006461e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>'}
0x180064625  mov     [rbx], rax
0x180064628  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18006462f  mov     [rdi], rax
0x180064632  mov     result, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180064639  test    result, result
0x18006463c  jz      short loc_18006464B
0x18006463e  mov     rax, [result]
0x180064641  mov     rax, [rax+8]
0x180064645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006464a  nop
0x18006464b  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>'}
0x180064652  mov     [rbx], rax
0x180064655  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18006465c  mov     [rdi], rax
0x18006465f  mov     dword ptr [rbx+30h], 0
0x180064666  mov     qword ptr [rbx+38h], 0
0x18006466e  mov     [rsp+38h+object.ptr_], rbx
0x180064673  mov     [rsp+38h+allocator.buffer_], 0
0x18006467c  mov     r9d, 1F0003h; dwDesiredAccess
0x180064682  xor     r8d, r8d; dwFlags
0x180064685  xor     edx, edx; lpName
0x180064687  xor     ecx, ecx; lpEventAttributes
0x180064689  call    cs:__imp_CreateEventExW
0x18006468f  mov     [rbx+38h], rax
0x180064693  test    rax, rax
0x180064696  jnz     short loc_1800646BD
0x180064698  call    cs:__imp_GetLastError
0x18006469e  mov     edi, eax
0x1800646a0  test    eax, eax
0x1800646a2  jle     short loc_1800646AD
0x1800646a4  movzx   edi, ax
0x1800646a7  or      edi, 80070000h
0x1800646ad  test    edi, edi
0x1800646af  jns     short loc_1800646BD
0x1800646b1  lea     result, [rsp+38h+object]; this
0x1800646b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800646bb  jmp     short loc_1800646DC
0x1800646bd  mov     rax, [rbx]
0x1800646c0  mov     result, rbx
0x1800646c3  mov     rax, [rax+8]
0x1800646c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800646cc  nop
0x1800646cd  mov     [rsi], rbx
0x1800646d0  lea     result, [rsp+38h+object]; this
0x1800646d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800646da  xor     edi, edi
0x1800646dc  lea     result, [rsp+38h+allocator]; this
0x1800646e1  call    ??1?$MakeAllocator@VProvisionedProfile@NetworkOperators@Networking@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Networking::NetworkOperators::ProvisionedProfile>::~MakeAllocator<Windows::Networking::NetworkOperators::ProvisionedProfile>(void)
0x1800646e6  mov     eax, edi
0x1800646e8  mov     rbx, [rsp+38h+arg_8]
0x1800646ed  mov     rsi, [rsp+38h+arg_10]
0x1800646f2  add     rsp, 30h
0x1800646f6  pop     rdi
0x1800646f7  retn
```
