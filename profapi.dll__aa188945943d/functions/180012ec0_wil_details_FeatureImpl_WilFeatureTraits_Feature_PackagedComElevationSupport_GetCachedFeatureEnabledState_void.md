# wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCachedFeatureEnabledState(void)

- ea: `0x180012ec0`
- end: `0x180012fa1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014fe0`
- `0x1800159f4`

## callees

- `0x180012c54`
- `0x180012ec0`
- `0x180013d68`
- `0x1800152fc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCachedFeatureEnabledState(
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
  wil::details *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_PackagedComElevationSupport__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_PackagedComElevationSupport__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_PackagedComElevationSupport__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_PackagedComElevationSupport__descriptor,
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
0x180012ec0  mov     [rsp+arg_10], rbx
0x180012ec5  mov     [rsp+arg_0], rcx
0x180012eca  push    rbp
0x180012ecb  push    rsi
0x180012ecc  push    rdi
0x180012ecd  sub     rsp, 20h
0x180012ed1  mov     rsi, cs:Feature_PackagedComElevationSupport__descriptor
0x180012ed8  mov     rdi, rdx
0x180012edb  mov     qword ptr [rdx], 0
0x180012ee2  mov     eax, [rsi]
0x180012ee4  mov     [rdx], eax
0x180012ee6  and     eax, 6
0x180012ee9  cmp     al, 6
0x180012eeb  jz      loc_180012F91
0x180012ef1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012ef6  lea     r8, [rsp+38h+arg_0]
0x180012efb  mov     dword ptr [rsp+38h+arg_0], 0
0x180012f03  lea     rdx, [rsp+38h+arg_8]
0x180012f08  mov     ebp, eax
0x180012f0a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCurrentFeatureEnabledState(int *)
0x180012f0f  mov     eax, [rdi]
0x180012f11  mov     rbx, [rsp+38h+arg_8]
0x180012f16  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012f1b  mov     edx, eax
0x180012f1d  mov     [rdi], eax
0x180012f1f  mov     ecx, eax
0x180012f21  jz      short loc_180012F3C
0x180012f23  test    dl, 2
0x180012f26  jnz     short loc_180012F3C
0x180012f28  and     ecx, 0FFFFF63Eh
0x180012f2e  mov     eax, ebx
0x180012f30  and     eax, 9C1h
0x180012f35  or      ecx, eax
0x180012f37  or      ecx, 2
0x180012f3a  mov     [rdi], ecx
0x180012f3c  mov     r8d, edx
0x180012f3f  and     r8d, 4
0x180012f43  jnz     short loc_180012F57
0x180012f45  btr     ecx, 0Ah
0x180012f49  mov     eax, ebx
0x180012f4b  and     eax, 400h
0x180012f50  or      ecx, eax
0x180012f52  or      ecx, 4
0x180012f55  mov     [rdi], ecx
0x180012f57  mov     eax, edx
0x180012f59  lock cmpxchg [rsi], ecx
0x180012f5d  jnz     short loc_180012F16
0x180012f5f  test    r8d, r8d
0x180012f62  jnz     short loc_180012F7C
0x180012f64  mov     r9d, ebp
0x180012f67  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180012f6e  mov     r8d, 3
0x180012f74  mov     rdx, rsi
0x180012f77  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012f7c  mov     eax, [rdi]
0x180012f7e  test    al, 2
0x180012f80  jnz     short loc_180012F91
0x180012f82  and     eax, 0FFFFF63Eh
0x180012f87  and     ebx, 9C1h
0x180012f8d  or      eax, ebx
0x180012f8f  mov     [rdi], eax
0x180012f91  mov     rbx, [rsp+38h+arg_10]
0x180012f96  mov     rax, rdi
0x180012f99  add     rsp, 20h
0x180012f9d  pop     rdi
0x180012f9e  pop     rsi
0x180012f9f  pop     rbp
0x180012fa0  retn
```
