# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x100a0dcf`
- end: `0x100a0e67`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@23@@@YGJPAU?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@23@@@YGJ012@Z@$$V@Details@WRL@Microsoft@@YGJPAPAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@23@@@YGJPAU?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PAX@Z@@Z`
- size: `152`
- prototype: `HRESULT __userpurge@<eax>(WaitForCompletion::__l2::FTMEventDelegate **result@<ecx>)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100a0f69`

## callees

- `0x10067bc0`
- `0x1006bcb5`
- `0x10073a99`
- `0x100a0dcf`
- `0x100a12a1`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x100a0e1e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x100a0e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a0e2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a0e2b`

## pseudocode

```c
unsigned int __thiscall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PAVStorageFile_Storage_Windows___23___YGJPAU__IAsyncOperation_PAVStorageFile_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PAVStorageFile_Storage_Windows___23___YGJ012_Z___V_Details_WRL_Microsoft__YGJPAPAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PAVStorageFile_Storage_Windows___23___YGJPAU__IAsyncOperation_PAVStorageFile_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PAX_Z__Z(
        Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase> **result)
{
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase> *v2; // eax
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase> *v3; // edi
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >_vtbl *Event; // eax
  signed int LastError; // eax
  unsigned int v7; // esi
  bool v8; // sf
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> >'::`2'::FTMEventDelegate> object; // [esp+Ch] [ebp-4h] BYREF

  *result = 0;
  v2 = (Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase> *)operator new(0x24u, &std::nothrow);
  v3 = v2;
  if ( !v2 )
    return -2147024882;
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>(v2);
  v3->Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>::Windows::Foundation::IAsyncOperationCompletedHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Storage::StorageFile *,Windows::Storage::IStorageFile *> >::IUnknown::__vftable = (Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>_vtbl *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>'::`2'::FTMEventDelegate::`vftable';
  v3->Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >_vtbl *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>'::`2'::FTMEventDelegate::`vftable';
  v3[1].Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>::Windows::Foundation::IAsyncOperationCompletedHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Storage::StorageFile *,Windows::Storage::IStorageFile *> >::IUnknown::__vftable = 0;
  v3[1].Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::__vftable = 0;
  object.ptr_ = (WaitForCompletion::__l2::FTMEventDelegate *)v3;
  Event = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >_vtbl *)CreateEventExW(0, 0, 0, 0x1F0003u);
  v3[1].Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::__vftable = Event;
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
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase> *))v3->AddRef)(
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
0x100a0dcf  mov     edi, edi
0x100a0dd1  push    ebp
0x100a0dd2  mov     ebp, esp
0x100a0dd4  push    result
0x100a0dd5  push    ebx
0x100a0dd6  push    esi
0x100a0dd7  push    edi
0x100a0dd8  mov     ebx, result
0x100a0dda  xor     esi, esi
0x100a0ddc  push    offset ?nothrow@std@@3Unothrow_t@1@B; __formal
0x100a0de1  push    24h ; '$'; size
0x100a0de3  mov     [ebx], esi
0x100a0de5  call    ??2@YAPAXIABUnothrow_t@std@@@Z; operator new(uint,std::nothrow_t const &)
0x100a0dea  mov     edi, eax
0x100a0dec  pop     result
0x100a0ded  pop     result
0x100a0dee  test    edi, edi
0x100a0df0  jnz     short loc_100A0DF9
0x100a0df2  mov     eax, 8007000Eh
0x100a0df7  jmp     short loc_100A0E62
0x100a0df9  mov     result, edi; this
0x100a0dfb  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@QAE@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>(void)
0x100a0e00  push    1F0003h; dwDesiredAccess
0x100a0e05  push    esi; dwFlags
0x100a0e06  push    esi; lpName
0x100a0e07  push    esi; lpEventAttributes
0x100a0e08  mov     dword ptr [edi], offset ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@23@@@YGJPAU?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PAX@Z@6B?$IAsyncOperationCompletedHandler@PAVStorageFile@Storage@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>'}
0x100a0e0e  mov     dword ptr [edi+4], offset ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@23@@@YGJPAU?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x100a0e15  mov     [edi+1Ch], esi
0x100a0e18  mov     [edi+20h], esi
0x100a0e1b  mov     [ebp+object.ptr_], edi
0x100a0e1e  call    ds:__imp__CreateEventExW@16; CreateEventExW(x,x,x,x)
0x100a0e24  mov     [edi+20h], eax
0x100a0e27  test    eax, eax
0x100a0e29  jnz     short loc_100A0E44
0x100a0e2b  call    ds:__imp__GetLastError@0; GetLastError()
0x100a0e31  mov     esi, eax
0x100a0e33  test    esi, esi
0x100a0e35  jle     short loc_100A0E42
0x100a0e37  movzx   esi, si
0x100a0e3a  or      esi, 80070000h
0x100a0e40  test    esi, esi
0x100a0e42  js      short loc_100A0E58
0x100a0e44  mov     eax, [edi]
0x100a0e46  push    edi
0x100a0e47  mov     esi, [eax+4]
0x100a0e4a  mov     result, esi; this
0x100a0e4c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a0e52  call    esi
0x100a0e54  mov     [ebx], edi
0x100a0e56  xor     esi, esi
0x100a0e58  lea     result, [ebp+object]; this
0x100a0e5b  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100a0e60  mov     eax, esi
0x100a0e62  pop     edi
0x100a0e63  pop     esi
0x100a0e64  pop     ebx
0x100a0e65  leave
0x100a0e66  retn
```
