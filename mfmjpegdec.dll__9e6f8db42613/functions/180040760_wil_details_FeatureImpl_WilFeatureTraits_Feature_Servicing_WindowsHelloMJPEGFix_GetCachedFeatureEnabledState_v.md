# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WindowsHelloMJPEGFix>::GetCachedFeatureEnabledState(void)

- ea: `0x180040760`
- end: `0x180040841`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WindowsHelloMJPEGFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180042814`
- `0x1800431b8`

## callees

- `0x18003b30c`
- `0x18003d6a0`
- `0x180040760`
- `0x1800409ac`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WindowsHelloMJPEGFix>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  wil::details *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Servicing_WindowsHelloMJPEGFix__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_WindowsHelloMJPEGFix__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WindowsHelloMJPEGFix>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
    v7 = *(_DWORD *)a2;
    v8 = v14;
    do
    {
      v9 = (_DWORD)v13 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_WindowsHelloMJPEGFix__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_Servicing_WindowsHelloMJPEGFix__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180040760  mov     [rsp+arg_10], rbx
0x180040765  mov     [rsp+arg_0], rcx
0x18004076a  push    rbp
0x18004076b  push    rsi
0x18004076c  push    rdi
0x18004076d  sub     rsp, 20h
0x180040771  mov     rsi, cs:Feature_Servicing_WindowsHelloMJPEGFix__descriptor
0x180040778  mov     rdi, rdx
0x18004077b  mov     qword ptr [rdx], 0
0x180040782  mov     eax, [rsi]
0x180040784  mov     [rdx], eax
0x180040786  and     eax, 6
0x180040789  cmp     al, 6
0x18004078b  jz      loc_180040831
0x180040791  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180040796  lea     r8, [rsp+38h+arg_0]
0x18004079b  mov     dword ptr [rsp+38h+arg_0], 0
0x1800407a3  lea     rdx, [rsp+38h+arg_8]
0x1800407a8  mov     ebp, eax
0x1800407aa  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WindowsHelloMJPEGFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WindowsHelloMJPEGFix>::GetCurrentFeatureEnabledState(int *)
0x1800407af  mov     eax, [rdi]
0x1800407b1  mov     rbx, [rsp+38h+arg_8]
0x1800407b6  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800407bb  mov     edx, eax
0x1800407bd  mov     [rdi], eax
0x1800407bf  mov     ecx, eax
0x1800407c1  jz      short loc_1800407DC
0x1800407c3  test    dl, 2
0x1800407c6  jnz     short loc_1800407DC
0x1800407c8  and     ecx, 0FFFFF63Eh
0x1800407ce  mov     eax, ebx
0x1800407d0  and     eax, 9C1h
0x1800407d5  or      ecx, eax
0x1800407d7  or      ecx, 2
0x1800407da  mov     [rdi], ecx
0x1800407dc  mov     r8d, edx
0x1800407df  and     r8d, 4
0x1800407e3  jnz     short loc_1800407F7
0x1800407e5  btr     ecx, 0Ah
0x1800407e9  mov     eax, ebx
0x1800407eb  and     eax, 400h
0x1800407f0  or      ecx, eax
0x1800407f2  or      ecx, 4
0x1800407f5  mov     [rdi], ecx
0x1800407f7  mov     eax, edx
0x1800407f9  lock cmpxchg [rsi], ecx
0x1800407fd  jnz     short loc_1800407B6
0x1800407ff  test    r8d, r8d
0x180040802  jnz     short loc_18004081C
0x180040804  mov     r9d, ebp
0x180040807  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18004080e  mov     r8d, 3
0x180040814  mov     rdx, rsi
0x180040817  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18004081c  mov     eax, [rdi]
0x18004081e  test    al, 2
0x180040820  jnz     short loc_180040831
0x180040822  and     eax, 0FFFFF63Eh
0x180040827  and     ebx, 9C1h
0x18004082d  or      eax, ebx
0x18004082f  mov     [rdi], eax
0x180040831  mov     rbx, [rsp+38h+arg_10]
0x180040836  mov     rax, rdi
0x180040839  add     rsp, 20h
0x18004083d  pop     rdi
0x18004083e  pop     rsi
0x18004083f  pop     rbp
0x180040840  retn
```
