# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x1800067c0`
- end: `0x1800068a7`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009400`

## callees

- `0x180005510`
- `0x1800067c0`
- `0x180008db8`
- `0x18000a3fc`

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
0x1800067c0  mov     [rsp+arg_0], rbx
0x1800067c5  mov     [rsp+arg_8], rbp
0x1800067ca  push    rsi
0x1800067cb  push    rdi
0x1800067cc  push    r14
0x1800067ce  sub     rsp, 30h
0x1800067d2  test    r9d, r9d
0x1800067d5  movzx   edi, r8b
0x1800067d9  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1800067e0  mov     esi, edx
0x1800067e2  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1800067e9  mov     rbp, rcx
0x1800067ec  cmovnz  rbx, rax
0x1800067f0  mov     r9d, [rbx]
0x1800067f3  mov     eax, r9d
0x1800067f6  and     al, 3
0x1800067f8  cmp     al, 2
0x1800067fa  jnz     short loc_180006803
0x1800067fc  xor     al, al
0x1800067fe  jmp     loc_180006894
0x180006803  test    r9b, 2
0x180006807  jnz     short loc_180006874
0x180006809  mov     [rsp+48h+arg_18], 1
0x180006811  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180006816  mov     rcx, [rsp+48h+arg_20]
0x18000681b  mov     r14d, eax
0x18000681e  mov     [rsp+48h+var_20], rcx
0x180006823  lea     rax, [rsp+48h+arg_18]
0x180006828  mov     rcx, rbp
0x18000682b  mov     [rsp+48h+var_28], rax
0x180006830  mov     r8d, edi
0x180006833  mov     edx, esi
0x180006835  call    wil_QueryFeatureState
0x18000683a  mov     r8d, [rsp+48h+arg_18]
0x18000683f  test    eax, eax
0x180006841  mov     ecx, r8d
0x180006844  setnz   dil
0x180006848  neg     ecx
0x18000684a  sbb     edx, edx
0x18000684c  neg     edx
0x18000684e  add     edx, 6
0x180006851  xchg    edx, [rbx]
0x180006853  test    r8d, r8d
0x180006856  jnz     short loc_18000686F
0x180006858  test    dl, 4
0x18000685b  jnz     short loc_18000686F
0x18000685d  mov     r9d, r14d
0x180006860  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180006867  mov     rdx, rbx
0x18000686a  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000686f  mov     al, dil
0x180006872  jmp     short loc_180006894
0x180006874  mov     rax, [rsp+48h+arg_20]
0x180006879  mov     r8d, edi
0x18000687c  mov     [rsp+48h+var_20], rax
0x180006881  mov     [rsp+48h+var_28], 0
0x18000688a  call    wil_QueryFeatureState
0x18000688f  test    eax, eax
0x180006891  setnz   al
0x180006894  mov     rbx, [rsp+48h+arg_0]
0x180006899  mov     rbp, [rsp+48h+arg_8]
0x18000689e  add     rsp, 30h
0x1800068a2  pop     r14
0x1800068a4  pop     rdi
0x1800068a5  pop     rsi
0x1800068a6  retn
```
