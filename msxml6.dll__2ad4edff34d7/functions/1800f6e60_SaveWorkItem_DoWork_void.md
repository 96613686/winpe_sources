# SaveWorkItem::DoWork(void)

- ea: `0x1800f6e60`
- end: `0x1800f707b`
- name: `?DoWork@SaveWorkItem@@EEAAJXZ`
- size: `539`
- prototype: `__int64 __fastcall(SaveWorkItem *this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180009490`
- `0x180056bdc`
- `0x1800730a4`
- `0x1800ebb60`
- `0x1800ebbd0`
- `0x1800ed594`
- `0x1800ed5b0`
- `0x1800f6e60`
- `0x180188010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800f6fa3`
- `OLEAUT32!__imp_VariantInit` at `0x1800f6fa3`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x1800f6f66`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x1800f6f66`

## pseudocode

```c
__int64 __fastcall SaveWorkItem::DoWork(SaveWorkItem *this)
{
  int Pointer; // esi
  Windows::Storage::IStorageFile *ptr; // rdi
  HRESULT (__fastcall *OpenAsync)(Windows::Storage::IStorageFile *, Windows::Storage::FileAccessMode, Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> **); // rbx
  DOMDocumentWrapper *document; // rcx
  DOMDocumentWrapper_vtbl *v7; // rax
  HRESULT (__fastcall *save)(IXMLDOMDocument *, tagVARIANT); // rax
  Windows::Storage::Streams::IRandomAccessStream *v9; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream> spRandomAccessStream; // [rsp+20h] [rbp-50h] BYREF
  Microsoft::WRL::ComPtr<Windows::Storage::IStorageFile> spFile; // [rsp+28h] [rbp-48h] BYREF
  _ULARGE_INTEGER libNewSize; // [rsp+30h] [rbp-40h] BYREF
  tagVARIANT v; // [rsp+38h] [rbp-38h] BYREF
  $D748BF15C0FD78A1D5EA62F74D6448CD v15; // [rsp+50h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-10h]
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> > spGetStreamOperation; // [rsp+A8h] [rbp+38h] BYREF
  Microsoft::WRL::ComPtr<IStream> pStream; // [rsp+B0h] [rbp+40h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IClosable> spCloseableStream; // [rsp+B8h] [rbp+48h] BYREF

  EnsureTls::EnsureTls((EnsureTls *)&libNewSize);
  if ( !libNewSize.QuadPart )
    return 2147500037LL;
  spFile.ptr_ = 0;
  spGetStreamOperation.ptr_ = 0;
  memset(&v, 0, sizeof(v));
  spRandomAccessStream.ptr_ = 0;
  spCloseableStream.ptr_ = 0;
  pStream.ptr_ = 0;
  libNewSize.QuadPart = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spFile);
  Pointer = _gitpointer<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>,&__s_GUID const _GUID_5e52f8ce_aced_5a42_95b4_f674dd84885e>::HrGetPointer(
              (_gitpointer<Windows::Foundation::IUriRuntimeClass,&_GUID_9e365e57_48b2_4160_956f_c7385120bbfc> *)&this->_gipFile,
              (Windows::Foundation::IUriRuntimeClass **)&spFile);
  if ( Pointer >= 0 )
  {
    ptr = spFile.ptr_;
    OpenAsync = spFile.ptr_->OpenAsync;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spGetStreamOperation);
    Pointer = OpenAsync(ptr, FileAccessMode_ReadWrite, &spGetStreamOperation.ptr_);
    if ( Pointer >= 0 )
    {
      Pointer = _gitpointer<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,&__s_GUID const _GUID_430ecece_1418_5d19_81b2_5ddb381603cc>::HrSetPointer(
                  &this->_gipStreamRetrievalOp,
                  spGetStreamOperation.ptr_);
      if ( Pointer >= 0 )
      {
        Pointer = WaitForCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Storage::Streams::IRandomAccessStream>(
                    spGetStreamOperation.ptr_,
                    (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream> >)&spRandomAccessStream);
        if ( Pointer >= 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&pStream);
          Pointer = CreateStreamOverRandomAccessStream(
                      spRandomAccessStream.ptr_,
                      &GUID_0000000c_0000_0000_c000_000000000046,
                      &pStream);
          if ( Pointer >= 0 )
          {
            assign(&this->_stm._pStream._p, pStream.ptr_);
            Pointer = ((__int64 (__fastcall *)(_QWORD, _QWORD))this->_stm.SetSize)(
                        &this->_stm,
                        (_ULARGE_INTEGER)libNewSize.QuadPart);
            if ( Pointer >= 0 )
            {
              VariantInit(&v);
              document = this->_document;
              v.vt = 13;
              v.llVal = (__int64)&this->_stm;
              v7 = document->_dispatchexport<Document,IXMLDOMDocument3,&LIBID_MSXML2,1,&IID_IXMLDOMDocument3>::IXMLDOMDocument3::IXMLDOMDocument2::IXMLDOMDocument::IXMLDOMNode::IDispatch::IUnknown::__vftable;
              pRecInfo = v.pRecInfo;
              save = v7->save;
              v15 = v.0;
              Pointer = ((__int64 (__fastcall *)(DOMDocumentWrapper *, $D748BF15C0FD78A1D5EA62F74D6448CD *))save)(
                          document,
                          &v15);
            }
          }
        }
      }
    }
  }
  safeRelease<Windows::Data::Xml::Dom::IXmlLoadSettings>(&this->_document);
  assign(&this->_stm._pStream._p, 0);
  v9 = spRandomAccessStream.ptr_;
  if ( spRandomAccessStream.ptr_ )
  {
    QueryInterface = spRandomAccessStream.ptr_->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spCloseableStream);
    QueryInterface(v9, &GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e, (void **)&spCloseableStream.ptr_);
    if ( spCloseableStream.ptr_ )
      spCloseableStream.ptr_->Close(spCloseableStream.ptr_);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&pStream);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spCloseableStream);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spRandomAccessStream);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spGetStreamOperation);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spFile);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x1800f6e60  push    rbp
0x1800f6e62  push    rbx
0x1800f6e63  push    rsi
0x1800f6e64  push    rdi
0x1800f6e65  push    r14
0x1800f6e67  mov     rbp, rsp
0x1800f6e6a  sub     rsp, 70h
0x1800f6e6e  mov     r14, this
0x1800f6e71  lea     this, [rbp+libNewSize]; this
0x1800f6e75  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x1800f6e7a  cmp     qword ptr [rbp+libNewSize], 0
0x1800f6e7f  jnz     short loc_1800F6E8B
0x1800f6e81  mov     eax, 80004005h
0x1800f6e86  jmp     loc_1800F7070
0x1800f6e8b  xorps   xmm0, xmm0
0x1800f6e8e  mov     [rbp+spFile.ptr_], 0
0x1800f6e96  xor     eax, eax
0x1800f6e98  mov     [rbp+spGetStreamOperation.ptr_], 0
0x1800f6ea0  lea     this, [rbp+spFile]; this
0x1800f6ea4  mov     [rbp+v.pRecInfo], rax
0x1800f6ea8  movups  xmmword ptr [rbp+v.___u0], xmm0
0x1800f6eac  mov     [rbp+spRandomAccessStream.ptr_], 0
0x1800f6eb4  mov     [rbp+spCloseableStream.ptr_], 0
0x1800f6ebc  mov     [rbp+pStream.ptr_], 0
0x1800f6ec4  mov     qword ptr [rbp+libNewSize], 0
0x1800f6ecc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f6ed1  lea     this, [r14+0F8h]; this
0x1800f6ed8  lea     rdx, [rbp+spFile]; pptr
0x1800f6edc  call    ?HrGetPointer@?$_gitpointer@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@$1?_GUID_5e52f8ce_aced_5a42_95b4_f674dd84885e@@3U__s_GUID@@B@@QEBAJPEAPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@@Z; _gitpointer<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>,&__s_GUID const _GUID_5e52f8ce_aced_5a42_95b4_f674dd84885e>::HrGetPointer(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> * *)
0x1800f6ee1  mov     esi, eax
0x1800f6ee3  test    eax, eax
0x1800f6ee5  js      $CleanUp_245
0x1800f6eeb  mov     rdi, [rbp+spFile.ptr_]
0x1800f6eef  lea     this, [rbp+spGetStreamOperation]; this
0x1800f6ef3  mov     rax, [rdi]
0x1800f6ef6  mov     rbx, [rax+40h]
0x1800f6efa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f6eff  lea     r8, [rbp+spGetStreamOperation]
0x1800f6f03  mov     edx, 1
0x1800f6f08  mov     this, rdi
0x1800f6f0b  mov     rax, rbx
0x1800f6f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6f13  mov     esi, eax
0x1800f6f15  test    eax, eax
0x1800f6f17  js      $CleanUp_245
0x1800f6f1d  mov     rdx, [rbp+spGetStreamOperation.ptr_]; ptr
0x1800f6f21  lea     this, [r14+100h]; this
0x1800f6f28  call    ?HrSetPointer@?$_gitpointer@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@$1?_GUID_430ecece_1418_5d19_81b2_5ddb381603cc@@3U__s_GUID@@B@@QEAAJPEAU?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@@Z; _gitpointer<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,&__s_GUID const _GUID_430ecece_1418_5d19_81b2_5ddb381603cc>::HrSetPointer(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *)
0x1800f6f2d  mov     esi, eax
0x1800f6f2f  test    eax, eax
0x1800f6f31  js      $CleanUp_245
0x1800f6f37  mov     this, [rbp+spGetStreamOperation.ptr_]; pOperation
0x1800f6f3b  lea     rdx, [rbp+spRandomAccessStream]; pp
0x1800f6f3f  call    ??$WaitForCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@UIRandomAccessStream@Streams@Storage@3@@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIRandomAccessStream@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; WaitForCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Storage::Streams::IRandomAccessStream>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>>)
0x1800f6f44  mov     esi, eax
0x1800f6f46  test    eax, eax
0x1800f6f48  js      $CleanUp_245
0x1800f6f4e  lea     this, [rbp+pStream]; this
0x1800f6f52  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f6f57  mov     this, [rbp+spRandomAccessStream.ptr_]
0x1800f6f5b  lea     r8, [rbp+pStream]
0x1800f6f5f  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x1800f6f66  call    cs:__imp_CreateStreamOverRandomAccessStream
0x1800f6f6c  mov     esi, eax
0x1800f6f6e  test    eax, eax
0x1800f6f70  js      short $CleanUp_245
0x1800f6f72  mov     rdx, [rbp+pStream.ptr_]; pref
0x1800f6f76  lea     rbx, [r14+0B0h]
0x1800f6f7d  lea     this, [rbx+18h]; ppref
0x1800f6f81  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800f6f86  mov     rax, [rbx]
0x1800f6f89  mov     this, rbx
0x1800f6f8c  mov     rdx, qword ptr [rbp+libNewSize]
0x1800f6f90  mov     rax, [rax+30h]
0x1800f6f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6f99  mov     esi, eax
0x1800f6f9b  test    eax, eax
0x1800f6f9d  js      short $CleanUp_245
0x1800f6f9f  lea     this, [rbp+v]; pvarg
0x1800f6fa3  call    cs:__imp_VariantInit
0x1800f6fa9  mov     this, [r14+0F0h]
0x1800f6fb0  lea     rdx, [rbp+var_20]
0x1800f6fb4  movsd   xmm1, [rbp+v.pRecInfo]
0x1800f6fb9  mov     eax, 0Dh
0x1800f6fbe  mov     word ptr [rbp+v.___u0], ax
0x1800f6fc2  mov     qword ptr [rbp+v.___u0+8], rbx
0x1800f6fc6  mov     rax, [this]
0x1800f6fc9  movups  xmm0, xmmword ptr [rbp+v.___u0]
0x1800f6fcd  movsd   [rbp+var_10], xmm1
0x1800f6fd2  mov     rax, [rax+210h]
0x1800f6fd9  movaps  [rbp+var_20], xmm0
0x1800f6fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6fe2  mov     esi, eax
0x1800f6fe4  lea     this, [r14+0F0h]; ptr
0x1800f6feb  call    ??$safeRelease@UIXmlLoadSettings@Dom@Xml@Data@Windows@@@@YAXAECREAUIXmlLoadSettings@Dom@Xml@Data@Windows@@@Z; safeRelease<Windows::Data::Xml::Dom::IXmlLoadSettings>(Windows::Data::Xml::Dom::IXmlLoadSettings * volatile &)
0x1800f6ff0  lea     this, [r14+0C8h]; ppref
0x1800f6ff7  xor     edx, edx; pref
0x1800f6ff9  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800f6ffe  mov     rbx, [rbp+spRandomAccessStream.ptr_]
0x1800f7002  test    rbx, rbx
0x1800f7005  jz      short loc_1800F7041
0x1800f7007  mov     rax, [rbx]
0x1800f700a  lea     this, [rbp+spCloseableStream]; this
0x1800f700e  mov     rdi, [rax]
0x1800f7011  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f7016  lea     r8, [rbp+spCloseableStream]
0x1800f701a  mov     this, rbx
0x1800f701d  lea     rdx, _GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e
0x1800f7024  mov     rax, rdi
0x1800f7027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f702c  mov     this, [rbp+spCloseableStream.ptr_]
0x1800f7030  test    this, this
0x1800f7033  jz      short loc_1800F7041
0x1800f7035  mov     rax, [this]
0x1800f7038  mov     rax, [rax+30h]
0x1800f703c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7041  lea     this, [rbp+pStream]; this
0x1800f7045  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f704a  lea     this, [rbp+spCloseableStream]; this
0x1800f704e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f7053  lea     this, [rbp+spRandomAccessStream]; this
0x1800f7057  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f705c  lea     this, [rbp+spGetStreamOperation]; this
0x1800f7060  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f7065  lea     this, [rbp+spFile]; this
0x1800f7069  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f706e  mov     eax, esi
0x1800f7070  add     rsp, 70h
0x1800f7074  pop     r14
0x1800f7076  pop     rdi
0x1800f7077  pop     rsi
0x1800f7078  pop     rbx
0x1800f7079  pop     rbp
0x1800f707a  retn
```
