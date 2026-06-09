# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180025030`
- end: `0x180025122`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180028ac0`

## callees

- `0x1800239b0`
- `0x180025030`
- `0x180028210`
- `0x18002a080`

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
  int v10; // r14d
  __int64 v11; // r9
  int v12; // eax
  int v13; // edx
  bool v14; // di
  char v15; // r9
  int v16; // [rsp+68h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
    return (unsigned int)wil_QueryFeatureState((__int64)a1, a2, a3, 0, 0, a5) != 0;
  v16 = 1;
  v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v12 = wil_QueryFeatureState((__int64)a1, a2, v5, v11, &v16, a5);
  v13 = v16;
  v14 = v12 != 0;
  v15 = _InterlockedExchange((volatile __int32 *)v7, (v16 != 0) + 6);
  if ( !v13 && (v15 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges((volatile signed __int32 *)v7, 0, v10);
  return v14;
}

```

## disassembly

```asm
0x180025030  mov     [rsp+arg_8], rbx
0x180025035  push    rbp
0x180025036  push    rsi
0x180025037  push    rdi
0x180025038  sub     rsp, 30h
0x18002503c  test    r9d, r9d
0x18002503f  movzx   edi, r8b
0x180025043  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18002504a  mov     esi, edx
0x18002504c  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180025053  mov     rbp, rcx
0x180025056  cmovnz  rbx, rax
0x18002505a  mov     r9d, [rbx]
0x18002505d  mov     eax, r9d
0x180025060  and     al, 3
0x180025062  cmp     al, 2
0x180025064  jnz     short loc_180025075
0x180025066  xor     al, al
0x180025068  mov     rbx, [rsp+48h+arg_8]
0x18002506d  add     rsp, 30h
0x180025071  pop     rdi
0x180025072  pop     rsi
0x180025073  pop     rbp
0x180025074  retn
0x180025075  test    r9b, 2
0x180025079  jnz     short loc_1800250F6
0x18002507b  mov     [rsp+48h+arg_0], r14
0x180025080  mov     [rsp+48h+arg_18], 1
0x180025088  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002508d  mov     rcx, [rsp+48h+arg_20]
0x180025092  mov     r14d, eax
0x180025095  mov     [rsp+48h+var_20], rcx
0x18002509a  lea     rax, [rsp+48h+arg_18]
0x18002509f  mov     rcx, rbp
0x1800250a2  mov     [rsp+48h+var_28], rax
0x1800250a7  mov     r8d, edi
0x1800250aa  mov     edx, esi
0x1800250ac  call    wil_QueryFeatureState
0x1800250b1  mov     edx, [rsp+48h+arg_18]
0x1800250b5  test    eax, eax
0x1800250b7  setnz   dil
0x1800250bb  xor     r9d, r9d
0x1800250be  test    edx, edx
0x1800250c0  setnz   r9b
0x1800250c4  add     r9d, 6
0x1800250c8  xchg    r9d, [rbx]
0x1800250cb  test    edx, edx
0x1800250cd  jnz     short loc_1800250E0
0x1800250cf  test    r9b, 4
0x1800250d3  jnz     short loc_1800250E0
0x1800250d5  mov     r8d, r14d
0x1800250d8  mov     rcx, rbx
0x1800250db  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800250e0  mov     r14, [rsp+48h+arg_0]
0x1800250e5  movzx   eax, dil
0x1800250e9  mov     rbx, [rsp+48h+arg_8]
0x1800250ee  add     rsp, 30h
0x1800250f2  pop     rdi
0x1800250f3  pop     rsi
0x1800250f4  pop     rbp
0x1800250f5  retn
0x1800250f6  mov     rax, [rsp+48h+arg_20]
0x1800250fb  xor     r9d, r9d
0x1800250fe  mov     [rsp+48h+var_20], rax
0x180025103  mov     r8d, edi
0x180025106  mov     [rsp+48h+var_28], r9
0x18002510b  call    wil_QueryFeatureState
0x180025110  mov     rbx, [rsp+48h+arg_8]
0x180025115  test    eax, eax
0x180025117  setnz   al
0x18002511a  add     rsp, 30h
0x18002511e  pop     rdi
0x18002511f  pop     rsi
0x180025120  pop     rbp
0x180025121  retn
```
