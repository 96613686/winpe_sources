# Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase> *,ulong *,_GUID * *)

- ea: `0x10090921`
- end: `0x10090972`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KGJPAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@Windows@@VFtmBase@23@@123@PAKPAPAU_GUID@@@Z`
- size: `81`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10092240`

## callees

- `0x10090921`
- `0x10091e39`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1009093d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1009093d`

## pseudocode

```c
HRESULT __userpurge Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>>@<eax>(
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase> *iidCount@<edx>,
        _GUID **iids,
        _GUID **implements)
{
  _GUID *v4; // eax
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,IWeakReferenceSource,Microsoft::WRL::FtmBase> *v5; // ecx
  unsigned int v6; // esi
  HRESULT result; // eax
  unsigned int index; // [esp+Ch] [ebp-4h] BYREF

  *iids = 0;
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>::Windows::Foundation::Collections::IIterator_impl<Windows::Data::Xml::Dom::IXmlNode *,1>::IInspectable::IUnknown::__vftable = 0;
  v4 = (_GUID *)CoTaskMemAlloc(0x20u);
  v6 = (unsigned int)v4;
  if ( !v4 )
    return -2147024882;
  index = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &index,
    v4);
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>::Windows::Foundation::Collections::IIterator_impl<Windows::Data::Xml::Dom::IXmlNode *,1>::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>_vtbl *)2;
  result = 0;
  *iids = (_GUID *)v6;
  return result;
}

```

## disassembly

```asm
0x10090921  mov     edi, edi
0x10090923  push    ebp
0x10090924  mov     ebp, esp
0x10090926  push    ecx
0x10090927  push    ebx
0x10090928  mov     ebx, [ebp+iids]
0x1009092b  push    esi
0x1009092c  push    edi
0x1009092d  mov     edi, iidCount
0x1009092f  mov     dword ptr [ebx], 0
0x10090935  push    20h ; ' '; cb
0x10090937  mov     dword ptr [edi], 0
0x1009093d  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10090943  mov     esi, eax
0x10090945  test    esi, esi
0x10090947  jnz     short loc_10090950
0x10090949  mov     eax, 8007000Eh
0x1009094e  jmp     short loc_1009096B
0x10090950  push    esi; iids
0x10090951  lea     eax, [ebp+index]
0x10090954  mov     [ebp+index], 0
0x1009095b  push    eax; index
0x1009095c  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$IIterator@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IAEXPAKPAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x10090961  mov     dword ptr [edi], 2
0x10090967  xor     eax, eax
0x10090969  mov     [ebx], esi
0x1009096b  pop     edi
0x1009096c  pop     esi
0x1009096d  pop     ebx
0x1009096e  leave
0x1009096f  retn    4
```
