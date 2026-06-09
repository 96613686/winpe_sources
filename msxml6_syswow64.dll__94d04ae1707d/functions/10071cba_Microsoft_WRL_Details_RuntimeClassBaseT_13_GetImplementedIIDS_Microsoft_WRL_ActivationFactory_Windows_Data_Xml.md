# Microsoft::WRL::Details::RuntimeClassBaseT<13>::GetImplementedIIDS<Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>>(Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0> *,ulong *,_GUID * *)

- ea: `0x10071cba`
- end: `0x10071d0b`
- name: `??$GetImplementedIIDS@V?$ActivationFactory@UIXmlDocumentStatics@Dom@Xml@Data@Windows@@VFtmBase@WRL@Microsoft@@VNil@Details@78@$0A@@WRL@Microsoft@@@?$RuntimeClassBaseT@$0N@@Details@WRL@Microsoft@@KGJPAV?$ActivationFactory@UIXmlDocumentStatics@Dom@Xml@Data@Windows@@VFtmBase@WRL@Microsoft@@VNil@Details@78@$0A@@23@PAKPAPAU_GUID@@@Z`
- size: `81`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x100734f0`

## callees

- `0x10071cba`
- `0x100732ef`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10071cd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10071cd6`

## pseudocode

```c
HRESULT __userpurge Microsoft::WRL::Details::RuntimeClassBaseT<13>::GetImplementedIIDS<Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>>@<eax>(
        Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0> *iidCount@<edx>,
        _GUID **iids,
        _GUID **implements)
{
  _GUID *v4; // eax
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil> *v5; // ecx
  unsigned int v6; // esi
  HRESULT result; // eax
  unsigned int index; // [esp+Ch] [ebp-4h] BYREF

  *iids = 0;
  iidCount->Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<IActivationFactory,Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::RuntimeClassFlags<13>,0,1,0>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::IActivationFactory::IInspectable::IUnknown::__vftable = 0;
  v4 = (_GUID *)CoTaskMemAlloc(0x20u);
  v6 = (unsigned int)v4;
  if ( !v4 )
    return -2147024882;
  index = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
    v5,
    &index,
    v4);
  iidCount->Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<IActivationFactory,Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::RuntimeClassFlags<13>,0,1,0>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::IActivationFactory::IInspectable::IUnknown::__vftable = (Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>_vtbl *)2;
  result = 0;
  *iids = (_GUID *)v6;
  return result;
}

```

## disassembly

```asm
0x10071cba  mov     edi, edi
0x10071cbc  push    ebp
0x10071cbd  mov     ebp, esp
0x10071cbf  push    ecx
0x10071cc0  push    ebx
0x10071cc1  mov     ebx, [ebp+iids]
0x10071cc4  push    esi
0x10071cc5  push    edi
0x10071cc6  mov     edi, iidCount
0x10071cc8  mov     dword ptr [ebx], 0
0x10071cce  push    20h ; ' '; cb
0x10071cd0  mov     dword ptr [edi], 0
0x10071cd6  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10071cdc  mov     esi, eax
0x10071cde  test    esi, esi
0x10071ce0  jnz     short loc_10071CE9
0x10071ce2  mov     eax, 8007000Eh
0x10071ce7  jmp     short loc_10071D04
0x10071ce9  push    esi; iids
0x10071cea  lea     eax, [ebp+index]
0x10071ced  mov     [ebp+index], 0
0x10071cf4  push    eax; index
0x10071cf5  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@UIXmlDocumentStatics@Dom@Xml@Data@Windows@@VFtmBase@23@VNil@Details@23@VNil@Details@23@@Details@WRL@Microsoft@@IAEXPAKPAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x10071cfa  mov     dword ptr [edi], 2
0x10071d00  xor     eax, eax
0x10071d02  mov     [ebx], esi
0x10071d04  pop     edi
0x10071d05  pop     esi
0x10071d06  pop     ebx
0x10071d07  leave
0x10071d08  retn    4
```
