# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>(void)

- ea: `0x180066de4`
- end: `0x180066ec0`
- name: `??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMFD3D12SynchronizationObjectCommands@@UIMFD3D12SynchronizationObject@@UIMFD3D12SynchronizationObjectCommandsInternal@@UIMFD3D11SynchronizationObjectCommands@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180066ec8`

## callees

- `0x180020598`
- `0x18004a11c`
- `0x180066de4`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180066e21`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180066e21`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>(
        __int64 a1)
{
  __int64 v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)(a1 + 32) = &Microsoft::WRL::FtmBase::`vftable';
  v2 = a1 + 56;
  *(_QWORD *)(a1 + 56) = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  *(_DWORD *)(a1 + 68) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>::`vftable';
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>::`vftable'{for `IMFD3D12SynchronizationObject'};
  *(_QWORD *)(a1 + 16) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>'};
  *(_QWORD *)(a1 + 24) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>::`vftable'{for `IMFD3D11SynchronizationObjectCommands'};
  *(_QWORD *)(a1 + 32) = &MFD3D12Sync::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return a1;
}

```

## disassembly

```asm
0x180066de4  push    rbx
0x180066de6  push    rsi
0x180066de7  push    rdi
0x180066de8  push    r14
0x180066dea  sub     rsp, 28h
0x180066dee  mov     rsi, rcx
0x180066df1  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180066df8  mov     [rcx+20h], rax
0x180066dfc  lea     r14, [rcx+38h]
0x180066e00  mov     qword ptr [r14], 0
0x180066e07  mov     [rsp+48h+ppunkMarshal], 0
0x180066e10  lea     rcx, [rsp+48h+ppunkMarshal]
0x180066e15  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180066e1a  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180066e1f  xor     ecx, ecx; punkOuter
0x180066e21  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180066e27  test    eax, eax
0x180066e29  js      short loc_180066E54
0x180066e2b  mov     rbx, [rsp+48h+ppunkMarshal]
0x180066e30  mov     rax, [rbx]
0x180066e33  mov     rdi, [rax]
0x180066e36  mov     rcx, r14
0x180066e39  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180066e3e  mov     r8, r14
0x180066e41  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180066e48  mov     rcx, rbx
0x180066e4b  mov     rax, rdi
0x180066e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e53  nop
0x180066e54  lea     rcx, [rsp+48h+ppunkMarshal]
0x180066e59  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180066e5e  mov     dword ptr [rsi+44h], 1
0x180066e65  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMFD3D12SynchronizationObjectCommands@@UIMFD3D12SynchronizationObject@@UIMFD3D12SynchronizationObjectCommandsInternal@@UIMFD3D11SynchronizationObjectCommands@@VFtmBase@23@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>::`vftable'
0x180066e6c  mov     [rsi], rax
0x180066e6f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMFD3D12SynchronizationObjectCommands@@UIMFD3D12SynchronizationObject@@UIMFD3D12SynchronizationObjectCommandsInternal@@UIMFD3D11SynchronizationObjectCommands@@VFtmBase@23@@WRL@Microsoft@@6BIMFD3D12SynchronizationObject@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>::`vftable'{for `IMFD3D12SynchronizationObject'}
0x180066e76  mov     [rsi+8], rax
0x180066e7a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMFD3D12SynchronizationObjectCommands@@UIMFD3D12SynchronizationObject@@UIMFD3D12SynchronizationObjectCommandsInternal@@UIMFD3D11SynchronizationObjectCommands@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMFD3D12SynchronizationObjectCommandsInternal@@UIMFD3D11SynchronizationObjectCommands@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>'}
0x180066e81  mov     [rsi+10h], rax
0x180066e85  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMFD3D12SynchronizationObjectCommands@@UIMFD3D12SynchronizationObject@@UIMFD3D12SynchronizationObjectCommandsInternal@@UIMFD3D11SynchronizationObjectCommands@@VFtmBase@23@@WRL@Microsoft@@6BIMFD3D11SynchronizationObjectCommands@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>::`vftable'{for `IMFD3D11SynchronizationObjectCommands'}
0x180066e8c  mov     [rsi+18h], rax
0x180066e90  lea     rax, ??_7MFD3D12Sync@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const MFD3D12Sync::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180066e97  mov     [rsi+20h], rax
0x180066e9b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180066ea2  test    rcx, rcx
0x180066ea5  jz      short loc_180066EB3
0x180066ea7  mov     rax, [rcx]
0x180066eaa  mov     rax, [rax+8]
0x180066eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066eb3  mov     rax, rsi
0x180066eb6  add     rsp, 28h
0x180066eba  pop     r14
0x180066ebc  pop     rdi
0x180066ebd  pop     rsi
0x180066ebe  pop     rbx
0x180066ebf  retn
```
