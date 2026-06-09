# CTray::_UnregisterForNotifications(void)

- ea: `0x1400a9284`
- end: `0x1400a93df`
- name: `?_UnregisterForNotifications@CTray@@IEAAXXZ`
- size: `347`
- prototype: `void __fastcall(CTray *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140025574`

## callees

- `0x14000edcc`
- `0x14008196c`
- `0x1400a9284`
- `0x1400b53fc`
- `0x1401036f4`
- `0x1401db010`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400a9323`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400a9340`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400a935d`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400a937a`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400a93a5`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400a9323`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400a9340`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400a935d`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400a937a`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400a93a5`

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
    &`wil::Feature<__WilFeatureTraits_Feature_53188129>::GetImpl'::`2'::impl,
    a2);
  if ( *((_QWORD *)this + 99) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 99) = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl'::`2'::impl) )
    wil::details::unique_storage<wil::details::resource_policy<GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *,void (*)(GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *),&void UnregisterGamingFullScreenExperienceChangeNotification(GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *),wistd::integral_constant<unsigned __int64,0>,GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *,GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *,0,std::nullptr_t>>::reset(
      (char *)this + 840,
      0);
}

```

## disassembly

```asm
0x1400a9284  mov     [rsp+arg_0], rbx
0x1400a9289  push    rdi
0x1400a928a  sub     rsp, 20h
0x1400a928e  mov     rbx, rcx
0x1400a9291  mov     rcx, [rcx+2E0h]
0x1400a9298  test    rcx, rcx
0x1400a929b  jz      short loc_1400A92E0
0x1400a929d  mov     edx, [rbx+2F0h]
0x1400a92a3  test    edx, edx
0x1400a92a5  jz      short loc_1400A92E0
0x1400a92a7  mov     rax, [rcx]
0x1400a92aa  mov     rax, [rax+20h]
0x1400a92ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a92b3  mov     dword ptr [rbx+2F0h], 0
0x1400a92bd  mov     rcx, [rbx+2E0h]
0x1400a92c4  mov     qword ptr [rbx+2E0h], 0
0x1400a92cf  test    rcx, rcx
0x1400a92d2  jz      short loc_1400A92E0
0x1400a92d4  mov     rax, [rcx]
0x1400a92d7  mov     rax, [rax+10h]
0x1400a92db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a92e0  lea     rdi, [rbx+2E8h]
0x1400a92e7  mov     rcx, [rdi]
0x1400a92ea  test    rcx, rcx
0x1400a92ed  jz      short loc_1400A9317
0x1400a92ef  mov     edx, [rbx+2F4h]
0x1400a92f5  test    edx, edx
0x1400a92f7  jz      short loc_1400A9317
0x1400a92f9  mov     rax, [rcx]
0x1400a92fc  mov     rax, [rax+20h]
0x1400a9300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a9305  mov     rcx, rdi
0x1400a9308  mov     dword ptr [rbx+2F4h], 0
0x1400a9312  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1400a9317  mov     rcx, [rbx+300h]
0x1400a931e  test    rcx, rcx
0x1400a9321  jz      short loc_1400A9334
0x1400a9323  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1400a9329  mov     qword ptr [rbx+300h], 0
0x1400a9334  mov     rcx, [rbx+2F8h]
0x1400a933b  test    rcx, rcx
0x1400a933e  jz      short loc_1400A9351
0x1400a9340  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1400a9346  mov     qword ptr [rbx+2F8h], 0
0x1400a9351  mov     rcx, [rbx+308h]
0x1400a9358  test    rcx, rcx
0x1400a935b  jz      short loc_1400A936E
0x1400a935d  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1400a9363  mov     qword ptr [rbx+308h], 0
0x1400a936e  mov     rcx, [rbx+310h]
0x1400a9375  test    rcx, rcx
0x1400a9378  jz      short loc_1400A938B
0x1400a937a  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1400a9380  mov     qword ptr [rbx+310h], 0
0x1400a938b  mov     dl, 3
0x1400a938d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53188129@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53188129@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53188129> `wil::Feature<__WilFeatureTraits_Feature_53188129>::GetImpl(void)'::`2'::impl
0x1400a9394  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_53188129@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53188129>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x1400a9399  mov     rcx, [rbx+318h]
0x1400a93a0  test    rcx, rcx
0x1400a93a3  jz      short loc_1400A93B6
0x1400a93a5  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1400a93ab  mov     qword ptr [rbx+318h], 0
0x1400a93b6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_52580392@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392> `wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl(void)'::`2'::impl
0x1400a93bd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(void)
0x1400a93c2  test    al, al
0x1400a93c4  jz      short loc_1400A93D4
0x1400a93c6  lea     rcx, [rbx+348h]
0x1400a93cd  xor     edx, edx
0x1400a93cf  call    ?reset@?$unique_storage@U?$resource_policy@PEAUGAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__@@P6AXPEAU1@@Z$1?UnregisterGamingFullScreenExperienceChangeNotification@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUGAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__@@@Z; wil::details::unique_storage<wil::details::resource_policy<GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *,void (*)(GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *),&UnregisterGamingFullScreenExperienceChangeNotification(GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *),wistd::integral_constant<unsigned __int64,0>,GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *,GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *,0,std::nullptr_t>>::reset(GAMING_FULL_SCREEN_EXPERIENCE_REGISTRATION__ *)
0x1400a93d4  mov     rbx, [rsp+28h+arg_0]
0x1400a93d9  add     rsp, 20h
0x1400a93dd  pop     rdi
0x1400a93de  retn
```
