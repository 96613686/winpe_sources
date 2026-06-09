# SaveWorkItem::DoWork(void)

- ea: `0x100b1b20`
- end: `0x100b1cdf`
- name: `?DoWork@SaveWorkItem@@EAEJXZ`
- size: `447`
- prototype: `HRESULT __thiscall(SaveWorkItem *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1003fb13`
- `0x100505bc`
- `0x10057ca1`
- `0x10067b20`
- `0x10073ac9`
- `0x100a0dd4`
- `0x100a1185`
- `0x100a11db`
- `0x100a27fa`
- `0x100b1b20`

## import_xrefs

- `OLEAUT32!__imp__VariantInit@4` at `0x100b1c20`
- `OLEAUT32!__imp__VariantInit@4` at `0x100b1c20`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x100b1be8`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x100b1be8`

## pseudocode

```c
HRESULT __thiscall SaveWorkItem::DoWork(SaveWorkItem *this)
{
  int Pointer; // ebx
  Windows::Storage::IStorageFile *ptr; // esi
  HRESULT (__stdcall *OpenAsync)(Windows::Storage::IStorageFile *, Windows::Storage::FileAccessMode, Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> **); // edi
  int v6; // eax
  SaveWorkItem *v7; // edi
  void **v8; // eax
  DOMDocumentWrapper *document; // ecx
  Windows::Storage::Streams::IRandomAccessStream *v10; // esi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const _GUID *, void **); // edi
  tagVARIANT v; // [esp+Ch] [ebp-2Ch] BYREF
  EnsureTls _EnsureTls; // [esp+1Ch] [ebp-1Ch] BYREF
  Microsoft::WRL::ComPtr<IStream> pStream; // [esp+20h] [ebp-18h] BYREF
  Microsoft::WRL::ComPtr<Windows::Storage::IStorageFile> spFile; // [esp+24h] [ebp-14h] BYREF
  Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream> spRandomAccessStream; // [esp+28h] [ebp-10h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IClosable> spCloseableStream; // [esp+2Ch] [ebp-Ch] BYREF
  SaveWorkItem *v18; // [esp+30h] [ebp-8h]
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> > spGetStreamOperation; // [esp+34h] [ebp-4h] BYREF

  v18 = this;
  EnsureTls::EnsureTls(&_EnsureTls);
  if ( !_EnsureTls._tlsdata )
    return -2147467259;
  spFile.ptr_ = 0;
  spGetStreamOperation.ptr_ = 0;
  spRandomAccessStream.ptr_ = 0;
  spCloseableStream.ptr_ = 0;
  pStream.ptr_ = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spFile);
  Pointer = _gitpointer<Windows::Storage::IStorageFile,&__s_GUID const _GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea>::HrGetPointer(
              (_gitpointer<IUnknown,&IID_IUnknown> *)&this->_gipFile,
              &spFile.ptr_);
  if ( Pointer >= 0 )
  {
    ptr = spFile.ptr_;
    OpenAsync = spFile.ptr_->OpenAsync;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spGetStreamOperation);
    v6 = ((int (__thiscall *)(HRESULT (__stdcall *)(Windows::Storage::IStorageFile *, Windows::Storage::FileAccessMode, Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> **), Windows::Storage::IStorageFile *, int, Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> > *))OpenAsync)(
           OpenAsync,
           ptr,
           1,
           &spGetStreamOperation);
    v7 = v18;
    Pointer = v6;
    if ( v6 < 0 )
      goto CleanUp_146;
    Pointer = _gitpointer<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,&__s_GUID const _GUID_430ecece_1418_5d19_81b2_5ddb381603cc>::HrSetPointer(
                &v18->_gipStreamRetrievalOp,
                spGetStreamOperation.ptr_);
    if ( Pointer < 0 )
      goto CleanUp_146;
    Pointer = WaitForCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Storage::Streams::IRandomAccessStream>(
                spGetStreamOperation.ptr_,
                (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream> >)&spRandomAccessStream);
    if ( Pointer < 0 )
      goto CleanUp_146;
    v8 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>((Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IStream> >)&pStream);
    Pointer = CreateStreamOverRandomAccessStream(
                spRandomAccessStream.ptr_,
                &_GUID_0000000c_0000_0000_c000_000000000046,
                v8);
    if ( Pointer < 0 )
      goto CleanUp_146;
    assign(&v7->_stm._pStream._p, pStream.ptr_);
    Pointer = ((int (__thiscall *)(HRESULT (__stdcall *)(IStream *, _ULARGE_INTEGER), CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName>::CAbortableIStream *, _DWORD, _DWORD))v7->_stm.SetSize)(
                v7->_stm.SetSize,
                &v7->_stm,
                0,
                0);
    if ( Pointer < 0 )
      goto CleanUp_146;
    VariantInit(&v);
    document = v7->_document;
    v.vt = 13;
    v.decVal.Lo32 = (unsigned int)&v7->_stm;
    Pointer = ((int (__thiscall *)(HRESULT (__stdcall *)(IXMLDOMDocument *, tagVARIANT), DOMDocumentWrapper *, _DWORD, unsigned int, CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName>::CAbortableIStream *, unsigned int))document->save)(
                document->save,
                document,
                *(_DWORD *)&v.vt,
                v.decVal.Hi32,
                &v7->_stm,
                v.decVal.Mid32);
  }
  v7 = v18;
CleanUp_146:
  safeRelease<DOMDocumentWrapper>(&v7->_document);
  assign(&v7->_stm._pStream._p, 0);
  v10 = spRandomAccessStream.ptr_;
  if ( spRandomAccessStream.ptr_ )
  {
    QueryInterface = spRandomAccessStream.ptr_->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spCloseableStream);
    ((void (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), Windows::Storage::Streams::IRandomAccessStream *, GUID *, Microsoft::WRL::ComPtr<Windows::Foundation::IClosable> *))QueryInterface)(
      QueryInterface,
      v10,
      &_GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e,
      &spCloseableStream);
    if ( spCloseableStream.ptr_ )
      ((void (__thiscall *)(HRESULT (__stdcall *)(Windows::Foundation::IClosable *), Windows::Foundation::IClosable *))spCloseableStream.ptr_->Close)(
        spCloseableStream.ptr_->Close,
        spCloseableStream.ptr_);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&pStream);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spCloseableStream);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spRandomAccessStream);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spGetStreamOperation);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spFile);
  return Pointer;
}

```

