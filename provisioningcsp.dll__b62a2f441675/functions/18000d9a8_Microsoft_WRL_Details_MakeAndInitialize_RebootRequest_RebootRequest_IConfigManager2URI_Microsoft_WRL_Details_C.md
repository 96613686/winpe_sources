# Microsoft::WRL::Details::MakeAndInitialize<RebootRequest,RebootRequest,IConfigManager2URI * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<RebootRequest>>,IConfigManager2URI * &)

- ea: `0x18000d9a8`
- end: `0x18000daca`
- name: `??$MakeAndInitialize@VRebootRequest@@V1@AEAPEAUIConfigManager2URI@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VRebootRequest@@@WRL@Microsoft@@@012@AEAPEAUIConfigManager2URI@@@Z`
- size: `290`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000de00`
- `0x18000e6e0`

## callees

- `0x1800030e8`
- `0x18000d9a8`
- `0x180012fcc`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<RebootRequest,RebootRequest,IConfigManager2URI * &>(
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
  v5 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v6 = v5;
  if ( v5 )
  {
    v5[5] = 1;
    *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'};
    *((_QWORD *)v5 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v6 = &RebootRequest::`vftable'{for `ICSPNode'};
    *((_QWORD *)v6 + 1) = &GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
    *((_QWORD *)v6 + 6) = 7;
    *((_QWORD *)v6 + 5) = 0;
    *((_WORD *)v6 + 12) = 0;
    v7 = RebootRequest::RuntimeClassInitialize((RebootRequest *)v6, *a2);
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
0x18000d9a8  mov     [rsp+arg_10], rbx
0x18000d9ad  mov     [rsp+arg_18], rsi
0x18000d9b2  push    rdi
0x18000d9b3  sub     rsp, 20h
0x18000d9b7  mov     rsi, rdx
0x18000d9ba  mov     rbx, rcx
0x18000d9bd  mov     rcx, [rcx]
0x18000d9c0  test    rcx, rcx
0x18000d9c3  jz      short loc_18000D9D9
0x18000d9c5  mov     qword ptr [rbx], 0
0x18000d9cc  mov     rax, [rcx]
0x18000d9cf  mov     rax, [rax+10h]
0x18000d9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9d8  nop
0x18000d9d9  mov     qword ptr [rbx], 0
0x18000d9e0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d9e7  mov     ecx, 40h ; '@'; unsigned __int64
0x18000d9ec  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d9f1  mov     rdi, rax
0x18000d9f4  mov     [rsp+28h+arg_0], rax
0x18000d9f9  test    rax, rax
0x18000d9fc  jnz     short loc_18000DA08
0x18000d9fe  mov     esi, 8007000Eh
0x18000da03  jmp     loc_18000DAB7
0x18000da08  mov     dword ptr [rax+14h], 1
0x18000da0f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6BICSPNode@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'}
0x18000da16  mov     [rdi], rax
0x18000da19  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x18000da20  mov     [rdi+8], rax
0x18000da24  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000da2b  test    rcx, rcx
0x18000da2e  jz      short loc_18000DA3D
0x18000da30  mov     rax, [rcx]
0x18000da33  mov     rax, [rax+8]
0x18000da37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da3c  nop
0x18000da3d  lea     rax, ??_7RebootRequest@@6BICSPNode@@@; const RebootRequest::`vftable'{for `ICSPNode'}
0x18000da44  mov     [rdi], rax
0x18000da47  lea     rax, ??_7GenericIntNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x18000da4e  mov     [rdi+8], rax
0x18000da52  mov     qword ptr [rdi+30h], 7
0x18000da5a  mov     qword ptr [rdi+28h], 0
0x18000da62  xor     eax, eax
0x18000da64  mov     [rdi+18h], ax
0x18000da68  mov     [rsp+28h+arg_8], rdi
0x18000da6d  mov     [rsp+28h+arg_0], rax
0x18000da72  mov     rdx, [rsi]; struct IConfigManager2URI *
0x18000da75  mov     rcx, rdi; this
0x18000da78  call    ?RuntimeClassInitialize@RebootRequest@@QEAAJPEAUIConfigManager2URI@@@Z; RebootRequest::RuntimeClassInitialize(IConfigManager2URI *)
0x18000da7d  mov     esi, eax
0x18000da7f  mov     rax, [rdi]
0x18000da82  test    esi, esi
0x18000da84  jns     short loc_18000DA95
0x18000da86  mov     rcx, rdi
0x18000da89  mov     rax, [rax+10h]
0x18000da8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da92  nop
0x18000da93  jmp     short loc_18000DAB7
0x18000da95  mov     rcx, rdi
0x18000da98  mov     rax, [rax+8]
0x18000da9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daa1  nop
0x18000daa2  mov     [rbx], rdi
0x18000daa5  mov     rax, [rdi]
0x18000daa8  mov     rcx, rdi
0x18000daab  mov     rax, [rax+10h]
0x18000daaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dab4  nop
0x18000dab5  xor     esi, esi
0x18000dab7  mov     eax, esi
0x18000dab9  mov     rbx, [rsp+28h+arg_10]
0x18000dabe  mov     rsi, [rsp+28h+arg_18]
0x18000dac3  add     rsp, 20h
0x18000dac7  pop     rdi
0x18000dac8  retn
```
