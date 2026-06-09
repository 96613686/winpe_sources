# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x100a0d31`
- end: `0x100a0dc9`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@YGJPAU?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@YGJ012@Z@$$V@Details@WRL@Microsoft@@YGJPAPAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@YGJPAU?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PAX@Z@@Z`
- size: `152`
- prototype: `HRESULT __userpurge@<eax>(WaitForCompletion::__l2::FTMEventDelegate **result@<ecx>)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100a0e6d`

## callees

- `0x10067bc0`
- `0x1006bcb5`
- `0x10073a99`
- `0x100a0d31`
- `0x100a1254`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x100a0d80`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x100a0d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a0d8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a0d8d`

## pseudocode

```c
unsigned int __thiscall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PAUIRandomAccessStream_Streams_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PAUIRandomAccessStream_Streams_Storage_Windows___23___YGJPAU__IAsyncOperation_PAUIRandomAccessStream_Streams_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PAUIRandomAccessStream_Streams_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PAUIRandomAccessStream_Streams_Storage_Windows___23___YGJ012_Z___V_Details_WRL_Microsoft__YGJPAPAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PAUIRandomAccessStream_Streams_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PAUIRandomAccessStream_Streams_Storage_Windows___23___YGJPAU__IAsyncOperation_PAUIRandomAccessStream_Streams_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PAX_Z__Z(
        Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase> **result)
{
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase> *v2; // eax
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase> *v3; // edi
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >_vtbl *Event; // eax
  signed int LastError; // eax
  unsigned int v7; // esi
  bool v8; // sf
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> >'::`2'::FTMEventDelegate> object; // [esp+Ch] [ebp-4h] BYREF

  *result = 0;
  v2 = (Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase> *)operator new(0x24u, &std::nothrow);
  v3 = v2;
  if ( !v2 )
    return -2147024882;
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>(v2);
  v3->Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>::Windows::Foundation::IAsyncOperationCompletedHandler_impl<Windows::Storage::Streams::IRandomAccessStream *>::IUnknown::__vftable = (Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>_vtbl *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>'::`2'::FTMEventDelegate::`vftable';
  v3->Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >_vtbl *)Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v3[1].Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>::Windows::Foundation::IAsyncOperationCompletedHandler_impl<Windows::Storage::Streams::IRandomAccessStream *>::IUnknown::__vftable = 0;
  v3[1].Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::__vftable = 0;
  object.ptr_ = (WaitForCompletion::__l2::FTMEventDelegate *)v3;
  Event = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >_vtbl *)CreateEventExW(0, 0, 0, 0x1F0003u);
  v3[1].Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::__vftable = Event;
  if ( Event )
    goto LABEL_7;
  LastError = GetLastError();
  v7 = LastError;
  v8 = LastError < 0;
  if ( LastError > 0 )
  {
    v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = 1;
  }
  if ( !v8 )
  {
LABEL_7:
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase> *))v3->AddRef)(
      v3->AddRef,
      v3);
    *result = v3;
    v7 = 0;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&object);
  return v7;
}

```

## disassembly

```asm
0x100a0d31  mov     edi, edi
0x100a0d33  push    ebp
0x100a0d34  mov     ebp, esp
0x100a0d36  push    result
0x100a0d37  push    ebx
0x100a0d38  push    esi
0x100a0d39  push    edi
0x100a0d3a  mov     ebx, result
0x100a0d3c  xor     esi, esi
0x100a0d3e  push    offset ?nothrow@std@@3Unothrow_t@1@B; __formal
0x100a0d43  push    24h ; '$'; size
0x100a0d45  mov     [ebx], esi
0x100a0d47  call    ??2@YAPAXIABUnothrow_t@std@@@Z; operator new(uint,std::nothrow_t const &)
0x100a0d4c  mov     edi, eax
0x100a0d4e  pop     result
0x100a0d4f  pop     result
0x100a0d50  test    edi, edi
0x100a0d52  jnz     short loc_100A0D5B
0x100a0d54  mov     eax, 8007000Eh
0x100a0d59  jmp     short loc_100A0DC4
0x100a0d5b  mov     result, edi; this
0x100a0d5d  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@QAE@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>(void)
0x100a0d62  push    1F0003h; dwDesiredAccess
0x100a0d67  push    esi; dwFlags
0x100a0d68  push    esi; lpName
0x100a0d69  push    esi; lpEventAttributes
0x100a0d6a  mov     dword ptr [edi], offset ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@YGJPAU?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PAX@Z@6B?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>'}
0x100a0d70  mov     dword ptr [edi+4], offset ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x100a0d77  mov     [edi+1Ch], esi
0x100a0d7a  mov     [edi+20h], esi
0x100a0d7d  mov     [ebp+object.ptr_], edi
0x100a0d80  call    ds:__imp__CreateEventExW@16; CreateEventExW(x,x,x,x)
0x100a0d86  mov     [edi+20h], eax
0x100a0d89  test    eax, eax
0x100a0d8b  jnz     short loc_100A0DA6
0x100a0d8d  call    ds:__imp__GetLastError@0; GetLastError()
0x100a0d93  mov     esi, eax
0x100a0d95  test    esi, esi
0x100a0d97  jle     short loc_100A0DA4
0x100a0d99  movzx   esi, si
0x100a0d9c  or      esi, 80070000h
0x100a0da2  test    esi, esi
0x100a0da4  js      short loc_100A0DBA
0x100a0da6  mov     eax, [edi]
0x100a0da8  push    edi
0x100a0da9  mov     esi, [eax+4]
0x100a0dac  mov     result, esi; this
0x100a0dae  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a0db4  call    esi
0x100a0db6  mov     [ebx], edi
0x100a0db8  xor     esi, esi
0x100a0dba  lea     result, [ebp+object]; this
0x100a0dbd  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100a0dc2  mov     eax, esi
0x100a0dc4  pop     edi
0x100a0dc5  pop     esi
0x100a0dc6  pop     ebx
0x100a0dc7  leave
0x100a0dc8  retn
```
