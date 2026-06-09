# Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase> *,ulong *,_GUID * *)

- ea: `0x10090938`
- end: `0x100909a3`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIXmlNodeList@Dom@Xml@Data@Windows@@U?$IIterable@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@8@U?$IVectorView@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@8@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KGJPAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIXmlNodeList@Dom@Xml@Data@Windows@@U?$IIterable@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@8@U?$IVectorView@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@8@VFtmBase@23@@123@PAKPAPAU_GUID@@@Z`
- size: `107`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x100921a0`

## callees

- `0x10090938`
- `0x10091d18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10090952`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10090952`

## pseudocode

```c
HRESULT __userpurge Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>>@<eax>(
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase> *iidCount@<edx>,
        _GUID **iids,
        _GUID **implements)
{
  _GUID *v4; // edx
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase> *v5; // ecx
  unsigned int v7; // edx
  unsigned int index; // [esp+4h] [ebp-4h] BYREF

  *iids = 0;
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Data::Xml::Dom::IXmlNodeList,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>::Windows::Data::Xml::Dom::IXmlNodeList::IInspectable::IUnknown::__vftable = 0;
  v4 = (_GUID *)CoTaskMemAlloc(0x40u);
  if ( !v4 )
    return -2147024882;
  index = 2;
  *v4 = _GUID_8c60ad77_83a4_4ec1_9c54_7ba429e13da6;
  v4[1] = _GUID_00000038_0000_0000_c000_000000000046;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &index,
    v4);
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Data::Xml::Dom::IXmlNodeList,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>::Windows::Data::Xml::Dom::IXmlNodeList::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>_vtbl *)4;
  *iids = (_GUID *)v7;
  return 0;
}

```

## disassembly

```asm
0x10090938  mov     edi, edi
0x1009093a  push    ebp
0x1009093b  mov     ebp, esp
0x1009093d  push    ecx
0x1009093e  mov     eax, [ebp+iids]
0x10090941  push    ebx
0x10090942  mov     ebx, iidCount
0x10090944  push    40h ; '@'; cb
0x10090946  mov     dword ptr [eax], 0
0x1009094c  mov     dword ptr [ebx], 0
0x10090952  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10090958  mov     iidCount, eax
0x1009095a  test    iidCount, iidCount
0x1009095c  jnz     short loc_10090965
0x1009095e  mov     eax, 8007000Eh
0x10090963  jmp     short loc_1009099E
0x10090965  push    esi
0x10090966  push    edi
0x10090967  mov     esi, offset __GUID_8c60ad77_83a4_4ec1_9c54_7ba429e13da6
0x1009096c  mov     [ebp+index], 2
0x10090973  mov     edi, iidCount
0x10090975  lea     eax, [ebp+index]
0x10090978  push    iidCount; iids
0x10090979  push    eax; index
0x1009097a  movsd
0x1009097b  movsd
0x1009097c  movsd
0x1009097d  movsd
0x1009097e  mov     esi, offset __GUID_00000038_0000_0000_c000_000000000046
0x10090983  lea     edi, [iidCount+10h]
0x10090986  movsd
0x10090987  movsd
0x10090988  movsd
0x10090989  movsd
0x1009098a  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$IIterable@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@Windows@@U?$IVectorView@PAUIXmlNode@Dom@Xml@Data@Windows@@@567@VFtmBase@23@@Details@WRL@Microsoft@@IAEXPAKPAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1009098f  mov     eax, [ebp+iids]
0x10090992  mov     dword ptr [ebx], 4
0x10090998  pop     edi
0x10090999  pop     esi
0x1009099a  mov     [eax], iidCount
0x1009099c  xor     eax, eax
0x1009099e  pop     ebx
0x1009099f  leave
0x100909a0  retn    4
```
