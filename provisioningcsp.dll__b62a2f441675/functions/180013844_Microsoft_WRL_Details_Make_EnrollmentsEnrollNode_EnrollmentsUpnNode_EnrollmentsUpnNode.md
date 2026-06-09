# Microsoft::WRL::Details::Make<EnrollmentsEnrollNode,EnrollmentsUpnNode *>(EnrollmentsUpnNode * &&)

- ea: `0x180013844`
- end: `0x180013956`
- name: `??$Make@VEnrollmentsEnrollNode@@PEAVEnrollmentsUpnNode@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VEnrollmentsEnrollNode@@@12@$$QEAPEAVEnrollmentsUpnNode@@@Z`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014870`

## callees

- `0x1800030e8`
- `0x180013844`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make<EnrollmentsEnrollNode,EnrollmentsUpnNode *>(_QWORD *a1, __int64 *a2)
{
  _DWORD *v4; // rdi
  __int64 v5; // rbx
  __int64 v6; // rcx

  *a1 = 0;
  v4 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
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
    *(_QWORD *)v4 = &EnrollmentsEnrollNode::`vftable'{for `ICSPNode'};
    *((_QWORD *)v4 + 1) = &GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
    *((_QWORD *)v4 + 3) = 0;
    if ( v5 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
      v6 = *((_QWORD *)v4 + 3);
      *((_QWORD *)v4 + 3) = v5;
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v4;
  }
  return a1;
}

```

## disassembly

```asm
0x180013844  mov     [rsp+arg_0], rbx
0x180013849  mov     [rsp+arg_8], rsi
0x18001384e  push    rdi
0x18001384f  sub     rsp, 20h
0x180013853  mov     rbx, rdx
0x180013856  mov     rsi, rcx
0x180013859  mov     qword ptr [rcx], 0
0x180013860  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013867  mov     ecx, 20h ; ' '; unsigned __int64
0x18001386c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013871  mov     rdi, rax
0x180013874  test    rax, rax
0x180013877  jz      loc_180013942
0x18001387d  mov     rbx, [rbx]
0x180013880  test    rbx, rbx
0x180013883  jz      short loc_180013895
0x180013885  mov     rcx, [rbx]
0x180013888  mov     rax, [rcx+8]
0x18001388c  mov     rcx, rbx
0x18001388f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013894  nop
0x180013895  mov     dword ptr [rdi+14h], 1
0x18001389c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6BICSPNode@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'}
0x1800138a3  mov     [rdi], rax
0x1800138a6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x1800138ad  mov     [rdi+8], rax
0x1800138b1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800138b8  test    rcx, rcx
0x1800138bb  jz      short loc_1800138CA
0x1800138bd  mov     rax, [rcx]
0x1800138c0  mov     rax, [rax+8]
0x1800138c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138c9  nop
0x1800138ca  lea     rax, ??_7EnrollmentsEnrollNode@@6BICSPNode@@@; const EnrollmentsEnrollNode::`vftable'{for `ICSPNode'}
0x1800138d1  mov     [rdi], rax
0x1800138d4  lea     rax, ??_7GenericIntNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x1800138db  mov     [rdi+8], rax
0x1800138df  mov     qword ptr [rdi+18h], 0
0x1800138e7  test    rbx, rbx
0x1800138ea  jz      short loc_180013916
0x1800138ec  mov     rax, [rbx]
0x1800138ef  mov     rcx, rbx
0x1800138f2  mov     rax, [rax+8]
0x1800138f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138fb  nop
0x1800138fc  mov     rcx, [rdi+18h]
0x180013900  mov     [rdi+18h], rbx
0x180013904  test    rcx, rcx
0x180013907  jz      short loc_180013916
0x180013909  mov     rax, [rcx]
0x18001390c  mov     rax, [rax+10h]
0x180013910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013915  nop
0x180013916  test    rbx, rbx
0x180013919  jz      short loc_18001392B
0x18001391b  mov     rax, [rbx]
0x18001391e  mov     rcx, rbx
0x180013921  mov     rax, [rax+10h]
0x180013925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001392a  nop
0x18001392b  mov     rcx, [rsi]
0x18001392e  test    rcx, rcx
0x180013931  jz      short loc_18001393F
0x180013933  mov     rax, [rcx]
0x180013936  mov     rax, [rax+10h]
0x18001393a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001393f  mov     [rsi], rdi
0x180013942  mov     rax, rsi
0x180013945  mov     rbx, [rsp+28h+arg_0]
0x18001394a  mov     rsi, [rsp+28h+arg_8]
0x18001394f  add     rsp, 20h
0x180013953  pop     rdi
0x180013954  retn
```
