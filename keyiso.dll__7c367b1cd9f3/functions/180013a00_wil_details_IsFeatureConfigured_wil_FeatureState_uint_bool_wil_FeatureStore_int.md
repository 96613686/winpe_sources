# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180013a00`
- end: `0x180013ade`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016280`

## callees

- `0x18000f9b0`
- `0x180012bf0`
- `0x180013a00`
- `0x180015be8`

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
  int v11; // r14d
  int v12; // eax
  int v13; // r8d
  bool v14; // di
  char v15; // dl
  int v16; // [rsp+58h] [rbp+20h] BYREF

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
    if ( !v13 && (v15 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)v7,
        0,
        v11);
    return v14;
  }
}

```

## disassembly

```asm
0x180013a00  mov     [rsp+arg_0], rbx
0x180013a05  mov     [rsp+arg_8], rbp
0x180013a0a  push    rsi
0x180013a0b  push    rdi
0x180013a0c  push    r14
0x180013a0e  sub     rsp, 20h
0x180013a12  test    r9d, r9d
0x180013a15  movzx   edi, r8b
0x180013a19  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180013a20  mov     esi, edx
0x180013a22  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180013a29  mov     rbp, rcx
0x180013a2c  cmovnz  rbx, rax
0x180013a30  mov     r9d, [rbx]
0x180013a33  mov     eax, r9d
0x180013a36  and     al, 3
0x180013a38  cmp     al, 2
0x180013a3a  jnz     short loc_180013A43
0x180013a3c  xor     al, al
0x180013a3e  jmp     loc_180013ACB
0x180013a43  test    r9b, 2
0x180013a47  jnz     short loc_180013AB0
0x180013a49  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013a4e  mov     rcx, [rsp+38h+arg_20]
0x180013a53  lea     r9, [rsp+38h+arg_18]
0x180013a58  mov     r8d, edi
0x180013a5b  mov     [rsp+38h+arg_18], 0
0x180013a63  mov     edx, esi
0x180013a65  mov     r14d, eax
0x180013a68  mov     dword ptr [rcx], 1
0x180013a6e  mov     rcx, rbp
0x180013a71  call    wil_RtlStagingConfig_QueryFeatureState
0x180013a76  mov     r8d, [rsp+38h+arg_18]
0x180013a7b  test    eax, eax
0x180013a7d  mov     ecx, r8d
0x180013a80  setnz   dil
0x180013a84  neg     ecx
0x180013a86  sbb     edx, edx
0x180013a88  neg     edx
0x180013a8a  add     edx, 6
0x180013a8d  xchg    edx, [rbx]
0x180013a8f  test    r8d, r8d
0x180013a92  jnz     short loc_180013AAB
0x180013a94  test    dl, 4
0x180013a97  jnz     short loc_180013AAB
0x180013a99  mov     r9d, r14d
0x180013a9c  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013aa3  mov     rdx, rbx
0x180013aa6  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013aab  mov     al, dil
0x180013aae  jmp     short loc_180013ACB
0x180013ab0  mov     rax, [rsp+38h+arg_20]
0x180013ab5  mov     r8d, edi
0x180013ab8  xor     r9d, r9d
0x180013abb  mov     dword ptr [rax], 1
0x180013ac1  call    wil_RtlStagingConfig_QueryFeatureState
0x180013ac6  test    eax, eax
0x180013ac8  setnz   al
0x180013acb  mov     rbx, [rsp+38h+arg_0]
0x180013ad0  mov     rbp, [rsp+38h+arg_8]
0x180013ad5  add     rsp, 20h
0x180013ad9  pop     r14
0x180013adb  pop     rdi
0x180013adc  pop     rsi
0x180013add  retn
```
