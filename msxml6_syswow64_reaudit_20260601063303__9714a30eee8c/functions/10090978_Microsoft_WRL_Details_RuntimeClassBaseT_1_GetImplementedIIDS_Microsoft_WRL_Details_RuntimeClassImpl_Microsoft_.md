# Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase> *,ulong *,_GUID * *)

- ea: `0x10090978`
- end: `0x100909e3`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIXmlNodeList@Dom@Xml@Data@Windows@@U?$IIterable@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@8@U?$IVectorView@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@8@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KGJPAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIXmlNodeList@Dom@Xml@Data@Windows@@U?$IIterable@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@8@U?$IVectorView@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@8@VFtmBase@23@@123@PAKPAPAU_GUID@@@Z`
- size: `107`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10092260`

## callees

- `0x10090978`
- `0x10091dd8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10090992`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10090992`

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
0x10090978  mov     edi, edi
0x1009097a  push    ebp
0x1009097b  mov     ebp, esp
0x1009097d  push    ecx
0x1009097e  mov     eax, [ebp+iids]
0x10090981  push    ebx
0x10090982  mov     ebx, iidCount
0x10090984  push    40h ; '@'; cb
0x10090986  mov     dword ptr [eax], 0
0x1009098c  mov     dword ptr [ebx], 0
0x10090992  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10090998  mov     iidCount, eax
0x1009099a  test    iidCount, iidCount
0x1009099c  jnz     short loc_100909A5
0x1009099e  mov     eax, 8007000Eh
0x100909a3  jmp     short loc_100909DE
0x100909a5  push    esi
0x100909a6  push    edi
0x100909a7  mov     esi, offset __GUID_8c60ad77_83a4_4ec1_9c54_7ba429e13da6
0x100909ac  mov     [ebp+index], 2
0x100909b3  mov     edi, iidCount
0x100909b5  lea     eax, [ebp+index]
0x100909b8  push    iidCount; iids
0x100909b9  push    eax; index
0x100909ba  movsd
0x100909bb  movsd
0x100909bc  movsd
0x100909bd  movsd
0x100909be  mov     esi, offset __GUID_00000038_0000_0000_c000_000000000046
0x100909c3  lea     edi, [iidCount+10h]
0x100909c6  movsd
0x100909c7  movsd
0x100909c8  movsd
0x100909c9  movsd
0x100909ca  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$IIterable@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@Windows@@U?$IVectorView@PAUIXmlNode@Dom@Xml@Data@Windows@@@567@VFtmBase@23@@Details@WRL@Microsoft@@IAEXPAKPAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x100909cf  mov     eax, [ebp+iids]
0x100909d2  mov     dword ptr [ebx], 4
0x100909d8  pop     edi
0x100909d9  pop     esi
0x100909da  mov     [eax], iidCount
0x100909dc  xor     eax, eax
0x100909de  pop     ebx
0x100909df  leave
0x100909e0  retn    4
```
