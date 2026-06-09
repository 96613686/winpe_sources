# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180007c14`
- end: `0x180007cf4`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007ba0`

## callees

- `0x180007c14`
- `0x180007cfc`
- `0x180007e28`
- `0x18000949c`

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
        wil::details::g_enabledStateManager,
        v7,
        0,
        v11);
    return v14;
  }
}

```

## disassembly

```asm
0x180007c14  mov     [rsp+arg_0], rbx
0x180007c19  mov     [rsp+arg_8], rbp
0x180007c1e  push    rsi
0x180007c1f  push    rdi
0x180007c20  push    r14
0x180007c22  sub     rsp, 20h
0x180007c26  test    r9d, r9d
0x180007c29  movzx   edi, r8b
0x180007c2d  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180007c34  mov     esi, edx
0x180007c36  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180007c3d  mov     rbp, rcx
0x180007c40  cmovnz  rbx, rax
0x180007c44  mov     r9d, [rbx]
0x180007c47  mov     eax, r9d
0x180007c4a  and     al, 3
0x180007c4c  cmp     al, 2
0x180007c4e  jnz     short loc_180007CB5
0x180007c50  xor     al, al
0x180007c52  jmp     short loc_180007CA2
0x180007c54  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180007c59  mov     rcx, [rsp+38h+arg_20]
0x180007c5e  lea     r9, [rsp+38h+arg_18]
0x180007c63  mov     r8d, edi
0x180007c66  mov     [rsp+38h+arg_18], 0
0x180007c6e  mov     edx, esi
0x180007c70  mov     r14d, eax
0x180007c73  mov     dword ptr [rcx], 1
0x180007c79  mov     rcx, rbp
0x180007c7c  call    wil_RtlStagingConfig_QueryFeatureState
0x180007c81  mov     r8d, [rsp+38h+arg_18]
0x180007c86  test    eax, eax
0x180007c88  mov     ecx, r8d
0x180007c8b  setnz   dil
0x180007c8f  neg     ecx
0x180007c91  sbb     edx, edx
0x180007c93  neg     edx
0x180007c95  add     edx, 6
0x180007c98  xchg    edx, [rbx]
0x180007c9a  test    r8d, r8d
0x180007c9d  jz      short loc_180007CD8
0x180007c9f  mov     al, dil
0x180007ca2  mov     rbx, [rsp+38h+arg_0]
0x180007ca7  mov     rbp, [rsp+38h+arg_8]
0x180007cac  add     rsp, 20h
0x180007cb0  pop     r14
0x180007cb2  pop     rdi
0x180007cb3  pop     rsi
0x180007cb4  retn
0x180007cb5  test    r9b, 2
0x180007cb9  jz      short loc_180007C54
0x180007cbb  mov     rax, [rsp+38h+arg_20]
0x180007cc0  mov     r8d, edi
0x180007cc3  xor     r9d, r9d
0x180007cc6  mov     dword ptr [rax], 1
0x180007ccc  call    wil_RtlStagingConfig_QueryFeatureState
0x180007cd1  test    eax, eax
0x180007cd3  setnz   al
0x180007cd6  jmp     short loc_180007CA2
0x180007cd8  test    dl, 4
0x180007cdb  jnz     short loc_180007C9F
0x180007cdd  mov     r9d, r14d
0x180007ce0  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180007ce7  xor     r8d, r8d
0x180007cea  mov     rdx, rbx
0x180007ced  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180007cf2  jmp     short loc_180007C9F
```
