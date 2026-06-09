# LoadWorkItem::LoadDocumentFromStream(Windows::Storage::Streams::IRandomAccessStream *)

- ea: `0x100a29a5`
- end: `0x100a2a85`
- name: `?LoadDocumentFromStream@LoadWorkItem@@AAEJPAUIRandomAccessStream@Streams@Storage@Windows@@@Z`
- size: `224`
- prototype: `HRESULT __thiscall(LoadWorkItem *this, Windows::Storage::Streams::IRandomAccessStream *pRandAccessStream)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x100a1ca0`

## callees

- `0x1003fba3`
- `0x10067bc0`
- `0x10073a99`
- `0x100911c0`
- `0x100a0d14`
- `0x100a10e9`
- `0x100a29a5`

## import_xrefs

- `OLEAUT32!__imp__VariantInit@4` at `0x100a2a29`
- `OLEAUT32!__imp__VariantInit@4` at `0x100a2a29`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x100a29ce`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x100a29ce`

## pseudocode

```c
HRESULT __thiscall LoadWorkItem::LoadDocumentFromStream(
        LoadWorkItem *this,
        Windows::Storage::Streams::IRandomAccessStream *pRandAccessStream)
{
  LoadWorkItem *v2; // ebx
  void **v3; // eax
  int StreamOverRandomAccessStream; // esi
  struct Document *v5; // ecx
  signed __int32 currentStatus; // ecx
  DOMDocumentWrapper *document; // ecx
  int v8; // eax
  bool v10; // [esp+0h] [ebp-28h]
  enum InvokingMethodType v11; // [esp+4h] [ebp-24h]
  tagVARIANT v; // [esp+Ch] [ebp-1Ch] BYREF
  LoadWorkItem *v13; // [esp+1Ch] [ebp-Ch]
  Microsoft::WRL::ComPtr<IStream> pStream; // [esp+20h] [ebp-8h] BYREF
  signed __int32 success; // [esp+24h] [ebp-4h] BYREF

  pStream.ptr_ = 0;
  v2 = this;
  v13 = this;
  v3 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>((Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IStream> >)&pStream);
  StreamOverRandomAccessStream = CreateStreamOverRandomAccessStream(
                                   pRandAccessStream,
                                   &_GUID_0000000c_0000_0000_c000_000000000046,
                                   v3);
  if ( StreamOverRandomAccessStream >= 0 )
  {
    assign(&v2->_stm._pStream._p, pStream.ptr_);
    StreamOverRandomAccessStream = ApplyLoadSettings(v5, StaticMethod, v10, v11);
    if ( StreamOverRandomAccessStream >= 0 )
    {
      safeRelease<DOMDocumentWrapper>((DOMDocumentWrapper *volatile *)&v2->_loadsettings);
      currentStatus = v2->currentStatus_;
      success = -2;
      _InterlockedCompareExchange(&success, currentStatus, -2);
      if ( !success )
      {
        VariantInit(&v);
        document = v2->_document;
        v.vt = 13;
        v.decVal.Lo32 = (unsigned int)&v2->_stm;
        v8 = ((int (__thiscall *)(HRESULT (__stdcall *)(IXMLDOMDocument *, tagVARIANT, __int16 *), DOMDocumentWrapper *, _DWORD, unsigned int, CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0>::CAbortableIStream *, unsigned int, signed __int32 *))document->load)(
               document->load,
               document,
               *(_DWORD *)&v.vt,
               v.decVal.Hi32,
               &v2->_stm,
               v.decVal.Mid32,
               &success);
        v2 = v13;
        StreamOverRandomAccessStream = v8;
      }
    }
  }
  assign(&v2->_stm._pStream._p, 0);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&pStream);
  return StreamOverRandomAccessStream;
}

```

## disassembly

