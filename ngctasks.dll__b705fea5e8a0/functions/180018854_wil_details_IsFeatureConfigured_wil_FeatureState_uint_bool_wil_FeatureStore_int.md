# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180018854`
- end: `0x18001893b`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `231`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001a630`

## callees

- `0x180017f9c`
- `0x180018854`
- `0x18001a280`
- `0x18001af70`

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
0x180018854  mov     [rsp+arg_0], rbx
0x180018859  mov     [rsp+arg_8], rbp
0x18001885e  push    rsi
0x18001885f  push    rdi
0x180018860  push    r14
0x180018862  sub     rsp, 30h
0x180018866  test    r9d, r9d
0x180018869  movzx   edi, r8b
0x18001886d  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180018874  mov     esi, edx
0x180018876  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18001887d  mov     rbp, rcx
0x180018880  cmovnz  rbx, rax
0x180018884  mov     r9d, [rbx]
0x180018887  mov     eax, r9d
0x18001888a  and     al, 3
0x18001888c  cmp     al, 2
0x18001888e  jnz     short loc_180018897
0x180018890  xor     al, al
0x180018892  jmp     loc_180018928
0x180018897  test    r9b, 2
0x18001889b  jnz     short loc_180018908
0x18001889d  mov     [rsp+48h+arg_18], 1
0x1800188a5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800188aa  mov     rcx, [rsp+48h+arg_20]
0x1800188af  mov     r14d, eax
0x1800188b2  mov     [rsp+48h+var_20], rcx
0x1800188b7  lea     rax, [rsp+48h+arg_18]
0x1800188bc  mov     rcx, rbp
0x1800188bf  mov     [rsp+48h+var_28], rax
0x1800188c4  mov     r8d, edi
0x1800188c7  mov     edx, esi
0x1800188c9  call    wil_QueryFeatureState
0x1800188ce  mov     r8d, [rsp+48h+arg_18]
0x1800188d3  test    eax, eax
0x1800188d5  mov     ecx, r8d
0x1800188d8  setnz   dil
0x1800188dc  neg     ecx
0x1800188de  sbb     edx, edx
0x1800188e0  neg     edx
0x1800188e2  add     edx, 6
0x1800188e5  xchg    edx, [rbx]
0x1800188e7  test    r8d, r8d
0x1800188ea  jnz     short loc_180018903
0x1800188ec  test    dl, 4
0x1800188ef  jnz     short loc_180018903
0x1800188f1  mov     r9d, r14d
0x1800188f4  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800188fb  mov     rdx, rbx
0x1800188fe  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180018903  mov     al, dil
0x180018906  jmp     short loc_180018928
0x180018908  mov     rax, [rsp+48h+arg_20]
0x18001890d  mov     r8d, edi
0x180018910  mov     [rsp+48h+var_20], rax
0x180018915  mov     [rsp+48h+var_28], 0
0x18001891e  call    wil_QueryFeatureState
0x180018923  test    eax, eax
0x180018925  setnz   al
0x180018928  mov     rbx, [rsp+48h+arg_0]
0x18001892d  mov     rbp, [rsp+48h+arg_8]
0x180018932  add     rsp, 30h
0x180018936  pop     r14
0x180018938  pop     rdi
0x180018939  pop     rsi
0x18001893a  retn
```
