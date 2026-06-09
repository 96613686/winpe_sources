# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18001e3b8`
- end: `0x18001e48e`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180025e80`

## callees

- `0x18001d144`
- `0x18001e3b8`
- `0x180025644`
- `0x180026ed4`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(
        wil::details *a1,
        unsigned int a2,
        unsigned __int8 a3,
        __int64 a4,
        _DWORD *a5)
{
  int v5; // edi
  __int64 *v7; // rbx
  unsigned int v10; // r14d
  __int64 v11; // r9
  bool v12; // di
  char v13; // dl
  int v14; // [rsp+68h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( (_DWORD)a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 2) != 0 )
    return (*(_DWORD *)v7 & 1) != 0 && (unsigned int)wil_QueryFeatureState((__int64)a1, a2, a3, a4, 0, a5) != 0;
  v14 = 1;
  v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v12 = (unsigned int)wil_QueryFeatureState((__int64)a1, a2, v5, v11, &v14, a5) != 0;
  v13 = _InterlockedExchange((volatile __int32 *)v7, (v14 != 0) + 6);
  if ( !v14 && (v13 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, 0, v10);
  return v12;
}

```

## disassembly

```asm
0x18001e3b8  mov     [rsp+arg_0], rbx
0x18001e3bd  mov     [rsp+arg_8], rbp
0x18001e3c2  push    rsi
0x18001e3c3  push    rdi
0x18001e3c4  push    r14
0x18001e3c6  sub     rsp, 30h
0x18001e3ca  test    r9d, r9d
0x18001e3cd  movzx   edi, r8b
0x18001e3d1  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18001e3d8  mov     esi, edx
0x18001e3da  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18001e3e1  mov     rbp, rcx
0x18001e3e4  cmovnz  rbx, rax
0x18001e3e8  mov     eax, [rbx]
0x18001e3ea  test    al, 2
0x18001e3ec  jz      short loc_18001E418
0x18001e3ee  test    al, 1
0x18001e3f0  jnz     short loc_18001E3F9
0x18001e3f2  xor     al, al
0x18001e3f4  jmp     loc_18001E47A
0x18001e3f9  mov     rax, [rsp+48h+arg_20]
0x18001e3fe  mov     r8d, edi
0x18001e401  mov     [rsp+48h+var_20], rax
0x18001e406  and     [rsp+48h+var_28], 0
0x18001e40c  call    wil_QueryFeatureState
0x18001e411  test    eax, eax
0x18001e413  setnz   al
0x18001e416  jmp     short loc_18001E47A
0x18001e418  mov     [rsp+48h+arg_18], 1
0x18001e420  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001e425  mov     rcx, [rsp+48h+arg_20]
0x18001e42a  mov     r14d, eax
0x18001e42d  mov     [rsp+48h+var_20], rcx
0x18001e432  lea     rax, [rsp+48h+arg_18]
0x18001e437  mov     rcx, rbp
0x18001e43a  mov     [rsp+48h+var_28], rax
0x18001e43f  mov     r8d, edi
0x18001e442  mov     edx, esi
0x18001e444  call    wil_QueryFeatureState
0x18001e449  mov     ecx, [rsp+48h+arg_18]
0x18001e44d  test    eax, eax
0x18001e44f  setnz   dil
0x18001e453  neg     ecx
0x18001e455  sbb     edx, edx
0x18001e457  neg     edx
0x18001e459  add     edx, 6
0x18001e45c  xchg    edx, [rbx]
0x18001e45e  cmp     [rsp+48h+arg_18], 0
0x18001e463  jnz     short loc_18001E477
0x18001e465  test    dl, 4
0x18001e468  jnz     short loc_18001E477
0x18001e46a  mov     r8d, r14d
0x18001e46d  xor     edx, edx
0x18001e46f  mov     rcx, rbx
0x18001e472  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001e477  mov     al, dil
0x18001e47a  mov     rbx, [rsp+48h+arg_0]
0x18001e47f  mov     rbp, [rsp+48h+arg_8]
0x18001e484  add     rsp, 30h
0x18001e488  pop     r14
0x18001e48a  pop     rdi
0x18001e48b  pop     rsi
0x18001e48c  retn
```
