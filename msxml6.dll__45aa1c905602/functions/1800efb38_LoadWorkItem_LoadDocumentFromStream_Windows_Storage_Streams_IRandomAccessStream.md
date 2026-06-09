# LoadWorkItem::LoadDocumentFromStream(Windows::Storage::Streams::IRandomAccessStream *)

- ea: `0x1800efb38`
- end: `0x1800efc70`
- name: `?LoadDocumentFromStream@LoadWorkItem@@AEAAJPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z`
- size: `312`
- prototype: `HRESULT __fastcall(LoadWorkItem *this, Windows::Storage::Streams::IRandomAccessStream *pRandAccessStream)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800eeb70`

## callees

- `0x180015a80`
- `0x1800719e4`
- `0x180077898`
- `0x1800eddd8`
- `0x1800efb38`
- `0x18018c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800efbf0`
- `OLEAUT32!__imp_VariantInit` at `0x1800efbf0`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x1800efb7f`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x1800efb7f`

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
0x1800efb38  mov     [rsp-18h+arg_8], rbx
0x1800efb3d  mov     [rsp-18h+arg_18], rsi
0x1800efb42  push    rbp
0x1800efb43  push    rdi
0x1800efb44  push    r14
0x1800efb46  mov     rbp, rsp
0x1800efb49  sub     rsp, 60h
0x1800efb4d  mov     rdi, this
0x1800efb50  mov     [rbp+pStream.ptr_], 0
0x1800efb58  xorps   xmm0, xmm0
0x1800efb5b  lea     this, [rbp+pStream]; this
0x1800efb5f  xor     eax, eax
0x1800efb61  mov     rbx, pRandAccessStream
0x1800efb64  movups  xmmword ptr [rbp+v.___u0], xmm0
0x1800efb68  mov     [rbp+v.pRecInfo], rax
0x1800efb6c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800efb71  lea     r8, [rbp+pStream]
0x1800efb75  mov     this, rbx
0x1800efb78  lea     pRandAccessStream, _GUID_0000000c_0000_0000_c000_000000000046
0x1800efb7f  call    cs:__imp_CreateStreamOverRandomAccessStream
0x1800efb86  nop     dword ptr [rax+rax+00h]
0x1800efb8b  mov     ebx, eax
0x1800efb8d  test    eax, eax
0x1800efb8f  js      $CleanUp_207
0x1800efb95  mov     pRandAccessStream, [rbp+pStream.ptr_]; pref
0x1800efb99  lea     r14, [rdi+0B0h]
0x1800efba0  lea     this, [r14+18h]; ppref
0x1800efba4  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800efba9  mov     this, [rdi+0F0h]
0x1800efbb0  lea     rsi, [rdi+0F8h]
0x1800efbb7  mov     pRandAccessStream, [rsi]; loadsettings
0x1800efbba  xor     r9d, r9d; doc
0x1800efbbd  mov     this, [this+30h]; doc
0x1800efbc1  call    ?ApplyLoadSettings@@YAJPEAVDocument@@PEAUIXmlLoadSettings@Dom@Xml@Data@Windows@@_NW4InvokingMethodType@@@Z; ApplyLoadSettings(Document *,Windows::Data::Xml::Dom::IXmlLoadSettings *,bool,InvokingMethodType)
0x1800efbc6  mov     ebx, eax
0x1800efbc8  test    eax, eax
0x1800efbca  js      short $CleanUp_207
0x1800efbcc  mov     this, rsi; ptr
0x1800efbcf  call    ??$safeRelease@UIXmlLoadSettings@Dom@Xml@Data@Windows@@@@YAXAECREAUIXmlLoadSettings@Dom@Xml@Data@Windows@@@Z; safeRelease<Windows::Data::Xml::Dom::IXmlLoadSettings>(Windows::Data::Xml::Dom::IXmlLoadSettings * volatile &)
0x1800efbd4  mov     ecx, [rdi+40h]
0x1800efbd7  mov     [rbp+success], 0FFFFFFFEh
0x1800efbde  mov     eax, [rbp+success]
0x1800efbe1  lock cmpxchg [rbp+success], ecx
0x1800efbe6  cmp     [rbp+success], 0
0x1800efbea  jnz     short $CleanUp_207
0x1800efbec  lea     this, [rbp+v]; pvarg
0x1800efbf0  call    cs:__imp_VariantInit
0x1800efbf7  nop     dword ptr [rax+rax+00h]
0x1800efbfc  mov     this, [rdi+0F0h]
0x1800efc03  lea     r8, [rbp+success]
0x1800efc07  movsd   xmm1, [rbp+v.pRecInfo]
0x1800efc0c  lea     pRandAccessStream, [rbp+var_20]
0x1800efc10  mov     eax, 0Dh
0x1800efc15  mov     qword ptr [rbp+v.___u0+8], r14
0x1800efc19  mov     word ptr [rbp+v.___u0], ax
0x1800efc1d  xor     eax, eax
0x1800efc1f  movups  xmm0, xmmword ptr [rbp+v.___u0]
0x1800efc23  mov     word ptr [rbp+success], ax
0x1800efc27  mov     rax, [this]
0x1800efc2a  movaps  [rbp+var_20], xmm0
0x1800efc2e  movsd   [rbp+var_10], xmm1
0x1800efc33  mov     rax, [rax+1D0h]
0x1800efc3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efc3f  mov     ebx, eax
0x1800efc41  lea     this, [rdi+0C8h]; ppref
0x1800efc48  xor     edx, edx; pref
0x1800efc4a  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800efc4f  lea     this, [rbp+pStream]; this
0x1800efc53  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800efc58  lea     r11, [rsp+60h+var_s0]
0x1800efc5d  mov     eax, ebx
0x1800efc5f  mov     rbx, [r11+28h]
0x1800efc63  mov     rsi, [r11+38h]
0x1800efc67  mov     rsp, r11
0x1800efc6a  pop     r14
0x1800efc6c  pop     rdi
0x1800efc6d  pop     rbp
0x1800efc6e  retn
```
