# Microsoft::WRL::Details::MakeAndInitialize<CEASConsentPopup,IUnknown,>(IUnknown * *)

- ea: `0x180001c84`
- end: `0x180001d4a`
- name: `??$MakeAndInitialize@VCEASConsentPopup@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001f80`

## callees

- `0x180001548`
- `0x180001c84`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CEASConsentPopup,IUnknown,>(_QWORD *a1)
{
  _DWORD *v2; // rax
  _DWORD *v3; // rdi
  struct Microsoft::WRL::Details::ModuleBase *v5; // rcx
  unsigned int v6; // ebx

  *a1 = 0;
  v2 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  v5 = Microsoft::WRL::Details::ModuleBase::module_;
  v2[5] = 1;
  *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEASConsentPopup,IPopupCommandHandler>::`vftable'{for `IEASConsentPopup'};
  *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEASConsentPopup,IPopupCommandHandler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IPopupCommandHandler>'};
  if ( v5 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v5 + 8LL))(v5);
  v3[6] = 0;
  *(_QWORD *)v3 = &CEASConsentPopup::`vftable'{for `IEASConsentPopup'};
  *((_QWORD *)v3 + 4) = 0;
  *((_QWORD *)v3 + 1) = &CEASConsentPopup::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IPopupCommandHandler>'};
  v6 = ((__int64 (__fastcall *)(_DWORD *, GUID *, _QWORD *))CEASConsentPopup::`vftable'{for `IEASConsentPopup'})(
         v3,
         &GUID_00000000_0000_0000_c000_000000000046,
         a1);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 16LL))(v3);
  return v6;
}

```

## disassembly

```asm
0x180001c84  mov     [rsp+arg_0], rbx
0x180001c89  push    rdi
0x180001c8a  sub     rsp, 20h
0x180001c8e  mov     rbx, rcx
0x180001c91  mov     qword ptr [rcx], 0
0x180001c98  mov     ecx, 28h ; '('; unsigned __int64
0x180001c9d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001ca4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001ca9  mov     rdi, rax
0x180001cac  test    rax, rax
0x180001caf  jnz     short loc_180001CBB
0x180001cb1  mov     eax, 8007000Eh
0x180001cb6  jmp     loc_180001D3F
0x180001cbb  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180001cc2  mov     dword ptr [rax+14h], 1
0x180001cc9  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIEASConsentPopup@@UIPopupCommandHandler@@@WRL@Microsoft@@6BIEASConsentPopup@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEASConsentPopup,IPopupCommandHandler>::`vftable'{for `IEASConsentPopup'}
0x180001cd0  mov     [rdi], rax
0x180001cd3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIEASConsentPopup@@UIPopupCommandHandler@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIPopupCommandHandler@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEASConsentPopup,IPopupCommandHandler>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IPopupCommandHandler>'}
0x180001cda  mov     [rdi+8], rax
0x180001cde  test    rcx, rcx
0x180001ce1  jz      short loc_180001CEF
0x180001ce3  mov     rax, [rcx]
0x180001ce6  mov     rax, [rax+8]
0x180001cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cef  lea     rax, ??_7CEASConsentPopup@@6BIEASConsentPopup@@@; const CEASConsentPopup::`vftable'{for `IEASConsentPopup'}
0x180001cf6  mov     dword ptr [rdi+18h], 0
0x180001cfd  mov     [rdi], rax
0x180001d00  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180001d07  lea     rax, ??_7CEASConsentPopup@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIPopupCommandHandler@@@Details@WRL@Microsoft@@@; const CEASConsentPopup::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IPopupCommandHandler>'}
0x180001d0e  mov     qword ptr [rdi+20h], 0
0x180001d16  mov     [rdi+8], rax
0x180001d1a  mov     r8, rbx
0x180001d1d  mov     rax, cs:??_7CEASConsentPopup@@6BIEASConsentPopup@@@; const CEASConsentPopup::`vftable'{for `IEASConsentPopup'}
0x180001d24  mov     rcx, rdi
0x180001d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d2c  mov     rcx, [rdi]
0x180001d2f  mov     ebx, eax
0x180001d31  mov     rax, [rcx+10h]
0x180001d35  mov     rcx, rdi
0x180001d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d3d  mov     eax, ebx
0x180001d3f  mov     rbx, [rsp+28h+arg_0]
0x180001d44  add     rsp, 20h
0x180001d48  pop     rdi
0x180001d49  retn
```
