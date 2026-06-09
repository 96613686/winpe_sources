# Microsoft::WRL::Details::MakeAndInitialize<PackageNode,PackageNode,IConfigManager2URI * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<PackageNode>>,IConfigManager2URI * &)

- ea: `0x18000e004`
- end: `0x18000e133`
- name: `??$MakeAndInitialize@VPackageNode@@V1@AEAPEAUIConfigManager2URI@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VPackageNode@@@WRL@Microsoft@@@012@AEAPEAUIConfigManager2URI@@@Z`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e6e0`

## callees

- `0x1800030e8`
- `0x18000e004`
- `0x1800133d8`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<PackageNode,PackageNode,IConfigManager2URI * &>(
        __int64 *a1,
        struct IConfigManager2URI **a2)
{
  __int64 v4; // rcx
  _DWORD *v5; // rax
  _DWORD *v6; // rdi
  int v7; // esi
  __int64 v8; // rax

  v4 = *a1;
  if ( v4 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  *a1 = 0;
  v5 = operator new(0x58u, (const struct std::nothrow_t *)std::nothrow);
  v6 = v5;
  if ( v5 )
  {
    v5[5] = 1;
    *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'};
    *((_QWORD *)v5 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v6 = &PackageNode::`vftable'{for `ICSPNode'};
    *((_QWORD *)v6 + 1) = &GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
    *((_QWORD *)v6 + 6) = 7;
    *((_QWORD *)v6 + 5) = 0;
    *((_WORD *)v6 + 12) = 0;
    *((_QWORD *)v6 + 10) = 7;
    *((_QWORD *)v6 + 9) = 0;
    *((_WORD *)v6 + 28) = 0;
    v7 = PackageNode::RuntimeClassInitialize((PackageNode *)v6, *a2);
    v8 = *(_QWORD *)v6;
    if ( v7 >= 0 )
    {
      (*(void (__fastcall **)(_DWORD *))(v8 + 8))(v6);
      *a1 = (__int64)v6;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
      return 0;
    }
    else
    {
      (*(void (__fastcall **)(_DWORD *))(v8 + 16))(v6);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000e004  mov     [rsp+arg_10], rbx
0x18000e009  mov     [rsp+arg_18], rsi
0x18000e00e  push    rdi
0x18000e00f  sub     rsp, 20h
0x18000e013  mov     rsi, rdx
0x18000e016  mov     rbx, rcx
0x18000e019  mov     rcx, [rcx]
0x18000e01c  test    rcx, rcx
0x18000e01f  jz      short loc_18000E035
0x18000e021  mov     qword ptr [rbx], 0
0x18000e028  mov     rax, [rcx]
0x18000e02b  mov     rax, [rax+10h]
0x18000e02f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e034  nop
0x18000e035  mov     qword ptr [rbx], 0
0x18000e03c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e043  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000e048  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e04d  mov     rdi, rax
0x18000e050  mov     [rsp+28h+arg_0], rax
0x18000e055  test    rax, rax
0x18000e058  jnz     short loc_18000E064
0x18000e05a  mov     esi, 8007000Eh
0x18000e05f  jmp     loc_18000E120
0x18000e064  mov     dword ptr [rax+14h], 1
0x18000e06b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6BICSPNode@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'}
0x18000e072  mov     [rdi], rax
0x18000e075  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x18000e07c  mov     [rdi+8], rax
0x18000e080  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000e087  test    rcx, rcx
0x18000e08a  jz      short loc_18000E099
0x18000e08c  mov     rax, [rcx]
0x18000e08f  mov     rax, [rax+8]
0x18000e093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e098  nop
0x18000e099  lea     rax, ??_7PackageNode@@6BICSPNode@@@; const PackageNode::`vftable'{for `ICSPNode'}
0x18000e0a0  mov     [rdi], rax
0x18000e0a3  lea     rax, ??_7GenericIntNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x18000e0aa  mov     [rdi+8], rax
0x18000e0ae  mov     ecx, 7
0x18000e0b3  mov     [rdi+30h], rcx
0x18000e0b7  mov     qword ptr [rdi+28h], 0
0x18000e0bf  xor     eax, eax
0x18000e0c1  mov     [rdi+18h], ax
0x18000e0c5  mov     [rdi+50h], rcx
0x18000e0c9  mov     [rdi+48h], rax
0x18000e0cd  mov     [rdi+38h], ax
0x18000e0d1  mov     [rsp+28h+arg_8], rdi
0x18000e0d6  mov     [rsp+28h+arg_0], rax
0x18000e0db  mov     rdx, [rsi]; struct IConfigManager2URI *
0x18000e0de  mov     rcx, rdi; this
0x18000e0e1  call    ?RuntimeClassInitialize@PackageNode@@QEAAJPEAUIConfigManager2URI@@@Z; PackageNode::RuntimeClassInitialize(IConfigManager2URI *)
0x18000e0e6  mov     esi, eax
0x18000e0e8  mov     rax, [rdi]
0x18000e0eb  test    esi, esi
0x18000e0ed  jns     short loc_18000E0FE
0x18000e0ef  mov     rcx, rdi
0x18000e0f2  mov     rax, [rax+10h]
0x18000e0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0fb  nop
0x18000e0fc  jmp     short loc_18000E120
0x18000e0fe  mov     rcx, rdi
0x18000e101  mov     rax, [rax+8]
0x18000e105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e10a  nop
0x18000e10b  mov     [rbx], rdi
0x18000e10e  mov     rax, [rdi]
0x18000e111  mov     rcx, rdi
0x18000e114  mov     rax, [rax+10h]
0x18000e118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e11d  nop
0x18000e11e  xor     esi, esi
0x18000e120  mov     eax, esi
0x18000e122  mov     rbx, [rsp+28h+arg_10]
0x18000e127  mov     rsi, [rsp+28h+arg_18]
0x18000e12c  add     rsp, 20h
0x18000e130  pop     rdi
0x18000e131  retn
```
