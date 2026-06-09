# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180005890`
- end: `0x180005972`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800088f0`

## callees

- `0x180004618`
- `0x180005890`
- `0x180008250`
- `0x18000954c`

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
  int v11; // r14d
  __int64 v12; // r9
  int v13; // eax
  int v14; // edx
  bool v15; // di
  char v16; // r8
  int v17; // [rsp+68h] [rbp+20h] BYREF

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
  if ( !v14 && (v16 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges((volatile signed __int32 *)v7, 0, v11);
  return v15;
}

```

## disassembly

```asm
0x180005890  mov     [rsp+arg_0], rbx
0x180005895  mov     [rsp+arg_8], rbp
0x18000589a  push    rsi
0x18000589b  push    rdi
0x18000589c  push    r14
0x18000589e  sub     rsp, 30h
0x1800058a2  test    r9d, r9d
0x1800058a5  movzx   edi, r8b
0x1800058a9  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1800058b0  mov     esi, edx
0x1800058b2  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1800058b9  mov     rbp, rcx
0x1800058bc  cmovnz  rbx, rax
0x1800058c0  mov     r9d, [rbx]
0x1800058c3  mov     eax, r9d
0x1800058c6  and     al, 3
0x1800058c8  cmp     al, 2
0x1800058ca  jnz     short loc_1800058D3
0x1800058cc  xor     al, al
0x1800058ce  jmp     loc_18000595F
0x1800058d3  test    r9b, 2
0x1800058d7  jnz     short loc_18000593F
0x1800058d9  mov     [rsp+48h+arg_18], 1
0x1800058e1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800058e6  mov     rcx, [rsp+48h+arg_20]
0x1800058eb  mov     r14d, eax
0x1800058ee  mov     [rsp+48h+var_20], rcx
0x1800058f3  lea     rax, [rsp+48h+arg_18]
0x1800058f8  mov     rcx, rbp
0x1800058fb  mov     [rsp+48h+var_28], rax
0x180005900  mov     r8d, edi
0x180005903  mov     edx, esi
0x180005905  call    wil_QueryFeatureState
0x18000590a  mov     edx, [rsp+48h+arg_18]
0x18000590e  test    eax, eax
0x180005910  mov     ecx, edx
0x180005912  setnz   dil
0x180005916  neg     ecx
0x180005918  sbb     r8d, r8d
0x18000591b  neg     r8d
0x18000591e  add     r8d, 6
0x180005922  xchg    r8d, [rbx]
0x180005925  test    edx, edx
0x180005927  jnz     short loc_18000593A
0x180005929  test    r8b, 4
0x18000592d  jnz     short loc_18000593A
0x18000592f  mov     r8d, r14d
0x180005932  mov     rcx, rbx
0x180005935  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000593a  mov     al, dil
0x18000593d  jmp     short loc_18000595F
0x18000593f  mov     rax, [rsp+48h+arg_20]
0x180005944  mov     r8d, edi
0x180005947  mov     [rsp+48h+var_20], rax
0x18000594c  mov     [rsp+48h+var_28], 0
0x180005955  call    wil_QueryFeatureState
0x18000595a  test    eax, eax
0x18000595c  setnz   al
0x18000595f  mov     rbx, [rsp+48h+arg_0]
0x180005964  mov     rbp, [rsp+48h+arg_8]
0x180005969  add     rsp, 30h
0x18000596d  pop     r14
0x18000596f  pop     rdi
0x180005970  pop     rsi
0x180005971  retn
```
