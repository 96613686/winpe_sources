# Microsoft::WRL::Details::MakeAndInitialize<DomainNode,DomainNode,CConfigServiceProvider2Impl * &,IConfigManager2URI * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<DomainNode>>,CConfigServiceProvider2Impl * &,IConfigManager2URI * &)

- ea: `0x18000aa98`
- end: `0x18000abaa`
- name: `??$MakeAndInitialize@VDomainNode@@V1@AEAPEAVCConfigServiceProvider2Impl@@AEAPEAUIConfigManager2URI@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VDomainNode@@@WRL@Microsoft@@@012@AEAPEAVCConfigServiceProvider2Impl@@AEAPEAUIConfigManager2URI@@@Z`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ae30`

## callees

- `0x1800030e8`
- `0x18000aa98`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<DomainNode,DomainNode,CConfigServiceProvider2Impl * &,IConfigManager2URI * &>(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v4; // rcx
  _QWORD *v5; // rax
  _QWORD *v6; // rdi

  v4 = *a1;
  if ( v4 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  *a1 = 0;
  v5 = operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  *((_DWORD *)v5 + 5) = 1;
  *v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'};
  v5[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *v6 = &DomainNode::`vftable'{for `ICSPNode'};
  v6[1] = &DomainNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
  v6[3] = 0;
  v6[4] = 0;
  v6[5] = 0;
  v6[6] = 0;
  v6[7] = 0;
  v6[8] = 0;
  v6[9] = *a2;
  ((void (__fastcall *)(_QWORD *))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICSPNode,ICSPNodeTransactioning>::AddRef)(v6);
  *a1 = (__int64)v6;
  (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
  return 0;
}

```

## disassembly

```asm
0x18000aa98  mov     [rsp+arg_0], rbx
0x18000aa9d  mov     [rsp+arg_8], rsi
0x18000aaa2  push    rdi
0x18000aaa3  sub     rsp, 20h
0x18000aaa7  mov     rsi, rdx
0x18000aaaa  mov     rbx, rcx
0x18000aaad  mov     rcx, [rcx]
0x18000aab0  test    rcx, rcx
0x18000aab3  jz      short loc_18000AAC9
0x18000aab5  mov     qword ptr [rbx], 0
0x18000aabc  mov     rax, [rcx]
0x18000aabf  mov     rax, [rax+10h]
0x18000aac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aac8  nop
0x18000aac9  mov     qword ptr [rbx], 0
0x18000aad0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000aad7  mov     ecx, 50h ; 'P'; unsigned __int64
0x18000aadc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000aae1  mov     rdi, rax
0x18000aae4  test    rax, rax
0x18000aae7  jnz     short loc_18000AAF3
0x18000aae9  mov     eax, 8007000Eh
0x18000aaee  jmp     loc_18000AB99
0x18000aaf3  mov     dword ptr [rax+14h], 1
0x18000aafa  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6BICSPNode@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'}
0x18000ab01  mov     [rdi], rax
0x18000ab04  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x18000ab0b  mov     [rdi+8], rax
0x18000ab0f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000ab16  test    rcx, rcx
0x18000ab19  jz      short loc_18000AB28
0x18000ab1b  mov     rax, [rcx]
0x18000ab1e  mov     rax, [rax+8]
0x18000ab22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab27  nop
0x18000ab28  lea     rax, ??_7DomainNode@@6BICSPNode@@@; const DomainNode::`vftable'{for `ICSPNode'}
0x18000ab2f  mov     [rdi], rax
0x18000ab32  lea     rax, ??_7DomainNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const DomainNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x18000ab39  mov     [rdi+8], rax
0x18000ab3d  mov     qword ptr [rdi+18h], 0
0x18000ab45  mov     qword ptr [rdi+20h], 0
0x18000ab4d  mov     qword ptr [rdi+28h], 0
0x18000ab55  mov     qword ptr [rdi+30h], 0
0x18000ab5d  mov     qword ptr [rdi+38h], 0
0x18000ab65  mov     qword ptr [rdi+40h], 0
0x18000ab6d  mov     rax, [rsi]
0x18000ab70  mov     [rdi+48h], rax
0x18000ab74  mov     rcx, rdi
0x18000ab77  mov     rax, cs:off_180039878
0x18000ab7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab83  nop
0x18000ab84  mov     [rbx], rdi
0x18000ab87  mov     rax, [rdi]
0x18000ab8a  mov     rcx, rdi
0x18000ab8d  mov     rax, [rax+10h]
0x18000ab91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab96  nop
0x18000ab97  xor     eax, eax
0x18000ab99  mov     rbx, [rsp+28h+arg_0]
0x18000ab9e  mov     rsi, [rsp+28h+arg_8]
0x18000aba3  add     rsp, 20h
0x18000aba7  pop     rdi
0x18000aba8  retn
```
