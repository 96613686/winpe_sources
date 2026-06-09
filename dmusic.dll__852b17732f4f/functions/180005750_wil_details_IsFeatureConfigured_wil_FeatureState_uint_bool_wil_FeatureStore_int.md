# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180005750`
- end: `0x180005832`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008910`

## callees

- `0x180004638`
- `0x180005750`
- `0x180008218`
- `0x1800094e8`

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
0x180005750  mov     [rsp+arg_0], rbx
0x180005755  mov     [rsp+arg_8], rbp
0x18000575a  push    rsi
0x18000575b  push    rdi
0x18000575c  push    r14
0x18000575e  sub     rsp, 30h
0x180005762  test    r9d, r9d
0x180005765  movzx   edi, r8b
0x180005769  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180005770  mov     esi, edx
0x180005772  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180005779  mov     rbp, rcx
0x18000577c  cmovnz  rbx, rax
0x180005780  mov     r9d, [rbx]
0x180005783  mov     eax, r9d
0x180005786  and     al, 3
0x180005788  cmp     al, 2
0x18000578a  jnz     short loc_180005793
0x18000578c  xor     al, al
0x18000578e  jmp     loc_18000581F
0x180005793  test    r9b, 2
0x180005797  jnz     short loc_1800057FF
0x180005799  mov     [rsp+48h+arg_18], 1
0x1800057a1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800057a6  mov     rcx, [rsp+48h+arg_20]
0x1800057ab  mov     r14d, eax
0x1800057ae  mov     [rsp+48h+var_20], rcx
0x1800057b3  lea     rax, [rsp+48h+arg_18]
0x1800057b8  mov     rcx, rbp
0x1800057bb  mov     [rsp+48h+var_28], rax
0x1800057c0  mov     r8d, edi
0x1800057c3  mov     edx, esi
0x1800057c5  call    wil_QueryFeatureState
0x1800057ca  mov     edx, [rsp+48h+arg_18]
0x1800057ce  test    eax, eax
0x1800057d0  mov     ecx, edx
0x1800057d2  setnz   dil
0x1800057d6  neg     ecx
0x1800057d8  sbb     r8d, r8d
0x1800057db  neg     r8d
0x1800057de  add     r8d, 6
0x1800057e2  xchg    r8d, [rbx]
0x1800057e5  test    edx, edx
0x1800057e7  jnz     short loc_1800057FA
0x1800057e9  test    r8b, 4
0x1800057ed  jnz     short loc_1800057FA
0x1800057ef  mov     r8d, r14d
0x1800057f2  mov     rcx, rbx
0x1800057f5  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800057fa  mov     al, dil
0x1800057fd  jmp     short loc_18000581F
0x1800057ff  mov     rax, [rsp+48h+arg_20]
0x180005804  mov     r8d, edi
0x180005807  mov     [rsp+48h+var_20], rax
0x18000580c  mov     [rsp+48h+var_28], 0
0x180005815  call    wil_QueryFeatureState
0x18000581a  test    eax, eax
0x18000581c  setnz   al
0x18000581f  mov     rbx, [rsp+48h+arg_0]
0x180005824  mov     rbp, [rsp+48h+arg_8]
0x180005829  add     rsp, 30h
0x18000582d  pop     r14
0x18000582f  pop     rdi
0x180005830  pop     rsi
0x180005831  retn
```
