# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>(void)

- ea: `0x180016864`
- end: `0x18001696a`
- name: `??0?$RuntimeClass@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ`
- size: `262`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013a04`
- `0x18002e2c8`

## callees

- `0x180016864`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800168a1`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800168a1`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>(
        _QWORD *a1)
{
  __int64 *v2; // rsi
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v5; // rcx
  LPUNKNOWN v6; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  a1[2] = &Windows::Storage::Streams::IBufferByteAccess::`vftable';
  a1[4] = &Microsoft::WRL::FtmBase::`vftable';
  v2 = a1 + 7;
  a1[7] = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v5 = *v2;
    if ( *v2 )
    {
      *v2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64 *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  v6 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v6->lpVtbl->Release)(v6);
  }
  a1[9] = 1;
  *a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::`vftable';
  a1[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
  a1[2] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>'};
  a1[3] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,IMarshal>'};
  a1[4] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return a1;
}

```

## disassembly

```asm
0x180016864  push    rbx
0x180016866  push    rbp
0x180016867  push    rsi
0x180016868  push    rdi
0x180016869  sub     rsp, 28h
0x18001686d  mov     rdi, rcx
0x180016870  lea     rax, ??_7IBufferByteAccess@Streams@Storage@Windows@@6B@; const Windows::Storage::Streams::IBufferByteAccess::`vftable'
0x180016877  mov     [rcx+10h], rax
0x18001687b  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180016882  mov     [rcx+20h], rax
0x180016886  lea     rsi, [rcx+38h]
0x18001688a  mov     qword ptr [rsi], 0
0x180016891  mov     [rsp+48h+ppunkMarshal], 0
0x18001689a  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18001689f  xor     ecx, ecx; punkOuter
0x1800168a1  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800168a7  test    eax, eax
0x1800168a9  js      short loc_1800168E8
0x1800168ab  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800168b0  mov     rax, [rbx]
0x1800168b3  mov     rbp, [rax]
0x1800168b6  mov     rcx, [rsi]
0x1800168b9  test    rcx, rcx
0x1800168bc  jz      short loc_1800168D2
0x1800168be  mov     qword ptr [rsi], 0
0x1800168c5  mov     rdx, [rcx]
0x1800168c8  mov     rax, [rdx+10h]
0x1800168cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168d1  nop
0x1800168d2  mov     r8, rsi
0x1800168d5  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800168dc  mov     rcx, rbx
0x1800168df  mov     rax, rbp
0x1800168e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168e7  nop
0x1800168e8  mov     rcx, [rsp+48h+ppunkMarshal]
0x1800168ed  test    rcx, rcx
0x1800168f0  jz      short loc_180016908
0x1800168f2  mov     [rsp+48h+ppunkMarshal], 0
0x1800168fb  mov     rax, [rcx]
0x1800168fe  mov     rax, [rax+10h]
0x180016902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016907  nop
0x180016908  mov     qword ptr [rdi+48h], 1
0x180016910  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::`vftable'
0x180016917  mov     [rdi], rax
0x18001691a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x180016921  mov     [rdi+8], rax
0x180016925  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>'}
0x18001692c  mov     [rdi+10h], rax
0x180016930  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00UIMarshal@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,IMarshal>'}
0x180016937  mov     [rdi+18h], rax
0x18001693b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180016942  mov     [rdi+20h], rax
0x180016946  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001694d  test    rcx, rcx
0x180016950  jz      short loc_18001695E
0x180016952  mov     rax, [rcx]
0x180016955  mov     rax, [rax+8]
0x180016959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001695e  mov     rax, rdi
0x180016961  add     rsp, 28h
0x180016965  pop     rdi
0x180016966  pop     rsi
0x180016967  pop     rbp
0x180016968  pop     rbx
0x180016969  retn
```
