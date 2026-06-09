# Microsoft::WRL::Details::RuntimeClassBaseT<13>::GetImplementedIIDS<Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>>(Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0> *,ulong *,_GUID * *)

- ea: `0x10071c71`
- end: `0x10071cc2`
- name: `??$GetImplementedIIDS@V?$ActivationFactory@UIXsltProcessorFactory@Xsl@Xml@Data@Windows@@VFtmBase@WRL@Microsoft@@VNil@Details@78@$0A@@WRL@Microsoft@@@?$RuntimeClassBaseT@$0N@@Details@WRL@Microsoft@@KGJPAV?$ActivationFactory@UIXsltProcessorFactory@Xsl@Xml@Data@Windows@@VFtmBase@WRL@Microsoft@@VNil@Details@78@$0A@@23@PAKPAPAU_GUID@@@Z`
- size: `81`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10073550`

## callees

- `0x10071c71`
- `0x10073354`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10071c8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10071c8d`

## pseudocode

```c
HRESULT __userpurge Microsoft::WRL::Details::RuntimeClassBaseT<13>::GetImplementedIIDS<Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>>@<eax>(
        Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0> *iidCount@<edx>,
        _GUID **iids,
        _GUID **implements)
{
  _GUID *v4; // eax
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil> *v5; // ecx
  unsigned int v6; // esi
  HRESULT result; // eax
  unsigned int index; // [esp+Ch] [ebp-4h] BYREF

  *iids = 0;
  iidCount->Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<IActivationFactory,Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::RuntimeClassFlags<13>,0,1,0>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::IActivationFactory::IInspectable::IUnknown::__vftable = 0;
  v4 = (_GUID *)CoTaskMemAlloc(0x20u);
  v6 = (unsigned int)v4;
  if ( !v4 )
    return -2147024882;
  index = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
    v5,
    &index,
    v4);
  iidCount->Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<IActivationFactory,Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::RuntimeClassFlags<13>,0,1,0>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::IActivationFactory::IInspectable::IUnknown::__vftable = (Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>_vtbl *)2;
  result = 0;
  *iids = (_GUID *)v6;
  return result;
}

```

## disassembly

```asm
0x10071c71  mov     edi, edi
0x10071c73  push    ebp
0x10071c74  mov     ebp, esp
0x10071c76  push    ecx
0x10071c77  push    ebx
0x10071c78  mov     ebx, [ebp+iids]
0x10071c7b  push    esi
0x10071c7c  push    edi
0x10071c7d  mov     edi, iidCount
0x10071c7f  mov     dword ptr [ebx], 0
0x10071c85  push    20h ; ' '; cb
0x10071c87  mov     dword ptr [edi], 0
0x10071c8d  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10071c93  mov     esi, eax
0x10071c95  test    esi, esi
0x10071c97  jnz     short loc_10071CA0
0x10071c99  mov     eax, 8007000Eh
0x10071c9e  jmp     short loc_10071CBB
0x10071ca0  push    esi; iids
0x10071ca1  lea     eax, [ebp+index]
0x10071ca4  mov     [ebp+index], 0
0x10071cab  push    eax; index
0x10071cac  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@UIXsltProcessorFactory@Xsl@Xml@Data@Windows@@VFtmBase@23@VNil@Details@23@VNil@Details@23@@Details@WRL@Microsoft@@IAEXPAKPAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x10071cb1  mov     dword ptr [edi], 2
0x10071cb7  xor     eax, eax
0x10071cb9  mov     [ebx], esi
0x10071cbb  pop     edi
0x10071cbc  pop     esi
0x10071cbd  pop     ebx
0x10071cbe  leave
0x10071cbf  retn    4
```
