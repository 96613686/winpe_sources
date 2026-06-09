# Microsoft::WRL::Details::RuntimeClassBaseT<3>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0>>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0>> *,ulong *,_GUID * *)

- ea: `0x100a0d73`
- end: `0x100a0dce`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$CAsyncOperationBase@U?$IAsyncOperation@PAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PAVXmlDocument@Dom@Xml@Data@Windows@@@23@$0A@@@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KGJPAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$CAsyncOperationBase@U?$IAsyncOperation@PAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PAVXmlDocument@Dom@Xml@Data@Windows@@@23@$0A@@@@123@PAKPAPAU_GUID@@@Z`
- size: `91`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0> > *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x100a24e0`

## callees

- `0x100a0d73`
- `0x100a20ea`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100a0d88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100a0d88`

## pseudocode

```c
HRESULT __userpurge Microsoft::WRL::Details::RuntimeClassBaseT<3>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0>>>@<eax>(
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0> > *iidCount@<edx>,
        _GUID **iids,
        _GUID **implements)
{
  _GUID *v4; // eax
  Microsoft::WRL::Implements<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > *v5; // ecx
  unsigned int v7; // edx
  unsigned int *v8; // edi
  unsigned int index; // [esp+8h] [ebp-4h] BYREF

  *iids = 0;
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Microsoft::WRL::Details::ImplementsMarker<CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0> >,IWeakReferenceSource>::Microsoft::WRL::Details::Selector<CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Microsoft::WRL::Details::ImplementsMarker<CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0> >,IWeakReferenceSource> >::CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0>::Microsoft::WRL::Implements<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > >::Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>::Windows::Foundation::IAsyncOperation_impl<Windows::Foundation::Internal::AggregateType<Windows::Data::Xml::Dom::XmlDocument *,Windows::Data::Xml::Dom::IXmlDocument *> >::IInspectable::IUnknown::__vftable = 0;
  v4 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v4 )
    return -2147024882;
  index = 0;
  Microsoft::WRL::Implements<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(
    v5,
    &index,
    v4);
  v8 = (unsigned int *)(v7 + 16 * index);
  *v8++ = _GUID_00000038_0000_0000_c000_000000000046.Data1;
  *v8++ = *(_DWORD *)&_GUID_00000038_0000_0000_c000_000000000046.Data2;
  *v8 = *(_DWORD *)_GUID_00000038_0000_0000_c000_000000000046.Data4;
  v8[1] = *(_DWORD *)&_GUID_00000038_0000_0000_c000_000000000046.Data4[4];
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Microsoft::WRL::Details::ImplementsMarker<CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0> >,IWeakReferenceSource>::Microsoft::WRL::Details::Selector<CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Microsoft::WRL::Details::ImplementsMarker<CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0> >,IWeakReferenceSource> >::CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0>::Microsoft::WRL::Implements<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > >::Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>::Windows::Foundation::IAsyncOperation_impl<Windows::Foundation::Internal::AggregateType<Windows::Data::Xml::Dom::XmlDocument *,Windows::Data::Xml::Dom::IXmlDocument *> >::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0> >_vtbl *)3;
  *iids = (_GUID *)v7;
  return 0;
}

```

## disassembly

```asm
0x100a0d73  mov     edi, edi
0x100a0d75  push    ebp
0x100a0d76  mov     ebp, esp
0x100a0d78  push    ecx
0x100a0d79  mov     eax, [ebp+iids]
0x100a0d7c  push    ebx
0x100a0d7d  push    esi
0x100a0d7e  mov     ebx, iidCount
0x100a0d80  xor     esi, esi
0x100a0d82  mov     [eax], esi
0x100a0d84  push    30h ; '0'; cb
0x100a0d86  mov     [ebx], esi
0x100a0d88  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x100a0d8e  mov     iidCount, eax
0x100a0d90  test    iidCount, iidCount
0x100a0d92  jnz     short loc_100A0D9B
0x100a0d94  mov     eax, 8007000Eh
0x100a0d99  jmp     short loc_100A0DC8
0x100a0d9b  push    edi
0x100a0d9c  push    iidCount; iids
0x100a0d9d  lea     eax, [ebp+index]
0x100a0da0  mov     [ebp+index], esi
0x100a0da3  push    eax; index
0x100a0da4  call    ?FillArrayWithIid@?$Implements@U?$IAsyncOperation@PAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@V?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@$00U?$AsyncCausalityOptions@$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@3@@WRL@Microsoft@@IAEXPAKPAU_GUID@@@Z; Microsoft::WRL::Implements<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(ulong *,_GUID *)
0x100a0da9  mov     edi, [ebp+index]
0x100a0dac  mov     esi, offset __GUID_00000038_0000_0000_c000_000000000046
0x100a0db1  mov     eax, [ebp+iids]
0x100a0db4  shl     edi, 4
0x100a0db7  add     edi, iidCount
0x100a0db9  movsd
0x100a0dba  movsd
0x100a0dbb  movsd
0x100a0dbc  movsd
0x100a0dbd  mov     dword ptr [ebx], 3
0x100a0dc3  mov     [eax], iidCount
0x100a0dc5  xor     eax, eax
0x100a0dc7  pop     edi
0x100a0dc8  pop     esi
0x100a0dc9  pop     ebx
0x100a0dca  leave
0x100a0dcb  retn    4
```
