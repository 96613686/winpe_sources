# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000957c`
- end: `0x180009663`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c030`

## callees

- `0x180008684`
- `0x18000957c`
- `0x18000b9d8`
- `0x18000d0a4`

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
0x18000957c  mov     [rsp+arg_0], rbx
0x180009581  mov     [rsp+arg_8], rbp
0x180009586  push    rsi
0x180009587  push    rdi
0x180009588  push    r14
0x18000958a  sub     rsp, 30h
0x18000958e  test    r9d, r9d
0x180009591  movzx   edi, r8b
0x180009595  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000959c  mov     esi, edx
0x18000959e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1800095a5  mov     rbp, rcx
0x1800095a8  cmovnz  rbx, rax
0x1800095ac  mov     r9d, [rbx]
0x1800095af  mov     eax, r9d
0x1800095b2  and     al, 3
0x1800095b4  cmp     al, 2
0x1800095b6  jnz     short loc_1800095BF
0x1800095b8  xor     al, al
0x1800095ba  jmp     loc_180009650
0x1800095bf  test    r9b, 2
0x1800095c3  jnz     short loc_180009630
0x1800095c5  mov     [rsp+48h+arg_18], 1
0x1800095cd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800095d2  mov     rcx, [rsp+48h+arg_20]
0x1800095d7  mov     r14d, eax
0x1800095da  mov     [rsp+48h+var_20], rcx
0x1800095df  lea     rax, [rsp+48h+arg_18]
0x1800095e4  mov     rcx, rbp
0x1800095e7  mov     [rsp+48h+var_28], rax
0x1800095ec  mov     r8d, edi
0x1800095ef  mov     edx, esi
0x1800095f1  call    wil_QueryFeatureState
0x1800095f6  mov     r8d, [rsp+48h+arg_18]
0x1800095fb  test    eax, eax
0x1800095fd  mov     ecx, r8d
0x180009600  setnz   dil
0x180009604  neg     ecx
0x180009606  sbb     edx, edx
0x180009608  neg     edx
0x18000960a  add     edx, 6
0x18000960d  xchg    edx, [rbx]
0x18000960f  test    r8d, r8d
0x180009612  jnz     short loc_18000962B
0x180009614  test    dl, 4
0x180009617  jnz     short loc_18000962B
0x180009619  mov     r9d, r14d
0x18000961c  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180009623  mov     rdx, rbx
0x180009626  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000962b  mov     al, dil
0x18000962e  jmp     short loc_180009650
0x180009630  mov     rax, [rsp+48h+arg_20]
0x180009635  mov     r8d, edi
0x180009638  mov     [rsp+48h+var_20], rax
0x18000963d  mov     [rsp+48h+var_28], 0
0x180009646  call    wil_QueryFeatureState
0x18000964b  test    eax, eax
0x18000964d  setnz   al
0x180009650  mov     rbx, [rsp+48h+arg_0]
0x180009655  mov     rbp, [rsp+48h+arg_8]
0x18000965a  add     rsp, 30h
0x18000965e  pop     r14
0x180009660  pop     rdi
0x180009661  pop     rsi
0x180009662  retn
```
