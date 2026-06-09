# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180013924`
- end: `0x180013a0b`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `231`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800152f0`

## callees

- `0x18000d520`
- `0x180013924`
- `0x180014db0`
- `0x180015c4c`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(wil::details *a1, int a2, unsigned __int8 a3, int a4, __int64 a5)
{
  int v5; // edi
  __int64 *v7; // rbx
  int v8; // ebp
  volatile __int32 v9; // r9d
  unsigned int v11; // r14d
  int v12; // r9d
  int FeatureState; // eax
  __int64 v14; // r8
  bool v15; // di
  char v16; // dl
  unsigned int v17; // [rsp+68h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  v8 = (int)a1;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  v9 = *(_DWORD *)v7;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (v9 & 2) != 0 )
    return (unsigned int)wil_QueryFeatureState((_DWORD)a1, a2, a3, v9, 0, a5) != 0;
  v17 = 1;
  v11 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  FeatureState = wil_QueryFeatureState(v8, a2, v5, v12, (__int64)&v17, a5);
  v14 = v17;
  v15 = FeatureState != 0;
  v16 = _InterlockedExchange((volatile __int32 *)v7, (v17 != 0) + 6);
  if ( !(_DWORD)v14 && (v16 & 4) == 0 )
    wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
      &wil::details::g_enabledStateManager,
      v7,
      v14,
      v11);
  return v15;
}

```

## disassembly

```asm
0x180013924  mov     [rsp+arg_0], rbx
0x180013929  mov     [rsp+arg_8], rbp
0x18001392e  push    rsi
0x18001392f  push    rdi
0x180013930  push    r14
0x180013932  sub     rsp, 30h
0x180013936  test    r9d, r9d
0x180013939  movzx   edi, r8b
0x18001393d  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180013944  mov     esi, edx
0x180013946  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18001394d  mov     rbp, rcx
0x180013950  cmovnz  rbx, rax
0x180013954  mov     r9d, [rbx]
0x180013957  mov     eax, r9d
0x18001395a  and     al, 3
0x18001395c  cmp     al, 2
0x18001395e  jnz     short loc_180013967
0x180013960  xor     al, al
0x180013962  jmp     loc_1800139F8
0x180013967  test    r9b, 2
0x18001396b  jnz     short loc_1800139D8
0x18001396d  mov     [rsp+48h+arg_18], 1
0x180013975  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001397a  mov     rcx, [rsp+48h+arg_20]
0x18001397f  mov     r14d, eax
0x180013982  mov     [rsp+48h+var_20], rcx
0x180013987  lea     rax, [rsp+48h+arg_18]
0x18001398c  mov     rcx, rbp
0x18001398f  mov     [rsp+48h+var_28], rax
0x180013994  mov     r8d, edi
0x180013997  mov     edx, esi
0x180013999  call    wil_QueryFeatureState
0x18001399e  mov     r8d, [rsp+48h+arg_18]
0x1800139a3  test    eax, eax
0x1800139a5  mov     ecx, r8d
0x1800139a8  setnz   dil
0x1800139ac  neg     ecx
0x1800139ae  sbb     edx, edx
0x1800139b0  neg     edx
0x1800139b2  add     edx, 6
0x1800139b5  xchg    edx, [rbx]
0x1800139b7  test    r8d, r8d
0x1800139ba  jnz     short loc_1800139D3
0x1800139bc  test    dl, 4
0x1800139bf  jnz     short loc_1800139D3
0x1800139c1  mov     r9d, r14d
0x1800139c4  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800139cb  mov     rdx, rbx
0x1800139ce  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800139d3  mov     al, dil
0x1800139d6  jmp     short loc_1800139F8
0x1800139d8  mov     rax, [rsp+48h+arg_20]
0x1800139dd  mov     r8d, edi
0x1800139e0  mov     [rsp+48h+var_20], rax
0x1800139e5  mov     [rsp+48h+var_28], 0
0x1800139ee  call    wil_QueryFeatureState
0x1800139f3  test    eax, eax
0x1800139f5  setnz   al
0x1800139f8  mov     rbx, [rsp+48h+arg_0]
0x1800139fd  mov     rbp, [rsp+48h+arg_8]
0x180013a02  add     rsp, 30h
0x180013a06  pop     r14
0x180013a08  pop     rdi
0x180013a09  pop     rsi
0x180013a0a  retn
```
