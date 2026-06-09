# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)

- ea: `0x1800075d0`
- end: `0x18000769e`
- name: `??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z`
- size: `206`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000adb0`

## callees

- `0x180006354`
- `0x1800075d0`
- `0x1800082e8`
- `0x1800087fc`
- `0x18000c590`
- `0x180022010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(
        _QWORD *a1,
        __int64 *a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  __int64 v6; // rsi
  _QWORD *v7; // rcx
  void *v9; // [rsp+60h] [rbp+18h] BYREF
  void *v10; // [rsp+68h] [rbp+20h]

  *a1 = 0;
  v9 = 0;
  v4 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  v9 = v4;
  if ( v4 )
  {
    v10 = v4;
    v6 = *a2;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(v4);
    *v7 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v5[4] = 0x3FFFFFFF;
    *(_QWORD *)v5 = &Microsoft::WRL::Details::WeakReferenceImpl::`vftable';
    *((_QWORD *)v5 + 3) = v6;
    v5[3] = 2;
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(*a1);
    *a1 = v5;
    v9 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext>::~MakeAllocator<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext>(&v9);
  return a1;
}

```

## disassembly

```asm
0x1800075d0  mov     rax, rsp
0x1800075d3  mov     [rax+8], rcx
0x1800075d7  push    rbx
0x1800075d8  push    rsi
0x1800075d9  push    rdi
0x1800075da  sub     rsp, 30h
0x1800075de  mov     rsi, rdx
0x1800075e1  mov     rdi, rcx
0x1800075e4  mov     dword ptr [rax-28h], 0
0x1800075eb  mov     qword ptr [rcx], 0
0x1800075f2  mov     dword ptr [rax-28h], 1
0x1800075f9  mov     qword ptr [rax+18h], 0
0x180007601  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007608  mov     ecx, 20h ; ' '; unsigned __int64
0x18000760d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007612  mov     rbx, rax
0x180007615  mov     [rsp+48h+arg_10], rax
0x18000761a  test    rax, rax
0x18000761d  jz      short loc_180007688
0x18000761f  mov     [rsp+48h+arg_18], rax
0x180007624  mov     rsi, [rsi]
0x180007627  mov     rcx, rax
0x18000762a  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(void)
0x18000762f  nop
0x180007630  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x180007637  mov     [rcx], rax
0x18000763a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007641  test    rcx, rcx
0x180007644  jz      short loc_180007653
0x180007646  mov     rax, [rcx]
0x180007649  mov     rax, [rax+8]
0x18000764d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007652  nop
0x180007653  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x18000765a  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x180007661  mov     [rbx], rax
0x180007664  mov     [rbx+18h], rsi
0x180007668  mov     dword ptr [rbx+0Ch], 2
0x18000766f  mov     rcx, [rdi]
0x180007672  test    rcx, rcx
0x180007675  jz      short loc_18000767C
0x180007677  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x18000767c  mov     [rdi], rbx
0x18000767f  mov     [rsp+48h+arg_10], 0
0x180007688  lea     rcx, [rsp+48h+arg_10]
0x18000768d  call    ??1?$MakeAllocator@VActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext>::~MakeAllocator<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext>(void)
0x180007692  mov     rax, rdi
0x180007695  add     rsp, 30h
0x180007699  pop     rdi
0x18000769a  pop     rsi
0x18000769b  pop     rbx
0x18000769c  retn
```
