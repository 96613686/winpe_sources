# wil::details::FeatureImpl<__WilFeatureTraits_Feature_DSSvc_RedirectionGuard>::GetCachedFeatureEnabledState(void)

- ea: `0x1800088c8`
- end: `0x1800089ab`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DSSvc_RedirectionGuard@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `227`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009d00`

## callees

- `0x1800085d8`
- `0x1800088c8`
- `0x1800089b4`
- `0x18000a100`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_DSSvc_RedirectionGuard>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  __int64 v12; // r8
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_DSSvc_RedirectionGuard__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_DSSvc_RedirectionGuard__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DSSvc_RedirectionGuard>::GetCurrentFeatureEnabledState(
      v6,
      &v15,
      &v14);
    if ( !v5 )
      LODWORD(v14) = 0;
    v7 = *(_DWORD *)a2;
    v8 = v15;
    do
    {
      v9 = (_DWORD)v14 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      v12 = v7 & 4;
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_DSSvc_RedirectionGuard__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !(_DWORD)v12 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        wil::details::g_enabledStateManager,
        Feature_DSSvc_RedirectionGuard__descriptor,
        v12,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800088c8  mov     [rsp+arg_10], rbx
0x1800088cd  mov     [rsp+arg_0], rcx
0x1800088d2  push    rbp
0x1800088d3  push    rsi
0x1800088d4  push    rdi
0x1800088d5  sub     rsp, 20h
0x1800088d9  mov     rsi, cs:Feature_DSSvc_RedirectionGuard__descriptor
0x1800088e0  mov     rdi, rdx
0x1800088e3  mov     qword ptr [rdx], 0
0x1800088ea  mov     eax, [rsi]
0x1800088ec  mov     [rdx], eax
0x1800088ee  and     eax, 6
0x1800088f1  cmp     al, 6
0x1800088f3  jz      loc_18000899B
0x1800088f9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800088fe  lea     r8, [rsp+38h+arg_0]
0x180008903  mov     dword ptr [rsp+38h+arg_0], 0
0x18000890b  lea     rdx, [rsp+38h+arg_8]
0x180008910  mov     ebp, eax
0x180008912  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DSSvc_RedirectionGuard@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DSSvc_RedirectionGuard>::GetCurrentFeatureEnabledState(int *)
0x180008917  test    ebp, ebp
0x180008919  jnz     short loc_18000891F
0x18000891b  mov     dword ptr [rsp+38h+arg_0], ebp
0x18000891f  mov     eax, [rdi]
0x180008921  mov     rbx, [rsp+38h+arg_8]
0x180008926  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000892b  mov     edx, eax
0x18000892d  mov     [rdi], eax
0x18000892f  mov     ecx, eax
0x180008931  jz      short loc_18000894C
0x180008933  test    dl, 2
0x180008936  jnz     short loc_18000894C
0x180008938  and     ecx, 0FFFFF63Eh
0x18000893e  mov     eax, ebx
0x180008940  and     eax, 9C1h
0x180008945  or      ecx, eax
0x180008947  or      ecx, 2
0x18000894a  mov     [rdi], ecx
0x18000894c  mov     r8d, edx
0x18000894f  and     r8d, 4
0x180008953  jnz     short loc_180008967
0x180008955  btr     ecx, 0Ah
0x180008959  mov     eax, ebx
0x18000895b  and     eax, 400h
0x180008960  or      ecx, eax
0x180008962  or      ecx, 4
0x180008965  mov     [rdi], ecx
0x180008967  mov     eax, edx
0x180008969  lock cmpxchg [rsi], ecx
0x18000896d  jnz     short loc_180008926
0x18000896f  test    r8d, r8d
0x180008972  jnz     short loc_180008986
0x180008974  mov     r9d, ebp
0x180008977  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000897e  mov     rdx, rsi
0x180008981  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008986  mov     eax, [rdi]
0x180008988  test    al, 2
0x18000898a  jnz     short loc_18000899B
0x18000898c  and     eax, 0FFFFF63Eh
0x180008991  and     ebx, 9C1h
0x180008997  or      eax, ebx
0x180008999  mov     [rdi], eax
0x18000899b  mov     rbx, [rsp+38h+arg_10]
0x1800089a0  mov     rax, rdi
0x1800089a3  add     rsp, 20h
0x1800089a7  pop     rdi
0x1800089a8  pop     rsi
0x1800089a9  pop     rbp
0x1800089aa  retn
```
