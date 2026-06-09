# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x1800eb7a0`
- end: `0x1800eb8d6`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `310`
- prototype: `HRESULT __fastcall(WaitForCompletion::__l2::FTMEventDelegate **result)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800eba00`

## callees

- `0x18002483c`
- `0x1800730a4`
- `0x1800a18a0`
- `0x1800cb4d8`
- `0x1800eb7a0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800eb868`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800eb868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eb877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eb877`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAVStorageFile_Storage_Windows___23___YAJPEAU__IAsyncOperation_PEAVStorageFile_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAVStorageFile_Storage_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAVStorageFile_Storage_Windows___23___YAJPEAU__IAsyncOperation_PEAVStorageFile_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        WaitForCompletion::__l2::FTMEventDelegate **result)
{
  WaitForCompletion::__l2::FTMEventDelegate *buffer; // rdi
  signed int v3; // ebx
  _QWORD *v4; // rbx
  Microsoft::WRL::Details::ModuleBase *v5; // rcx
  HANDLE Event; // rax
  signed int LastError; // eax
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> >'::`2'::FTMEventDelegate> object; // [rsp+30h] [rbp+8h] BYREF
  Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> >'::`2'::FTMEventDelegate> allocator; // [rsp+38h] [rbp+10h] BYREF

  *result = 0;
  allocator.buffer_ = operator new(0x40u, &std::nothrow);
  buffer = (WaitForCompletion::__l2::FTMEventDelegate *)allocator.buffer_;
  if ( allocator.buffer_ )
  {
    v4 = (char *)allocator.buffer_ + 8;
    *(_QWORD *)allocator.buffer_ = Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase(&buffer->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >);
    v5 = Microsoft::WRL::Details::ModuleBase::module_;
    buffer->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Windows::Foundation::IAsyncActionCompletedHandler::IUnknown::__vftable = (WaitForCompletion::__l2::FTMEventDelegate_vtbl *)Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>'};
    buffer->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >_vtbl *)Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    buffer->refcount_ = 1;
    if ( v5 )
      v5->IncrementObjectCount(v5);
    buffer->_status = Started;
    buffer->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Windows::Foundation::IAsyncActionCompletedHandler::IUnknown::__vftable = (WaitForCompletion::__l2::FTMEventDelegate_vtbl *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>'::`2'::FTMEventDelegate::`vftable';
    buffer->_hEventCompleted = 0;
    *v4 = Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    object.ptr_ = buffer;
    allocator.buffer_ = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    buffer->_hEventCompleted = Event;
    if ( Event )
      goto LABEL_10;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_10:
      buffer->AddRef(buffer);
      *result = buffer;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&object);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&object);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  _stack<ElementDecl *>::~_stack<ElementDecl *>((_stack<DeclAttDef *> *)&allocator);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800eb7a0  mov     [rsp+arg_10], rbx
0x1800eb7a5  mov     [rsp+arg_18], rsi
0x1800eb7aa  push    rdi
0x1800eb7ab  sub     rsp, 20h
0x1800eb7af  mov     rsi, result
0x1800eb7b2  mov     qword ptr [result], 0
0x1800eb7b9  mov     ecx, 40h ; '@'; size
0x1800eb7be  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; __formal
0x1800eb7c5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800eb7ca  mov     [rsp+28h+allocator.buffer_], rax
0x1800eb7cf  mov     rdi, rax
0x1800eb7d2  test    rax, rax
0x1800eb7d5  jnz     short loc_1800EB7E1
0x1800eb7d7  mov     ebx, 8007000Eh
0x1800eb7dc  jmp     loc_1800EB8BA
0x1800eb7e1  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>::`vftable'
0x1800eb7e8  lea     rbx, [rdi+8]
0x1800eb7ec  mov     [rdi], rax
0x1800eb7ef  mov     result, rbx; this
0x1800eb7f2  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800eb7f7  mov     result, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800eb7fe  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>'}
0x1800eb805  mov     [rdi], rax
0x1800eb808  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800eb80f  mov     [rbx], rax
0x1800eb812  mov     dword ptr [rdi+2Ch], 1
0x1800eb819  test    result, result
0x1800eb81c  jz      short loc_1800EB82A
0x1800eb81e  mov     rax, [result]
0x1800eb821  mov     rax, [rax+8]
0x1800eb825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb82a  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>'}
0x1800eb831  mov     dword ptr [rdi+30h], 0
0x1800eb838  mov     [rdi], rax
0x1800eb83b  mov     r9d, 1F0003h; dwDesiredAccess
0x1800eb841  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800eb848  mov     qword ptr [rdi+38h], 0
0x1800eb850  xor     r8d, r8d; dwFlags
0x1800eb853  mov     [rbx], rax
0x1800eb856  xor     edx, edx; lpName
0x1800eb858  mov     [rsp+28h+object.ptr_], rdi
0x1800eb85d  xor     ecx, ecx; lpEventAttributes
0x1800eb85f  mov     [rsp+28h+allocator.buffer_], 0
0x1800eb868  call    cs:__imp_CreateEventExW
0x1800eb86e  mov     [rdi+38h], rax
0x1800eb872  test    rax, rax
0x1800eb875  jnz     short loc_1800EB89C
0x1800eb877  call    cs:__imp_GetLastError
0x1800eb87d  mov     ebx, eax
0x1800eb87f  test    eax, eax
0x1800eb881  jle     short loc_1800EB88C
0x1800eb883  movzx   ebx, ax
0x1800eb886  or      ebx, 80070000h
0x1800eb88c  test    ebx, ebx
0x1800eb88e  jns     short loc_1800EB89C
0x1800eb890  lea     result, [rsp+28h+object]; this
0x1800eb895  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800eb89a  jmp     short loc_1800EB8BA
0x1800eb89c  mov     rax, [rdi]
0x1800eb89f  mov     result, rdi
0x1800eb8a2  mov     rax, [rax+8]
0x1800eb8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb8ab  lea     result, [rsp+28h+object]; this
0x1800eb8b0  mov     [rsi], rdi
0x1800eb8b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800eb8b8  xor     ebx, ebx
0x1800eb8ba  lea     result, [rsp+28h+allocator]; this
0x1800eb8bf  call    ??1?$_stack@PEAVElementDecl@@@@QEAA@XZ; _stack<ElementDecl *>::~_stack<ElementDecl *>(void)
0x1800eb8c4  mov     rsi, [rsp+28h+arg_18]
0x1800eb8c9  mov     eax, ebx
0x1800eb8cb  mov     rbx, [rsp+28h+arg_10]
0x1800eb8d0  add     rsp, 20h
0x1800eb8d4  pop     rdi
0x1800eb8d5  retn
```
