# Microsoft::WRL::Details::Make<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost,>(void)

- ea: `0x180009b28`
- end: `0x180009c06`
- name: `??$Make@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@12@XZ`
- size: `222`
- prototype: `Microsoft::WRL::FtmBase **__fastcall(Microsoft::WRL::FtmBase **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b9cc`

## callees

- `0x180002f60`
- `0x180007dd0`
- `0x180009b28`
- `0x18000a730`
- `0x18000a748`
- `0x18000a9f4`
- `0x18001b010`

## pseudocode

```c
Microsoft::WRL::FtmBase **__fastcall Microsoft::WRL::Details::Make<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost,>(
        Microsoft::WRL::FtmBase **a1)
{
  Microsoft::WRL::FtmBase *v2; // rax
  Microsoft::WRL::FtmBase *v3; // rbx
  Microsoft::WRL::FtmBase *v5; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = (Microsoft::WRL::FtmBase *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v5 = v2;
  if ( v2 )
  {
    Microsoft::WRL::FtmBase::FtmBase(v2);
    *((_DWORD *)v3 + 11) = 1;
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::IoT::ShellExtension::ILauncherControl>>'};
    *((_QWORD *)v3 + 4) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::IoT::ShellExtension::ILauncherControl>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::IoT::ShellExtension::ILauncherControl>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v3 = &Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::IoT::ShellExtension::ILauncherControl>>'};
    *((_QWORD *)v3 + 4) = &Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::IoT::ShellExtension::ILauncherControl>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::IoT::ShellExtension::ILauncherControl>>'};
    std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>((char *)v3 + 48);
    *((_QWORD *)v3 + 9) = 0;
    *((_QWORD *)v3 + 10) = 0;
    *((_BYTE *)v3 + 88) = 0;
    *((_QWORD *)v3 + 12) = 0;
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(*a1);
    *a1 = v3;
    v5 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::~MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>(&v5);
  return a1;
}

```

## disassembly

```asm
0x180009b28  mov     [rsp+arg_8], rbx
0x180009b2d  push    rdi
0x180009b2e  sub     rsp, 20h
0x180009b32  mov     rdi, rcx
0x180009b35  mov     qword ptr [rcx], 0
0x180009b3c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009b43  mov     ecx, 68h ; 'h'; unsigned __int64
0x180009b48  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009b4d  mov     rbx, rax
0x180009b50  mov     [rsp+28h+arg_0], rax
0x180009b55  test    rax, rax
0x180009b58  jz      loc_180009BEE
0x180009b5e  mov     rcx, rax; this
0x180009b61  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180009b66  mov     dword ptr [rbx+2Ch], 1
0x180009b6d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VFtmBase@23@UILauncherControl@ShellExtension@IoT@3@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UILauncherControl@ShellExtension@IoT@3@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::IoT::ShellExtension::ILauncherControl>>'}
0x180009b74  mov     [rbx], rax
0x180009b77  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VFtmBase@23@UILauncherControl@ShellExtension@IoT@3@@WRL@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UILauncherControl@ShellExtension@IoT@3@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UILauncherControl@ShellExtension@IoT@3@@234@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::IoT::ShellExtension::ILauncherControl>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::IoT::ShellExtension::ILauncherControl>>'}
0x180009b7e  mov     [rbx+20h], rax
0x180009b82  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180009b89  test    rcx, rcx
0x180009b8c  jz      short loc_180009B9B
0x180009b8e  mov     rax, [rcx]
0x180009b91  mov     rax, [rax+8]
0x180009b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b9a  nop
0x180009b9b  lea     rax, ??_7EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UILauncherControl@ShellExtension@IoT@3@@Details@23@@Details@WRL@3@@; const Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::IoT::ShellExtension::ILauncherControl>>'}
0x180009ba2  mov     [rbx], rax
0x180009ba5  lea     rax, ??_7EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UILauncherControl@ShellExtension@IoT@3@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UILauncherControl@ShellExtension@IoT@3@@234@@Details@WRL@3@@; const Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::IoT::ShellExtension::ILauncherControl>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::IoT::ShellExtension::ILauncherControl>>'}
0x180009bac  mov     [rbx+20h], rax
0x180009bb0  lea     rcx, [rbx+30h]
0x180009bb4  call    ??0?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(void)
0x180009bb9  mov     qword ptr [rbx+48h], 0
0x180009bc1  mov     qword ptr [rbx+50h], 0
0x180009bc9  mov     byte ptr [rbx+58h], 0
0x180009bcd  mov     qword ptr [rbx+60h], 0
0x180009bd5  mov     rcx, [rdi]
0x180009bd8  test    rcx, rcx
0x180009bdb  jz      short loc_180009BE2
0x180009bdd  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VFtmBase@23@UILauncherControl@ShellExtension@IoT@3@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(void)
0x180009be2  mov     [rdi], rbx
0x180009be5  mov     [rsp+28h+arg_0], 0
0x180009bee  lea     rcx, [rsp+28h+arg_0]
0x180009bf3  call    ??1?$MakeAllocator@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::~MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>(void)
0x180009bf8  mov     rax, rdi
0x180009bfb  mov     rbx, [rsp+28h+arg_8]
0x180009c00  add     rsp, 20h
0x180009c04  pop     rdi
0x180009c05  retn
```
