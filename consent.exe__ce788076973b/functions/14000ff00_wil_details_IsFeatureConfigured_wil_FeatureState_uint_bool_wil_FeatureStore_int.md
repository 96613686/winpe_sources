# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x14000ff00`
- end: `0x14000ffde`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `222`
- prototype: `bool __fastcall(wil::details *, __int64, unsigned __int8, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000fe90`

## callees

- `0x14000ff00`
- `0x140014c90`
- `0x140017a74`
- `0x140018254`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(wil::details *a1, __int64 a2, unsigned __int8 a3, int a4, _DWORD *a5)
{
  unsigned int v5; // edi
  unsigned int v6; // esi
  __int64 *v7; // rbx
  unsigned int v10; // eax
  unsigned int v11; // r14d
  int v12; // eax
  __int64 v13; // r8
  bool v14; // di
  char v15; // dl
  unsigned int v16; // [rsp+58h] [rbp+20h] BYREF

  v5 = a3;
  v6 = a2;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    *a5 = 1;
    return (unsigned int)wil_RtlStagingConfig_QueryFeatureState(a1, a2, a3, 0) != 0;
  }
  else
  {
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v16 = 0;
    v11 = v10;
    *a5 = 1;
    v12 = wil_RtlStagingConfig_QueryFeatureState(a1, v6, v5, &v16);
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
0x14000ff00  mov     [rsp+arg_0], rbx
0x14000ff05  mov     [rsp+arg_8], rbp
0x14000ff0a  push    rsi
0x14000ff0b  push    rdi
0x14000ff0c  push    r14
0x14000ff0e  sub     rsp, 20h
0x14000ff12  test    r9d, r9d
0x14000ff15  movzx   edi, r8b
0x14000ff19  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x14000ff20  mov     esi, edx
0x14000ff22  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x14000ff29  mov     rbp, rcx
0x14000ff2c  cmovnz  rbx, rax
0x14000ff30  mov     r9d, [rbx]
0x14000ff33  mov     eax, r9d
0x14000ff36  and     al, 3
0x14000ff38  cmp     al, 2
0x14000ff3a  jnz     short loc_14000FF43
0x14000ff3c  xor     al, al
0x14000ff3e  jmp     loc_14000FFCB
0x14000ff43  test    r9b, 2
0x14000ff47  jnz     short loc_14000FFB0
0x14000ff49  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000ff4e  mov     rcx, [rsp+38h+arg_20]
0x14000ff53  lea     r9, [rsp+38h+arg_18]
0x14000ff58  mov     r8d, edi
0x14000ff5b  mov     [rsp+38h+arg_18], 0
0x14000ff63  mov     edx, esi
0x14000ff65  mov     r14d, eax
0x14000ff68  mov     dword ptr [rcx], 1
0x14000ff6e  mov     rcx, rbp
0x14000ff71  call    wil_RtlStagingConfig_QueryFeatureState
0x14000ff76  mov     r8d, [rsp+38h+arg_18]
0x14000ff7b  test    eax, eax
0x14000ff7d  mov     ecx, r8d
0x14000ff80  setnz   dil
0x14000ff84  neg     ecx
0x14000ff86  sbb     edx, edx
0x14000ff88  neg     edx
0x14000ff8a  add     edx, 6
0x14000ff8d  xchg    edx, [rbx]
0x14000ff8f  test    r8d, r8d
0x14000ff92  jnz     short loc_14000FFAB
0x14000ff94  test    dl, 4
0x14000ff97  jnz     short loc_14000FFAB
0x14000ff99  mov     r9d, r14d
0x14000ff9c  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000ffa3  mov     rdx, rbx
0x14000ffa6  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000ffab  mov     al, dil
0x14000ffae  jmp     short loc_14000FFCB
0x14000ffb0  mov     rax, [rsp+38h+arg_20]
0x14000ffb5  mov     r8d, edi
0x14000ffb8  xor     r9d, r9d
0x14000ffbb  mov     dword ptr [rax], 1
0x14000ffc1  call    wil_RtlStagingConfig_QueryFeatureState
0x14000ffc6  test    eax, eax
0x14000ffc8  setnz   al
0x14000ffcb  mov     rbx, [rsp+38h+arg_0]
0x14000ffd0  mov     rbp, [rsp+38h+arg_8]
0x14000ffd5  add     rsp, 20h
0x14000ffd9  pop     r14
0x14000ffdb  pop     rdi
0x14000ffdc  pop     rsi
0x14000ffdd  retn
```