```asm
0x100a29a5  mov     edi, edi
0x100a29a7  push    ebp
0x100a29a8  mov     ebp, esp
0x100a29aa  sub     esp, 1Ch
0x100a29ad  push    ebx
0x100a29ae  push    esi
0x100a29af  push    edi
0x100a29b0  lea     eax, [ebp+pStream]
0x100a29b3  mov     [ebp+pStream.ptr_], 0
0x100a29ba  mov     ebx, this
0x100a29bc  push    eax; pp
0x100a29bd  mov     [ebp+var_C], ebx
0x100a29c0  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YGPAPAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x100a29c5  push    eax
0x100a29c6  push    offset __GUID_0000000c_0000_0000_c000_000000000046
0x100a29cb  push    [ebp+pRandAccessStream]
0x100a29ce  call    ds:__imp__CreateStreamOverRandomAccessStream@12; CreateStreamOverRandomAccessStream(x,x,x)
0x100a29d4  mov     esi, eax
0x100a29d6  test    esi, esi
0x100a29d8  js      CleanUp_85
0x100a29de  mov     edx, [ebp+pStream.ptr_]; pref
0x100a29e1  lea     this, [ebx+6Ch]; ppref
0x100a29e4  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100a29e9  mov     eax, [ebx+80h]
0x100a29ef  lea     edi, [ebx+84h]
0x100a29f5  mov     edx, [edi]; loadsettings
0x100a29f7  push    0
0x100a29f9  push    this; invokeType
0x100a29fa  mov     this, [eax+18h]; doc
0x100a29fd  call    ?ApplyLoadSettings@@YGJPAVDocument@@PAUIXmlLoadSettings@Dom@Xml@Data@Windows@@_NW4InvokingMethodType@@@Z; ApplyLoadSettings(Document *,Windows::Data::Xml::Dom::IXmlLoadSettings *,bool,InvokingMethodType)
0x100a2a02  mov     esi, eax
0x100a2a04  test    esi, esi
0x100a2a06  js      short CleanUp_85
0x100a2a08  mov     this, edi; ptr
0x100a2a0a  call    ??$safeRelease@VDOMDocumentWrapper@@@@YGXACRAVDOMDocumentWrapper@@@Z; safeRelease<DOMDocumentWrapper>(DOMDocumentWrapper * volatile &)
0x100a2a0f  mov     this, [ebx+24h]
0x100a2a12  lea     edx, [ebp+success]
0x100a2a15  push    0FFFFFFFEh
0x100a2a17  pop     eax
0x100a2a18  mov     [ebp+success], eax
0x100a2a1b  lock cmpxchg [edx], this
0x100a2a1f  cmp     [ebp+success], 0
0x100a2a23  jnz     short CleanUp_85
0x100a2a25  lea     eax, [ebp+v]
0x100a2a28  push    eax; pvarg
0x100a2a29  call    ds:__imp__VariantInit@4; VariantInit(x)
0x100a2a2f  mov     this, [ebx+80h]
0x100a2a35  lea     esi, [ebp+v]
0x100a2a38  push    0Dh
0x100a2a3a  pop     eax
0x100a2a3b  mov     word ptr [ebp+v.___u0], ax
0x100a2a3f  lea     eax, [ebx+60h]
0x100a2a42  mov     dword ptr [ebp+v.___u0+8], eax
0x100a2a45  mov     eax, [this]
0x100a2a47  mov     ebx, [eax+0E8h]
0x100a2a4d  lea     eax, [ebp+success]
0x100a2a50  push    eax
0x100a2a51  sub     esp, 10h
0x100a2a54  mov     edi, esp
0x100a2a56  push    this
0x100a2a57  movsd
0x100a2a58  mov     this, ebx; this
0x100a2a5a  movsd
0x100a2a5b  movsd
0x100a2a5c  movsd
0x100a2a5d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a2a63  call    ebx
0x100a2a65  mov     ebx, [ebp+var_C]
0x100a2a68  mov     esi, eax
0x100a2a6a  lea     this, [ebx+6Ch]; ppref
0x100a2a6d  xor     edx, edx; pref
0x100a2a6f  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100a2a74  lea     this, [ebp+pStream]; this
0x100a2a77  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100a2a7c  pop     edi
0x100a2a7d  mov     eax, esi
0x100a2a7f  pop     esi
0x100a2a80  pop     ebx
0x100a2a81  leave
0x100a2a82  retn    4
```
