# Microsoft::WRL::Details::Make<C3DPrintShellExtension,>(void)

- ea: `0x1800029cc`
- end: `0x180002a86`
- name: `??$Make@VC3DPrintShellExtension@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VC3DPrintShellExtension@@@12@XZ`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002df0`

## callees

- `0x180001f14`
- `0x1800029cc`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make<C3DPrintShellExtension,>(_QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx

  *a1 = 0;
  v2 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( v2 )
  {
    *((_DWORD *)v2 + 7) = 1;
    *v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::`vftable';
    v2[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::`vftable'{for `IInitializeCommand'};
    v2[2] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectWithSelection>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v3 = &C3DPrintShellExtension::`vftable';
    v3[1] = &C3DPrintShellExtension::`vftable'{for `IInitializeCommand'};
    v3[2] = &C3DPrintShellExtension::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectWithSelection>'};
    v3[4] = 0;
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v3;
  }
  return a1;
}

```

## disassembly

```asm
0x1800029cc  mov     [rsp+arg_0], rbx
0x1800029d1  push    rdi
0x1800029d2  sub     rsp, 20h
0x1800029d6  mov     rdi, rcx
0x1800029d9  mov     qword ptr [rcx], 0
0x1800029e0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800029e7  mov     ecx, 28h ; '('; unsigned __int64
0x1800029ec  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800029f1  mov     rbx, rax
0x1800029f4  test    rax, rax
0x1800029f7  jz      short loc_180002A78
0x1800029f9  mov     dword ptr [rax+1Ch], 1
0x180002a00  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIExecuteCommand@@UIInitializeCommand@@UIObjectWithSelection@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::`vftable'
0x180002a07  mov     [rbx], rax
0x180002a0a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIExecuteCommand@@UIInitializeCommand@@UIObjectWithSelection@@@WRL@Microsoft@@6BIInitializeCommand@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::`vftable'{for `IInitializeCommand'}
0x180002a11  mov     [rbx+8], rax
0x180002a15  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIExecuteCommand@@UIInitializeCommand@@UIObjectWithSelection@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIObjectWithSelection@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectWithSelection>'}
0x180002a1c  mov     [rbx+10h], rax
0x180002a20  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002a27  test    rcx, rcx
0x180002a2a  jz      short loc_180002A39
0x180002a2c  mov     rax, [rcx]
0x180002a2f  mov     rax, [rax+8]
0x180002a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a38  nop
0x180002a39  lea     rax, ??_7C3DPrintShellExtension@@6B@; const C3DPrintShellExtension::`vftable'
0x180002a40  mov     [rbx], rax
0x180002a43  lea     rax, ??_7C3DPrintShellExtension@@6BIInitializeCommand@@@; const C3DPrintShellExtension::`vftable'{for `IInitializeCommand'}
0x180002a4a  mov     [rbx+8], rax
0x180002a4e  lea     rax, ??_7C3DPrintShellExtension@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIObjectWithSelection@@@Details@WRL@Microsoft@@@; const C3DPrintShellExtension::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectWithSelection>'}
0x180002a55  mov     [rbx+10h], rax
0x180002a59  mov     qword ptr [rbx+20h], 0
0x180002a61  mov     rcx, [rdi]
0x180002a64  test    rcx, rcx
0x180002a67  jz      short loc_180002A75
0x180002a69  mov     rax, [rcx]
0x180002a6c  mov     rax, [rax+10h]
0x180002a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a75  mov     [rdi], rbx
0x180002a78  mov     rax, rdi
0x180002a7b  mov     rbx, [rsp+28h+arg_0]
0x180002a80  add     rsp, 20h
0x180002a84  pop     rdi
0x180002a85  retn
```
