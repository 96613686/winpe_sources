# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x100a0ea8`
- end: `0x100a0f59`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@23@@@YGJPAU?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@23@@@YGJ012@Z@$$V@Details@WRL@Microsoft@@YGJPAPAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@23@@@YGJPAU?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PAX@Z@@Z`
- size: `177`
- prototype: `HRESULT __userpurge@<eax>(WaitForCompletion::__l2::FTMEventDelegate **result@<ecx>)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100a105b`

## callees

- `0x10067b20`
- `0x1006bc15`
- `0x10072758`
- `0x10073ac9`
- `0x100a0ea8`
- `0x100a1393`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x100a0efe`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x100a0efe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a0f0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a0f0b`

## pseudocode

```c
unsigned int __thiscall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PAVStorageFile_Storage_Windows___23___YGJPAU__IAsyncOperation_PAVStorageFile_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PAVStorageFile_Storage_Windows___23___YGJ012_Z___V_Details_WRL_Microsoft__YGJPAPAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PAVStorageFile_Storage_Windows___23___YGJPAU__IAsyncOperation_PAVStorageFile_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PAX_Z__Z(
        WaitForCompletion::__l2::FTMEventDelegate **result)
{
  char *v2; // eax
  char *v3; // edi
  unsigned int v4; // esi
  HANDLE Event; // eax
  signed int LastError; // eax
  bool v7; // sf
  Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> >'::`2'::FTMEventDelegate> allocator; // [esp+Ch] [ebp-8h] BYREF
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> >'::`2'::FTMEventDelegate> object; // [esp+10h] [ebp-4h] BYREF

  *result = 0;
  v2 = (char *)operator new(0x24u, &std::nothrow);
  v3 = v2;
  allocator.buffer_ = v2;
  if ( v2 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>((Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase> *)v2);
    *(_DWORD *)v3 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>'::`2'::FTMEventDelegate::`vftable';
    *((_DWORD *)v3 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>'::`2'::FTMEventDelegate::`vftable';
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
  Microsoft::WRL::Details::MakeAllocator<NodeIterator>::~MakeAllocator<NodeIterator>(&allocator);
  return v4;
}

```

## disassembly

```asm
0x100a0ea8  mov     edi, edi
0x100a0eaa  push    ebp
0x100a0eab  mov     ebp, esp
0x100a0ead  push    result
0x100a0eae  push    result
0x100a0eaf  push    ebx
0x100a0eb0  push    esi
0x100a0eb1  push    edi
0x100a0eb2  mov     ebx, result
0x100a0eb4  xor     esi, esi
0x100a0eb6  push    offset ?nothrow@std@@3Unothrow_t@1@B; __formal
0x100a0ebb  push    24h ; '$'; size
0x100a0ebd  mov     [ebx], esi
0x100a0ebf  call    ??2@YAPAXIABUnothrow_t@std@@@Z; operator new(uint,std::nothrow_t const &)
0x100a0ec4  mov     edi, eax
0x100a0ec6  mov     [ebp+allocator.buffer_], edi
0x100a0ec9  pop     result
0x100a0eca  pop     result
0x100a0ecb  test    edi, edi
0x100a0ecd  jnz     short loc_100A0ED6
0x100a0ecf  mov     esi, 8007000Eh
0x100a0ed4  jmp     short loc_100A0F4A
0x100a0ed6  mov     result, edi; this
0x100a0ed8  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@QAE@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>(void)
0x100a0edd  push    1F0003h; dwDesiredAccess
0x100a0ee2  push    esi; dwFlags
0x100a0ee3  push    esi; lpName
0x100a0ee4  push    esi; lpEventAttributes
0x100a0ee5  mov     dword ptr [edi], offset ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@23@@@YGJPAU?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PAX@Z@6B?$IAsyncOperationCompletedHandler@PAVStorageFile@Storage@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>'}
0x100a0eeb  mov     dword ptr [edi+4], offset ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@23@@@YGJPAU?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x100a0ef2  mov     [edi+1Ch], esi
0x100a0ef5  mov     [edi+20h], esi
0x100a0ef8  mov     [ebp+object.ptr_], edi
0x100a0efb  mov     [ebp+allocator.buffer_], esi
0x100a0efe  call    ds:__imp__CreateEventExW@16; CreateEventExW(x,x,x,x)
0x100a0f04  mov     [edi+20h], eax
0x100a0f07  test    eax, eax
0x100a0f09  jnz     short loc_100A0F2E
0x100a0f0b  call    ds:__imp__GetLastError@0; GetLastError()
0x100a0f11  mov     esi, eax
0x100a0f13  test    esi, esi
0x100a0f15  jle     short loc_100A0F22
0x100a0f17  movzx   esi, si
0x100a0f1a  or      esi, 80070000h
0x100a0f20  test    esi, esi
0x100a0f22  jns     short loc_100A0F2E
0x100a0f24  lea     result, [ebp+object]; this
0x100a0f27  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100a0f2c  jmp     short loc_100A0F4A
0x100a0f2e  mov     eax, [edi]
0x100a0f30  push    edi
0x100a0f31  mov     esi, [eax+4]
0x100a0f34  mov     result, esi; this
0x100a0f36  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a0f3c  call    esi
0x100a0f3e  lea     result, [ebp+object]; this
0x100a0f41  mov     [ebx], edi
0x100a0f43  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100a0f48  xor     esi, esi
0x100a0f4a  lea     result, [ebp+allocator]; this
0x100a0f4d  call    ??1?$MakeAllocator@VNodeIterator@@@Details@WRL@Microsoft@@QAE@XZ; Microsoft::WRL::Details::MakeAllocator<NodeIterator>::~MakeAllocator<NodeIterator>(void)
0x100a0f52  pop     edi
0x100a0f53  mov     eax, esi
0x100a0f55  pop     esi
0x100a0f56  pop     ebx
0x100a0f57  leave
0x100a0f58  retn
```
