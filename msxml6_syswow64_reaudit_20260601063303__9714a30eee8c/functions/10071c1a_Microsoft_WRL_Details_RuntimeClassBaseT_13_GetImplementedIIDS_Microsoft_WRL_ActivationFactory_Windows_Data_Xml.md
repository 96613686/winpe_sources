# Microsoft::WRL::Details::RuntimeClassBaseT<13>::GetImplementedIIDS<Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>>(Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0> *,ulong *,_GUID * *)

- ea: `0x10071c1a`
- end: `0x10071c6b`
- name: `??$GetImplementedIIDS@V?$ActivationFactory@UIXmlDocumentStatics@Dom@Xml@Data@Windows@@VFtmBase@WRL@Microsoft@@VNil@Details@78@$0A@@WRL@Microsoft@@@?$RuntimeClassBaseT@$0N@@Details@WRL@Microsoft@@KGJPAV?$ActivationFactory@UIXmlDocumentStatics@Dom@Xml@Data@Windows@@VFtmBase@WRL@Microsoft@@VNil@Details@78@$0A@@23@PAKPAPAU_GUID@@@Z`
- size: `81`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10073520`

## callees

- `0x10071c1a`
- `0x1007331f`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10071c36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10071c36`

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
0x10071c1a  mov     edi, edi
0x10071c1c  push    ebp
0x10071c1d  mov     ebp, esp
0x10071c1f  push    ecx
0x10071c20  push    ebx
0x10071c21  mov     ebx, [ebp+iids]
0x10071c24  push    esi
0x10071c25  push    edi
0x10071c26  mov     edi, iidCount
0x10071c28  mov     dword ptr [ebx], 0
0x10071c2e  push    20h ; ' '; cb
0x10071c30  mov     dword ptr [edi], 0
0x10071c36  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10071c3c  mov     esi, eax
0x10071c3e  test    esi, esi
0x10071c40  jnz     short loc_10071C49
0x10071c42  mov     eax, 8007000Eh
0x10071c47  jmp     short loc_10071C64
0x10071c49  push    esi; iids
0x10071c4a  lea     eax, [ebp+index]
0x10071c4d  mov     [ebp+index], 0
0x10071c54  push    eax; index
0x10071c55  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@UIXmlDocumentStatics@Dom@Xml@Data@Windows@@VFtmBase@23@VNil@Details@23@VNil@Details@23@@Details@WRL@Microsoft@@IAEXPAKPAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x10071c5a  mov     dword ptr [edi], 2
0x10071c60  xor     eax, eax
0x10071c62  mov     [ebx], esi
0x10071c64  pop     edi
0x10071c65  pop     esi
0x10071c66  pop     ebx
0x10071c67  leave
0x10071c68  retn    4
```
