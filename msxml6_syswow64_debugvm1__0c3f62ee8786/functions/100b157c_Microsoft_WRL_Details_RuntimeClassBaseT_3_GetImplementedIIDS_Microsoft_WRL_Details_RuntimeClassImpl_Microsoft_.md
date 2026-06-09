# Microsoft::WRL::Details::RuntimeClassBaseT<3>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&ushort const * const SaveToFileAsyncOperationName>>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&ushort const * const SaveToFileAsyncOperationName>> *,ulong *,_GUID * *)

- ea: `0x100b157c`
- end: `0x100b15d7`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$CAsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$1?SaveToFileAsyncOperationName@@3QBGB@@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KGJPAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$CAsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$1?SaveToFileAsyncOperationName@@3QBGB@@@123@PAKPAPAU_GUID@@@Z`
- size: `91`
- prototype: `HRESULT __userpurge@<eax>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName> > *iidCount@<edx>, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x100b1ec0`

## callees

- `0x100b157c`
- `0x100b1bd5`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100b1591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100b1591`

## pseudocode

```c
HRESULT __userpurge Microsoft::WRL::Details::RuntimeClassBaseT<3>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&unsigned short const * const SaveToFileAsyncOperationName>>>@<eax>(
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName> > *iidCount@<edx>,
        _GUID **iids,
        _GUID **implements)
{
  _GUID *v4; // eax
  Microsoft::WRL::Implements<Windows::Foundation::IAsyncAction,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > *v5; // ecx
  unsigned int v7; // edx
  unsigned int *v8; // edi
  unsigned int index; // [esp+8h] [ebp-4h] BYREF

  *iids = 0;
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Microsoft::WRL::Details::ImplementsMarker<CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName> >,IWeakReferenceSource>::Microsoft::WRL::Details::Selector<CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Microsoft::WRL::Details::ImplementsMarker<CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName> >,IWeakReferenceSource> >::CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName>::Microsoft::WRL::Implements<Windows::Foundation::IAsyncAction,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IAsyncAction,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > >::Windows::Foundation::IAsyncAction::IInspectable::IUnknown::__vftable = 0;
  v4 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v4 )
    return -2147024882;
  index = 0;
  Microsoft::WRL::Implements<Windows::Foundation::IAsyncAction,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(
    v5,
    &index,
    v4);
  v8 = (unsigned int *)(v7 + 16 * index);
  *v8++ = _GUID_00000038_0000_0000_c000_000000000046.Data1;
  *v8++ = *(_DWORD *)&_GUID_00000038_0000_0000_c000_000000000046.Data2;
  *v8 = *(_DWORD *)_GUID_00000038_0000_0000_c000_000000000046.Data4;
  v8[1] = *(_DWORD *)&_GUID_00000038_0000_0000_c000_000000000046.Data4[4];
  iidCount->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Microsoft::WRL::Details::ImplementsMarker<CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName> >,IWeakReferenceSource>::Microsoft::WRL::Details::Selector<CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Microsoft::WRL::Details::ImplementsMarker<CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName> >,IWeakReferenceSource> >::CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName>::Microsoft::WRL::Implements<Windows::Foundation::IAsyncAction,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IAsyncAction,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > >::Windows::Foundation::IAsyncAction::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName> >_vtbl *)3;
  *iids = (_GUID *)v7;
  return 0;
}

```

## disassembly

```asm
0x100b157c  mov     edi, edi
0x100b157e  push    ebp
0x100b157f  mov     ebp, esp
0x100b1581  push    ecx
0x100b1582  mov     eax, [ebp+iids]
0x100b1585  push    ebx
0x100b1586  push    esi
0x100b1587  mov     ebx, iidCount
0x100b1589  xor     esi, esi
0x100b158b  mov     [eax], esi
0x100b158d  push    30h ; '0'; cb
0x100b158f  mov     [ebx], esi
0x100b1591  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x100b1597  mov     iidCount, eax
0x100b1599  test    iidCount, iidCount
0x100b159b  jnz     short loc_100B15A4
0x100b159d  mov     eax, 8007000Eh
0x100b15a2  jmp     short loc_100B15D1
0x100b15a4  push    edi
0x100b15a5  push    iidCount; iids
0x100b15a6  lea     eax, [ebp+index]
0x100b15a9  mov     [ebp+index], esi
0x100b15ac  push    eax; index
0x100b15ad  call    ?FillArrayWithIid@?$Implements@UIAsyncAction@Foundation@Windows@@V?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?SaveToFileAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@3@@WRL@Microsoft@@IAEXPAKPAU_GUID@@@Z; Microsoft::WRL::Implements<Windows::Foundation::IAsyncAction,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(ulong *,_GUID *)
0x100b15b2  mov     edi, [ebp+index]
0x100b15b5  mov     esi, offset __GUID_00000038_0000_0000_c000_000000000046
0x100b15ba  mov     eax, [ebp+iids]
0x100b15bd  shl     edi, 4
0x100b15c0  add     edi, iidCount
0x100b15c2  movsd
0x100b15c3  movsd
0x100b15c4  movsd
0x100b15c5  movsd
0x100b15c6  mov     dword ptr [ebx], 3
0x100b15cc  mov     [eax], iidCount
0x100b15ce  xor     eax, eax
0x100b15d0  pop     edi
0x100b15d1  pop     esi
0x100b15d2  pop     ebx
0x100b15d3  leave
0x100b15d4  retn    4
```
