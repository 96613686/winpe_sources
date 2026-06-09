# Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlLoadSettings,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlLoadSettings,Microsoft::WRL::FtmBase> *,ulong *,_GUID * *)

- ea: `0x10071d1f`
- end: `0x10071d70`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIXmlLoadSettings@Dom@Xml@Data@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KGJPAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIXmlLoadSettings@Dom@Xml@Data@Windows@@VFtmBase@23@@123@PAKPAPAU_GUID@@@Z`
- size: `81`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlLoadSettings,Microsoft::WRL::FtmBase> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x100735a0`

## callees

- `0x10071d1f`
- `0x10073292`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10071d3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10071d3b`

## pseudocode

```c
HRESULT __userpurge Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlLoadSettings,Microsoft::WRL::FtmBase>>@<eax>(
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlLoadSettings,Microsoft::WRL::FtmBase> *iidCount@<edx>,
        _GUID **iids,
        _GUID **implements)
{
  _GUID *v4; // eax
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Data::Xml::Dom::IXmlLoadSettings,IWeakReferenceSource,Microsoft::WRL::FtmBase> *v5; // ecx
  unsigned int v6; // esi
  HRESULT result; // eax
  unsigned int index; // [esp+Ch] [ebp-4h] BYREF

  *iids = 0;
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Data::Xml::Dom::IXmlLoadSettings,IWeakReferenceSource,Microsoft::WRL::FtmBase>::Windows::Data::Xml::Dom::IXmlLoadSettings::IInspectable::IUnknown::__vftable = 0;
  v4 = (_GUID *)CoTaskMemAlloc(0x20u);
  v6 = (unsigned int)v4;
  if ( !v4 )
    return -2147024882;
  index = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Data::Xml::Dom::IXmlLoadSettings,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &index,
    v4);
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Data::Xml::Dom::IXmlLoadSettings,IWeakReferenceSource,Microsoft::WRL::FtmBase>::Windows::Data::Xml::Dom::IXmlLoadSettings::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlLoadSettings,Microsoft::WRL::FtmBase>_vtbl *)2;
  result = 0;
  *iids = (_GUID *)v6;
  return result;
}

```

## disassembly

```asm
0x10071d1f  mov     edi, edi
0x10071d21  push    ebp
0x10071d22  mov     ebp, esp
0x10071d24  push    ecx
0x10071d25  push    ebx
0x10071d26  mov     ebx, [ebp+iids]
0x10071d29  push    esi
0x10071d2a  push    edi
0x10071d2b  mov     edi, iidCount
0x10071d2d  mov     dword ptr [ebx], 0
0x10071d33  push    20h ; ' '; cb
0x10071d35  mov     dword ptr [edi], 0
0x10071d3b  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10071d41  mov     esi, eax
0x10071d43  test    esi, esi
0x10071d45  jnz     short loc_10071D4E
0x10071d47  mov     eax, 8007000Eh
0x10071d4c  jmp     short loc_10071D69
0x10071d4e  push    esi; iids
0x10071d4f  lea     eax, [ebp+index]
0x10071d52  mov     [ebp+index], 0
0x10071d59  push    eax; index
0x10071d5a  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIXmlLoadSettings@Dom@Xml@Data@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IAEXPAKPAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Data::Xml::Dom::IXmlLoadSettings,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x10071d5f  mov     dword ptr [edi], 2
0x10071d65  xor     eax, eax
0x10071d67  mov     [ebx], esi
0x10071d69  pop     edi
0x10071d6a  pop     esi
0x10071d6b  pop     ebx
0x10071d6c  leave
0x10071d6d  retn    4
```
