# Microsoft::WRL::Details::RuntimeClassBaseT<7>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>>(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *,ulong *,_GUID * *)

- ea: `0x100a953d`
- end: `0x100a95a0`
- name: `??$GetImplementedIIDS@V?$RuntimeClass@U?$InterfaceListHelper@UIXmlNamedNodeMap@Dom@Xml@Data@Windows@@U?$IIterable@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@5@U?$IVectorView@PAUIXmlNode@Dom@Xml@Data@Windows@@@785@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$06@Details@WRL@Microsoft@@KGJPAV?$RuntimeClass@U?$InterfaceListHelper@UIXmlNamedNodeMap@Dom@Xml@Data@Windows@@U?$IIterable@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@5@U?$IVectorView@PAUIXmlNode@Dom@Xml@Data@Windows@@@785@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@123@PAKPAPAU_GUID@@@Z`
- size: `99`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x100a9e40`

## callees

- `0x100a953d`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100a9556`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100a9556`

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
0x100a953d  mov     edi, edi
0x100a953f  push    ebp
0x100a9540  mov     ebp, esp
0x100a9542  mov     eax, [ebp+iids]
0x100a9545  push    ebx
0x100a9546  mov     ebx, iidCount
0x100a9548  push    30h ; '0'; cb
0x100a954a  mov     dword ptr [eax], 0
0x100a9550  mov     dword ptr [ebx], 0
0x100a9556  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x100a955c  test    eax, eax
0x100a955e  jnz     short loc_100A9567
0x100a9560  mov     eax, 8007000Eh
0x100a9565  jmp     short loc_100A959B
0x100a9567  push    esi
0x100a9568  push    edi
0x100a9569  mov     edi, eax
0x100a956b  mov     ecx, [ebp+iids]
0x100a956e  mov     esi, offset __GUID_b3a69eb0_aab0_4b82_a6fa_b1453f7c021b
0x100a9573  movsd
0x100a9574  movsd
0x100a9575  movsd
0x100a9576  movsd
0x100a9577  mov     esi, offset __GUID_f1146ffc_8c92_56e8_93f1_711f86722633
0x100a957c  lea     edi, [eax+10h]
0x100a957f  movsd
0x100a9580  movsd
0x100a9581  movsd
0x100a9582  movsd
0x100a9583  mov     esi, offset __GUID_139d959e_e7b5_5cb6_a596_4b544478da9b
0x100a9588  lea     edi, [eax+20h]
0x100a958b  movsd
0x100a958c  movsd
0x100a958d  movsd
0x100a958e  movsd
0x100a958f  mov     dword ptr [ebx], 3
0x100a9595  pop     edi
0x100a9596  mov     [ecx], eax
0x100a9598  xor     eax, eax
0x100a959a  pop     esi
0x100a959b  pop     ebx
0x100a959c  pop     ebp
0x100a959d  retn    4
```
