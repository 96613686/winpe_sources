# Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Xsl::IXsltProcessor,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Xsl::IXsltProcessor,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase> *,ulong *,_GUID * *)

- ea: `0x10071d76`
- end: `0x10071dd5`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIXsltProcessor@Xsl@Xml@Data@Windows@@UIXsltProcessor2@5678@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KGJPAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIXsltProcessor@Xsl@Xml@Data@Windows@@UIXsltProcessor2@5678@VFtmBase@23@@123@PAKPAPAU_GUID@@@Z`
- size: `95`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Xsl::IXsltProcessor,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase> *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x100735c0`

## callees

- `0x10071d76`
- `0x10073205`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10071d90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10071d90`

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
0x10071d76  mov     edi, edi
0x10071d78  push    ebp
0x10071d79  mov     ebp, esp
0x10071d7b  push    ecx
0x10071d7c  mov     eax, [ebp+iids]
0x10071d7f  push    ebx
0x10071d80  mov     ebx, iidCount
0x10071d82  push    30h ; '0'; cb
0x10071d84  mov     dword ptr [eax], 0
0x10071d8a  mov     dword ptr [ebx], 0
0x10071d90  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10071d96  mov     iidCount, eax
0x10071d98  test    iidCount, iidCount
0x10071d9a  jnz     short loc_10071DA3
0x10071d9c  mov     eax, 8007000Eh
0x10071da1  jmp     short loc_10071DD0
0x10071da3  push    esi
0x10071da4  push    edi
0x10071da5  mov     esi, offset __GUID_7b64703f_550c_48c6_a90f_93a5b964518f
0x10071daa  mov     [ebp+index], 1
0x10071db1  mov     edi, iidCount
0x10071db3  lea     eax, [ebp+index]
0x10071db6  push    iidCount; iids
0x10071db7  push    eax; index
0x10071db8  movsd
0x10071db9  movsd
0x10071dba  movsd
0x10071dbb  movsd
0x10071dbc  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIXsltProcessor2@Xsl@Xml@Data@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IAEXPAKPAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x10071dc1  mov     eax, [ebp+iids]
0x10071dc4  mov     dword ptr [ebx], 3
0x10071dca  pop     edi
0x10071dcb  pop     esi
0x10071dcc  mov     [eax], iidCount
0x10071dce  xor     eax, eax
0x10071dd0  pop     ebx
0x10071dd1  leave
0x10071dd2  retn    4
```
