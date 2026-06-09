# Microsoft::WRL::Details::RuntimeClassBaseT<7>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>>(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *,ulong *,_GUID * *)

- ea: `0x100a964d`
- end: `0x100a96b0`
- name: `??$GetImplementedIIDS@V?$RuntimeClass@U?$InterfaceListHelper@UIXmlNamedNodeMap@Dom@Xml@Data@Windows@@U?$IIterable@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@5@U?$IVectorView@PAUIXmlNode@Dom@Xml@Data@Windows@@@785@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$06@Details@WRL@Microsoft@@KGJPAV?$RuntimeClass@U?$InterfaceListHelper@UIXmlNamedNodeMap@Dom@Xml@Data@Windows@@U?$IIterable@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@5@U?$IVectorView@PAUIXmlNode@Dom@Xml@Data@Windows@@@785@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@123@PAKPAPAU_GUID@@@Z`
- size: `99`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x100a9f50`

## callees

- `0x100a964d`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100a9666`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100a9666`

## pseudocode

```c
HRESULT __userpurge Microsoft::WRL::Details::RuntimeClassBaseT<7>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>>@<eax>(
        Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *iidCount@<edx>,
        _GUID **iids,
        _GUID **implements)
{
  GUID *v4; // eax

  *iids = 0;
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<7>,0,Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >::Windows::Data::Xml::Dom::IXmlNamedNodeMap::IInspectable::IUnknown::__vftable = 0;
  v4 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v4 )
    return -2147024882;
  *v4 = _GUID_b3a69eb0_aab0_4b82_a6fa_b1453f7c021b;
  v4[1] = _GUID_f1146ffc_8c92_56e8_93f1_711f86722633;
  v4[2] = _GUID_139d959e_e7b5_5cb6_a596_4b544478da9b;
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<7>,0,Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >::Windows::Data::Xml::Dom::IXmlNamedNodeMap::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>_vtbl *)3;
  *iids = v4;
  return 0;
}

```

## disassembly

```asm
0x100a964d  mov     edi, edi
0x100a964f  push    ebp
0x100a9650  mov     ebp, esp
0x100a9652  mov     eax, [ebp+iids]
0x100a9655  push    ebx
0x100a9656  mov     ebx, iidCount
0x100a9658  push    30h ; '0'; cb
0x100a965a  mov     dword ptr [eax], 0
0x100a9660  mov     dword ptr [ebx], 0
0x100a9666  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x100a966c  test    eax, eax
0x100a966e  jnz     short loc_100A9677
0x100a9670  mov     eax, 8007000Eh
0x100a9675  jmp     short loc_100A96AB
0x100a9677  push    esi
0x100a9678  push    edi
0x100a9679  mov     edi, eax
0x100a967b  mov     ecx, [ebp+iids]
0x100a967e  mov     esi, offset __GUID_b3a69eb0_aab0_4b82_a6fa_b1453f7c021b
0x100a9683  movsd
0x100a9684  movsd
0x100a9685  movsd
0x100a9686  movsd
0x100a9687  mov     esi, offset __GUID_f1146ffc_8c92_56e8_93f1_711f86722633
0x100a968c  lea     edi, [eax+10h]
0x100a968f  movsd
0x100a9690  movsd
0x100a9691  movsd
0x100a9692  movsd
0x100a9693  mov     esi, offset __GUID_139d959e_e7b5_5cb6_a596_4b544478da9b
0x100a9698  lea     edi, [eax+20h]
0x100a969b  movsd
0x100a969c  movsd
0x100a969d  movsd
0x100a969e  movsd
0x100a969f  mov     dword ptr [ebx], 3
0x100a96a5  pop     edi
0x100a96a6  mov     [ecx], eax
0x100a96a8  xor     eax, eax
0x100a96aa  pop     esi
0x100a96ab  pop     ebx
0x100a96ac  pop     ebp
0x100a96ad  retn    4
```
