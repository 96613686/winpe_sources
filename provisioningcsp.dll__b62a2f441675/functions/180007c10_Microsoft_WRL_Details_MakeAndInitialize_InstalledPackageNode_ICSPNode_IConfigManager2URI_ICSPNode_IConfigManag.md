# Microsoft::WRL::Details::MakeAndInitialize<InstalledPackageNode,ICSPNode,IConfigManager2URI *>(ICSPNode * *,IConfigManager2URI * &&)

- ea: `0x180007c10`
- end: `0x180007d28`
- name: `??$MakeAndInitialize@VInstalledPackageNode@@UICSPNode@@PEAUIConfigManager2URI@@@Details@WRL@Microsoft@@YAJPEAPEAUICSPNode@@$$QEAPEAUIConfigManager2URI@@@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008660`

## callees

- `0x1800030e8`
- `0x180007c10`
- `0x180008d50`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<InstalledPackageNode,ICSPNode,IConfigManager2URI *>(
        _QWORD *a1,
        struct IConfigManager2URI **a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  int v6; // edi
  __int64 v7; // rax

  *a1 = 0;
  v4 = operator new(0x58u, (const struct std::nothrow_t *)std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    v4[5] = 1;
    *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'};
    *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v5 = &InstalledPackageNode::`vftable'{for `ICSPNode'};
    *((_QWORD *)v5 + 1) = &GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
    *((_QWORD *)v5 + 6) = 7;
    *((_QWORD *)v5 + 5) = 0;
    *((_WORD *)v5 + 12) = 0;
    *((_QWORD *)v5 + 10) = 7;
    *((_QWORD *)v5 + 9) = 0;
    *((_WORD *)v5 + 28) = 0;
    v6 = InstalledPackageNode::RuntimeClassInitialize((InstalledPackageNode *)v5, *a2);
    v7 = *(_QWORD *)v5;
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(_DWORD *, GUID *, _QWORD *))v7)(
             v5,
             &GUID_8a13633c_797d_46e9_b602_d982b8ec9847,
             a1);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
    }
    else
    {
      (*(void (__fastcall **)(_DWORD *))(v7 + 16))(v5);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180007c10  mov     [rsp+arg_8], rbx
0x180007c15  mov     [rsp+arg_18], rsi
0x180007c1a  push    rdi
0x180007c1b  sub     rsp, 20h
0x180007c1f  mov     rdi, rdx
0x180007c22  mov     rsi, rcx
0x180007c25  mov     qword ptr [rcx], 0
0x180007c2c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007c33  mov     ecx, 58h ; 'X'; unsigned __int64
0x180007c38  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007c3d  mov     rbx, rax
0x180007c40  mov     [rsp+28h+arg_0], rax
0x180007c45  test    rax, rax
0x180007c48  jnz     short loc_180007C54
0x180007c4a  mov     edi, 8007000Eh
0x180007c4f  jmp     loc_180007D15
0x180007c54  mov     dword ptr [rax+14h], 1
0x180007c5b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6BICSPNode@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'}
0x180007c62  mov     [rbx], rax
0x180007c65  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x180007c6c  mov     [rbx+8], rax
0x180007c70  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007c77  test    rcx, rcx
0x180007c7a  jz      short loc_180007C89
0x180007c7c  mov     rax, [rcx]
0x180007c7f  mov     rax, [rax+8]
0x180007c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c88  nop
0x180007c89  lea     rax, ??_7InstalledPackageNode@@6BICSPNode@@@; const InstalledPackageNode::`vftable'{for `ICSPNode'}
0x180007c90  mov     [rbx], rax
0x180007c93  lea     rax, ??_7GenericIntNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x180007c9a  mov     [rbx+8], rax
0x180007c9e  mov     ecx, 7
0x180007ca3  mov     [rbx+30h], rcx
0x180007ca7  mov     qword ptr [rbx+28h], 0
0x180007caf  xor     eax, eax
0x180007cb1  mov     [rbx+18h], ax
0x180007cb5  mov     [rbx+50h], rcx
0x180007cb9  mov     [rbx+48h], rax
0x180007cbd  mov     [rbx+38h], ax
0x180007cc1  mov     [rsp+28h+arg_10], rbx
0x180007cc6  mov     [rsp+28h+arg_0], rax
0x180007ccb  mov     rdx, [rdi]; struct IConfigManager2URI *
0x180007cce  mov     rcx, rbx; this
0x180007cd1  call    ?RuntimeClassInitialize@InstalledPackageNode@@QEAAJPEAUIConfigManager2URI@@@Z; InstalledPackageNode::RuntimeClassInitialize(IConfigManager2URI *)
0x180007cd6  mov     edi, eax
0x180007cd8  mov     rax, [rbx]
0x180007cdb  test    edi, edi
0x180007cdd  jns     short loc_180007CEE
0x180007cdf  mov     rcx, rbx
0x180007ce2  mov     rax, [rax+10h]
0x180007ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ceb  nop
0x180007cec  jmp     short loc_180007D15
0x180007cee  mov     r8, rsi
0x180007cf1  lea     rdx, _GUID_8a13633c_797d_46e9_b602_d982b8ec9847
0x180007cf8  mov     rcx, rbx
0x180007cfb  mov     rax, [rax]
0x180007cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d03  mov     edi, eax
0x180007d05  mov     rax, [rbx]
0x180007d08  mov     rcx, rbx
0x180007d0b  mov     rax, [rax+10h]
0x180007d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d14  nop
0x180007d15  mov     eax, edi
0x180007d17  mov     rbx, [rsp+28h+arg_8]
0x180007d1c  mov     rsi, [rsp+28h+arg_18]
0x180007d21  add     rsp, 20h
0x180007d25  pop     rdi
0x180007d26  retn
```
