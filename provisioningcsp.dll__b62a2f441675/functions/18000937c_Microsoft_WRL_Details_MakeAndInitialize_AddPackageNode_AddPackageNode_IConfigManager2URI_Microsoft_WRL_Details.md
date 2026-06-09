# Microsoft::WRL::Details::MakeAndInitialize<AddPackageNode,AddPackageNode,IConfigManager2URI * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<AddPackageNode>>,IConfigManager2URI * &)

- ea: `0x18000937c`
- end: `0x180009457`
- name: `??$MakeAndInitialize@VAddPackageNode@@V1@AEAPEAUIConfigManager2URI@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VAddPackageNode@@@WRL@Microsoft@@@012@AEAPEAUIConfigManager2URI@@@Z`
- size: `219`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009890`
- `0x18000e6e0`

## callees

- `0x1800030e8`
- `0x18000937c`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<AddPackageNode,AddPackageNode,IConfigManager2URI * &>(
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
  v3 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  v4 = v3;
  if ( !v3 )
    return 2147942414LL;
  *((_DWORD *)v3 + 5) = 1;
  *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'};
  v3[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *v4 = &AddPackageNode::`vftable'{for `ICSPNode'};
  v4[1] = &GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
  v4[3] = 0;
  v4[4] = 0;
  ((void (__fastcall *)(_QWORD *))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICSPNode,ICSPNodeTransactioning>::AddRef)(v4);
  *a1 = (__int64)v4;
  (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x18000937c  mov     [rsp+arg_0], rbx
0x180009381  push    rdi
0x180009382  sub     rsp, 20h
0x180009386  mov     rbx, rcx
0x180009389  mov     rcx, [rcx]
0x18000938c  test    rcx, rcx
0x18000938f  jz      short loc_1800093A5
0x180009391  mov     qword ptr [rbx], 0
0x180009398  mov     rax, [rcx]
0x18000939b  mov     rax, [rax+10h]
0x18000939f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093a4  nop
0x1800093a5  mov     qword ptr [rbx], 0
0x1800093ac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800093b3  mov     ecx, 28h ; '('; unsigned __int64
0x1800093b8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800093bd  mov     rdi, rax
0x1800093c0  test    rax, rax
0x1800093c3  jnz     short loc_1800093CC
0x1800093c5  mov     eax, 8007000Eh
0x1800093ca  jmp     short loc_18000944B
0x1800093cc  mov     dword ptr [rax+14h], 1
0x1800093d3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6BICSPNode@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'}
0x1800093da  mov     [rdi], rax
0x1800093dd  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x1800093e4  mov     [rdi+8], rax
0x1800093e8  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800093ef  test    rcx, rcx
0x1800093f2  jz      short loc_180009401
0x1800093f4  mov     rax, [rcx]
0x1800093f7  mov     rax, [rax+8]
0x1800093fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009400  nop
0x180009401  lea     rax, ??_7AddPackageNode@@6BICSPNode@@@; const AddPackageNode::`vftable'{for `ICSPNode'}
0x180009408  mov     [rdi], rax
0x18000940b  lea     rax, ??_7GenericIntNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x180009412  mov     [rdi+8], rax
0x180009416  mov     qword ptr [rdi+18h], 0
0x18000941e  mov     qword ptr [rdi+20h], 0
0x180009426  mov     rcx, rdi
0x180009429  mov     rax, cs:off_1800395E8
0x180009430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009435  nop
0x180009436  mov     [rbx], rdi
0x180009439  mov     rax, [rdi]
0x18000943c  mov     rcx, rdi
0x18000943f  mov     rax, [rax+10h]
0x180009443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009448  nop
0x180009449  xor     eax, eax
0x18000944b  mov     rbx, [rsp+28h+arg_0]
0x180009450  add     rsp, 20h
0x180009454  pop     rdi
0x180009455  retn
```
