# Microsoft::WRL::Details::Make<AddPackageInstallNode,Microsoft::WRL::ComPtr<GenericBStrNode> &>(Microsoft::WRL::ComPtr<GenericBStrNode> &)

- ea: `0x180010a00`
- end: `0x180010afa`
- name: `??$Make@VAddPackageInstallNode@@AEAV?$ComPtr@VGenericBStrNode@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAddPackageInstallNode@@@12@AEAV?$ComPtr@VGenericBStrNode@@@12@@Z`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180010bb0`

## callees

- `0x1800030e8`
- `0x180010a00`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make<AddPackageInstallNode,Microsoft::WRL::ComPtr<GenericBStrNode> &>(
        _QWORD *a1,
        __int64 *a2)
{
  _DWORD *v4; // rdi
  __int64 v5; // rbx

  *a1 = 0;
  v4 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  if ( v4 )
  {
    v5 = *a2;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    v4[5] = 1;
    *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'};
    *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v4 = &AddPackageInstallNode::`vftable'{for `ICSPNode'};
    *((_QWORD *)v4 + 1) = &GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
    *((_WORD *)v4 + 12) = 0;
    *((_QWORD *)v4 + 4) = v5;
    if ( v5 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v4;
  }
  return a1;
}

```

## disassembly

```asm
0x180010a00  mov     [rsp+arg_0], rbx
0x180010a05  mov     [rsp+arg_8], rsi
0x180010a0a  push    rdi
0x180010a0b  sub     rsp, 20h
0x180010a0f  mov     rbx, rdx
0x180010a12  mov     rsi, rcx
0x180010a15  mov     qword ptr [rcx], 0
0x180010a1c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010a23  mov     ecx, 28h ; '('; unsigned __int64
0x180010a28  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010a2d  mov     rdi, rax
0x180010a30  test    rax, rax
0x180010a33  jz      loc_180010AE6
0x180010a39  mov     rbx, [rbx]
0x180010a3c  test    rbx, rbx
0x180010a3f  jz      short loc_180010A51
0x180010a41  mov     rcx, [rbx]
0x180010a44  mov     rax, [rcx+8]
0x180010a48  mov     rcx, rbx
0x180010a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a50  nop
0x180010a51  mov     dword ptr [rdi+14h], 1
0x180010a58  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6BICSPNode@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'}
0x180010a5f  mov     [rdi], rax
0x180010a62  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x180010a69  mov     [rdi+8], rax
0x180010a6d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180010a74  test    rcx, rcx
0x180010a77  jz      short loc_180010A86
0x180010a79  mov     rax, [rcx]
0x180010a7c  mov     rax, [rax+8]
0x180010a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a85  nop
0x180010a86  lea     rax, ??_7AddPackageInstallNode@@6BICSPNode@@@; const AddPackageInstallNode::`vftable'{for `ICSPNode'}
0x180010a8d  mov     [rdi], rax
0x180010a90  lea     rax, ??_7GenericIntNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x180010a97  mov     [rdi+8], rax
0x180010a9b  xor     eax, eax
0x180010a9d  mov     [rdi+18h], ax
0x180010aa1  mov     [rdi+20h], rbx
0x180010aa5  test    rbx, rbx
0x180010aa8  jz      short loc_180010ABA
0x180010aaa  mov     rax, [rbx]
0x180010aad  mov     rcx, rbx
0x180010ab0  mov     rax, [rax+8]
0x180010ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ab9  nop
0x180010aba  test    rbx, rbx
0x180010abd  jz      short loc_180010ACF
0x180010abf  mov     rax, [rbx]
0x180010ac2  mov     rcx, rbx
0x180010ac5  mov     rax, [rax+10h]
0x180010ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ace  nop
0x180010acf  mov     rcx, [rsi]
0x180010ad2  test    rcx, rcx
0x180010ad5  jz      short loc_180010AE3
0x180010ad7  mov     rax, [rcx]
0x180010ada  mov     rax, [rax+10h]
0x180010ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ae3  mov     [rsi], rdi
0x180010ae6  mov     rax, rsi
0x180010ae9  mov     rbx, [rsp+28h+arg_0]
0x180010aee  mov     rsi, [rsp+28h+arg_8]
0x180010af3  add     rsp, 20h
0x180010af7  pop     rdi
0x180010af8  retn
```
