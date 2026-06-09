# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000e0b0`
- end: `0x18000e18e`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `222`
- prototype: `bool __fastcall(wil::details *, __int64, unsigned __int8, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e040`

## callees

- `0x18000e0b0`
- `0x180012c54`
- `0x1800152fc`
- `0x180015e0c`

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
0x18000e0b0  mov     [rsp+arg_0], rbx
0x18000e0b5  mov     [rsp+arg_8], rbp
0x18000e0ba  push    rsi
0x18000e0bb  push    rdi
0x18000e0bc  push    r14
0x18000e0be  sub     rsp, 20h
0x18000e0c2  test    r9d, r9d
0x18000e0c5  movzx   edi, r8b
0x18000e0c9  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000e0d0  mov     esi, edx
0x18000e0d2  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18000e0d9  mov     rbp, rcx
0x18000e0dc  cmovnz  rbx, rax
0x18000e0e0  mov     r9d, [rbx]
0x18000e0e3  mov     eax, r9d
0x18000e0e6  and     al, 3
0x18000e0e8  cmp     al, 2
0x18000e0ea  jnz     short loc_18000E0F3
0x18000e0ec  xor     al, al
0x18000e0ee  jmp     loc_18000E17B
0x18000e0f3  test    r9b, 2
0x18000e0f7  jnz     short loc_18000E160
0x18000e0f9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e0fe  mov     rcx, [rsp+38h+arg_20]
0x18000e103  lea     r9, [rsp+38h+arg_18]
0x18000e108  mov     r8d, edi
0x18000e10b  mov     [rsp+38h+arg_18], 0
0x18000e113  mov     edx, esi
0x18000e115  mov     r14d, eax
0x18000e118  mov     dword ptr [rcx], 1
0x18000e11e  mov     rcx, rbp
0x18000e121  call    wil_RtlStagingConfig_QueryFeatureState
0x18000e126  mov     r8d, [rsp+38h+arg_18]
0x18000e12b  test    eax, eax
0x18000e12d  mov     ecx, r8d
0x18000e130  setnz   dil
0x18000e134  neg     ecx
0x18000e136  sbb     edx, edx
0x18000e138  neg     edx
0x18000e13a  add     edx, 6
0x18000e13d  xchg    edx, [rbx]
0x18000e13f  test    r8d, r8d
0x18000e142  jnz     short loc_18000E15B
0x18000e144  test    dl, 4
0x18000e147  jnz     short loc_18000E15B
0x18000e149  mov     r9d, r14d
0x18000e14c  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000e153  mov     rdx, rbx
0x18000e156  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e15b  mov     al, dil
0x18000e15e  jmp     short loc_18000E17B
0x18000e160  mov     rax, [rsp+38h+arg_20]
0x18000e165  mov     r8d, edi
0x18000e168  xor     r9d, r9d
0x18000e16b  mov     dword ptr [rax], 1
0x18000e171  call    wil_RtlStagingConfig_QueryFeatureState
0x18000e176  test    eax, eax
0x18000e178  setnz   al
0x18000e17b  mov     rbx, [rsp+38h+arg_0]
0x18000e180  mov     rbp, [rsp+38h+arg_8]
0x18000e185  add     rsp, 20h
0x18000e189  pop     r14
0x18000e18b  pop     rdi
0x18000e18c  pop     rsi
0x18000e18d  retn
```
