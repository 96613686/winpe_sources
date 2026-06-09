# CTray::_UnregisterForNotifications(void)

- ea: `0x1400aef1c`
- end: `0x1400af096`
- name: `?_UnregisterForNotifications@CTray@@IEAAXXZ`
- size: `378`
- prototype: `void __fastcall(CTray *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140012bd8`

## callees

- `0x140012594`
- `0x140015f4c`
- `0x1400aef1c`
- `0x1400bb4e0`
- `0x14010d764`
- `0x1401d9010`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400aefbb`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400aefde`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400af001`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400af024`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400af055`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400aefbb`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400aefde`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400af001`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400af024`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400af055`

## pseudocode

```c
void __fastcall CTray::_UnregisterForNotifications(CTray *this, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  v3 = *((_QWORD *)this + 92);
  if ( v3 )
  {
    a2 = *((unsigned int *)this + 188);
    if ( (_DWORD)a2 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 32LL))(v3);
      *((_DWORD *)this + 188) = 0;
      v4 = *((_QWORD *)this + 92);
      *((_QWORD *)this + 92) = 0;
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
  v5 = *((_QWORD *)this + 93);
  if ( v5 )
  {
    a2 = *((unsigned int *)this + 189);
    if ( (_DWORD)a2 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
      *((_DWORD *)this + 189) = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 744);
    }
  }
  if ( *((_QWORD *)this + 96) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 96) = 0;
  }
  if ( *((_QWORD *)this + 95) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 95) = 0;
  }
  if ( *((_QWORD *)this + 97) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 97) = 0;
  }
  if ( *((_QWORD *)this + 98) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 98) = 0;
  }
  LOBYTE(a2) = 3;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_53188129>::__private_IsEnabledPreCheck(
    `wil::Feature<__WilFeatureTraits_Feature_53188129>::GetImpl'::`2'::impl,
    a2);
  if ( *((_QWORD *)this + 99) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 99) = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl'::`2'::impl) )
    wil::details::unique_storage<wil::details::resource_policy<GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *,void (*)(GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *),&void UnregisterGamingFullScreenExperienceChangeNotification(GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *),wistd::integral_constant<unsigned __int64,0>,GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *,GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *,0,std::nullptr_t>>::reset(
      (char *)this + 840,
      0);
}

```

## disassembly

```asm
0x1400aef1c  mov     [rsp+arg_0], rbx
0x1400aef21  push    rdi
0x1400aef22  sub     rsp, 20h
0x1400aef26  mov     rbx, rcx
0x1400aef29  mov     rcx, [rcx+2E0h]
0x1400aef30  test    rcx, rcx
0x1400aef33  jz      short loc_1400AEF78
0x1400aef35  mov     edx, [rbx+2F0h]
0x1400aef3b  test    edx, edx
0x1400aef3d  jz      short loc_1400AEF78
0x1400aef3f  mov     rax, [rcx]
0x1400aef42  mov     rax, [rax+20h]
0x1400aef46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400aef4b  mov     dword ptr [rbx+2F0h], 0
0x1400aef55  mov     rcx, [rbx+2E0h]
0x1400aef5c  mov     qword ptr [rbx+2E0h], 0
0x1400aef67  test    rcx, rcx
0x1400aef6a  jz      short loc_1400AEF78
0x1400aef6c  mov     rax, [rcx]
0x1400aef6f  mov     rax, [rax+10h]
0x1400aef73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400aef78  lea     rdi, [rbx+2E8h]
0x1400aef7f  mov     rcx, [rdi]
0x1400aef82  test    rcx, rcx
0x1400aef85  jz      short loc_1400AEFAF
0x1400aef87  mov     edx, [rbx+2F4h]
0x1400aef8d  test    edx, edx
0x1400aef8f  jz      short loc_1400AEFAF
0x1400aef91  mov     rax, [rcx]
0x1400aef94  mov     rax, [rax+20h]
0x1400aef98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400aef9d  mov     rcx, rdi
0x1400aefa0  mov     dword ptr [rbx+2F4h], 0
0x1400aefaa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1400aefaf  mov     rcx, [rbx+300h]
0x1400aefb6  test    rcx, rcx
0x1400aefb9  jz      short loc_1400AEFD2
0x1400aefbb  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1400aefc2  nop     dword ptr [rax+rax+00h]
0x1400aefc7  mov     qword ptr [rbx+300h], 0
0x1400aefd2  mov     rcx, [rbx+2F8h]
0x1400aefd9  test    rcx, rcx
0x1400aefdc  jz      short loc_1400AEFF5
0x1400aefde  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1400aefe5  nop     dword ptr [rax+rax+00h]
0x1400aefea  mov     qword ptr [rbx+2F8h], 0
0x1400aeff5  mov     rcx, [rbx+308h]
0x1400aeffc  test    rcx, rcx
0x1400aefff  jz      short loc_1400AF018
0x1400af001  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1400af008  nop     dword ptr [rax+rax+00h]
0x1400af00d  mov     qword ptr [rbx+308h], 0
0x1400af018  mov     rcx, [rbx+310h]
0x1400af01f  test    rcx, rcx
0x1400af022  jz      short loc_1400AF03B
0x1400af024  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1400af02b  nop     dword ptr [rax+rax+00h]
0x1400af030  mov     qword ptr [rbx+310h], 0
0x1400af03b  mov     dl, 3
0x1400af03d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53188129@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53188129@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53188129> `wil::Feature<__WilFeatureTraits_Feature_53188129>::GetImpl(void)'::`2'::impl
0x1400af044  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_53188129@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53188129>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x1400af049  mov     rcx, [rbx+318h]
0x1400af050  test    rcx, rcx
0x1400af053  jz      short loc_1400AF06C
0x1400af055  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1400af05c  nop     dword ptr [rax+rax+00h]
0x1400af061  mov     qword ptr [rbx+318h], 0
0x1400af06c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_52580392@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392> `wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl(void)'::`2'::impl
0x1400af073  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(void)
0x1400af078  test    al, al
0x1400af07a  jz      short loc_1400AF08A
0x1400af07c  lea     rcx, [rbx+348h]
0x1400af083  xor     edx, edx
0x1400af085  call    ?reset@?$unique_storage@U?$resource_policy@PEAUGAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__@@P6AXPEAU1@@Z$1?UnregisterGamingFullScreenExperienceChangeNotification@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUGAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__@@@Z; wil::details::unique_storage<wil::details::resource_policy<GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *,void (*)(GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *),&UnregisterGamingFullScreenExperienceChangeNotification(GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *),wistd::integral_constant<unsigned __int64,0>,GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *,GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *,0,std::nullptr_t>>::reset(GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *)
0x1400af08a  mov     rbx, [rsp+28h+arg_0]
0x1400af08f  add     rsp, 20h
0x1400af093  pop     rdi
0x1400af094  retn
```
