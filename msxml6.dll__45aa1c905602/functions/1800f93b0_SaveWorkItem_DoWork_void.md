# SaveWorkItem::DoWork(void)

- ea: `0x1800f93b0`
- end: `0x1800f95d8`
- name: `?DoWork@SaveWorkItem@@EEAAJXZ`
- size: `552`
- prototype: `HRESULT __fastcall(SaveWorkItem *this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180015a80`
- `0x180058ef4`
- `0x1800719e4`
- `0x1800edd64`
- `0x1800eddd8`
- `0x1800ef8b4`
- `0x1800ef8d4`
- `0x1800f93b0`
- `0x18018c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800f94f9`
- `OLEAUT32!__imp_VariantInit` at `0x1800f94f9`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x1800f94b6`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x1800f94b6`

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
  $BE4DFD8530E26B14EE6F3813E010A638 v15; // [rsp+50h] [rbp-20h] BYREF
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
  Pointer = _gitpointer<IDispatch,&_GUID const IID_IDispatch>::HrGetPointer(
              (_gitpointer<IPropertyNotifySink,&IID_IPropertyNotifySink> *)&this->_gipFile,
              (IPropertyNotifySink **)&spFile);
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
              Pointer = ((__int64 (__fastcall *)(DOMDocumentWrapper *, $BE4DFD8530E26B14EE6F3813E010A638 *))save)(
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
0x1800f93b0  push    rbp
0x1800f93b2  push    rbx
0x1800f93b3  push    rsi
0x1800f93b4  push    rdi
0x1800f93b5  push    r14
0x1800f93b7  mov     rbp, rsp
0x1800f93ba  sub     rsp, 70h
0x1800f93be  mov     r14, this
0x1800f93c1  lea     this, [rbp+libNewSize]; this
0x1800f93c5  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x1800f93ca  cmp     qword ptr [rbp+libNewSize], 0
0x1800f93cf  jnz     short loc_1800F93DB
0x1800f93d1  mov     eax, 80004005h
0x1800f93d6  jmp     loc_1800F95CC
0x1800f93db  xorps   xmm0, xmm0
0x1800f93de  mov     [rbp+spFile.ptr_], 0
0x1800f93e6  xor     eax, eax
0x1800f93e8  mov     [rbp+spGetStreamOperation.ptr_], 0
0x1800f93f0  lea     this, [rbp+spFile]; this
0x1800f93f4  mov     [rbp+v.pRecInfo], rax
0x1800f93f8  movups  xmmword ptr [rbp+v.___u0], xmm0
0x1800f93fc  mov     [rbp+spRandomAccessStream.ptr_], 0
0x1800f9404  mov     [rbp+spCloseableStream.ptr_], 0
0x1800f940c  mov     [rbp+pStream.ptr_], 0
0x1800f9414  mov     qword ptr [rbp+libNewSize], 0
0x1800f941c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f9421  lea     this, [r14+0F8h]; this
0x1800f9428  lea     rdx, [rbp+spFile]; pptr
0x1800f942c  call    ?HrGetPointer@?$_gitpointer@UIDispatch@@$1?IID_IDispatch@@3U_GUID@@B@@QEBAJPEAPEAUIDispatch@@@Z; _gitpointer<IDispatch,&_GUID const IID_IDispatch>::HrGetPointer(IDispatch * *)
0x1800f9431  mov     esi, eax
0x1800f9433  test    eax, eax
0x1800f9435  js      $CleanUp_245
0x1800f943b  mov     rdi, [rbp+spFile.ptr_]
0x1800f943f  lea     this, [rbp+spGetStreamOperation]; this
0x1800f9443  mov     rax, [rdi]
0x1800f9446  mov     rbx, [rax+40h]
0x1800f944a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f944f  lea     r8, [rbp+spGetStreamOperation]
0x1800f9453  mov     edx, 1
0x1800f9458  mov     this, rdi
0x1800f945b  mov     rax, rbx
0x1800f945e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9463  mov     esi, eax
0x1800f9465  test    eax, eax
0x1800f9467  js      $CleanUp_245
0x1800f946d  mov     rdx, [rbp+spGetStreamOperation.ptr_]; ptr
0x1800f9471  lea     this, [r14+100h]; this
0x1800f9478  call    ?HrSetPointer@?$_gitpointer@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@$1?_GUID_430ecece_1418_5d19_81b2_5ddb381603cc@@3U__s_GUID@@B@@QEAAJPEAU?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@@Z; _gitpointer<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,&__s_GUID const _GUID_430ecece_1418_5d19_81b2_5ddb381603cc>::HrSetPointer(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *)
0x1800f947d  mov     esi, eax
0x1800f947f  test    eax, eax
0x1800f9481  js      $CleanUp_245
0x1800f9487  mov     this, [rbp+spGetStreamOperation.ptr_]; pOperation
0x1800f948b  lea     rdx, [rbp+spRandomAccessStream]; pp
0x1800f948f  call    ??$WaitForCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@UIRandomAccessStream@Streams@Storage@3@@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIRandomAccessStream@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; WaitForCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Storage::Streams::IRandomAccessStream>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>>)
0x1800f9494  mov     esi, eax
0x1800f9496  test    eax, eax
0x1800f9498  js      $CleanUp_245
0x1800f949e  lea     this, [rbp+pStream]; this
0x1800f94a2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f94a7  mov     this, [rbp+spRandomAccessStream.ptr_]
0x1800f94ab  lea     r8, [rbp+pStream]
0x1800f94af  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x1800f94b6  call    cs:__imp_CreateStreamOverRandomAccessStream
0x1800f94bd  nop     dword ptr [rax+rax+00h]
0x1800f94c2  mov     esi, eax
0x1800f94c4  test    eax, eax
0x1800f94c6  js      short $CleanUp_245
0x1800f94c8  mov     rdx, [rbp+pStream.ptr_]; pref
0x1800f94cc  lea     rbx, [r14+0B0h]
0x1800f94d3  lea     this, [rbx+18h]; ppref
0x1800f94d7  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800f94dc  mov     rax, [rbx]
0x1800f94df  mov     this, rbx
0x1800f94e2  mov     rdx, qword ptr [rbp+libNewSize]
0x1800f94e6  mov     rax, [rax+30h]
0x1800f94ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f94ef  mov     esi, eax
0x1800f94f1  test    eax, eax
0x1800f94f3  js      short $CleanUp_245
0x1800f94f5  lea     this, [rbp+v]; pvarg
0x1800f94f9  call    cs:__imp_VariantInit
0x1800f9500  nop     dword ptr [rax+rax+00h]
0x1800f9505  mov     this, [r14+0F0h]
0x1800f950c  lea     rdx, [rbp+var_20]
0x1800f9510  movsd   xmm1, [rbp+v.pRecInfo]
0x1800f9515  mov     eax, 0Dh
0x1800f951a  mov     word ptr [rbp+v.___u0], ax
0x1800f951e  mov     qword ptr [rbp+v.___u0+8], rbx
0x1800f9522  mov     rax, [this]
0x1800f9525  movups  xmm0, xmmword ptr [rbp+v.___u0]
0x1800f9529  movsd   [rbp+var_10], xmm1
0x1800f952e  mov     rax, [rax+210h]
0x1800f9535  movaps  [rbp+var_20], xmm0
0x1800f9539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f953e  mov     esi, eax
0x1800f9540  lea     this, [r14+0F0h]; ptr
0x1800f9547  call    ??$safeRelease@UIXmlLoadSettings@Dom@Xml@Data@Windows@@@@YAXAECREAUIXmlLoadSettings@Dom@Xml@Data@Windows@@@Z; safeRelease<Windows::Data::Xml::Dom::IXmlLoadSettings>(Windows::Data::Xml::Dom::IXmlLoadSettings * volatile &)
0x1800f954c  lea     this, [r14+0C8h]; ppref
0x1800f9553  xor     edx, edx; pref
0x1800f9555  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800f955a  mov     rbx, [rbp+spRandomAccessStream.ptr_]
0x1800f955e  test    rbx, rbx
0x1800f9561  jz      short loc_1800F959D
0x1800f9563  mov     rax, [rbx]
0x1800f9566  lea     this, [rbp+spCloseableStream]; this
0x1800f956a  mov     rdi, [rax]
0x1800f956d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f9572  lea     r8, [rbp+spCloseableStream]
0x1800f9576  mov     this, rbx
0x1800f9579  lea     rdx, _GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e
0x1800f9580  mov     rax, rdi
0x1800f9583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9588  mov     this, [rbp+spCloseableStream.ptr_]
0x1800f958c  test    this, this
0x1800f958f  jz      short loc_1800F959D
0x1800f9591  mov     rax, [this]
0x1800f9594  mov     rax, [rax+30h]
0x1800f9598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f959d  lea     this, [rbp+pStream]; this
0x1800f95a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f95a6  lea     this, [rbp+spCloseableStream]; this
0x1800f95aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f95af  lea     this, [rbp+spRandomAccessStream]; this
0x1800f95b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f95b8  lea     this, [rbp+spGetStreamOperation]; this
0x1800f95bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f95c1  lea     this, [rbp+spFile]; this
0x1800f95c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f95ca  mov     eax, esi
0x1800f95cc  add     rsp, 70h
0x1800f95d0  pop     r14
0x1800f95d2  pop     rdi
0x1800f95d3  pop     rsi
0x1800f95d4  pop     rbx
0x1800f95d5  pop     rbp
0x1800f95d6  retn
```
