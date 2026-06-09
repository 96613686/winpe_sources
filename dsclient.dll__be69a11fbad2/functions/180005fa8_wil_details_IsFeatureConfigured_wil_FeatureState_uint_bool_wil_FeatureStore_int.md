# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180005fa8`
- end: `0x180006081`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details *, __int64, unsigned __int8, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008600`

## callees

- `0x1800052d4`
- `0x180005fa8`
- `0x180007fd8`
- `0x180009144`

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
  __int64 v13; // rdx
  bool v14; // di
  char v15; // r8
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, v13, v11);
    return v14;
  }
}

```

## disassembly

```asm
0x180005fa8  mov     [rsp+arg_0], rbx
0x180005fad  mov     [rsp+arg_8], rbp
0x180005fb2  push    rsi
0x180005fb3  push    rdi
0x180005fb4  push    r14
0x180005fb6  sub     rsp, 20h
0x180005fba  test    r9d, r9d
0x180005fbd  movzx   edi, r8b
0x180005fc1  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180005fc8  mov     esi, edx
0x180005fca  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180005fd1  mov     rbp, rcx
0x180005fd4  cmovnz  rbx, rax
0x180005fd8  mov     r9d, [rbx]
0x180005fdb  mov     eax, r9d
0x180005fde  and     al, 3
0x180005fe0  cmp     al, 2
0x180005fe2  jnz     short loc_180005FEB
0x180005fe4  xor     al, al
0x180005fe6  jmp     loc_18000606E
0x180005feb  test    r9b, 2
0x180005fef  jnz     short loc_180006053
0x180005ff1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180005ff6  mov     rcx, [rsp+38h+arg_20]
0x180005ffb  lea     r9, [rsp+38h+arg_18]
0x180006000  mov     r8d, edi
0x180006003  mov     [rsp+38h+arg_18], 0
0x18000600b  mov     edx, esi
0x18000600d  mov     r14d, eax
0x180006010  mov     dword ptr [rcx], 1
0x180006016  mov     rcx, rbp
0x180006019  call    wil_RtlStagingConfig_QueryFeatureState
0x18000601e  mov     edx, [rsp+38h+arg_18]
0x180006022  test    eax, eax
0x180006024  mov     ecx, edx
0x180006026  setnz   dil
0x18000602a  neg     ecx
0x18000602c  sbb     r8d, r8d
0x18000602f  neg     r8d
0x180006032  add     r8d, 6
0x180006036  xchg    r8d, [rbx]
0x180006039  test    edx, edx
0x18000603b  jnz     short loc_18000604E
0x18000603d  test    r8b, 4
0x180006041  jnz     short loc_18000604E
0x180006043  mov     r8d, r14d
0x180006046  mov     rcx, rbx
0x180006049  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000604e  mov     al, dil
0x180006051  jmp     short loc_18000606E
0x180006053  mov     rax, [rsp+38h+arg_20]
0x180006058  mov     r8d, edi
0x18000605b  xor     r9d, r9d
0x18000605e  mov     dword ptr [rax], 1
0x180006064  call    wil_RtlStagingConfig_QueryFeatureState
0x180006069  test    eax, eax
0x18000606b  setnz   al
0x18000606e  mov     rbx, [rsp+38h+arg_0]
0x180006073  mov     rbp, [rsp+38h+arg_8]
0x180006078  add     rsp, 20h
0x18000607c  pop     r14
0x18000607e  pop     rdi
0x18000607f  pop     rsi
0x180006080  retn
```
