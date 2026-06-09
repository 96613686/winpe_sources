# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180012370`
- end: `0x18001244e`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180014c20`

## callees

- `0x1800110e8`
- `0x180012370`
- `0x180014608`
- `0x1800160bc`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(
        wil::details *a1,
        unsigned int a2,
        unsigned __int8 a3,
        int a4,
        _DWORD *a5)
{
  int v5; // edi
  __int64 *v7; // rbx
  unsigned int v10; // eax
  unsigned int v11; // r14d
  int v12; // eax
  __int64 v13; // r8
  bool v14; // di
  char v15; // dl
  unsigned int v16; // [rsp+58h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    *a5 = 1;
    return (unsigned int)wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, a3, 0) != 0;
  }
  else
  {
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v16 = 0;
    v11 = v10;
    *a5 = 1;
    v12 = wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, v5, &v16);
    v13 = v16;
    v14 = v12 != 0;
    v15 = _InterlockedExchange((volatile __int32 *)v7, (v16 != 0) + 6);
    if ( !(_DWORD)v13 && (v15 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        v7,
        v13,
        v11);
    return v14;
  }
}

```

## disassembly

```asm
0x180012370  mov     [rsp+arg_0], rbx
0x180012375  mov     [rsp+arg_8], rbp
0x18001237a  push    rsi
0x18001237b  push    rdi
0x18001237c  push    r14
0x18001237e  sub     rsp, 20h
0x180012382  test    r9d, r9d
0x180012385  movzx   edi, r8b
0x180012389  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180012390  mov     esi, edx
0x180012392  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180012399  mov     rbp, rcx
0x18001239c  cmovnz  rbx, rax
0x1800123a0  mov     r9d, [rbx]
0x1800123a3  mov     eax, r9d
0x1800123a6  and     al, 3
0x1800123a8  cmp     al, 2
0x1800123aa  jnz     short loc_1800123B3
0x1800123ac  xor     al, al
0x1800123ae  jmp     loc_18001243B
0x1800123b3  test    r9b, 2
0x1800123b7  jnz     short loc_180012420
0x1800123b9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800123be  mov     rcx, [rsp+38h+arg_20]
0x1800123c3  lea     r9, [rsp+38h+arg_18]
0x1800123c8  mov     r8d, edi
0x1800123cb  mov     [rsp+38h+arg_18], 0
0x1800123d3  mov     edx, esi
0x1800123d5  mov     r14d, eax
0x1800123d8  mov     dword ptr [rcx], 1
0x1800123de  mov     rcx, rbp
0x1800123e1  call    wil_RtlStagingConfig_QueryFeatureState
0x1800123e6  mov     r8d, [rsp+38h+arg_18]
0x1800123eb  test    eax, eax
0x1800123ed  mov     ecx, r8d
0x1800123f0  setnz   dil
0x1800123f4  neg     ecx
0x1800123f6  sbb     edx, edx
0x1800123f8  neg     edx
0x1800123fa  add     edx, 6
0x1800123fd  xchg    edx, [rbx]
0x1800123ff  test    r8d, r8d
0x180012402  jnz     short loc_18001241B
0x180012404  test    dl, 4
0x180012407  jnz     short loc_18001241B
0x180012409  mov     r9d, r14d
0x18001240c  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180012413  mov     rdx, rbx
0x180012416  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001241b  mov     al, dil
0x18001241e  jmp     short loc_18001243B
0x180012420  mov     rax, [rsp+38h+arg_20]
0x180012425  mov     r8d, edi
0x180012428  xor     r9d, r9d
0x18001242b  mov     dword ptr [rax], 1
0x180012431  call    wil_RtlStagingConfig_QueryFeatureState
0x180012436  test    eax, eax
0x180012438  setnz   al
0x18001243b  mov     rbx, [rsp+38h+arg_0]
0x180012440  mov     rbp, [rsp+38h+arg_8]
0x180012445  add     rsp, 20h
0x180012449  pop     r14
0x18001244b  pop     rdi
0x18001244c  pop     rsi
0x18001244d  retn
```
