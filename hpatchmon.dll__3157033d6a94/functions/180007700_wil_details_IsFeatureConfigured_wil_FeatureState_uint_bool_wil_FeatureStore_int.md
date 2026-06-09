# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180007700`
- end: `0x1800077e2`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000bfd0`

## callees

- `0x1800058f8`
- `0x180007700`
- `0x18000b7c8`
- `0x18000ce60`

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
  __int64 v14; // rdx
  bool v15; // di
  char v16; // r8
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
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, v14, v11);
  return v15;
}

```

## disassembly

```asm
0x180007700  mov     [rsp+arg_0], rbx
0x180007705  mov     [rsp+arg_8], rbp
0x18000770a  push    rsi
0x18000770b  push    rdi
0x18000770c  push    r14
0x18000770e  sub     rsp, 30h
0x180007712  test    r9d, r9d
0x180007715  movzx   edi, r8b
0x180007719  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180007720  mov     esi, edx
0x180007722  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180007729  mov     rbp, rcx
0x18000772c  cmovnz  rbx, rax
0x180007730  mov     r9d, [rbx]
0x180007733  mov     eax, r9d
0x180007736  and     al, 3
0x180007738  cmp     al, 2
0x18000773a  jnz     short loc_180007743
0x18000773c  xor     al, al
0x18000773e  jmp     loc_1800077CF
0x180007743  test    r9b, 2
0x180007747  jnz     short loc_1800077AF
0x180007749  mov     [rsp+48h+arg_18], 1
0x180007751  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180007756  mov     rcx, [rsp+48h+arg_20]
0x18000775b  mov     r14d, eax
0x18000775e  mov     [rsp+48h+var_20], rcx
0x180007763  lea     rax, [rsp+48h+arg_18]
0x180007768  mov     rcx, rbp
0x18000776b  mov     [rsp+48h+var_28], rax
0x180007770  mov     r8d, edi
0x180007773  mov     edx, esi
0x180007775  call    wil_QueryFeatureState
0x18000777a  mov     edx, [rsp+48h+arg_18]
0x18000777e  test    eax, eax
0x180007780  mov     ecx, edx
0x180007782  setnz   dil
0x180007786  neg     ecx
0x180007788  sbb     r8d, r8d
0x18000778b  neg     r8d
0x18000778e  add     r8d, 6
0x180007792  xchg    r8d, [rbx]
0x180007795  test    edx, edx
0x180007797  jnz     short loc_1800077AA
0x180007799  test    r8b, 4
0x18000779d  jnz     short loc_1800077AA
0x18000779f  mov     r8d, r14d
0x1800077a2  mov     rcx, rbx
0x1800077a5  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800077aa  mov     al, dil
0x1800077ad  jmp     short loc_1800077CF
0x1800077af  mov     rax, [rsp+48h+arg_20]
0x1800077b4  mov     r8d, edi
0x1800077b7  mov     [rsp+48h+var_20], rax
0x1800077bc  mov     [rsp+48h+var_28], 0
0x1800077c5  call    wil_QueryFeatureState
0x1800077ca  test    eax, eax
0x1800077cc  setnz   al
0x1800077cf  mov     rbx, [rsp+48h+arg_0]
0x1800077d4  mov     rbp, [rsp+48h+arg_8]
0x1800077d9  add     rsp, 30h
0x1800077dd  pop     r14
0x1800077df  pop     rdi
0x1800077e0  pop     rsi
0x1800077e1  retn
```
