# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x1007269a`
- end: `0x100726fc`
- name: `??0FtmBase@WRL@Microsoft@@QAE@XZ`
- size: `98`
- prototype: `void __thiscall(Microsoft::WRL::FtmBase *this)`
- caller_count: `11`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100724b2`
- `0x1007250e`
- `0x1007256a`
- `0x100725e7`
- `0x10072635`
- `0x10090d67`
- `0x10090de3`
- `0x100a1303`
- `0x100a1346`
- `0x100a1393`
- `0x100b176e`

## callees

- `0x10067b20`
- `0x1007269a`
- `0x10073ac9`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x100726bf`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x100726bf`

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
0x1007269a  mov     edi, edi
0x1007269c  push    ebp
0x1007269d  mov     ebp, esp
0x1007269f  push    this
0x100726a0  push    ebx
0x100726a1  mov     ebx, this
0x100726a3  lea     this, [ebp+unknown]; this
0x100726a6  push    esi
0x100726a7  xor     esi, esi
0x100726a9  mov     [ebp+unknown.ptr_], esi
0x100726ac  mov     dword ptr [ebx], offset ??_7?$CAsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$1?SaveToFileAsyncOperationName@@3QBGB@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SaveToFileAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&ushort const * const SaveToFileAsyncOperationName>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x100726b2  mov     [ebx+0Ch], esi
0x100726b5  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100726ba  lea     eax, [ebp+unknown]
0x100726bd  push    eax; ppunkMarshal
0x100726be  push    esi; punkOuter
0x100726bf  call    ds:__imp__CoCreateFreeThreadedMarshaler@8; CoCreateFreeThreadedMarshaler(x,x)
0x100726c5  test    eax, eax
0x100726c7  js      short loc_100726EE
0x100726c9  mov     esi, [ebp+unknown.ptr_]
0x100726cc  lea     this, [ebx+0Ch]; this
0x100726cf  push    edi
0x100726d0  mov     eax, [esi]
0x100726d2  mov     edi, [eax]
0x100726d4  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100726d9  lea     eax, [ebx+0Ch]
0x100726dc  mov     this, edi; this
0x100726de  push    eax
0x100726df  push    offset __GUID_00000003_0000_0000_c000_000000000046
0x100726e4  push    esi
0x100726e5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100726eb  call    edi
0x100726ed  pop     edi
0x100726ee  lea     this, [ebp+unknown]; this
0x100726f1  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100726f6  pop     esi
0x100726f7  mov     eax, ebx
0x100726f9  pop     ebx
0x100726fa  leave
0x100726fb  retn
```
