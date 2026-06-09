# wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowProcessingColorFiltersOnHardware>::GetCachedFeatureEnabledState(void)

- ea: `0x14002265c`
- end: `0x14002273f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowProcessingColorFiltersOnHardware@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002328c`

## callees

- `0x140006020`
- `0x14000a0d4`
- `0x14002265c`
- `0x140022748`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowProcessingColorFiltersOnHardware>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_AllowProcessingColorFiltersOnHardware__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_AllowProcessingColorFiltersOnHardware__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowProcessingColorFiltersOnHardware>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_AllowProcessingColorFiltersOnHardware__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !(_DWORD)v12 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_AllowProcessingColorFiltersOnHardware__descriptor,
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
0x14002265c  mov     [rsp+arg_10], rbx
0x140022661  mov     [rsp+arg_0], rcx
0x140022666  push    rbp
0x140022667  push    rsi
0x140022668  push    rdi
0x140022669  sub     rsp, 20h
0x14002266d  mov     rsi, cs:Feature_AllowProcessingColorFiltersOnHardware__descriptor
0x140022674  mov     rdi, rdx
0x140022677  mov     qword ptr [rdx], 0
0x14002267e  mov     eax, [rsi]
0x140022680  mov     [rdx], eax
0x140022682  and     eax, 6
0x140022685  cmp     al, 6
0x140022687  jz      loc_14002272F
0x14002268d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140022692  lea     r8, [rsp+38h+arg_0]
0x140022697  mov     dword ptr [rsp+38h+arg_0], 0
0x14002269f  lea     rdx, [rsp+38h+arg_8]
0x1400226a4  mov     ebp, eax
0x1400226a6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowProcessingColorFiltersOnHardware@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowProcessingColorFiltersOnHardware>::GetCurrentFeatureEnabledState(int *)
0x1400226ab  test    ebp, ebp
0x1400226ad  jnz     short loc_1400226B3
0x1400226af  mov     dword ptr [rsp+38h+arg_0], ebp
0x1400226b3  mov     eax, [rdi]
0x1400226b5  mov     rbx, [rsp+38h+arg_8]
0x1400226ba  cmp     dword ptr [rsp+38h+arg_0], 0
0x1400226bf  mov     edx, eax
0x1400226c1  mov     [rdi], eax
0x1400226c3  mov     ecx, eax
0x1400226c5  jz      short loc_1400226E0
0x1400226c7  test    dl, 2
0x1400226ca  jnz     short loc_1400226E0
0x1400226cc  and     ecx, 0FFFFF63Eh
0x1400226d2  mov     eax, ebx
0x1400226d4  and     eax, 9C1h
0x1400226d9  or      ecx, eax
0x1400226db  or      ecx, 2
0x1400226de  mov     [rdi], ecx
0x1400226e0  mov     r8d, edx
0x1400226e3  and     r8d, 4
0x1400226e7  jnz     short loc_1400226FB
0x1400226e9  btr     ecx, 0Ah
0x1400226ed  mov     eax, ebx
0x1400226ef  and     eax, 400h
0x1400226f4  or      ecx, eax
0x1400226f6  or      ecx, 4
0x1400226f9  mov     [rdi], ecx
0x1400226fb  mov     eax, edx
0x1400226fd  lock cmpxchg [rsi], ecx
0x140022701  jnz     short loc_1400226BA
0x140022703  test    r8d, r8d
0x140022706  jnz     short loc_14002271A
0x140022708  mov     r9d, ebp
0x14002270b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140022712  mov     rdx, rsi
0x140022715  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14002271a  mov     eax, [rdi]
0x14002271c  test    al, 2
0x14002271e  jnz     short loc_14002272F
0x140022720  and     eax, 0FFFFF63Eh
0x140022725  and     ebx, 9C1h
0x14002272b  or      eax, ebx
0x14002272d  mov     [rdi], eax
0x14002272f  mov     rbx, [rsp+38h+arg_10]
0x140022734  mov     rax, rdi
0x140022737  add     rsp, 20h
0x14002273b  pop     rdi
0x14002273c  pop     rsi
0x14002273d  pop     rbp
0x14002273e  retn
```
