# RegistryKeyWatcher::~RegistryKeyWatcher(void)

- ea: `0x18001f4cc`
- end: `0x18001f565`
- name: `??1RegistryKeyWatcher@@UEAA@XZ`
- size: `153`
- prototype: `void __fastcall(RegistryKeyWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f490`

## callees

- `0x18001f4cc`
- `0x18001f56c`
- `0x18001f5c8`
- `0x18001f5e0`
- `0x180075618`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f51f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f51f`

## pseudocode

```c
void __fastcall RegistryKeyWatcher::~RegistryKeyWatcher(RegistryKeyWatcher *this)
{
  bool v1; // zf
  __int64 v3; // rcx

  v1 = *((_QWORD *)this + 7) == 0;
  *(_QWORD *)this = &RegistryKeyWatcher::`vftable';
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IUnknown>::`vftable'{for `IUnknown'};
  *((_QWORD *)this + 2) = &RegistryKeyWatcher::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  if ( !v1 || *((_QWORD *)this + 8) )
    RegistryKeyWatcher::Shutdown(this);
  std::_Func_class<void,>::_Tidy((char *)this + 136);
  v3 = *((_QWORD *)this + 16);
  if ( v3 )
  {
    *((_QWORD *)this + 16) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  *((_QWORD *)this + 9) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close((char *)this + 72);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IUnknown>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IUnknown>(this);
}

```

## disassembly

```asm
0x18001f4cc  push    rbx
0x18001f4ce  sub     rsp, 20h
0x18001f4d2  cmp     qword ptr [rcx+38h], 0
0x18001f4d7  lea     rax, ??_7RegistryKeyWatcher@@6B@; const RegistryKeyWatcher::`vftable'
0x18001f4de  mov     [rcx], rax
0x18001f4e1  mov     rbx, rcx
0x18001f4e4  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6BIUnknown@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IUnknown>::`vftable'{for `IUnknown'}
0x18001f4eb  mov     [rcx+8], rax
0x18001f4ef  lea     rax, ??_7RegistryKeyWatcher@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const RegistryKeyWatcher::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x18001f4f6  mov     [rcx+10h], rax
0x18001f4fa  jnz     short loc_18001F545
0x18001f4fc  cmp     qword ptr [rcx+40h], 0
0x18001f501  jnz     short loc_18001F545
0x18001f503  lea     rcx, [rbx+88h]
0x18001f50a  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18001f50f  mov     rcx, [rbx+80h]
0x18001f516  test    rcx, rcx
0x18001f519  jnz     short loc_18001F54C
0x18001f51b  lea     rcx, [rbx+58h]; lpCriticalSection
0x18001f51f  call    cs:__imp_DeleteCriticalSection
0x18001f525  lea     rcx, [rbx+48h]
0x18001f529  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18001f530  mov     [rcx], rax
0x18001f533  call    ?Close@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(void)
0x18001f538  mov     rcx, rbx; this
0x18001f53b  add     rsp, 20h
0x18001f53f  pop     rbx
0x18001f540  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IUnknown>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IUnknown>(void)
0x18001f545  call    ?Shutdown@RegistryKeyWatcher@@QEAAXXZ; RegistryKeyWatcher::Shutdown(void)
0x18001f54a  jmp     short loc_18001F503
0x18001f54c  mov     qword ptr [rbx+80h], 0
0x18001f557  mov     rax, [rcx]
0x18001f55a  mov     rax, [rax+10h]
0x18001f55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f563  jmp     short loc_18001F51B
```
