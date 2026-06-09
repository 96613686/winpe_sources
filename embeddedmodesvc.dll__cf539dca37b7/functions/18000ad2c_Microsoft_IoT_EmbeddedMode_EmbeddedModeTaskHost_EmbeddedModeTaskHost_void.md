# Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::~EmbeddedModeTaskHost(void)

- ea: `0x18000ad2c`
- end: `0x18000adb4`
- name: `??1EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@UEAA@XZ`
- size: `136`
- prototype: `void __fastcall(Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *this, struct wil::details::wnf_subscription_state_base *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b360`

## callees

- `0x180005590`
- `0x180009f7c`
- `0x180009fb0`
- `0x18000ab9c`
- `0x18000ad2c`
- `0x18000c300`

## pseudocode

```c
void __fastcall Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::~EmbeddedModeTaskHost(
        Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *this,
        struct wil::details::wnf_subscription_state_base *a2)
{
  std::_Ref_count_base *v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::IoT::ShellExtension::ILauncherControl>>'};
  *((_QWORD *)this + 4) = &Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::IoT::ShellExtension::ILauncherControl>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::IoT::ShellExtension::ILauncherControl>>'};
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(
    (wil::details **)this + 12,
    a2);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 10);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  v4 = *((_QWORD *)this + 6);
  if ( v4 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>(
      v4,
      *((_QWORD *)this + 7));
    std::_Deallocate<16>(
      *((_QWORD **)this + 6),
      (*((_QWORD *)this + 8) - *((_QWORD *)this + 6)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 8) = 0;
  }
  *((_DWORD *)this + 11) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
}

```

## disassembly

```asm
0x18000ad2c  push    rbx
0x18000ad2e  sub     rsp, 20h
0x18000ad32  lea     rax, ??_7EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UILauncherControl@ShellExtension@IoT@3@@Details@23@@Details@WRL@3@@; const Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::IoT::ShellExtension::ILauncherControl>>'}
0x18000ad39  mov     rbx, rcx
0x18000ad3c  mov     [rcx], rax
0x18000ad3f  lea     rax, ??_7EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UILauncherControl@ShellExtension@IoT@3@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UILauncherControl@ShellExtension@IoT@3@@234@@Details@WRL@3@@; const Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::IoT::ShellExtension::ILauncherControl>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::IoT::ShellExtension::ILauncherControl>>'}
0x18000ad46  mov     [rcx+20h], rax
0x18000ad4a  add     rcx, 60h ; '`'
0x18000ad4e  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18000ad53  mov     rcx, [rbx+50h]; this
0x18000ad57  test    rcx, rcx
0x18000ad5a  jz      short loc_18000AD61
0x18000ad5c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ad61  mov     rcx, [rbx+30h]
0x18000ad65  test    rcx, rcx
0x18000ad68  jz      short loc_18000AD9F
0x18000ad6a  mov     rdx, [rbx+38h]
0x18000ad6e  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>(Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> *,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> * const,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>> &)
0x18000ad73  mov     rcx, [rbx+30h]
0x18000ad77  mov     rdx, [rbx+40h]
0x18000ad7b  sub     rdx, rcx
0x18000ad7e  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000ad82  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000ad87  mov     qword ptr [rbx+30h], 0
0x18000ad8f  mov     qword ptr [rbx+38h], 0
0x18000ad97  mov     qword ptr [rbx+40h], 0
0x18000ad9f  lea     rcx, [rbx+18h]
0x18000ada3  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18000adaa  add     rsp, 20h
0x18000adae  pop     rbx
0x18000adaf  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
