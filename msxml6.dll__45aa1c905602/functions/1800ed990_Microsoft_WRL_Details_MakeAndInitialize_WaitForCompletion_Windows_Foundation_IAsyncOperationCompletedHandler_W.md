# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x1800ed990`
- end: `0x1800edad3`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `323`
- prototype: `HRESULT __fastcall(WaitForCompletion::__l2::FTMEventDelegate **result)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800edc00`

## callees

- `0x1800719e4`
- `0x1800a218c`
- `0x1800b062c`
- `0x1800ccdf8`
- `0x1800ed990`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800eda58`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800eda58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eda6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eda6d`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAVStorageFile_Storage_Windows___23___YAJPEAU__IAsyncOperation_PEAVStorageFile_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAVStorageFile_Storage_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAVStorageFile_Storage_Windows___23___YAJPEAU__IAsyncOperation_PEAVStorageFile_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        WaitForCompletion::__l2::FTMEventDelegate **result)
{
  char *buffer; // rdi
  signed int v3; // ebx
  char *v4; // rbx
  Microsoft::WRL::Details::ModuleBase *v5; // rcx
  HANDLE Event; // rax
  signed int LastError; // eax
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> >'::`2'::FTMEventDelegate> object; // [rsp+30h] [rbp+8h] BYREF
  Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> >'::`2'::FTMEventDelegate> allocator; // [rsp+38h] [rbp+10h] BYREF

  *result = 0;
  allocator.buffer_ = (char *)operator new(0x40u, &std::nothrow);
  buffer = allocator.buffer_;
  if ( allocator.buffer_ )
  {
    v4 = allocator.buffer_ + 8;
    *(_QWORD *)allocator.buffer_ = Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(buffer + 8));
    v5 = Microsoft::WRL::Details::ModuleBase::module_;
    *(_QWORD *)buffer = Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>'};
    *((_QWORD *)buffer + 1) = Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *((_DWORD *)buffer + 11) = 1;
    if ( v5 )
      v5->IncrementObjectCount(v5);
    *((_DWORD *)buffer + 12) = 0;
    *(_QWORD *)buffer = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)buffer + 7) = 0;
    *(_QWORD *)v4 = Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    object.ptr_ = (WaitForCompletion::__l2::FTMEventDelegate *)buffer;
    allocator.buffer_ = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    *((_QWORD *)buffer + 7) = Event;
    if ( Event )
      goto LABEL_10;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_10:
      (*(void (__fastcall **)(char *))(*(_QWORD *)buffer + 8LL))(buffer);
      *result = (WaitForCompletion::__l2::FTMEventDelegate *)buffer;
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
  Microsoft::WRL::Details::MakeAllocator<NodeIterator>::~MakeAllocator<NodeIterator>(&allocator);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800ed990  mov     [rsp+arg_10], rbx
0x1800ed995  mov     [rsp+arg_18], rsi
0x1800ed99a  push    rdi
0x1800ed99b  sub     rsp, 20h
0x1800ed99f  mov     rsi, result
0x1800ed9a2  mov     qword ptr [result], 0
0x1800ed9a9  mov     ecx, 40h ; '@'; size
0x1800ed9ae  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; __formal
0x1800ed9b5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800ed9ba  mov     [rsp+28h+allocator.buffer_], rax
0x1800ed9bf  mov     rdi, rax
0x1800ed9c2  test    rax, rax
0x1800ed9c5  jnz     short loc_1800ED9D1
0x1800ed9c7  mov     ebx, 8007000Eh
0x1800ed9cc  jmp     loc_1800EDAB6
0x1800ed9d1  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>::`vftable'
0x1800ed9d8  lea     rbx, [rdi+8]
0x1800ed9dc  mov     [rdi], rax
0x1800ed9df  mov     result, rbx; this
0x1800ed9e2  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800ed9e7  mov     result, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800ed9ee  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>'}
0x1800ed9f5  mov     [rdi], rax
0x1800ed9f8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800ed9ff  mov     [rbx], rax
0x1800eda02  mov     dword ptr [rdi+2Ch], 1
0x1800eda09  test    result, result
0x1800eda0c  jz      short loc_1800EDA1A
0x1800eda0e  mov     rax, [result]
0x1800eda11  mov     rax, [rax+8]
0x1800eda15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eda1a  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>'}
0x1800eda21  mov     dword ptr [rdi+30h], 0
0x1800eda28  mov     [rdi], rax
0x1800eda2b  mov     r9d, 1F0003h; dwDesiredAccess
0x1800eda31  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800eda38  mov     qword ptr [rdi+38h], 0
0x1800eda40  xor     r8d, r8d; dwFlags
0x1800eda43  mov     [rbx], rax
0x1800eda46  xor     edx, edx; lpName
0x1800eda48  mov     [rsp+28h+object.ptr_], rdi
0x1800eda4d  xor     ecx, ecx; lpEventAttributes
0x1800eda4f  mov     [rsp+28h+allocator.buffer_], 0
0x1800eda58  call    cs:__imp_CreateEventExW
0x1800eda5f  nop     dword ptr [rax+rax+00h]
0x1800eda64  mov     [rdi+38h], rax
0x1800eda68  test    rax, rax
0x1800eda6b  jnz     short loc_1800EDA98
0x1800eda6d  call    cs:__imp_GetLastError
0x1800eda74  nop     dword ptr [rax+rax+00h]
0x1800eda79  mov     ebx, eax
0x1800eda7b  test    eax, eax
0x1800eda7d  jle     short loc_1800EDA88
0x1800eda7f  movzx   ebx, ax
0x1800eda82  or      ebx, 80070000h
0x1800eda88  test    ebx, ebx
0x1800eda8a  jns     short loc_1800EDA98
0x1800eda8c  lea     result, [rsp+28h+object]; this
0x1800eda91  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800eda96  jmp     short loc_1800EDAB6
0x1800eda98  mov     rax, [rdi]
0x1800eda9b  mov     result, rdi
0x1800eda9e  mov     rax, [rax+8]
0x1800edaa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edaa7  lea     result, [rsp+28h+object]; this
0x1800edaac  mov     [rsi], rdi
0x1800edaaf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800edab4  xor     ebx, ebx
0x1800edab6  lea     result, [rsp+28h+allocator]; this
0x1800edabb  call    ??1?$MakeAllocator@VNodeIterator@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<NodeIterator>::~MakeAllocator<NodeIterator>(void)
0x1800edac0  mov     rsi, [rsp+28h+arg_18]
0x1800edac5  mov     eax, ebx
0x1800edac7  mov     rbx, [rsp+28h+arg_10]
0x1800edacc  add     rsp, 20h
0x1800edad0  pop     rdi
0x1800edad1  retn
```
