# Microsoft::WRL::Details::RuntimeClassBaseT<7>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>>(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *,ulong *,_GUID * *)

- ea: `0x100a95a6`
- end: `0x100a9609`
- name: `??$GetImplementedIIDS@V?$RuntimeClass@U?$InterfaceListHelper@UIXmlNodeList@Dom@Xml@Data@Windows@@U?$IIterable@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@5@U?$IVectorView@PAUIXmlNode@Dom@Xml@Data@Windows@@@785@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$06@Details@WRL@Microsoft@@KGJPAV?$RuntimeClass@U?$InterfaceListHelper@UIXmlNodeList@Dom@Xml@Data@Windows@@U?$IIterable@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@5@U?$IVectorView@PAUIXmlNode@Dom@Xml@Data@Windows@@@785@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@123@PAKPAPAU_GUID@@@Z`
- size: `99`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x100a9e80`

## callees

- `0x100a95a6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100a95bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100a95bf`

## pseudocode

```c
HRESULT __userpurge Microsoft::WRL::Details::RuntimeClassBaseT<7>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>>@<eax>(
        Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *iidCount@<edx>,
        _GUID **iids,
        _GUID **implements)
{
  GUID *v4; // eax

  *iids = 0;
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<7>,0,Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >::Windows::Data::Xml::Dom::IXmlNodeList::IInspectable::IUnknown::__vftable = 0;
  v4 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v4 )
    return -2147024882;
  *v4 = _GUID_8c60ad77_83a4_4ec1_9c54_7ba429e13da6;
  v4[1] = _GUID_f1146ffc_8c92_56e8_93f1_711f86722633;
  v4[2] = _GUID_139d959e_e7b5_5cb6_a596_4b544478da9b;
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<7>,0,Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >::Windows::Data::Xml::Dom::IXmlNodeList::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>_vtbl *)3;
  *iids = v4;
  return 0;
}

```

## disassembly

```asm
0x100a95a6  mov     edi, edi
0x100a95a8  push    ebp
0x100a95a9  mov     ebp, esp
0x100a95ab  mov     eax, [ebp+iids]
0x100a95ae  push    ebx
0x100a95af  mov     ebx, iidCount
0x100a95b1  push    30h ; '0'; cb
0x100a95b3  mov     dword ptr [eax], 0
0x100a95b9  mov     dword ptr [ebx], 0
0x100a95bf  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x100a95c5  test    eax, eax
0x100a95c7  jnz     short loc_100A95D0
0x100a95c9  mov     eax, 8007000Eh
0x100a95ce  jmp     short loc_100A9604
0x100a95d0  push    esi
0x100a95d1  push    edi
0x100a95d2  mov     edi, eax
0x100a95d4  mov     ecx, [ebp+iids]
0x100a95d7  mov     esi, offset __GUID_8c60ad77_83a4_4ec1_9c54_7ba429e13da6
0x100a95dc  movsd
0x100a95dd  movsd
0x100a95de  movsd
0x100a95df  movsd
0x100a95e0  mov     esi, offset __GUID_f1146ffc_8c92_56e8_93f1_711f86722633
0x100a95e5  lea     edi, [eax+10h]
0x100a95e8  movsd
0x100a95e9  movsd
0x100a95ea  movsd
0x100a95eb  movsd
0x100a95ec  mov     esi, offset __GUID_139d959e_e7b5_5cb6_a596_4b544478da9b
0x100a95f1  lea     edi, [eax+20h]
0x100a95f4  movsd
0x100a95f5  movsd
0x100a95f6  movsd
0x100a95f7  movsd
0x100a95f8  mov     dword ptr [ebx], 3
0x100a95fe  pop     edi
0x100a95ff  mov     [ecx], eax
0x100a9601  xor     eax, eax
0x100a9603  pop     esi
0x100a9604  pop     ebx
0x100a9605  pop     ebp
0x100a9606  retn    4
```
