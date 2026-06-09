# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Media::Streaming::IDeviceControllerFinderHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Media::Streaming::IDeviceControllerFinderHandler,Microsoft::WRL::FtmBase>(void)

- ea: `0x180001750`
- end: `0x18000182f`
- name: `??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDeviceControllerFinderHandler@Streaming@Media@Windows@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ`
- size: `223`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002c00`
- `0x180022124`

## callees

- `0x180001750`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180001783`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180001783`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Media::Streaming::IDeviceControllerFinderHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Media::Streaming::IDeviceControllerFinderHandler,Microsoft::WRL::FtmBase>(
        __int64 a1)
{
  LPUNKNOWN v2; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v4; // rcx
  LPUNKNOWN v5; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::FtmBase::`vftable';
  *(_QWORD *)(a1 + 32) = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v2 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v4 = *(_QWORD *)(a1 + 32);
    if ( v4 )
    {
      *(_QWORD *)(a1 + 32) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64))QueryInterface)(
      v2,
      &GUID_00000003_0000_0000_c000_000000000046,
      a1 + 32);
  }
  v5 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v5->lpVtbl->Release)(v5);
  }
  *(_DWORD *)(a1 + 44) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Media::Streaming::IDeviceControllerFinderHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Media::Streaming::IDeviceControllerFinderHandler'};
  *(_QWORD *)(a1 + 8) = &CDeviceDepartureDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return a1;
}

```

## disassembly

```asm
0x180001750  mov     [rsp+arg_8], rbx
0x180001755  mov     [rsp+arg_10], rbp
0x18000175a  push    rsi
0x18000175b  push    rdi
0x18000175c  push    r14
0x18000175e  sub     rsp, 20h
0x180001762  mov     rdi, rcx
0x180001765  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000176c  mov     [rcx+8], rax
0x180001770  xor     r14d, r14d
0x180001773  mov     [rcx+20h], r14
0x180001777  mov     [rsp+38h+ppunkMarshal], r14
0x18000177c  lea     rdx, [rsp+38h+ppunkMarshal]; ppunkMarshal
0x180001781  xor     ecx, ecx; punkOuter
0x180001783  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180001789  test    eax, eax
0x18000178b  js      short loc_1800017C9
0x18000178d  mov     rbx, [rsp+38h+ppunkMarshal]
0x180001792  mov     rax, [rbx]
0x180001795  mov     rbp, [rax]
0x180001798  mov     rcx, [rdi+20h]
0x18000179c  test    rcx, rcx
0x18000179f  jz      short loc_1800017B2
0x1800017a1  mov     [rdi+20h], r14
0x1800017a5  mov     rdx, [rcx]
0x1800017a8  mov     rax, [rdx+10h]
0x1800017ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017b1  nop
0x1800017b2  lea     r8, [rdi+20h]
0x1800017b6  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800017bd  mov     rcx, rbx
0x1800017c0  mov     rax, rbp
0x1800017c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017c8  nop
0x1800017c9  mov     rcx, [rsp+38h+ppunkMarshal]
0x1800017ce  test    rcx, rcx
0x1800017d1  jz      short loc_1800017E5
0x1800017d3  mov     [rsp+38h+ppunkMarshal], r14
0x1800017d8  mov     rax, [rcx]
0x1800017db  mov     rax, [rax+10h]
0x1800017df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017e4  nop
0x1800017e5  mov     dword ptr [rdi+2Ch], 1
0x1800017ec  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDeviceControllerFinderHandler@Streaming@Media@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIDeviceControllerFinderHandler@Streaming@Media@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Media::Streaming::IDeviceControllerFinderHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Media::Streaming::IDeviceControllerFinderHandler'}
0x1800017f3  mov     [rdi], rax
0x1800017f6  lea     rax, ??_7CDeviceDepartureDelegate@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CDeviceDepartureDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800017fd  mov     [rdi+8], rax
0x180001801  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180001808  test    rcx, rcx
0x18000180b  jz      short loc_180001819
0x18000180d  mov     rax, [rcx]
0x180001810  mov     rax, [rax+8]
0x180001814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001819  mov     rax, rdi
0x18000181c  mov     rbx, [rsp+38h+arg_8]
0x180001821  mov     rbp, [rsp+38h+arg_10]
0x180001826  add     rsp, 20h
0x18000182a  pop     r14
0x18000182c  pop     rdi
0x18000182d  pop     rsi
0x18000182e  retn
```
