# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180008ad0`
- end: `0x180008bb7`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a4d0`

## callees

- `0x1800085d8`
- `0x180008ad0`
- `0x18000a100`
- `0x18000ae20`

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
0x180008ad0  mov     [rsp+arg_0], rbx
0x180008ad5  mov     [rsp+arg_8], rbp
0x180008ada  push    rsi
0x180008adb  push    rdi
0x180008adc  push    r14
0x180008ade  sub     rsp, 30h
0x180008ae2  test    r9d, r9d
0x180008ae5  movzx   edi, r8b
0x180008ae9  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180008af0  mov     esi, edx
0x180008af2  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180008af9  mov     rbp, rcx
0x180008afc  cmovnz  rbx, rax
0x180008b00  mov     r9d, [rbx]
0x180008b03  mov     eax, r9d
0x180008b06  and     al, 3
0x180008b08  cmp     al, 2
0x180008b0a  jnz     short loc_180008B13
0x180008b0c  xor     al, al
0x180008b0e  jmp     loc_180008BA4
0x180008b13  test    r9b, 2
0x180008b17  jnz     short loc_180008B84
0x180008b19  mov     [rsp+48h+arg_18], 1
0x180008b21  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008b26  mov     rcx, [rsp+48h+arg_20]
0x180008b2b  mov     r14d, eax
0x180008b2e  mov     [rsp+48h+var_20], rcx
0x180008b33  lea     rax, [rsp+48h+arg_18]
0x180008b38  mov     rcx, rbp
0x180008b3b  mov     [rsp+48h+var_28], rax
0x180008b40  mov     r8d, edi
0x180008b43  mov     edx, esi
0x180008b45  call    wil_QueryFeatureState
0x180008b4a  mov     r8d, [rsp+48h+arg_18]
0x180008b4f  test    eax, eax
0x180008b51  mov     ecx, r8d
0x180008b54  setnz   dil
0x180008b58  neg     ecx
0x180008b5a  sbb     edx, edx
0x180008b5c  neg     edx
0x180008b5e  add     edx, 6
0x180008b61  xchg    edx, [rbx]
0x180008b63  test    r8d, r8d
0x180008b66  jnz     short loc_180008B7F
0x180008b68  test    dl, 4
0x180008b6b  jnz     short loc_180008B7F
0x180008b6d  mov     r9d, r14d
0x180008b70  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008b77  mov     rdx, rbx
0x180008b7a  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008b7f  mov     al, dil
0x180008b82  jmp     short loc_180008BA4
0x180008b84  mov     rax, [rsp+48h+arg_20]
0x180008b89  mov     r8d, edi
0x180008b8c  mov     [rsp+48h+var_20], rax
0x180008b91  mov     [rsp+48h+var_28], 0
0x180008b9a  call    wil_QueryFeatureState
0x180008b9f  test    eax, eax
0x180008ba1  setnz   al
0x180008ba4  mov     rbx, [rsp+48h+arg_0]
0x180008ba9  mov     rbp, [rsp+48h+arg_8]
0x180008bae  add     rsp, 30h
0x180008bb2  pop     r14
0x180008bb4  pop     rdi
0x180008bb5  pop     rsi
0x180008bb6  retn
```
