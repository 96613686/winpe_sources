# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000ded4`
- end: `0x18000dfb7`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180013860`

## callees

- `0x18000bdd8`
- `0x18000ded4`
- `0x180012fb4`
- `0x18001c398`

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
  __int64 v9; // r9
  unsigned int v11; // r14d
  __int64 v12; // r9
  int v13; // eax
  __int64 v14; // rdx
  bool v15; // di
  char v16; // r8
  unsigned int v17; // [rsp+68h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  v9 = *(unsigned int *)v7;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (v9 & 2) != 0 )
    return (unsigned int)wil_QueryFeatureState((__int64)a1, a2, a3, v9, 0, a5) != 0;
  v17 = 1;
  v11 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v13 = wil_QueryFeatureState((__int64)a1, a2, v5, v12, &v17, a5);
  v14 = v17;
  v15 = v13 != 0;
  v16 = _InterlockedExchange((volatile __int32 *)v7, (v17 != 0) + 6);
  if ( !(_DWORD)v14 && (v16 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, v14, v11);
  return v15;
}

```

## disassembly

```asm
0x18000ded4  mov     [rsp+arg_0], rbx
0x18000ded9  mov     [rsp+arg_8], rbp
0x18000dede  push    rsi
0x18000dedf  push    rdi
0x18000dee0  push    r14
0x18000dee2  sub     rsp, 30h
0x18000dee6  test    r9d, r9d
0x18000dee9  movzx   edi, r8b
0x18000deed  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000def4  mov     esi, edx
0x18000def6  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18000defd  mov     rbp, rcx
0x18000df00  cmovnz  rbx, rax
0x18000df04  mov     r9d, [rbx]
0x18000df07  mov     eax, r9d
0x18000df0a  and     al, 3
0x18000df0c  cmp     al, 2
0x18000df0e  jnz     short loc_18000DF17
0x18000df10  xor     al, al
0x18000df12  jmp     loc_18000DFA3
0x18000df17  test    r9b, 2
0x18000df1b  jnz     short loc_18000DF83
0x18000df1d  mov     [rsp+48h+arg_18], 1
0x18000df25  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000df2a  mov     rcx, [rsp+48h+arg_20]
0x18000df2f  mov     r14d, eax
0x18000df32  mov     [rsp+48h+var_20], rcx
0x18000df37  lea     rax, [rsp+48h+arg_18]
0x18000df3c  mov     rcx, rbp
0x18000df3f  mov     [rsp+48h+var_28], rax
0x18000df44  mov     r8d, edi
0x18000df47  mov     edx, esi
0x18000df49  call    wil_QueryFeatureState
0x18000df4e  mov     edx, [rsp+48h+arg_18]
0x18000df52  test    eax, eax
0x18000df54  mov     ecx, edx
0x18000df56  setnz   dil
0x18000df5a  neg     ecx
0x18000df5c  sbb     r8d, r8d
0x18000df5f  neg     r8d
0x18000df62  add     r8d, 6
0x18000df66  xchg    r8d, [rbx]
0x18000df69  test    edx, edx
0x18000df6b  jnz     short loc_18000DF7E
0x18000df6d  test    r8b, 4
0x18000df71  jnz     short loc_18000DF7E
0x18000df73  mov     r8d, r14d
0x18000df76  mov     rcx, rbx
0x18000df79  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000df7e  mov     al, dil
0x18000df81  jmp     short loc_18000DFA3
0x18000df83  mov     rax, [rsp+48h+arg_20]
0x18000df88  mov     r8d, edi
0x18000df8b  mov     [rsp+48h+var_20], rax
0x18000df90  mov     [rsp+48h+var_28], 0
0x18000df99  call    wil_QueryFeatureState
0x18000df9e  test    eax, eax
0x18000dfa0  setnz   al
0x18000dfa3  mov     rbx, [rsp+48h+arg_0]
0x18000dfa8  mov     rbp, [rsp+48h+arg_8]
0x18000dfad  add     rsp, 30h
0x18000dfb1  pop     r14
0x18000dfb3  pop     rdi
0x18000dfb4  pop     rsi
0x18000dfb5  retn
```
