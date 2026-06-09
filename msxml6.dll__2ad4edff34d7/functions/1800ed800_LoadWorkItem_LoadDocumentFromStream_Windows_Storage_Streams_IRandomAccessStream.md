# LoadWorkItem::LoadDocumentFromStream(Windows::Storage::Streams::IRandomAccessStream *)

- ea: `0x1800ed800`
- end: `0x1800ed92b`
- name: `?LoadDocumentFromStream@LoadWorkItem@@AEAAJPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(LoadWorkItem *this, Windows::Storage::Streams::IRandomAccessStream *pRandAccessStream)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800ec8f0`

## callees

- `0x180009490`
- `0x1800730a4`
- `0x1800786f8`
- `0x1800ebbd0`
- `0x1800ed800`
- `0x180188010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800ed8b2`
- `OLEAUT32!__imp_VariantInit` at `0x1800ed8b2`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x1800ed847`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x1800ed847`

## pseudocode

```c
__int64 __fastcall LoadWorkItem::LoadDocumentFromStream(
        LoadWorkItem *this,
        Windows::Storage::Streams::IRandomAccessStream *pRandAccessStream)
{
  int Settings; // ebx
  bool v5; // r8
  volatile Microsoft::WRL::Details::AsyncStatusInternal currentStatus; // ecx
  DOMDocumentWrapper *document; // rcx
  DOMDocumentWrapper_vtbl *v8; // rax
  tagVARIANT v; // [rsp+20h] [rbp-40h] BYREF
  tagVARIANT v11; // [rsp+40h] [rbp-20h] BYREF
  signed __int32 success; // [rsp+80h] [rbp+20h] BYREF
  Microsoft::WRL::ComPtr<IStream> pStream; // [rsp+90h] [rbp+30h] BYREF

  pStream.ptr_ = 0;
  memset(&v, 0, sizeof(v));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&pStream);
  Settings = CreateStreamOverRandomAccessStream(pRandAccessStream, &GUID_0000000c_0000_0000_c000_000000000046, &pStream);
  if ( Settings >= 0 )
  {
    assign(&this->_stm._pStream._p, pStream.ptr_);
    Settings = ApplyLoadSettings((Document *)this->_document->_pWrapped._p, this->_loadsettings, v5, StaticMethod);
    if ( Settings >= 0 )
    {
      safeRelease<Windows::Data::Xml::Dom::IXmlLoadSettings>((DOMDocumentWrapper *volatile *)&this->_loadsettings);
      currentStatus = this->currentStatus_;
      success = -2;
      _InterlockedCompareExchange(&success, currentStatus, -2);
      if ( !success )
      {
        VariantInit(&v);
        document = this->_document;
        v.llVal = (__int64)&this->_stm;
        v.vt = 13;
        LOWORD(success) = 0;
        v8 = document->_dispatchexport<Document,IXMLDOMDocument3,&LIBID_MSXML2,1,&IID_IXMLDOMDocument3>::IXMLDOMDocument3::IXMLDOMDocument2::IXMLDOMDocument::IXMLDOMNode::IDispatch::IUnknown::__vftable;
        v11 = v;
        Settings = ((__int64 (__fastcall *)(DOMDocumentWrapper *, tagVARIANT *, signed __int32 *))v8->load)(
                     document,
                     &v11,
                     &success);
      }
    }
  }
  assign(&this->_stm._pStream._p, 0);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&pStream);
  return (unsigned int)Settings;
}

```

## disassembly

