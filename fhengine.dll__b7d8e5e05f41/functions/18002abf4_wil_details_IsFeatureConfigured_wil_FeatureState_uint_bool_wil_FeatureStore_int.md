# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18002abf4`
- end: `0x18002accd`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details *, __int64, unsigned __int8, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002ddb0`

## callees

- `0x180028ab4`
- `0x18002abf4`
- `0x18002d7b8`
- `0x18002ebbc`

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
0x18002abf4  mov     [rsp+arg_0], rbx
0x18002abf9  mov     [rsp+arg_8], rbp
0x18002abfe  push    rsi
0x18002abff  push    rdi
0x18002ac00  push    r14
0x18002ac02  sub     rsp, 20h
0x18002ac06  test    r9d, r9d
0x18002ac09  movzx   edi, r8b
0x18002ac0d  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18002ac14  mov     esi, edx
0x18002ac16  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18002ac1d  mov     rbp, rcx
0x18002ac20  cmovnz  rbx, rax
0x18002ac24  mov     r9d, [rbx]
0x18002ac27  mov     eax, r9d
0x18002ac2a  and     al, 3
0x18002ac2c  cmp     al, 2
0x18002ac2e  jnz     short loc_18002AC37
0x18002ac30  xor     al, al
0x18002ac32  jmp     loc_18002ACBA
0x18002ac37  test    r9b, 2
0x18002ac3b  jnz     short loc_18002AC9F
0x18002ac3d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002ac42  mov     rcx, [rsp+38h+arg_20]
0x18002ac47  lea     r9, [rsp+38h+arg_18]
0x18002ac4c  mov     r8d, edi
0x18002ac4f  mov     [rsp+38h+arg_18], 0
0x18002ac57  mov     edx, esi
0x18002ac59  mov     r14d, eax
0x18002ac5c  mov     dword ptr [rcx], 1
0x18002ac62  mov     rcx, rbp
0x18002ac65  call    wil_RtlStagingConfig_QueryFeatureState
0x18002ac6a  mov     edx, [rsp+38h+arg_18]
0x18002ac6e  test    eax, eax
0x18002ac70  mov     ecx, edx
0x18002ac72  setnz   dil
0x18002ac76  neg     ecx
0x18002ac78  sbb     r8d, r8d
0x18002ac7b  neg     r8d
0x18002ac7e  add     r8d, 6
0x18002ac82  xchg    r8d, [rbx]
0x18002ac85  test    edx, edx
0x18002ac87  jnz     short loc_18002AC9A
0x18002ac89  test    r8b, 4
0x18002ac8d  jnz     short loc_18002AC9A
0x18002ac8f  mov     r8d, r14d
0x18002ac92  mov     rcx, rbx
0x18002ac95  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002ac9a  mov     al, dil
0x18002ac9d  jmp     short loc_18002ACBA
0x18002ac9f  mov     rax, [rsp+38h+arg_20]
0x18002aca4  mov     r8d, edi
0x18002aca7  xor     r9d, r9d
0x18002acaa  mov     dword ptr [rax], 1
0x18002acb0  call    wil_RtlStagingConfig_QueryFeatureState
0x18002acb5  test    eax, eax
0x18002acb7  setnz   al
0x18002acba  mov     rbx, [rsp+38h+arg_0]
0x18002acbf  mov     rbp, [rsp+38h+arg_8]
0x18002acc4  add     rsp, 20h
0x18002acc8  pop     r14
0x18002acca  pop     rdi
0x18002accb  pop     rsi
0x18002accc  retn
```
