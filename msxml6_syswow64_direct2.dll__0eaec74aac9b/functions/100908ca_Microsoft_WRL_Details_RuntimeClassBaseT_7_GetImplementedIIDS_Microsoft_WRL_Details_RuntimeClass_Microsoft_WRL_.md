# Microsoft::WRL::Details::RuntimeClassBaseT<7>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>>(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *,ulong *,_GUID * *)

- ea: `0x100908ca`
- end: `0x1009091b`
- name: `??$GetImplementedIIDS@V?$RuntimeClass@U?$InterfaceListHelper@U?$ChainInterfaces@UIXmlDocument@Dom@Xml@Data@Windows@@UIXmlNode@2345@UIXmlNodeSelector@2345@VNil@Details@WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@@WRL@Microsoft@@UIXmlNodeSerializer@Dom@Xml@Data@Windows@@UIXmlDocumentIO@5678@UIXmlDocumentIO2@5678@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$06@Details@WRL@Microsoft@@KGJPAV?$RuntimeClass@U?$InterfaceListHelper@U?$ChainInterfaces@UIXmlDocument@Dom@Xml@Data@Windows@@UIXmlNode@2345@UIXmlNodeSelector@2345@VNil@Details@WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@@WRL@Microsoft@@UIXmlNodeSerializer@Dom@Xml@Data@Windows@@UIXmlDocumentIO@5678@UIXmlDocumentIO2@5678@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@123@PAKPAPAU_GUID@@@Z`
- size: `81`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x100921f0`

## callees

- `0x100908ca`
- `0x10091e6e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100908e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100908e6`

## pseudocode

```c
HRESULT __userpurge Microsoft::WRL::Details::RuntimeClassBaseT<7>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>>@<eax>(
        Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *iidCount@<edx>,
        _GUID **iids,
        _GUID **implements)
{
  _GUID *v4; // eax
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<7>,0,Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2> *v5; // ecx
  unsigned int v6; // esi
  HRESULT result; // eax
  unsigned int index; // [esp+Ch] [ebp-4h] BYREF

  *iids = 0;
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<7>,0,Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>::Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::Windows::Data::Xml::Dom::IXmlDocument::IInspectable::IUnknown::__vftable = 0;
  v4 = (_GUID *)CoTaskMemAlloc(0x60u);
  v6 = (unsigned int)v4;
  if ( !v4 )
    return -2147024882;
  index = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<7>,0,Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>::FillArrayWithIid(
    v5,
    &index,
    v4);
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<7>,0,Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>::Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::Windows::Data::Xml::Dom::IXmlDocument::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>_vtbl *)6;
  result = 0;
  *iids = (_GUID *)v6;
  return result;
}

```

## disassembly

```asm
0x100908ca  mov     edi, edi
0x100908cc  push    ebp
0x100908cd  mov     ebp, esp
0x100908cf  push    ecx
0x100908d0  push    ebx
0x100908d1  mov     ebx, [ebp+iids]
0x100908d4  push    esi
0x100908d5  push    edi
0x100908d6  mov     edi, iidCount
0x100908d8  mov     dword ptr [ebx], 0
0x100908de  push    60h ; '`'; cb
0x100908e0  mov     dword ptr [edi], 0
0x100908e6  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x100908ec  mov     esi, eax
0x100908ee  test    esi, esi
0x100908f0  jnz     short loc_100908F9
0x100908f2  mov     eax, 8007000Eh
0x100908f7  jmp     short loc_10090914
0x100908f9  push    esi; iids
0x100908fa  lea     eax, [ebp+index]
0x100908fd  mov     [ebp+index], 0
0x10090904  push    eax; index
0x10090905  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$06@WRL@Microsoft@@$0A@U?$ChainInterfaces@UIXmlDocument@Dom@Xml@Data@Windows@@UIXmlNode@2345@UIXmlNodeSelector@2345@VNil@Details@WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@@23@UIXmlNodeSerializer@Dom@Xml@Data@Windows@@UIXmlDocumentIO@6789@UIXmlDocumentIO2@6789@@Details@WRL@Microsoft@@IAEXPAKPAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<7>,0,Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>::FillArrayWithIid(ulong *,_GUID *)
0x1009090a  mov     dword ptr [edi], 6
0x10090910  xor     eax, eax
0x10090912  mov     [ebx], esi
0x10090914  pop     edi
0x10090915  pop     esi
0x10090916  pop     ebx
0x10090917  leave
0x10090918  retn    4
```
