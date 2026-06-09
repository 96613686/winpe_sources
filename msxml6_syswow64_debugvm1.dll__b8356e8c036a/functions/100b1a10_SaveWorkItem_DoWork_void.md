# SaveWorkItem::DoWork(void)

- ea: `0x100b1a10`
- end: `0x100b1bcf`
- name: `?DoWork@SaveWorkItem@@EAEJXZ`
- size: `447`
- prototype: `HRESULT __thiscall(SaveWorkItem *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1003fba3`
- `0x1005064c`
- `0x10057d31`
- `0x10067bc0`
- `0x10073a99`
- `0x100a0d14`
- `0x100a1093`
- `0x100a10e9`
- `0x100a26ea`
- `0x100b1a10`

## import_xrefs

- `OLEAUT32!__imp__VariantInit@4` at `0x100b1b10`
- `OLEAUT32!__imp__VariantInit@4` at `0x100b1b10`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x100b1ad8`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x100b1ad8`

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
0x100b1a10  mov     edi, edi
0x100b1a12  push    ebp
0x100b1a13  mov     ebp, esp
0x100b1a15  sub     esp, 2Ch
0x100b1a18  push    ebx
0x100b1a19  push    esi
0x100b1a1a  mov     ebx, this
0x100b1a1c  lea     this, [ebp+_EnsureTls]; this
0x100b1a1f  push    edi
0x100b1a20  mov     [ebp+var_8], ebx
0x100b1a23  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100b1a28  cmp     [ebp+_EnsureTls._tlsdata], 0
0x100b1a2c  jnz     short loc_100B1A38
0x100b1a2e  mov     eax, 80004005h
0x100b1a33  jmp     loc_100B1BCA
0x100b1a38  xor     eax, eax
0x100b1a3a  lea     this, [ebp+spFile]; this
0x100b1a3d  mov     [ebp+spFile.ptr_], eax
0x100b1a40  mov     [ebp+spGetStreamOperation.ptr_], eax
0x100b1a43  mov     [ebp+spRandomAccessStream.ptr_], eax
0x100b1a46  mov     [ebp+spCloseableStream.ptr_], eax
0x100b1a49  mov     [ebp+pStream.ptr_], eax
0x100b1a4c  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100b1a51  lea     eax, [ebp+spFile]
0x100b1a54  push    eax; pptr
0x100b1a55  lea     this, [ebx+84h]; this
0x100b1a5b  call    ?HrGetPointer@?$_gitpointer@UIStorageFile@Storage@Windows@@$1?_GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea@@3U__s_GUID@@B@@QBEJPAPAUIStorageFile@Storage@Windows@@@Z; _gitpointer<Windows::Storage::IStorageFile,&__s_GUID const _GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea>::HrGetPointer(Windows::Storage::IStorageFile * *)
0x100b1a60  mov     ebx, eax
0x100b1a62  test    ebx, ebx
0x100b1a64  js      loc_100B1B4A
0x100b1a6a  mov     esi, [ebp+spFile.ptr_]
0x100b1a6d  lea     this, [ebp+spGetStreamOperation]; this
0x100b1a70  mov     eax, [esi]
0x100b1a72  mov     edi, [eax+20h]
0x100b1a75  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100b1a7a  lea     eax, [ebp+spGetStreamOperation]
0x100b1a7d  mov     this, edi; this
0x100b1a7f  push    eax
0x100b1a80  push    1
0x100b1a82  push    esi
0x100b1a83  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100b1a89  call    edi
0x100b1a8b  mov     edi, [ebp+var_8]
0x100b1a8e  mov     ebx, eax
0x100b1a90  test    ebx, ebx
0x100b1a92  js      CleanUp_146
0x100b1a98  push    [ebp+spGetStreamOperation.ptr_]; ptr
0x100b1a9b  lea     this, [edi+88h]; this
0x100b1aa1  call    ?HrSetPointer@?$_gitpointer@U?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@$1?_GUID_430ecece_1418_5d19_81b2_5ddb381603cc@@3U__s_GUID@@B@@QAEJPAU?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@@Z; _gitpointer<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,&__s_GUID const _GUID_430ecece_1418_5d19_81b2_5ddb381603cc>::HrSetPointer(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *)
0x100b1aa6  mov     ebx, eax
0x100b1aa8  test    ebx, ebx
0x100b1aaa  js      CleanUp_146
0x100b1ab0  mov     this, [ebp+spGetStreamOperation.ptr_]; pOperation
0x100b1ab3  lea     eax, [ebp+spRandomAccessStream]
0x100b1ab6  push    eax; pp
0x100b1ab7  call    ??$WaitForCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@23@UIRandomAccessStream@Streams@Storage@3@@@YGJPAU?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIRandomAccessStream@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; WaitForCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Storage::Streams::IRandomAccessStream>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>>)
0x100b1abc  mov     ebx, eax
0x100b1abe  test    ebx, ebx
0x100b1ac0  js      CleanUp_146
0x100b1ac6  lea     eax, [ebp+pStream]
0x100b1ac9  push    eax; pp
0x100b1aca  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YGPAPAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x100b1acf  push    eax
0x100b1ad0  push    offset __GUID_0000000c_0000_0000_c000_000000000046
0x100b1ad5  push    [ebp+spRandomAccessStream.ptr_]
0x100b1ad8  call    ds:__imp__CreateStreamOverRandomAccessStream@12; CreateStreamOverRandomAccessStream(x,x,x)
0x100b1ade  mov     ebx, eax
0x100b1ae0  test    ebx, ebx
0x100b1ae2  js      short CleanUp_146
0x100b1ae4  mov     edx, [ebp+pStream.ptr_]; pref
0x100b1ae7  lea     this, [edi+6Ch]; ppref
0x100b1aea  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100b1aef  lea     this, [edi+60h]
0x100b1af2  mov     eax, [this]
0x100b1af4  push    0
0x100b1af6  push    0
0x100b1af8  push    this
0x100b1af9  mov     esi, [eax+18h]
0x100b1afc  mov     this, esi; this
0x100b1afe  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100b1b04  call    esi
0x100b1b06  mov     ebx, eax
0x100b1b08  test    ebx, ebx
0x100b1b0a  js      short CleanUp_146
0x100b1b0c  lea     eax, [ebp+v]
0x100b1b0f  push    eax; pvarg
0x100b1b10  call    ds:__imp__VariantInit@4; VariantInit(x)
0x100b1b16  mov     this, [edi+80h]
0x100b1b1c  lea     esi, [ebp+v]
0x100b1b1f  push    0Dh
0x100b1b21  pop     eax
0x100b1b22  mov     word ptr [ebp+v.___u0], ax
0x100b1b26  sub     esp, 10h
0x100b1b29  lea     eax, [edi+60h]
0x100b1b2c  mov     edi, esp
0x100b1b2e  mov     dword ptr [ebp+v.___u0+8], eax
0x100b1b31  mov     eax, [this]
0x100b1b33  push    this
0x100b1b34  movsd
0x100b1b35  mov     ebx, [eax+108h]
0x100b1b3b  mov     this, ebx; this
0x100b1b3d  movsd
0x100b1b3e  movsd
0x100b1b3f  movsd
0x100b1b40  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100b1b46  call    ebx
0x100b1b48  mov     ebx, eax
0x100b1b4a  mov     edi, [ebp+var_8]
0x100b1b4d  lea     this, [edi+80h]; ptr
0x100b1b53  call    ??$safeRelease@VDOMDocumentWrapper@@@@YGXACRAVDOMDocumentWrapper@@@Z; safeRelease<DOMDocumentWrapper>(DOMDocumentWrapper * volatile &)
0x100b1b58  lea     this, [edi+6Ch]; ppref
0x100b1b5b  xor     edx, edx; pref
0x100b1b5d  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100b1b62  mov     esi, [ebp+spRandomAccessStream.ptr_]
0x100b1b65  test    esi, esi
0x100b1b67  jz      short loc_100B1BA0
0x100b1b69  mov     eax, [esi]
0x100b1b6b  lea     this, [ebp+spCloseableStream]; this
0x100b1b6e  mov     edi, [eax]
0x100b1b70  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100b1b75  lea     eax, [ebp+spCloseableStream]
0x100b1b78  mov     this, edi; this
0x100b1b7a  push    eax
0x100b1b7b  push    offset __GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e
0x100b1b80  push    esi
0x100b1b81  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100b1b87  call    edi
0x100b1b89  mov     eax, [ebp+spCloseableStream.ptr_]
0x100b1b8c  test    eax, eax
0x100b1b8e  jz      short loc_100B1BA0
0x100b1b90  mov     this, [eax]
0x100b1b92  push    eax
0x100b1b93  mov     esi, [this+18h]
0x100b1b96  mov     this, esi; this
0x100b1b98  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100b1b9e  call    esi
0x100b1ba0  lea     this, [ebp+pStream]; this
0x100b1ba3  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100b1ba8  lea     this, [ebp+spCloseableStream]; this
0x100b1bab  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100b1bb0  lea     this, [ebp+spRandomAccessStream]; this
0x100b1bb3  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100b1bb8  lea     this, [ebp+spGetStreamOperation]; this
0x100b1bbb  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100b1bc0  lea     this, [ebp+spFile]; this
0x100b1bc3  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100b1bc8  mov     eax, ebx
0x100b1bca  pop     edi
0x100b1bcb  pop     esi
0x100b1bcc  pop     ebx
0x100b1bcd  leave
0x100b1bce  retn
```
