# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000e634`
- end: `0x18000e70a`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800158d0`

## callees

- `0x18000ae90`
- `0x18000e634`
- `0x1800140e0`
- `0x18001a748`

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
  volatile __int32 *v7; // rbx
  int v10; // r14d
  __int64 v11; // r9
  bool v12; // di
  char v13; // dl
  int v14; // [rsp+68h] [rbp+20h] BYREF

  v5 = a3;
  v7 = (volatile __int32 *)&`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( (_DWORD)a4 )
    v7 = (volatile __int32 *)&`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*v7 & 2) != 0 )
    return (*v7 & 1) != 0 && (unsigned int)wil_QueryFeatureState((__int64)a1, a2, a3, a4, 0, a5) != 0;
  v14 = 1;
  v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v12 = (unsigned int)wil_QueryFeatureState((__int64)a1, a2, v5, v11, &v14, a5) != 0;
  v13 = _InterlockedExchange(v7, (v14 != 0) + 6);
  if ( !v14 && (v13 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, 0, v10);
  return v12;
}

```

## disassembly

```asm
0x18000e634  mov     [rsp+arg_0], rbx
0x18000e639  mov     [rsp+arg_8], rbp
0x18000e63e  push    rsi
0x18000e63f  push    rdi
0x18000e640  push    r14
0x18000e642  sub     rsp, 30h
0x18000e646  test    r9d, r9d
0x18000e649  movzx   edi, r8b
0x18000e64d  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000e654  mov     esi, edx
0x18000e656  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18000e65d  mov     rbp, rcx
0x18000e660  cmovnz  rbx, rax
0x18000e664  mov     eax, [rbx]
0x18000e666  test    al, 2
0x18000e668  jz      short loc_18000E694
0x18000e66a  test    al, 1
0x18000e66c  jnz     short loc_18000E675
0x18000e66e  xor     al, al
0x18000e670  jmp     loc_18000E6F6
0x18000e675  mov     rax, [rsp+48h+arg_20]
0x18000e67a  mov     r8d, edi
0x18000e67d  mov     [rsp+48h+var_20], rax
0x18000e682  and     [rsp+48h+var_28], 0
0x18000e688  call    wil_QueryFeatureState
0x18000e68d  test    eax, eax
0x18000e68f  setnz   al
0x18000e692  jmp     short loc_18000E6F6
0x18000e694  mov     [rsp+48h+arg_18], 1
0x18000e69c  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e6a1  mov     rcx, [rsp+48h+arg_20]
0x18000e6a6  mov     r14d, eax
0x18000e6a9  mov     [rsp+48h+var_20], rcx
0x18000e6ae  lea     rax, [rsp+48h+arg_18]
0x18000e6b3  mov     rcx, rbp
0x18000e6b6  mov     [rsp+48h+var_28], rax
0x18000e6bb  mov     r8d, edi
0x18000e6be  mov     edx, esi
0x18000e6c0  call    wil_QueryFeatureState
0x18000e6c5  mov     ecx, [rsp+48h+arg_18]
0x18000e6c9  test    eax, eax
0x18000e6cb  setnz   dil
0x18000e6cf  neg     ecx
0x18000e6d1  sbb     edx, edx
0x18000e6d3  neg     edx
0x18000e6d5  add     edx, 6
0x18000e6d8  xchg    edx, [rbx]
0x18000e6da  cmp     [rsp+48h+arg_18], 0
0x18000e6df  jnz     short loc_18000E6F3
0x18000e6e1  test    dl, 4
0x18000e6e4  jnz     short loc_18000E6F3
0x18000e6e6  mov     r8d, r14d
0x18000e6e9  xor     edx, edx
0x18000e6eb  mov     rcx, rbx
0x18000e6ee  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e6f3  mov     al, dil
0x18000e6f6  mov     rbx, [rsp+48h+arg_0]
0x18000e6fb  mov     rbp, [rsp+48h+arg_8]
0x18000e700  add     rsp, 30h
0x18000e704  pop     r14
0x18000e706  pop     rdi
0x18000e707  pop     rsi
0x18000e708  retn
```
