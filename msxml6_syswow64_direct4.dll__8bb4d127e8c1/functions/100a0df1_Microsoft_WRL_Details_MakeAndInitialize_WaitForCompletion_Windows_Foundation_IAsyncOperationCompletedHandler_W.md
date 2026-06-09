# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x100a0df1`
- end: `0x100a0ea2`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@YGJPAU?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@YGJ012@Z@$$V@Details@WRL@Microsoft@@YGJPAPAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@YGJPAU?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PAX@Z@@Z`
- size: `177`
- prototype: `HRESULT __userpurge@<eax>(WaitForCompletion::__l2::FTMEventDelegate **result@<ecx>)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100a0f5f`

## callees

- `0x10067b20`
- `0x1006bc15`
- `0x10072758`
- `0x10073ac9`
- `0x100a0df1`
- `0x100a1346`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x100a0e47`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x100a0e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a0e54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a0e54`

## pseudocode

```c
unsigned int __thiscall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PAUIRandomAccessStream_Streams_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PAUIRandomAccessStream_Streams_Storage_Windows___23___YGJPAU__IAsyncOperation_PAUIRandomAccessStream_Streams_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PAUIRandomAccessStream_Streams_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PAUIRandomAccessStream_Streams_Storage_Windows___23___YGJ012_Z___V_Details_WRL_Microsoft__YGJPAPAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PAUIRandomAccessStream_Streams_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PAUIRandomAccessStream_Streams_Storage_Windows___23___YGJPAU__IAsyncOperation_PAUIRandomAccessStream_Streams_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PAX_Z__Z(
        WaitForCompletion::__l2::FTMEventDelegate **result)
{
  char *v2; // eax
  char *v3; // edi
  unsigned int v4; // esi
  HANDLE Event; // eax
  signed int LastError; // eax
  bool v7; // sf
  Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> >'::`2'::FTMEventDelegate> allocator; // [esp+Ch] [ebp-8h] BYREF
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> >'::`2'::FTMEventDelegate> object; // [esp+10h] [ebp-4h] BYREF

  *result = 0;
  v2 = (char *)operator new(0x24u, &std::nothrow);
  v3 = v2;
  allocator.buffer_ = v2;
  if ( v2 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>((Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase> *)v2);
    *(_DWORD *)v3 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>'::`2'::FTMEventDelegate::`vftable';
    *((_DWORD *)v3 + 1) = Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *((_DWORD *)v3 + 7) = 0;
    *((_DWORD *)v3 + 8) = 0;
    object.ptr_ = (WaitForCompletion::__l2::FTMEventDelegate *)v3;
    allocator.buffer_ = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    *((_DWORD *)v3 + 8) = Event;
    if ( Event )
      goto LABEL_8;
    LastError = GetLastError();
    v4 = LastError;
    v7 = LastError < 0;
    if ( LastError > 0 )
    {
      v4 = (unsigned __int16)LastError | 0x80070000;
      v7 = 1;
    }
    if ( !v7 )
    {
LABEL_8:
      (*(void (__thiscall **)(_DWORD, char *))(*(_DWORD *)v3 + 4))(*(_DWORD *)(*(_DWORD *)v3 + 4), v3);
      *result = (WaitForCompletion::__l2::FTMEventDelegate *)v3;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&object);
      v4 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&object);
    }
  }
  else
  {
    v4 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<NodeIterator>::~MakeAllocator<NodeIterator>((Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> >'::`2'::FTMEventDelegate> *)&allocator);
  return v4;
}

```

## disassembly

```asm
0x100a0df1  mov     edi, edi
0x100a0df3  push    ebp
0x100a0df4  mov     ebp, esp
0x100a0df6  push    result
0x100a0df7  push    result
0x100a0df8  push    ebx
0x100a0df9  push    esi
0x100a0dfa  push    edi
0x100a0dfb  mov     ebx, result
0x100a0dfd  xor     esi, esi
0x100a0dff  push    offset ?nothrow@std@@3Unothrow_t@1@B; __formal
0x100a0e04  push    24h ; '$'; size
0x100a0e06  mov     [ebx], esi
0x100a0e08  call    ??2@YAPAXIABUnothrow_t@std@@@Z; operator new(uint,std::nothrow_t const &)
0x100a0e0d  mov     edi, eax
0x100a0e0f  mov     [ebp+allocator.buffer_], edi
0x100a0e12  pop     result
0x100a0e13  pop     result
0x100a0e14  test    edi, edi
0x100a0e16  jnz     short loc_100A0E1F
0x100a0e18  mov     esi, 8007000Eh
0x100a0e1d  jmp     short loc_100A0E93
0x100a0e1f  mov     result, edi; this
0x100a0e21  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@QAE@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>(void)
0x100a0e26  push    1F0003h; dwDesiredAccess
0x100a0e2b  push    esi; dwFlags
0x100a0e2c  push    esi; lpName
0x100a0e2d  push    esi; lpEventAttributes
0x100a0e2e  mov     dword ptr [edi], offset ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@YGJPAU?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PAX@Z@6B?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>'}
0x100a0e34  mov     dword ptr [edi+4], offset ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x100a0e3b  mov     [edi+1Ch], esi
0x100a0e3e  mov     [edi+20h], esi
0x100a0e41  mov     [ebp+object.ptr_], edi
0x100a0e44  mov     [ebp+allocator.buffer_], esi
0x100a0e47  call    ds:__imp__CreateEventExW@16; CreateEventExW(x,x,x,x)
0x100a0e4d  mov     [edi+20h], eax
0x100a0e50  test    eax, eax
0x100a0e52  jnz     short loc_100A0E77
0x100a0e54  call    ds:__imp__GetLastError@0; GetLastError()
0x100a0e5a  mov     esi, eax
0x100a0e5c  test    esi, esi
0x100a0e5e  jle     short loc_100A0E6B
0x100a0e60  movzx   esi, si
0x100a0e63  or      esi, 80070000h
0x100a0e69  test    esi, esi
0x100a0e6b  jns     short loc_100A0E77
0x100a0e6d  lea     result, [ebp+object]; this
0x100a0e70  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100a0e75  jmp     short loc_100A0E93
0x100a0e77  mov     eax, [edi]
0x100a0e79  push    edi
0x100a0e7a  mov     esi, [eax+4]
0x100a0e7d  mov     result, esi; this
0x100a0e7f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a0e85  call    esi
0x100a0e87  lea     result, [ebp+object]; this
0x100a0e8a  mov     [ebx], edi
0x100a0e8c  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100a0e91  xor     esi, esi
0x100a0e93  lea     result, [ebp+allocator]; this
0x100a0e96  call    ??1?$MakeAllocator@VNodeIterator@@@Details@WRL@Microsoft@@QAE@XZ; Microsoft::WRL::Details::MakeAllocator<NodeIterator>::~MakeAllocator<NodeIterator>(void)
0x100a0e9b  pop     edi
0x100a0e9c  mov     eax, esi
0x100a0e9e  pop     esi
0x100a0e9f  pop     ebx
0x100a0ea0  leave
0x100a0ea1  retn
```
