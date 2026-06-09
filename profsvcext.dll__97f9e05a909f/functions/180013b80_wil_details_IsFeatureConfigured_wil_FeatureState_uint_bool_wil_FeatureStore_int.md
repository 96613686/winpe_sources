# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180013b80`
- end: `0x180013c59`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details *, __int64, unsigned __int8, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180015ab0`

## callees

- `0x180013270`
- `0x180013b80`
- `0x1800155a0`
- `0x1800176e4`

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
0x180013b80  mov     [rsp+arg_0], rbx
0x180013b85  mov     [rsp+arg_8], rbp
0x180013b8a  push    rsi
0x180013b8b  push    rdi
0x180013b8c  push    r14
0x180013b8e  sub     rsp, 20h
0x180013b92  test    r9d, r9d
0x180013b95  movzx   edi, r8b
0x180013b99  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180013ba0  mov     esi, edx
0x180013ba2  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180013ba9  mov     rbp, rcx
0x180013bac  cmovnz  rbx, rax
0x180013bb0  mov     r9d, [rbx]
0x180013bb3  mov     eax, r9d
0x180013bb6  and     al, 3
0x180013bb8  cmp     al, 2
0x180013bba  jnz     short loc_180013BC3
0x180013bbc  xor     al, al
0x180013bbe  jmp     loc_180013C46
0x180013bc3  test    r9b, 2
0x180013bc7  jnz     short loc_180013C2B
0x180013bc9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013bce  mov     rcx, [rsp+38h+arg_20]
0x180013bd3  lea     r9, [rsp+38h+arg_18]
0x180013bd8  mov     r8d, edi
0x180013bdb  mov     [rsp+38h+arg_18], 0
0x180013be3  mov     edx, esi
0x180013be5  mov     r14d, eax
0x180013be8  mov     dword ptr [rcx], 1
0x180013bee  mov     rcx, rbp
0x180013bf1  call    wil_RtlStagingConfig_QueryFeatureState
0x180013bf6  mov     edx, [rsp+38h+arg_18]
0x180013bfa  test    eax, eax
0x180013bfc  mov     ecx, edx
0x180013bfe  setnz   dil
0x180013c02  neg     ecx
0x180013c04  sbb     r8d, r8d
0x180013c07  neg     r8d
0x180013c0a  add     r8d, 6
0x180013c0e  xchg    r8d, [rbx]
0x180013c11  test    edx, edx
0x180013c13  jnz     short loc_180013C26
0x180013c15  test    r8b, 4
0x180013c19  jnz     short loc_180013C26
0x180013c1b  mov     r8d, r14d
0x180013c1e  mov     rcx, rbx
0x180013c21  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013c26  mov     al, dil
0x180013c29  jmp     short loc_180013C46
0x180013c2b  mov     rax, [rsp+38h+arg_20]
0x180013c30  mov     r8d, edi
0x180013c33  xor     r9d, r9d
0x180013c36  mov     dword ptr [rax], 1
0x180013c3c  call    wil_RtlStagingConfig_QueryFeatureState
0x180013c41  test    eax, eax
0x180013c43  setnz   al
0x180013c46  mov     rbx, [rsp+38h+arg_0]
0x180013c4b  mov     rbp, [rsp+38h+arg_8]
0x180013c50  add     rsp, 20h
0x180013c54  pop     r14
0x180013c56  pop     rdi
0x180013c57  pop     rsi
0x180013c58  retn
```
