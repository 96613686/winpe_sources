# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x14000921c`
- end: `0x140009303`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000b320`

## callees

- `0x140008084`
- `0x14000921c`
- `0x14000aeac`
- `0x14000bf4c`

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
      wil::details::g_enabledStateManager,
      v7,
      v14,
      v11);
  return v15;
}

```

## disassembly

```asm
0x14000921c  mov     [rsp+arg_0], rbx
0x140009221  mov     [rsp+arg_8], rbp
0x140009226  push    rsi
0x140009227  push    rdi
0x140009228  push    r14
0x14000922a  sub     rsp, 30h
0x14000922e  test    r9d, r9d
0x140009231  movzx   edi, r8b
0x140009235  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x14000923c  mov     esi, edx
0x14000923e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x140009245  mov     rbp, rcx
0x140009248  cmovnz  rbx, rax
0x14000924c  mov     r9d, [rbx]
0x14000924f  mov     eax, r9d
0x140009252  and     al, 3
0x140009254  cmp     al, 2
0x140009256  jnz     short loc_14000925F
0x140009258  xor     al, al
0x14000925a  jmp     loc_1400092F0
0x14000925f  test    r9b, 2
0x140009263  jnz     short loc_1400092D0
0x140009265  mov     [rsp+48h+arg_18], 1
0x14000926d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140009272  mov     rcx, [rsp+48h+arg_20]
0x140009277  mov     r14d, eax
0x14000927a  mov     [rsp+48h+var_20], rcx
0x14000927f  lea     rax, [rsp+48h+arg_18]
0x140009284  mov     rcx, rbp
0x140009287  mov     [rsp+48h+var_28], rax
0x14000928c  mov     r8d, edi
0x14000928f  mov     edx, esi
0x140009291  call    wil_QueryFeatureState
0x140009296  mov     r8d, [rsp+48h+arg_18]
0x14000929b  test    eax, eax
0x14000929d  mov     ecx, r8d
0x1400092a0  setnz   dil
0x1400092a4  neg     ecx
0x1400092a6  sbb     edx, edx
0x1400092a8  neg     edx
0x1400092aa  add     edx, 6
0x1400092ad  xchg    edx, [rbx]
0x1400092af  test    r8d, r8d
0x1400092b2  jnz     short loc_1400092CB
0x1400092b4  test    dl, 4
0x1400092b7  jnz     short loc_1400092CB
0x1400092b9  mov     r9d, r14d
0x1400092bc  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400092c3  mov     rdx, rbx
0x1400092c6  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1400092cb  mov     al, dil
0x1400092ce  jmp     short loc_1400092F0
0x1400092d0  mov     rax, [rsp+48h+arg_20]
0x1400092d5  mov     r8d, edi
0x1400092d8  mov     [rsp+48h+var_20], rax
0x1400092dd  mov     [rsp+48h+var_28], 0
0x1400092e6  call    wil_QueryFeatureState
0x1400092eb  test    eax, eax
0x1400092ed  setnz   al
0x1400092f0  mov     rbx, [rsp+48h+arg_0]
0x1400092f5  mov     rbp, [rsp+48h+arg_8]
0x1400092fa  add     rsp, 30h
0x1400092fe  pop     r14
0x140009300  pop     rdi
0x140009301  pop     rsi
0x140009302  retn
```
