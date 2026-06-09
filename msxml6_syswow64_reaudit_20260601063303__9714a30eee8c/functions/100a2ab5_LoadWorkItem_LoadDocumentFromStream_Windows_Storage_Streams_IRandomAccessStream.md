# LoadWorkItem::LoadDocumentFromStream(Windows::Storage::Streams::IRandomAccessStream *)

- ea: `0x100a2ab5`
- end: `0x100a2b95`
- name: `?LoadDocumentFromStream@LoadWorkItem@@AAEJPAUIRandomAccessStream@Streams@Storage@Windows@@@Z`
- size: `224`
- prototype: `HRESULT __thiscall(LoadWorkItem *this, Windows::Storage::Streams::IRandomAccessStream *pRandAccessStream)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x100a1d90`

## callees

- `0x1003fb13`
- `0x10067b20`
- `0x10073ac9`
- `0x10091290`
- `0x100a0dd4`
- `0x100a11db`
- `0x100a2ab5`

## import_xrefs

- `OLEAUT32!__imp__VariantInit@4` at `0x100a2b39`
- `OLEAUT32!__imp__VariantInit@4` at `0x100a2b39`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x100a2ade`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x100a2ade`

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
0x100a2ab5  mov     edi, edi
0x100a2ab7  push    ebp
0x100a2ab8  mov     ebp, esp
0x100a2aba  sub     esp, 1Ch
0x100a2abd  push    ebx
0x100a2abe  push    esi
0x100a2abf  push    edi
0x100a2ac0  lea     eax, [ebp+pStream]
0x100a2ac3  mov     [ebp+pStream.ptr_], 0
0x100a2aca  mov     ebx, this
0x100a2acc  push    eax; pp
0x100a2acd  mov     [ebp+var_C], ebx
0x100a2ad0  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YGPAPAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x100a2ad5  push    eax
0x100a2ad6  push    offset __GUID_0000000c_0000_0000_c000_000000000046
0x100a2adb  push    [ebp+pRandAccessStream]
0x100a2ade  call    ds:__imp__CreateStreamOverRandomAccessStream@12; CreateStreamOverRandomAccessStream(x,x,x)
0x100a2ae4  mov     esi, eax
0x100a2ae6  test    esi, esi
0x100a2ae8  js      CleanUp_85
0x100a2aee  mov     edx, [ebp+pStream.ptr_]; pref
0x100a2af1  lea     this, [ebx+6Ch]; ppref
0x100a2af4  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100a2af9  mov     eax, [ebx+80h]
0x100a2aff  lea     edi, [ebx+84h]
0x100a2b05  mov     edx, [edi]; loadsettings
0x100a2b07  push    0
0x100a2b09  push    this; invokeType
0x100a2b0a  mov     this, [eax+18h]; doc
0x100a2b0d  call    ?ApplyLoadSettings@@YGJPAVDocument@@PAUIXmlLoadSettings@Dom@Xml@Data@Windows@@_NW4InvokingMethodType@@@Z; ApplyLoadSettings(Document *,Windows::Data::Xml::Dom::IXmlLoadSettings *,bool,InvokingMethodType)
0x100a2b12  mov     esi, eax
0x100a2b14  test    esi, esi
0x100a2b16  js      short CleanUp_85
0x100a2b18  mov     this, edi; ptr
0x100a2b1a  call    ??$safeRelease@VDOMDocumentWrapper@@@@YGXACRAVDOMDocumentWrapper@@@Z; safeRelease<DOMDocumentWrapper>(DOMDocumentWrapper * volatile &)
0x100a2b1f  mov     this, [ebx+24h]
0x100a2b22  lea     edx, [ebp+success]
0x100a2b25  push    0FFFFFFFEh
0x100a2b27  pop     eax
0x100a2b28  mov     [ebp+success], eax
0x100a2b2b  lock cmpxchg [edx], this
0x100a2b2f  cmp     [ebp+success], 0
0x100a2b33  jnz     short CleanUp_85
0x100a2b35  lea     eax, [ebp+v]
0x100a2b38  push    eax; pvarg
0x100a2b39  call    ds:__imp__VariantInit@4; VariantInit(x)
0x100a2b3f  mov     this, [ebx+80h]
0x100a2b45  lea     esi, [ebp+v]
0x100a2b48  push    0Dh
0x100a2b4a  pop     eax
0x100a2b4b  mov     word ptr [ebp+v.___u0], ax
0x100a2b4f  lea     eax, [ebx+60h]
0x100a2b52  mov     dword ptr [ebp+v.___u0+8], eax
0x100a2b55  mov     eax, [this]
0x100a2b57  mov     ebx, [eax+0E8h]
0x100a2b5d  lea     eax, [ebp+success]
0x100a2b60  push    eax
0x100a2b61  sub     esp, 10h
0x100a2b64  mov     edi, esp
0x100a2b66  push    this
0x100a2b67  movsd
0x100a2b68  mov     this, ebx; this
0x100a2b6a  movsd
0x100a2b6b  movsd
0x100a2b6c  movsd
0x100a2b6d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a2b73  call    ebx
0x100a2b75  mov     ebx, [ebp+var_C]
0x100a2b78  mov     esi, eax
0x100a2b7a  lea     this, [ebx+6Ch]; ppref
0x100a2b7d  xor     edx, edx; pref
0x100a2b7f  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100a2b84  lea     this, [ebp+pStream]; this
0x100a2b87  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100a2b8c  pop     edi
0x100a2b8d  mov     eax, esi
0x100a2b8f  pop     esi
0x100a2b90  pop     ebx
0x100a2b91  leave
0x100a2b92  retn    4
```
