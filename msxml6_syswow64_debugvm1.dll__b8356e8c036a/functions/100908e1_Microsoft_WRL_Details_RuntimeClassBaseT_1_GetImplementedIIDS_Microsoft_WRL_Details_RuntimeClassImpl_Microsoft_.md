# Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase> *,ulong *,_GUID * *)

- ea: `0x100908e1`
- end: `0x10090932`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KGJPAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@Windows@@VFtmBase@23@@123@PAKPAPAU_GUID@@@Z`
- size: `81`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10092180`

## callees

- `0x100908e1`
- `0x10091d79`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100908fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100908fd`

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
0x100908e1  mov     edi, edi
0x100908e3  push    ebp
0x100908e4  mov     ebp, esp
0x100908e6  push    ecx
0x100908e7  push    ebx
0x100908e8  mov     ebx, [ebp+iids]
0x100908eb  push    esi
0x100908ec  push    edi
0x100908ed  mov     edi, iidCount
0x100908ef  mov     dword ptr [ebx], 0
0x100908f5  push    20h ; ' '; cb
0x100908f7  mov     dword ptr [edi], 0
0x100908fd  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10090903  mov     esi, eax
0x10090905  test    esi, esi
0x10090907  jnz     short loc_10090910
0x10090909  mov     eax, 8007000Eh
0x1009090e  jmp     short loc_1009092B
0x10090910  push    esi; iids
0x10090911  lea     eax, [ebp+index]
0x10090914  mov     [ebp+index], 0
0x1009091b  push    eax; index
0x1009091c  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$IIterator@PAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IAEXPAKPAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x10090921  mov     dword ptr [edi], 2
0x10090927  xor     eax, eax
0x10090929  mov     [ebx], esi
0x1009092b  pop     edi
0x1009092c  pop     esi
0x1009092d  pop     ebx
0x1009092e  leave
0x1009092f  retn    4
```
