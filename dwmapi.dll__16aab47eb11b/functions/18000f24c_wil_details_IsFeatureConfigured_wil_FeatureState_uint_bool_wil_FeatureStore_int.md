# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000f24c`
- end: `0x18000f32a`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180010520`

## callees

- `0x18000eb58`
- `0x18000f24c`
- `0x18001011c`
- `0x180010d0c`

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
    v7 = `wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
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
0x18000f24c  mov     [rsp+arg_0], rbx
0x18000f251  mov     [rsp+arg_8], rbp
0x18000f256  push    rsi
0x18000f257  push    rdi
0x18000f258  push    r14
0x18000f25a  sub     rsp, 20h
0x18000f25e  test    r9d, r9d
0x18000f261  movzx   edi, r8b
0x18000f265  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000f26c  mov     esi, edx
0x18000f26e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18000f275  mov     rbp, rcx
0x18000f278  cmovnz  rbx, rax
0x18000f27c  mov     r9d, [rbx]
0x18000f27f  mov     eax, r9d
0x18000f282  and     al, 3
0x18000f284  cmp     al, 2
0x18000f286  jnz     short loc_18000F28F
0x18000f288  xor     al, al
0x18000f28a  jmp     loc_18000F317
0x18000f28f  test    r9b, 2
0x18000f293  jnz     short loc_18000F2FC
0x18000f295  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f29a  mov     rcx, [rsp+38h+arg_20]
0x18000f29f  lea     r9, [rsp+38h+arg_18]
0x18000f2a4  mov     r8d, edi
0x18000f2a7  mov     [rsp+38h+arg_18], 0
0x18000f2af  mov     edx, esi
0x18000f2b1  mov     r14d, eax
0x18000f2b4  mov     dword ptr [rcx], 1
0x18000f2ba  mov     rcx, rbp
0x18000f2bd  call    wil_RtlStagingConfig_QueryFeatureState
0x18000f2c2  mov     r8d, [rsp+38h+arg_18]
0x18000f2c7  test    eax, eax
0x18000f2c9  mov     ecx, r8d
0x18000f2cc  setnz   dil
0x18000f2d0  neg     ecx
0x18000f2d2  sbb     edx, edx
0x18000f2d4  neg     edx
0x18000f2d6  add     edx, 6
0x18000f2d9  xchg    edx, [rbx]
0x18000f2db  test    r8d, r8d
0x18000f2de  jnz     short loc_18000F2F7
0x18000f2e0  test    dl, 4
0x18000f2e3  jnz     short loc_18000F2F7
0x18000f2e5  mov     r9d, r14d
0x18000f2e8  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000f2ef  mov     rdx, rbx
0x18000f2f2  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000f2f7  mov     al, dil
0x18000f2fa  jmp     short loc_18000F317
0x18000f2fc  mov     rax, [rsp+38h+arg_20]
0x18000f301  mov     r8d, edi
0x18000f304  xor     r9d, r9d
0x18000f307  mov     dword ptr [rax], 1
0x18000f30d  call    wil_RtlStagingConfig_QueryFeatureState
0x18000f312  test    eax, eax
0x18000f314  setnz   al
0x18000f317  mov     rbx, [rsp+38h+arg_0]
0x18000f31c  mov     rbp, [rsp+38h+arg_8]
0x18000f321  add     rsp, 20h
0x18000f325  pop     r14
0x18000f327  pop     rdi
0x18000f328  pop     rsi
0x18000f329  retn
```
