# wil::details::BufferOverFlatBuffer::BufferOverFlatBuffer(void)

- ea: `0x1800442ac`
- end: `0x180044429`
- name: `??0BufferOverFlatBuffer@details@wil@@QEAA@XZ`
- size: `381`
- prototype: `__int64 __fastcall(wil::details::BufferOverFlatBuffer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003abd4`

## callees

- `0x1800442ac`
- `0x180061010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800442ec`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800442ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
wil::details::BufferOverFlatBuffer *__fastcall wil::details::BufferOverFlatBuffer::BufferOverFlatBuffer(
        wil::details::BufferOverFlatBuffer *this)
{
  __int64 *v2; // rsi
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v5; // rcx
  LPUNKNOWN v6; // rcx
  LPUNKNOWN v8; // [rsp+40h] [rbp+8h] BYREF

  *((_QWORD *)this + 2) = &winrt::impl::producers_base<PluginUtils::PluginProxyOps,std::tuple<IPluginAuthenticatorInitializer,IPluginAuthenticator>>::`vftable'{for `winrt::impl::producer_convert<PluginUtils::PluginProxyOps,IPluginAuthenticatorInitializer,void>'};
  *((_QWORD *)this + 3) = &Microsoft::WRL::FtmBase::`vftable';
  v2 = (__int64 *)((char *)this + 48);
  *((_QWORD *)this + 6) = 0;
  v8 = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &v8) >= 0 )
  {
    v3 = v8;
    QueryInterface = v8->lpVtbl->QueryInterface;
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
  v6 = v8;
  if ( v8 )
  {
    v8 = 0;
    ((void (__fastcall *)(LPUNKNOWN))v6->lpVtbl->Release)(v6);
  }
  *((_QWORD *)this + 8) = 1;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Storage::Streams::IBuffer'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Storage::Streams::IBufferByteAccess'};
  *((_QWORD *)this + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &wil::details::BufferOverFlatBuffer::`vftable'{for `Windows::Storage::Streams::IBuffer'};
  *((_QWORD *)this + 1) = &wil::details::BufferOverFlatBuffer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &wil::details::BufferOverFlatBuffer::`vftable'{for `Windows::Storage::Streams::IBufferByteAccess'};
  *((_QWORD *)this + 3) = &wil::details::BufferOverFlatBuffer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 9) = 0;
  *((_BYTE *)this + 80) = 0;
  *((_QWORD *)this + 11) = 1024;
  *((_QWORD *)this + 12) = 8;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 1;
  *((_WORD *)this + 80) = 256;
  *((_QWORD *)this + 21) = 0;
  return this;
}

