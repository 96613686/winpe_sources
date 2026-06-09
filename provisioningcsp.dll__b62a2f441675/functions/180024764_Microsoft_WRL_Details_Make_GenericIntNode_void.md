# Microsoft::WRL::Details::Make<GenericIntNode,>(void)

- ea: `0x180024764`
- end: `0x180024801`
- name: `??$Make@VGenericIntNode@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VGenericIntNode@@@12@XZ`
- size: `157`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180025e18`
- `0x180026248`

## callees

- `0x1800030e8`
- `0x180024764`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make<GenericIntNode,>(_QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx

  *a1 = 0;
  v2 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  if ( v2 )
  {
    *((_DWORD *)v2 + 5) = 1;
    *v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'};
    v2[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v3 = &GenericIntNode::`vftable'{for `ICSPNode'};
    v3[1] = &GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v3;
  }
  return a1;
}

```

## disassembly

```asm
0x180024764  mov     [rsp+arg_0], rbx
0x180024769  push    rdi
0x18002476a  sub     rsp, 20h
0x18002476e  mov     rdi, rcx
0x180024771  mov     qword ptr [rcx], 0
0x180024778  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002477f  mov     ecx, 20h ; ' '; unsigned __int64
0x180024784  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180024789  mov     rbx, rax
0x18002478c  test    rax, rax
0x18002478f  jz      short loc_1800247F2
0x180024791  mov     dword ptr [rax+14h], 1
0x180024798  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6BICSPNode@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'}
0x18002479f  mov     [rbx], rax
0x1800247a2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x1800247a9  mov     [rbx+8], rax
0x1800247ad  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800247b4  test    rcx, rcx
0x1800247b7  jz      short loc_1800247C6
0x1800247b9  mov     rax, [rcx]
0x1800247bc  mov     rax, [rax+8]
0x1800247c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247c5  nop
0x1800247c6  lea     rax, ??_7GenericIntNode@@6BICSPNode@@@; const GenericIntNode::`vftable'{for `ICSPNode'}
0x1800247cd  mov     [rbx], rax
0x1800247d0  lea     rax, ??_7GenericIntNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x1800247d7  mov     [rbx+8], rax
0x1800247db  mov     rcx, [rdi]
0x1800247de  test    rcx, rcx
0x1800247e1  jz      short loc_1800247EF
0x1800247e3  mov     rax, [rcx]
0x1800247e6  mov     rax, [rax+10h]
0x1800247ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247ef  mov     [rdi], rbx
0x1800247f2  mov     rax, rdi
0x1800247f5  mov     rbx, [rsp+28h+arg_0]
0x1800247fa  add     rsp, 20h
0x1800247fe  pop     rdi
0x1800247ff  retn
```
