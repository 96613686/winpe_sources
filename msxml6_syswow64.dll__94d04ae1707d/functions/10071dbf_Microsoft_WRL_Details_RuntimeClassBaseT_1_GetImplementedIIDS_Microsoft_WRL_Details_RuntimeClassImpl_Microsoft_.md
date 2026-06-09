# Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlLoadSettings,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlLoadSettings,Microsoft::WRL::FtmBase> *,ulong *,_GUID * *)

- ea: `0x10071dbf`
- end: `0x10071e10`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIXmlLoadSettings@Dom@Xml@Data@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KGJPAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIXmlLoadSettings@Dom@Xml@Data@Windows@@VFtmBase@23@@123@PAKPAPAU_GUID@@@Z`
- size: `81`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Dom::IXmlLoadSettings,Microsoft::WRL::FtmBase> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10073570`

## callees

- `0x10071dbf`
- `0x10073262`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10071ddb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10071ddb`

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
0x10071dbf  mov     edi, edi
0x10071dc1  push    ebp
0x10071dc2  mov     ebp, esp
0x10071dc4  push    ecx
0x10071dc5  push    ebx
0x10071dc6  mov     ebx, [ebp+iids]
0x10071dc9  push    esi
0x10071dca  push    edi
0x10071dcb  mov     edi, iidCount
0x10071dcd  mov     dword ptr [ebx], 0
0x10071dd3  push    20h ; ' '; cb
0x10071dd5  mov     dword ptr [edi], 0
0x10071ddb  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10071de1  mov     esi, eax
0x10071de3  test    esi, esi
0x10071de5  jnz     short loc_10071DEE
0x10071de7  mov     eax, 8007000Eh
0x10071dec  jmp     short loc_10071E09
0x10071dee  push    esi; iids
0x10071def  lea     eax, [ebp+index]
0x10071df2  mov     [ebp+index], 0
0x10071df9  push    eax; index
0x10071dfa  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIXmlLoadSettings@Dom@Xml@Data@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IAEXPAKPAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Data::Xml::Dom::IXmlLoadSettings,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x10071dff  mov     dword ptr [edi], 2
0x10071e05  xor     eax, eax
0x10071e07  mov     [ebx], esi
0x10071e09  pop     edi
0x10071e0a  pop     esi
0x10071e0b  pop     ebx
0x10071e0c  leave
0x10071e0d  retn    4
```
