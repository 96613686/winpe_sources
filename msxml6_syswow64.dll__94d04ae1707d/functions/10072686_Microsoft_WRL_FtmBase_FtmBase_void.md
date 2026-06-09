# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x10072686`
- end: `0x100726e8`
- name: `??0FtmBase@WRL@Microsoft@@QAE@XZ`
- size: `98`
- prototype: `void __thiscall(Microsoft::WRL::FtmBase *this)`
- caller_count: `11`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1007249e`
- `0x100724fa`
- `0x10072556`
- `0x100725d3`
- `0x10072621`
- `0x10090c9d`
- `0x10090d19`
- `0x100a1211`
- `0x100a1254`
- `0x100a12a1`
- `0x100b165e`

## callees

- `0x10067bc0`
- `0x10072686`
- `0x10073a99`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x100726ab`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x100726ab`

## pseudocode

```c
void __thiscall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  IUnknown *ptr; // esi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const _GUID *, void **); // edi
  Microsoft::WRL::ComPtr<IUnknown> unknown; // [esp+8h] [ebp-4h] BYREF

  unknown.ptr_ = 0;
  this->__vftable = (Microsoft::WRL::FtmBase_vtbl *)CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&unsigned short const * const SaveToFileAsyncOperationName>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  this->marshaller_.ptr_ = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&unknown);
  if ( CoCreateFreeThreadedMarshaler(0, &unknown.ptr_) >= 0 )
  {
    ptr = unknown.ptr_;
    QueryInterface = unknown.ptr_->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&this->marshaller_);
    ((void (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IUnknown *, GUID *, Microsoft::WRL::ComPtr<IMarshal> *))QueryInterface)(
      QueryInterface,
      ptr,
      &_GUID_00000003_0000_0000_c000_000000000046,
      &this->marshaller_);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&unknown);
}

```

## disassembly

```asm
0x10072686  mov     edi, edi
0x10072688  push    ebp
0x10072689  mov     ebp, esp
0x1007268b  push    this
0x1007268c  push    ebx
0x1007268d  mov     ebx, this
0x1007268f  lea     this, [ebp+unknown]; this
0x10072692  push    esi
0x10072693  xor     esi, esi
0x10072695  mov     [ebp+unknown.ptr_], esi
0x10072698  mov     dword ptr [ebx], offset ??_7?$CAsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$1?SaveToFileAsyncOperationName@@3QBGB@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SaveToFileAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&ushort const * const SaveToFileAsyncOperationName>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1007269e  mov     [ebx+0Ch], esi
0x100726a1  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100726a6  lea     eax, [ebp+unknown]
0x100726a9  push    eax; ppunkMarshal
0x100726aa  push    esi; punkOuter
0x100726ab  call    ds:__imp__CoCreateFreeThreadedMarshaler@8; CoCreateFreeThreadedMarshaler(x,x)
0x100726b1  test    eax, eax
0x100726b3  js      short loc_100726DA
0x100726b5  mov     esi, [ebp+unknown.ptr_]
0x100726b8  lea     this, [ebx+0Ch]; this
0x100726bb  push    edi
0x100726bc  mov     eax, [esi]
0x100726be  mov     edi, [eax]
0x100726c0  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100726c5  lea     eax, [ebx+0Ch]
0x100726c8  mov     this, edi; this
0x100726ca  push    eax
0x100726cb  push    offset __GUID_00000003_0000_0000_c000_000000000046
0x100726d0  push    esi
0x100726d1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100726d7  call    edi
0x100726d9  pop     edi
0x100726da  lea     this, [ebp+unknown]; this
0x100726dd  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100726e2  pop     esi
0x100726e3  mov     eax, ebx
0x100726e5  pop     ebx
0x100726e6  leave
0x100726e7  retn
```
