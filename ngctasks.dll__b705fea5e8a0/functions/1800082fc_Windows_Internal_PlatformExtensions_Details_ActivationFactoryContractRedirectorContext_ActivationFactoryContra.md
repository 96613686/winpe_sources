# Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext::ActivationFactoryContractRedirectorContext(void)

- ea: `0x1800082fc`
- end: `0x18000839a`
- name: `??0ActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ`
- size: `158`
- prototype: `Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext *__fastcall(Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800076a4`

## callees

- `0x1800082fc`
- `0x1800083a0`
- `0x180022010`

## pseudocode

```c
Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext *__fastcall Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext::ActivationFactoryContractRedirectorContext(
        Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext *this)
{
  _QWORD *v2; // rdi

  v2 = (_QWORD *)((char *)this + 8);
  Microsoft::WRL::FtmBase::FtmBase((Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext *)((char *)this + 16));
  *((_QWORD *)this + 7) = 1;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::`vftable';
  *v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext::`vftable';
  *v2 = &Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 8) = 0;
  return this;
}

```

## disassembly

```asm
0x1800082fc  mov     rax, rsp
0x1800082ff  mov     [rax+20h], rbx
0x180008303  mov     [rax+8], rcx
0x180008307  push    rdi
0x180008308  sub     rsp, 20h
0x18000830c  mov     rbx, rcx
0x18000830f  lea     rdi, [rcx+8]
0x180008313  mov     [rax+10h], rdi
0x180008317  lea     rcx, [rdi+8]; this
0x18000831b  mov     [rax+18h], rcx
0x18000831f  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180008324  nop
0x180008325  mov     qword ptr [rbx+38h], 1
0x18000832d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::`vftable'
0x180008334  mov     [rbx], rax
0x180008337  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x18000833e  mov     [rdi], rax
0x180008341  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180008348  mov     [rbx+10h], rax
0x18000834c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180008353  test    rcx, rcx
0x180008356  jz      short loc_180008365
0x180008358  mov     rax, [rcx]
0x18000835b  mov     rax, [rax+8]
0x18000835f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008364  nop
0x180008365  lea     rax, ??_7ActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext::`vftable'
0x18000836c  mov     [rbx], rax
0x18000836f  lea     rax, ??_7ActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@6BIWeakReferenceSource@@@; const Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext::`vftable'{for `IWeakReferenceSource'}
0x180008376  mov     [rdi], rax
0x180008379  lea     rax, ??_7ActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@1WRL@Microsoft@@@; const Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180008380  mov     [rbx+10h], rax
0x180008384  mov     qword ptr [rbx+40h], 0
0x18000838c  mov     rax, rbx
0x18000838f  mov     rbx, [rsp+28h+arg_18]
0x180008394  add     rsp, 20h
0x180008398  pop     rdi
0x180008399  retn
```