```

## disassembly

```asm
0x1800442ac  mov     r11, rsp
0x1800442af  mov     [r11+10h], rbx
0x1800442b3  mov     [r11+18h], rbp
0x1800442b7  push    rsi
0x1800442b8  push    rdi
0x1800442b9  push    r14
0x1800442bb  sub     rsp, 20h
0x1800442bf  mov     rdi, rcx
0x1800442c2  lea     rax, ??_7?$producers_base@UPluginProxyOps@PluginUtils@@V?$tuple@UIPluginAuthenticatorInitializer@@UIPluginAuthenticator@@@std@@@impl@winrt@@6B?$producer_convert@UPluginProxyOps@PluginUtils@@UIPluginAuthenticatorInitializer@@X@12@@; const winrt::impl::producers_base<PluginUtils::PluginProxyOps,std::tuple<IPluginAuthenticatorInitializer,IPluginAuthenticator>>::`vftable'{for `winrt::impl::producer_convert<PluginUtils::PluginProxyOps,IPluginAuthenticatorInitializer,void>'}
0x1800442c9  mov     [rcx+10h], rax
0x1800442cd  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800442d4  mov     [rcx+18h], rax
0x1800442d8  lea     rsi, [rcx+30h]
0x1800442dc  xor     r14d, r14d
0x1800442df  mov     [rsi], r14
0x1800442e2  mov     [r11+8], r14
0x1800442e6  lea     rdx, [r11+8]; ppunkMarshal
0x1800442ea  xor     ecx, ecx; punkOuter
0x1800442ec  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800442f2  test    eax, eax
0x1800442f4  js      short loc_18004432F
0x1800442f6  mov     rbx, [rsp+38h+arg_0]
0x1800442fb  mov     rax, [rbx]
0x1800442fe  mov     rbp, [rax]
0x180044301  mov     rcx, [rsi]
0x180044304  test    rcx, rcx
0x180044307  jz      short loc_180044319
0x180044309  mov     [rsi], r14
0x18004430c  mov     rdx, [rcx]
0x18004430f  mov     rax, [rdx+10h]
0x180044313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044318  nop
0x180044319  mov     r8, rsi
0x18004431c  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180044323  mov     rcx, rbx
0x180044326  mov     rax, rbp
0x180044329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004432e  nop
0x18004432f  mov     rcx, [rsp+38h+arg_0]
0x180044334  test    rcx, rcx
0x180044337  jz      short loc_18004434B
0x180044339  mov     [rsp+38h+arg_0], r14
0x18004433e  mov     rax, [rcx]
0x180044341  mov     rax, [rax+10h]
0x180044345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004434a  nop
0x18004434b  mov     ebx, 1
0x180044350  mov     [rdi+40h], rbx
0x180044354  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIBuffer@Streams@Storage@Windows@@UIBufferByteAccess@567@VFtmBase@23@@WRL@Microsoft@@6BIBuffer@Streams@Storage@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Storage::Streams::IBuffer'}
0x18004435b  mov     [rdi], rax
0x18004435e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIBuffer@Streams@Storage@Windows@@UIBufferByteAccess@567@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIBufferByteAccess@Streams@Storage@Windows@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>'}
0x180044365  mov     [rdi+8], rax
0x180044369  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIBuffer@Streams@Storage@Windows@@UIBufferByteAccess@567@VFtmBase@23@@WRL@Microsoft@@6BIBufferByteAccess@Streams@Storage@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Storage::Streams::IBufferByteAccess'}
0x180044370  mov     [rdi+10h], rax
0x180044374  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIBuffer@Streams@Storage@Windows@@UIBufferByteAccess@567@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004437b  mov     [rdi+18h], rax
0x18004437f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180044386  test    rcx, rcx
0x180044389  jz      short loc_180044398
0x18004438b  mov     rax, [rcx]
0x18004438e  mov     rax, [rax+8]
0x180044392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044397  nop
0x180044398  lea     rax, ??_7BufferOverFlatBuffer@details@wil@@6BIBuffer@Streams@Storage@Windows@@@; const wil::details::BufferOverFlatBuffer::`vftable'{for `Windows::Storage::Streams::IBuffer'}
0x18004439f  mov     [rdi], rax
0x1800443a2  lea     rax, ??_7BufferOverFlatBuffer@details@wil@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIBufferByteAccess@Streams@Storage@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@; const wil::details::BufferOverFlatBuffer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>'}
0x1800443a9  mov     [rdi+8], rax
0x1800443ad  lea     rax, ??_7BufferOverFlatBuffer@details@wil@@6BIBufferByteAccess@Streams@Storage@Windows@@@; const wil::details::BufferOverFlatBuffer::`vftable'{for `Windows::Storage::Streams::IBufferByteAccess'}
0x1800443b4  mov     [rdi+10h], rax
0x1800443b8  lea     rax, ??_7BufferOverFlatBuffer@details@wil@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const wil::details::BufferOverFlatBuffer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800443bf  mov     [rdi+18h], rax
0x1800443c3  mov     [rdi+48h], r14
0x1800443c7  mov     [rdi+50h], r14b
0x1800443cb  mov     qword ptr [rdi+58h], 400h
0x1800443d3  mov     qword ptr [rdi+60h], 8
0x1800443db  mov     [rdi+68h], r14
0x1800443df  mov     [rdi+70h], r14d
0x1800443e3  mov     [rdi+78h], r14
0x1800443e7  mov     [rdi+80h], r14
0x1800443ee  mov     [rdi+88h], r14
0x1800443f5  mov     [rdi+90h], r14
0x1800443fc  mov     [rdi+98h], rbx
0x180044403  mov     word ptr [rdi+0A0h], 100h
0x18004440c  mov     [rdi+0A8h], r14
0x180044413  mov     rax, rdi
0x180044416  mov     rbx, [rsp+38h+arg_8]
0x18004441b  mov     rbp, [rsp+38h+arg_10]
0x180044420  add     rsp, 20h
0x180044424  pop     r14
0x180044426  pop     rdi
0x180044427  pop     rsi
0x180044428  retn
```
