# Microsoft::WRL::Details::MakeAndInitialize<LocalAccountsNode,LocalAccountsNode,IConfigManager2URI * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<LocalAccountsNode>>,IConfigManager2URI * &)

- ea: `0x18000abb0`
- end: `0x18000ac7b`
- name: `??$MakeAndInitialize@VLocalAccountsNode@@V1@AEAPEAUIConfigManager2URI@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VLocalAccountsNode@@@WRL@Microsoft@@@012@AEAPEAUIConfigManager2URI@@@Z`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ae30`

## callees

- `0x1800030e8`
- `0x18000abb0`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<LocalAccountsNode,LocalAccountsNode,IConfigManager2URI * &>(
        __int64 *a1)
{
  __int64 v2; // rcx
  _QWORD *v3; // rax
  _QWORD *v4; // rdi

  v2 = *a1;
  if ( v2 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  *a1 = 0;
  v3 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v4 = v3;
  if ( !v3 )
    return 2147942414LL;
  *((_DWORD *)v3 + 5) = 1;
  *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'};
  v3[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *v4 = &LocalAccountsNode::`vftable'{for `ICSPNode'};
  v4[1] = &GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
  ((void (__fastcall *)(_QWORD *))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICSPNode,ICSPNodeTransactioning>::AddRef)(v4);
  *a1 = (__int64)v4;
  (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x18000abb0  mov     [rsp+arg_0], rbx
0x18000abb5  push    rdi
0x18000abb6  sub     rsp, 20h
0x18000abba  mov     rbx, rcx
0x18000abbd  mov     rcx, [rcx]
0x18000abc0  test    rcx, rcx
0x18000abc3  jz      short loc_18000ABD9
0x18000abc5  mov     qword ptr [rbx], 0
0x18000abcc  mov     rax, [rcx]
0x18000abcf  mov     rax, [rax+10h]
0x18000abd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abd8  nop
0x18000abd9  mov     qword ptr [rbx], 0
0x18000abe0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000abe7  mov     ecx, 18h; unsigned __int64
0x18000abec  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000abf1  mov     rdi, rax
0x18000abf4  test    rax, rax
0x18000abf7  jnz     short loc_18000AC00
0x18000abf9  mov     eax, 8007000Eh
0x18000abfe  jmp     short loc_18000AC6F
0x18000ac00  mov     dword ptr [rax+14h], 1
0x18000ac07  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6BICSPNode@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'}
0x18000ac0e  mov     [rdi], rax
0x18000ac11  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x18000ac18  mov     [rdi+8], rax
0x18000ac1c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000ac23  test    rcx, rcx
0x18000ac26  jz      short loc_18000AC35
0x18000ac28  mov     rax, [rcx]
0x18000ac2b  mov     rax, [rax+8]
0x18000ac2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac34  nop
0x18000ac35  lea     rax, ??_7LocalAccountsNode@@6BICSPNode@@@; const LocalAccountsNode::`vftable'{for `ICSPNode'}
0x18000ac3c  mov     [rdi], rax
0x18000ac3f  lea     rax, ??_7GenericIntNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x18000ac46  mov     [rdi+8], rax
0x18000ac4a  mov     rcx, rdi
0x18000ac4d  mov     rax, cs:off_180039900
0x18000ac54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac59  nop
0x18000ac5a  mov     [rbx], rdi
0x18000ac5d  mov     rax, [rdi]
0x18000ac60  mov     rcx, rdi
0x18000ac63  mov     rax, [rax+10h]
0x18000ac67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac6c  nop
0x18000ac6d  xor     eax, eax
0x18000ac6f  mov     rbx, [rsp+28h+arg_0]
0x18000ac74  add     rsp, 20h
0x18000ac78  pop     rdi
0x18000ac79  retn
```