## disassembly

```asm
0x100b1b20  mov     edi, edi
0x100b1b22  push    ebp
0x100b1b23  mov     ebp, esp
0x100b1b25  sub     esp, 2Ch
0x100b1b28  push    ebx
0x100b1b29  push    esi
0x100b1b2a  mov     ebx, this
0x100b1b2c  lea     this, [ebp+_EnsureTls]; this
0x100b1b2f  push    edi
0x100b1b30  mov     [ebp+var_8], ebx
0x100b1b33  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100b1b38  cmp     [ebp+_EnsureTls._tlsdata], 0
0x100b1b3c  jnz     short loc_100B1B48
0x100b1b3e  mov     eax, 80004005h
0x100b1b43  jmp     loc_100B1CDA
0x100b1b48  xor     eax, eax
0x100b1b4a  lea     this, [ebp+spFile]; this
0x100b1b4d  mov     [ebp+spFile.ptr_], eax
0x100b1b50  mov     [ebp+spGetStreamOperation.ptr_], eax
0x100b1b53  mov     [ebp+spRandomAccessStream.ptr_], eax
0x100b1b56  mov     [ebp+spCloseableStream.ptr_], eax
0x100b1b59  mov     [ebp+pStream.ptr_], eax
0x100b1b5c  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100b1b61  lea     eax, [ebp+spFile]
0x100b1b64  push    eax; pptr
0x100b1b65  lea     this, [ebx+84h]; this
0x100b1b6b  call    ?HrGetPointer@?$_gitpointer@UIStorageFile@Storage@Windows@@$1?_GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea@@3U__s_GUID@@B@@QBEJPAPAUIStorageFile@Storage@Windows@@@Z; _gitpointer<Windows::Storage::IStorageFile,&__s_GUID const _GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea>::HrGetPointer(Windows::Storage::IStorageFile * *)
0x100b1b70  mov     ebx, eax
0x100b1b72  test    ebx, ebx
0x100b1b74  js      loc_100B1C5A
0x100b1b7a  mov     esi, [ebp+spFile.ptr_]
0x100b1b7d  lea     this, [ebp+spGetStreamOperation]; this
0x100b1b80  mov     eax, [esi]
0x100b1b82  mov     edi, [eax+20h]
0x100b1b85  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100b1b8a  lea     eax, [ebp+spGetStreamOperation]
0x100b1b8d  mov     this, edi; this
0x100b1b8f  push    eax
0x100b1b90  push    1
0x100b1b92  push    esi
0x100b1b93  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100b1b99  call    edi
0x100b1b9b  mov     edi, [ebp+var_8]
0x100b1b9e  mov     ebx, eax
0x100b1ba0  test    ebx, ebx
0x100b1ba2  js      CleanUp_146
0x100b1ba8  push    [ebp+spGetStreamOperation.ptr_]; ptr
0x100b1bab  lea     this, [edi+88h]; this
0x100b1bb1  call    ?HrSetPointer@?$_gitpointer@U?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@$1?_GUID_430ecece_1418_5d19_81b2_5ddb381603cc@@3U__s_GUID@@B@@QAEJPAU?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@@Z; _gitpointer<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,&__s_GUID const _GUID_430ecece_1418_5d19_81b2_5ddb381603cc>::HrSetPointer(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *)
0x100b1bb6  mov     ebx, eax
0x100b1bb8  test    ebx, ebx
0x100b1bba  js      CleanUp_146
0x100b1bc0  mov     this, [ebp+spGetStreamOperation.ptr_]; pOperation
0x100b1bc3  lea     eax, [ebp+spRandomAccessStream]
0x100b1bc6  push    eax; pp
0x100b1bc7  call    ??$WaitForCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@23@UIRandomAccessStream@Streams@Storage@3@@@YGJPAU?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIRandomAccessStream@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; WaitForCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Storage::Streams::IRandomAccessStream>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>>)
0x100b1bcc  mov     ebx, eax
0x100b1bce  test    ebx, ebx
0x100b1bd0  js      CleanUp_146
0x100b1bd6  lea     eax, [ebp+pStream]
0x100b1bd9  push    eax; pp
0x100b1bda  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YGPAPAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x100b1bdf  push    eax
0x100b1be0  push    offset __GUID_0000000c_0000_0000_c000_000000000046
0x100b1be5  push    [ebp+spRandomAccessStream.ptr_]
0x100b1be8  call    ds:__imp__CreateStreamOverRandomAccessStream@12; CreateStreamOverRandomAccessStream(x,x,x)
0x100b1bee  mov     ebx, eax
0x100b1bf0  test    ebx, ebx
0x100b1bf2  js      short CleanUp_146
0x100b1bf4  mov     edx, [ebp+pStream.ptr_]; pref
0x100b1bf7  lea     this, [edi+6Ch]; ppref
0x100b1bfa  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100b1bff  lea     this, [edi+60h]
0x100b1c02  mov     eax, [this]
0x100b1c04  push    0
0x100b1c06  push    0
0x100b1c08  push    this
0x100b1c09  mov     esi, [eax+18h]
0x100b1c0c  mov     this, esi; this
0x100b1c0e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100b1c14  call    esi
0x100b1c16  mov     ebx, eax
0x100b1c18  test    ebx, ebx
0x100b1c1a  js      short CleanUp_146
0x100b1c1c  lea     eax, [ebp+v]
0x100b1c1f  push    eax; pvarg
0x100b1c20  call    ds:__imp__VariantInit@4; VariantInit(x)
0x100b1c26  mov     this, [edi+80h]
0x100b1c2c  lea     esi, [ebp+v]
0x100b1c2f  push    0Dh
0x100b1c31  pop     eax
0x100b1c32  mov     word ptr [ebp+v.___u0], ax
0x100b1c36  sub     esp, 10h
0x100b1c39  lea     eax, [edi+60h]
0x100b1c3c  mov     edi, esp
0x100b1c3e  mov     dword ptr [ebp+v.___u0+8], eax
0x100b1c41  mov     eax, [this]
0x100b1c43  push    this
0x100b1c44  movsd
0x100b1c45  mov     ebx, [eax+108h]
0x100b1c4b  mov     this, ebx; this
0x100b1c4d  movsd
0x100b1c4e  movsd
0x100b1c4f  movsd
0x100b1c50  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100b1c56  call    ebx
0x100b1c58  mov     ebx, eax
0x100b1c5a  mov     edi, [ebp+var_8]
0x100b1c5d  lea     this, [edi+80h]; ptr
0x100b1c63  call    ??$safeRelease@VDOMDocumentWrapper@@@@YGXACRAVDOMDocumentWrapper@@@Z; safeRelease<DOMDocumentWrapper>(DOMDocumentWrapper * volatile &)
0x100b1c68  lea     this, [edi+6Ch]; ppref
0x100b1c6b  xor     edx, edx; pref
0x100b1c6d  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100b1c72  mov     esi, [ebp+spRandomAccessStream.ptr_]
0x100b1c75  test    esi, esi
0x100b1c77  jz      short loc_100B1CB0
0x100b1c79  mov     eax, [esi]
0x100b1c7b  lea     this, [ebp+spCloseableStream]; this
0x100b1c7e  mov     edi, [eax]
0x100b1c80  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100b1c85  lea     eax, [ebp+spCloseableStream]
0x100b1c88  mov     this, edi; this
0x100b1c8a  push    eax
0x100b1c8b  push    offset __GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e
0x100b1c90  push    esi
0x100b1c91  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100b1c97  call    edi
0x100b1c99  mov     eax, [ebp+spCloseableStream.ptr_]
0x100b1c9c  test    eax, eax
0x100b1c9e  jz      short loc_100B1CB0
0x100b1ca0  mov     this, [eax]
0x100b1ca2  push    eax
0x100b1ca3  mov     esi, [this+18h]
0x100b1ca6  mov     this, esi; this
0x100b1ca8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100b1cae  call    esi
0x100b1cb0  lea     this, [ebp+pStream]; this
0x100b1cb3  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100b1cb8  lea     this, [ebp+spCloseableStream]; this
0x100b1cbb  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100b1cc0  lea     this, [ebp+spRandomAccessStream]; this
0x100b1cc3  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100b1cc8  lea     this, [ebp+spGetStreamOperation]; this
0x100b1ccb  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100b1cd0  lea     this, [ebp+spFile]; this
0x100b1cd3  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100b1cd8  mov     eax, ebx
0x100b1cda  pop     edi
0x100b1cdb  pop     esi
0x100b1cdc  pop     ebx
0x100b1cdd  leave
0x100b1cde  retn
```
