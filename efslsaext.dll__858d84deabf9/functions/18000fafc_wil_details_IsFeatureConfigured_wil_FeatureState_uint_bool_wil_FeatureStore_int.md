# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000fafc`
- end: `0x18000fbde`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180011160`

## callees

- `0x18000426c`
- `0x180005e58`
- `0x18000fafc`
- `0x18001196c`

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
0x18000fafc  mov     [rsp+arg_0], rbx
0x18000fb01  mov     [rsp+arg_8], rbp
0x18000fb06  push    rsi
0x18000fb07  push    rdi
0x18000fb08  push    r14
0x18000fb0a  sub     rsp, 30h
0x18000fb0e  test    r9d, r9d
0x18000fb11  movzx   edi, r8b
0x18000fb15  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000fb1c  mov     esi, edx
0x18000fb1e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18000fb25  mov     rbp, rcx
0x18000fb28  cmovnz  rbx, rax
0x18000fb2c  mov     r9d, [rbx]
0x18000fb2f  mov     eax, r9d
0x18000fb32  and     al, 3
0x18000fb34  cmp     al, 2
0x18000fb36  jnz     short loc_18000FB3F
0x18000fb38  xor     al, al
0x18000fb3a  jmp     loc_18000FBCB
0x18000fb3f  test    r9b, 2
0x18000fb43  jnz     short loc_18000FBAB
0x18000fb45  mov     [rsp+48h+arg_18], 1
0x18000fb4d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000fb52  mov     rcx, [rsp+48h+arg_20]
0x18000fb57  mov     r14d, eax
0x18000fb5a  mov     [rsp+48h+var_20], rcx
0x18000fb5f  lea     rax, [rsp+48h+arg_18]
0x18000fb64  mov     rcx, rbp
0x18000fb67  mov     [rsp+48h+var_28], rax
0x18000fb6c  mov     r8d, edi
0x18000fb6f  mov     edx, esi
0x18000fb71  call    wil_QueryFeatureState
0x18000fb76  mov     edx, [rsp+48h+arg_18]
0x18000fb7a  test    eax, eax
0x18000fb7c  mov     ecx, edx
0x18000fb7e  setnz   dil
0x18000fb82  neg     ecx
0x18000fb84  sbb     r8d, r8d
0x18000fb87  neg     r8d
0x18000fb8a  add     r8d, 6
0x18000fb8e  xchg    r8d, [rbx]
0x18000fb91  test    edx, edx
0x18000fb93  jnz     short loc_18000FBA6
0x18000fb95  test    r8b, 4
0x18000fb99  jnz     short loc_18000FBA6
0x18000fb9b  mov     r8d, r14d
0x18000fb9e  mov     rcx, rbx
0x18000fba1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000fba6  mov     al, dil
0x18000fba9  jmp     short loc_18000FBCB
0x18000fbab  mov     rax, [rsp+48h+arg_20]
0x18000fbb0  mov     r8d, edi
0x18000fbb3  mov     [rsp+48h+var_20], rax
0x18000fbb8  mov     [rsp+48h+var_28], 0
0x18000fbc1  call    wil_QueryFeatureState
0x18000fbc6  test    eax, eax
0x18000fbc8  setnz   al
0x18000fbcb  mov     rbx, [rsp+48h+arg_0]
0x18000fbd0  mov     rbp, [rsp+48h+arg_8]
0x18000fbd5  add     rsp, 30h
0x18000fbd9  pop     r14
0x18000fbdb  pop     rdi
0x18000fbdc  pop     rsi
0x18000fbdd  retn
```
