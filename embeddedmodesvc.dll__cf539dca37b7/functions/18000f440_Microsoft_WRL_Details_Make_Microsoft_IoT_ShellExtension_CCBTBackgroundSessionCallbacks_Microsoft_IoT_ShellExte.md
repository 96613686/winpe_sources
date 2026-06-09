# Microsoft::WRL::Details::Make<Microsoft::IoT::ShellExtension::CCBTBackgroundSessionCallbacks,Microsoft::IoT::ShellExtension::CCBTLauncher *>(Microsoft::IoT::ShellExtension::CCBTLauncher * &&)

- ea: `0x18000f440`
- end: `0x18000f4d4`
- name: `??$Make@VCCBTBackgroundSessionCallbacks@ShellExtension@IoT@Microsoft@@PEAVCCBTLauncher@234@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCCBTBackgroundSessionCallbacks@ShellExtension@IoT@Microsoft@@@12@$$QEAPEAVCCBTLauncher@ShellExtension@IoT@2@@Z`
- size: `148`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001029c`

## callees

- `0x180002f60`
- `0x180007dd0`
- `0x18000a9f4`
- `0x18000f440`
- `0x18000ff60`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make<Microsoft::IoT::ShellExtension::CCBTBackgroundSessionCallbacks,Microsoft::IoT::ShellExtension::CCBTLauncher *>(
        _QWORD *a1,
        __int64 *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  __int64 v6; // rbx
  _QWORD *v8; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v4;
  v5 = v4;
  if ( v4 )
  {
    v6 = *a2;
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IBackgroundSessionCallbacks>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IBackgroundSessionCallbacks>(v4);
    v5[6] = v6;
    *v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IBackgroundSessionCallbacks>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IBackgroundSessionCallbacks>>'};
    v5[4] = &Microsoft::IoT::ShellExtension::CCBTBackgroundSessionCallbacks::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IBackgroundSessionCallbacks>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IBackgroundSessionCallbacks>>'};
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(*a1);
    *a1 = v5;
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::~MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>(&v8);
  return a1;
}

```

## disassembly

```asm
0x18000f440  mov     [rsp+arg_8], rbx
0x18000f445  mov     [rsp+arg_10], rsi
0x18000f44a  push    rdi
0x18000f44b  sub     rsp, 20h
0x18000f44f  mov     rbx, rdx
0x18000f452  mov     qword ptr [rcx], 0
0x18000f459  mov     rsi, rcx
0x18000f45c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f463  mov     ecx, 38h ; '8'; unsigned __int64
0x18000f468  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f46d  mov     [rsp+28h+arg_0], rax
0x18000f472  mov     rdi, rax
0x18000f475  test    rax, rax
0x18000f478  jz      short loc_18000F4B7
0x18000f47a  mov     rbx, [rbx]
0x18000f47d  mov     rcx, rax
0x18000f480  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VFtmBase@23@UIBackgroundSessionCallbacks@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IBackgroundSessionCallbacks>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IBackgroundSessionCallbacks>(void)
0x18000f485  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VFtmBase@23@UIBackgroundSessionCallbacks@@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIBackgroundSessionCallbacks@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IBackgroundSessionCallbacks>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IBackgroundSessionCallbacks>>'}
0x18000f48c  mov     [rdi+30h], rbx
0x18000f490  mov     [rdi], rax
0x18000f493  lea     rax, ??_7CCBTBackgroundSessionCallbacks@ShellExtension@IoT@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIBackgroundSessionCallbacks@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIBackgroundSessionCallbacks@@@234@@Details@WRL@3@@; const Microsoft::IoT::ShellExtension::CCBTBackgroundSessionCallbacks::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IBackgroundSessionCallbacks>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IBackgroundSessionCallbacks>>'}
0x18000f49a  mov     [rdi+20h], rax
0x18000f49e  mov     rcx, [rsi]
0x18000f4a1  test    rcx, rcx
0x18000f4a4  jz      short loc_18000F4AB
0x18000f4a6  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VFtmBase@23@UILauncherControl@ShellExtension@IoT@3@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(void)
0x18000f4ab  mov     [rsi], rdi
0x18000f4ae  mov     [rsp+28h+arg_0], 0
0x18000f4b7  lea     rcx, [rsp+28h+arg_0]
0x18000f4bc  call    ??1?$MakeAllocator@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::~MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>(void)
0x18000f4c1  mov     rbx, [rsp+28h+arg_8]
0x18000f4c6  mov     rax, rsi
0x18000f4c9  mov     rsi, [rsp+28h+arg_10]
0x18000f4ce  add     rsp, 20h
0x18000f4d2  pop     rdi
0x18000f4d3  retn
```
