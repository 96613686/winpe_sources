# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x1800178ec`
- end: `0x1800179c5`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001a1b0`

## callees

- `0x180016c14`
- `0x1800178ec`
- `0x180019b00`
- `0x18001af34`

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
  int v13; // edx
  bool v14; // di
  char v15; // r8
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges((volatile signed __int32 *)v7, 0, v11);
    return v14;
  }
}

```

## disassembly

```asm
0x1800178ec  mov     [rsp+arg_0], rbx
0x1800178f1  mov     [rsp+arg_8], rbp
0x1800178f6  push    rsi
0x1800178f7  push    rdi
0x1800178f8  push    r14
0x1800178fa  sub     rsp, 20h
0x1800178fe  test    r9d, r9d
0x180017901  movzx   edi, r8b
0x180017905  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18001790c  mov     esi, edx
0x18001790e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180017915  mov     rbp, rcx
0x180017918  cmovnz  rbx, rax
0x18001791c  mov     r9d, [rbx]
0x18001791f  mov     eax, r9d
0x180017922  and     al, 3
0x180017924  cmp     al, 2
0x180017926  jnz     short loc_18001792F
0x180017928  xor     al, al
0x18001792a  jmp     loc_1800179B2
0x18001792f  test    r9b, 2
0x180017933  jnz     short loc_180017997
0x180017935  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001793a  mov     rcx, [rsp+38h+arg_20]
0x18001793f  lea     r9, [rsp+38h+arg_18]
0x180017944  mov     r8d, edi
0x180017947  mov     [rsp+38h+arg_18], 0
0x18001794f  mov     edx, esi
0x180017951  mov     r14d, eax
0x180017954  mov     dword ptr [rcx], 1
0x18001795a  mov     rcx, rbp
0x18001795d  call    wil_RtlStagingConfig_QueryFeatureState
0x180017962  mov     edx, [rsp+38h+arg_18]
0x180017966  test    eax, eax
0x180017968  mov     ecx, edx
0x18001796a  setnz   dil
0x18001796e  neg     ecx
0x180017970  sbb     r8d, r8d
0x180017973  neg     r8d
0x180017976  add     r8d, 6
0x18001797a  xchg    r8d, [rbx]
0x18001797d  test    edx, edx
0x18001797f  jnz     short loc_180017992
0x180017981  test    r8b, 4
0x180017985  jnz     short loc_180017992
0x180017987  mov     r8d, r14d
0x18001798a  mov     rcx, rbx
0x18001798d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180017992  mov     al, dil
0x180017995  jmp     short loc_1800179B2
0x180017997  mov     rax, [rsp+38h+arg_20]
0x18001799c  mov     r8d, edi
0x18001799f  xor     r9d, r9d
0x1800179a2  mov     dword ptr [rax], 1
0x1800179a8  call    wil_RtlStagingConfig_QueryFeatureState
0x1800179ad  test    eax, eax
0x1800179af  setnz   al
0x1800179b2  mov     rbx, [rsp+38h+arg_0]
0x1800179b7  mov     rbp, [rsp+38h+arg_8]
0x1800179bc  add     rsp, 20h
0x1800179c0  pop     r14
0x1800179c2  pop     rdi
0x1800179c3  pop     rsi
0x1800179c4  retn
```
