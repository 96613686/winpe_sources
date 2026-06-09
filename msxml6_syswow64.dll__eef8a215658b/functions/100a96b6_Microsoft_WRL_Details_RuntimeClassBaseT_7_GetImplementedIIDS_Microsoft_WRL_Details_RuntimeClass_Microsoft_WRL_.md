# Microsoft::WRL::Details::RuntimeClassBaseT<7>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>>(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *,ulong *,_GUID * *)

- ea: `0x100a96b6`
- end: `0x100a9719`
- name: `??$GetImplementedIIDS@V?$RuntimeClass@U?$InterfaceListHelper@UIXmlNodeList@Dom@Xml@Data@Windows@@U?$IIterable@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@5@U?$IVectorView@PAUIXmlNode@Dom@Xml@Data@Windows@@@785@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$06@Details@WRL@Microsoft@@KGJPAV?$RuntimeClass@U?$InterfaceListHelper@UIXmlNodeList@Dom@Xml@Data@Windows@@U?$IIterable@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@5@U?$IVectorView@PAUIXmlNode@Dom@Xml@Data@Windows@@@785@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@123@PAKPAPAU_GUID@@@Z`
- size: `99`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x100a9f90`

## callees

- `0x100a96b6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100a96cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100a96cf`

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
0x100a96b6  mov     edi, edi
0x100a96b8  push    ebp
0x100a96b9  mov     ebp, esp
0x100a96bb  mov     eax, [ebp+iids]
0x100a96be  push    ebx
0x100a96bf  mov     ebx, iidCount
0x100a96c1  push    30h ; '0'; cb
0x100a96c3  mov     dword ptr [eax], 0
0x100a96c9  mov     dword ptr [ebx], 0
0x100a96cf  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x100a96d5  test    eax, eax
0x100a96d7  jnz     short loc_100A96E0
0x100a96d9  mov     eax, 8007000Eh
0x100a96de  jmp     short loc_100A9714
0x100a96e0  push    esi
0x100a96e1  push    edi
0x100a96e2  mov     edi, eax
0x100a96e4  mov     ecx, [ebp+iids]
0x100a96e7  mov     esi, offset __GUID_8c60ad77_83a4_4ec1_9c54_7ba429e13da6
0x100a96ec  movsd
0x100a96ed  movsd
0x100a96ee  movsd
0x100a96ef  movsd
0x100a96f0  mov     esi, offset __GUID_f1146ffc_8c92_56e8_93f1_711f86722633
0x100a96f5  lea     edi, [eax+10h]
0x100a96f8  movsd
0x100a96f9  movsd
0x100a96fa  movsd
0x100a96fb  movsd
0x100a96fc  mov     esi, offset __GUID_139d959e_e7b5_5cb6_a596_4b544478da9b
0x100a9701  lea     edi, [eax+20h]
0x100a9704  movsd
0x100a9705  movsd
0x100a9706  movsd
0x100a9707  movsd
0x100a9708  mov     dword ptr [ebx], 3
0x100a970e  pop     edi
0x100a970f  mov     [ecx], eax
0x100a9711  xor     eax, eax
0x100a9713  pop     esi
0x100a9714  pop     ebx
0x100a9715  pop     ebp
0x100a9716  retn    4
```
