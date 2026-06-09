# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x1800ac4e0`
- end: `0x1800ac612`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `306`
- prototype: `HRESULT __fastcall(WaitForCompletion::__l2::FTMEventDelegate **result)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800edadc`

## callees

- `0x1800719e4`
- `0x1800a218c`
- `0x1800ac4e0`
- `0x1800b062c`
- `0x1800ccdf8`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800ac5a3`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800ac5a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac5b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac5b8`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUIRandomAccessStream_Streams_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAUIRandomAccessStream_Streams_Storage_Windows___23___YAJPEAU__IAsyncOperation_PEAUIRandomAccessStream_Streams_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUIRandomAccessStream_Streams_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAUIRandomAccessStream_Streams_Storage_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUIRandomAccessStream_Streams_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAUIRandomAccessStream_Streams_Storage_Windows___23___YAJPEAU__IAsyncOperation_PEAUIRandomAccessStream_Streams_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        WaitForCompletion::__l2::FTMEventDelegate **result)
{
  WaitForCompletion::__l2::FTMEventDelegate *v2; // rdi
  Microsoft::WRL::Details::ModuleBase *v4; // rcx
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v7; // ebx
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> >'::`2'::FTMEventDelegate> object; // [rsp+30h] [rbp+8h] BYREF
  Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> >'::`2'::FTMEventDelegate> allocator; // [rsp+38h] [rbp+10h] BYREF

  *result = 0;
  v2 = (WaitForCompletion::__l2::FTMEventDelegate *)operator new(0x40u, &std::nothrow);
  if ( !v2 )
    return 2147942414LL;
  v2->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Windows::Foundation::IAsyncActionCompletedHandler::IUnknown::__vftable = (WaitForCompletion::__l2::FTMEventDelegate_vtbl *)Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase(&v2->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >);
  v4 = Microsoft::WRL::Details::ModuleBase::module_;
  v2->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Windows::Foundation::IAsyncActionCompletedHandler::IUnknown::__vftable = (WaitForCompletion::__l2::FTMEventDelegate_vtbl *)Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>'};
  v2->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >_vtbl *)Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2->refcount_ = 1;
  if ( v4 )
    v4->IncrementObjectCount(v4);
  v2->_status = Started;
  v2->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Windows::Foundation::IAsyncActionCompletedHandler::IUnknown::__vftable = (WaitForCompletion::__l2::FTMEventDelegate_vtbl *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>'::`2'::FTMEventDelegate::`vftable';
  v2->_hEventCompleted = 0;
  v2->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >_vtbl *)Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  object.ptr_ = v2;
  allocator.buffer_ = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v2->_hEventCompleted = Event;
  if ( Event )
    goto LABEL_9;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_9:
    v2->AddRef(v2);
    v7 = 0;
    *result = v2;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&object);
  Microsoft::WRL::Details::MakeAllocator<NodeIterator>::~MakeAllocator<NodeIterator>((Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> >'::`2'::FTMEventDelegate> *)&allocator);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800ac4e0  mov     [rsp+arg_10], rbx
0x1800ac4e5  mov     [rsp+arg_18], rsi
0x1800ac4ea  push    rdi
0x1800ac4eb  sub     rsp, 20h
0x1800ac4ef  mov     rsi, result
0x1800ac4f2  mov     qword ptr [result], 0
0x1800ac4f9  mov     ecx, 40h ; '@'; size
0x1800ac4fe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; __formal
0x1800ac505  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800ac50a  mov     rdi, rax
0x1800ac50d  test    rax, rax
0x1800ac510  jnz     short loc_1800AC51C
0x1800ac512  mov     eax, 8007000Eh
0x1800ac517  jmp     loc_1800AC601
0x1800ac51c  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>::`vftable'
0x1800ac523  lea     rbx, [rdi+8]
0x1800ac527  mov     [rdi], rax
0x1800ac52a  mov     result, rbx; this
0x1800ac52d  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800ac532  mov     result, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800ac539  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>'}
0x1800ac540  mov     [rdi], rax
0x1800ac543  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800ac54a  mov     [rbx], rax
0x1800ac54d  mov     dword ptr [rdi+2Ch], 1
0x1800ac554  test    result, result
0x1800ac557  jz      short loc_1800AC565
0x1800ac559  mov     rax, [result]
0x1800ac55c  mov     rax, [rax+8]
0x1800ac560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac565  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>'}
0x1800ac56c  mov     dword ptr [rdi+30h], 0
0x1800ac573  mov     [rdi], rax
0x1800ac576  mov     r9d, 1F0003h; dwDesiredAccess
0x1800ac57c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800ac583  mov     qword ptr [rdi+38h], 0
0x1800ac58b  xor     r8d, r8d; dwFlags
0x1800ac58e  mov     [rbx], rax
0x1800ac591  xor     edx, edx; lpName
0x1800ac593  mov     [rsp+28h+object.ptr_], rdi
0x1800ac598  xor     ecx, ecx; lpEventAttributes
0x1800ac59a  mov     [rsp+28h+allocator.buffer_], 0
0x1800ac5a3  call    cs:__imp_CreateEventExW
0x1800ac5aa  nop     dword ptr [rax+rax+00h]
0x1800ac5af  mov     [rdi+38h], rax
0x1800ac5b3  test    rax, rax
0x1800ac5b6  jnz     short loc_1800AC5D7
0x1800ac5b8  call    cs:__imp_GetLastError
0x1800ac5bf  nop     dword ptr [rax+rax+00h]
0x1800ac5c4  mov     ebx, eax
0x1800ac5c6  test    eax, eax
0x1800ac5c8  jle     short loc_1800AC5D3
0x1800ac5ca  movzx   ebx, ax
0x1800ac5cd  or      ebx, 80070000h
0x1800ac5d3  test    ebx, ebx
0x1800ac5d5  js      short loc_1800AC5EB
0x1800ac5d7  mov     rax, [rdi]
0x1800ac5da  mov     result, rdi
0x1800ac5dd  mov     rax, [rax+8]
0x1800ac5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac5e6  xor     ebx, ebx
0x1800ac5e8  mov     [rsi], rdi
0x1800ac5eb  lea     result, [rsp+28h+object]; this
0x1800ac5f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ac5f5  lea     result, [rsp+28h+allocator]; this
0x1800ac5fa  call    ??1?$MakeAllocator@VNodeIterator@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<NodeIterator>::~MakeAllocator<NodeIterator>(void)
0x1800ac5ff  mov     eax, ebx
0x1800ac601  mov     rbx, [rsp+28h+arg_10]
0x1800ac606  mov     rsi, [rsp+28h+arg_18]
0x1800ac60b  add     rsp, 20h
0x1800ac60f  pop     rdi
0x1800ac610  retn
```
