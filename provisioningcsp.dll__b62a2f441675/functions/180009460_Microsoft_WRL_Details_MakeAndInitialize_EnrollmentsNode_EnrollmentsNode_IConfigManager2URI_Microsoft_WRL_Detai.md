# Microsoft::WRL::Details::MakeAndInitialize<EnrollmentsNode,EnrollmentsNode,IConfigManager2URI * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<EnrollmentsNode>>,IConfigManager2URI * &)

- ea: `0x180009460`
- end: `0x180009533`
- name: `??$MakeAndInitialize@VEnrollmentsNode@@V1@AEAPEAUIConfigManager2URI@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VEnrollmentsNode@@@WRL@Microsoft@@@012@AEAPEAUIConfigManager2URI@@@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009890`

## callees

- `0x1800030e8`
- `0x180009460`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<EnrollmentsNode,EnrollmentsNode,IConfigManager2URI * &>(
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
  v3 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  v4 = v3;
  if ( !v3 )
    return 2147942414LL;
  *((_DWORD *)v3 + 5) = 1;
  *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'};
  v3[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *v4 = &EnrollmentsNode::`vftable'{for `ICSPNode'};
  v4[1] = &GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
  v4[3] = 0;
  ((void (__fastcall *)(_QWORD *))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICSPNode,ICSPNodeTransactioning>::AddRef)(v4);
  *a1 = (__int64)v4;
  (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x180009460  mov     [rsp+arg_0], rbx
0x180009465  push    rdi
0x180009466  sub     rsp, 20h
0x18000946a  mov     rbx, rcx
0x18000946d  mov     rcx, [rcx]
0x180009470  test    rcx, rcx
0x180009473  jz      short loc_180009489
0x180009475  mov     qword ptr [rbx], 0
0x18000947c  mov     rax, [rcx]
0x18000947f  mov     rax, [rax+10h]
0x180009483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009488  nop
0x180009489  mov     qword ptr [rbx], 0
0x180009490  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009497  mov     ecx, 20h ; ' '; unsigned __int64
0x18000949c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800094a1  mov     rdi, rax
0x1800094a4  test    rax, rax
0x1800094a7  jnz     short loc_1800094B0
0x1800094a9  mov     eax, 8007000Eh
0x1800094ae  jmp     short loc_180009527
0x1800094b0  mov     dword ptr [rax+14h], 1
0x1800094b7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6BICSPNode@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'}
0x1800094be  mov     [rdi], rax
0x1800094c1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x1800094c8  mov     [rdi+8], rax
0x1800094cc  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800094d3  test    rcx, rcx
0x1800094d6  jz      short loc_1800094E5
0x1800094d8  mov     rax, [rcx]
0x1800094db  mov     rax, [rax+8]
0x1800094df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094e4  nop
0x1800094e5  lea     rax, ??_7EnrollmentsNode@@6BICSPNode@@@; const EnrollmentsNode::`vftable'{for `ICSPNode'}
0x1800094ec  mov     [rdi], rax
0x1800094ef  lea     rax, ??_7GenericIntNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x1800094f6  mov     [rdi+8], rax
0x1800094fa  mov     qword ptr [rdi+18h], 0
0x180009502  mov     rcx, rdi
0x180009505  mov     rax, cs:off_180039560
0x18000950c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009511  nop
0x180009512  mov     [rbx], rdi
0x180009515  mov     rax, [rdi]
0x180009518  mov     rcx, rdi
0x18000951b  mov     rax, [rax+10h]
0x18000951f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009524  nop
0x180009525  xor     eax, eax
0x180009527  mov     rbx, [rsp+28h+arg_0]
0x18000952c  add     rsp, 20h
0x180009530  pop     rdi
0x180009531  retn
```
