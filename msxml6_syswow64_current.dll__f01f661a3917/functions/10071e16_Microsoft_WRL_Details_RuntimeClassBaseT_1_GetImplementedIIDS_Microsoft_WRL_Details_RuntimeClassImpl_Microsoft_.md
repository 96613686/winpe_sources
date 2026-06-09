# Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Xsl::IXsltProcessor,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Xsl::IXsltProcessor,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase> *,ulong *,_GUID * *)

- ea: `0x10071e16`
- end: `0x10071e75`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIXsltProcessor@Xsl@Xml@Data@Windows@@UIXsltProcessor2@5678@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KGJPAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIXsltProcessor@Xsl@Xml@Data@Windows@@UIXsltProcessor2@5678@VFtmBase@23@@123@PAKPAPAU_GUID@@@Z`
- size: `95`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Xsl::IXsltProcessor,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10073590`

## callees

- `0x10071e16`
- `0x100731d5`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10071e30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10071e30`

## pseudocode

```c
HRESULT __userpurge Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Xsl::IXsltProcessor,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase>>@<eax>(
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Xsl::IXsltProcessor,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase> *iidCount@<edx>,
        _GUID **iids,
        _GUID **implements)
{
  _GUID *v4; // edx
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase> *v5; // ecx
  unsigned int v7; // edx
  unsigned int index; // [esp+4h] [ebp-4h] BYREF

  *iids = 0;
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Data::Xml::Xsl::IXsltProcessor,IWeakReferenceSource,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase>::Windows::Data::Xml::Xsl::IXsltProcessor::IInspectable::IUnknown::__vftable = 0;
  v4 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v4 )
    return -2147024882;
  index = 1;
  *v4 = _GUID_7b64703f_550c_48c6_a90f_93a5b964518f;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &index,
    v4);
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Data::Xml::Xsl::IXsltProcessor,IWeakReferenceSource,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase>::Windows::Data::Xml::Xsl::IXsltProcessor::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Xsl::IXsltProcessor,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase>_vtbl *)3;
  *iids = (_GUID *)v7;
  return 0;
}

```

## disassembly

```asm
0x10071e16  mov     edi, edi
0x10071e18  push    ebp
0x10071e19  mov     ebp, esp
0x10071e1b  push    ecx
0x10071e1c  mov     eax, [ebp+iids]
0x10071e1f  push    ebx
0x10071e20  mov     ebx, iidCount
0x10071e22  push    30h ; '0'; cb
0x10071e24  mov     dword ptr [eax], 0
0x10071e2a  mov     dword ptr [ebx], 0
0x10071e30  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10071e36  mov     iidCount, eax
0x10071e38  test    iidCount, iidCount
0x10071e3a  jnz     short loc_10071E43
0x10071e3c  mov     eax, 8007000Eh
0x10071e41  jmp     short loc_10071E70
0x10071e43  push    esi
0x10071e44  push    edi
0x10071e45  mov     esi, offset __GUID_7b64703f_550c_48c6_a90f_93a5b964518f
0x10071e4a  mov     [ebp+index], 1
0x10071e51  mov     edi, iidCount
0x10071e53  lea     eax, [ebp+index]
0x10071e56  push    iidCount; iids
0x10071e57  push    eax; index
0x10071e58  movsd
0x10071e59  movsd
0x10071e5a  movsd
0x10071e5b  movsd
0x10071e5c  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIXsltProcessor2@Xsl@Xml@Data@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IAEXPAKPAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x10071e61  mov     eax, [ebp+iids]
0x10071e64  mov     dword ptr [ebx], 3
0x10071e6a  pop     edi
0x10071e6b  pop     esi
0x10071e6c  mov     [eax], iidCount
0x10071e6e  xor     eax, eax
0x10071e70  pop     ebx
0x10071e71  leave
0x10071e72  retn    4
```