```asm
0x1800ed800  mov     [rsp-18h+arg_8], rbx
0x1800ed805  mov     [rsp-18h+arg_18], rsi
0x1800ed80a  push    rbp
0x1800ed80b  push    rdi
0x1800ed80c  push    r14
0x1800ed80e  mov     rbp, rsp
0x1800ed811  sub     rsp, 60h
0x1800ed815  mov     rdi, this
0x1800ed818  mov     [rbp+pStream.ptr_], 0
0x1800ed820  xorps   xmm0, xmm0
0x1800ed823  lea     this, [rbp+pStream]; this
0x1800ed827  xor     eax, eax
0x1800ed829  mov     rbx, pRandAccessStream
0x1800ed82c  movups  xmmword ptr [rbp+v.___u0], xmm0
0x1800ed830  mov     [rbp+v.pRecInfo], rax
0x1800ed834  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ed839  lea     r8, [rbp+pStream]
0x1800ed83d  mov     this, rbx
0x1800ed840  lea     pRandAccessStream, _GUID_0000000c_0000_0000_c000_000000000046
0x1800ed847  call    cs:__imp_CreateStreamOverRandomAccessStream
0x1800ed84d  mov     ebx, eax
0x1800ed84f  test    eax, eax
0x1800ed851  js      $CleanUp_207
0x1800ed857  mov     pRandAccessStream, [rbp+pStream.ptr_]; pref
0x1800ed85b  lea     r14, [rdi+0B0h]
0x1800ed862  lea     this, [r14+18h]; ppref
0x1800ed866  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800ed86b  mov     this, [rdi+0F0h]
0x1800ed872  lea     rsi, [rdi+0F8h]
0x1800ed879  mov     pRandAccessStream, [rsi]; loadsettings
0x1800ed87c  xor     r9d, r9d; doc
0x1800ed87f  mov     this, [this+30h]; doc
0x1800ed883  call    ?ApplyLoadSettings@@YAJPEAVDocument@@PEAUIXmlLoadSettings@Dom@Xml@Data@Windows@@_NW4InvokingMethodType@@@Z; ApplyLoadSettings(Document *,Windows::Data::Xml::Dom::IXmlLoadSettings *,bool,InvokingMethodType)
0x1800ed888  mov     ebx, eax
0x1800ed88a  test    eax, eax
0x1800ed88c  js      short $CleanUp_207
0x1800ed88e  mov     this, rsi; ptr
0x1800ed891  call    ??$safeRelease@UIXmlLoadSettings@Dom@Xml@Data@Windows@@@@YAXAECREAUIXmlLoadSettings@Dom@Xml@Data@Windows@@@Z; safeRelease<Windows::Data::Xml::Dom::IXmlLoadSettings>(Windows::Data::Xml::Dom::IXmlLoadSettings * volatile &)
0x1800ed896  mov     ecx, [rdi+40h]
0x1800ed899  mov     [rbp+success], 0FFFFFFFEh
0x1800ed8a0  mov     eax, [rbp+success]
0x1800ed8a3  lock cmpxchg [rbp+success], ecx
0x1800ed8a8  cmp     [rbp+success], 0
0x1800ed8ac  jnz     short $CleanUp_207
0x1800ed8ae  lea     this, [rbp+v]; pvarg
0x1800ed8b2  call    cs:__imp_VariantInit
0x1800ed8b8  mov     this, [rdi+0F0h]
0x1800ed8bf  lea     r8, [rbp+success]
0x1800ed8c3  movsd   xmm1, [rbp+v.pRecInfo]
0x1800ed8c8  lea     pRandAccessStream, [rbp+var_20]
0x1800ed8cc  mov     eax, 0Dh
0x1800ed8d1  mov     qword ptr [rbp+v.___u0+8], r14
0x1800ed8d5  mov     word ptr [rbp+v.___u0], ax
0x1800ed8d9  xor     eax, eax
0x1800ed8db  movups  xmm0, xmmword ptr [rbp+v.___u0]
0x1800ed8df  mov     word ptr [rbp+success], ax
0x1800ed8e3  mov     rax, [this]
0x1800ed8e6  movaps  [rbp+var_20], xmm0
0x1800ed8ea  movsd   [rbp+var_10], xmm1
0x1800ed8ef  mov     rax, [rax+1D0h]
0x1800ed8f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed8fb  mov     ebx, eax
0x1800ed8fd  lea     this, [rdi+0C8h]; ppref
0x1800ed904  xor     edx, edx; pref
0x1800ed906  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800ed90b  lea     this, [rbp+pStream]; this
0x1800ed90f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ed914  lea     r11, [rsp+60h+var_s0]
0x1800ed919  mov     eax, ebx
0x1800ed91b  mov     rbx, [r11+28h]
0x1800ed91f  mov     rsi, [r11+38h]
0x1800ed923  mov     rsp, r11
0x1800ed926  pop     r14
0x1800ed928  pop     rdi
0x1800ed929  pop     rbp
0x1800ed92a  retn
```
