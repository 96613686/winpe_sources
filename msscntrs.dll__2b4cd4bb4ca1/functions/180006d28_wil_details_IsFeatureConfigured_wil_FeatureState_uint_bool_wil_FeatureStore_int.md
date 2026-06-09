# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180006d28`
- end: `0x180006e0a`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009e10`

## callees

- `0x180005c18`
- `0x180006d28`
- `0x180009714`
- `0x18000ac98`

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
0x180006d28  mov     [rsp+arg_0], rbx
0x180006d2d  mov     [rsp+arg_8], rbp
0x180006d32  push    rsi
0x180006d33  push    rdi
0x180006d34  push    r14
0x180006d36  sub     rsp, 30h
0x180006d3a  test    r9d, r9d
0x180006d3d  movzx   edi, r8b
0x180006d41  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180006d48  mov     esi, edx
0x180006d4a  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180006d51  mov     rbp, rcx
0x180006d54  cmovnz  rbx, rax
0x180006d58  mov     r9d, [rbx]
0x180006d5b  mov     eax, r9d
0x180006d5e  and     al, 3
0x180006d60  cmp     al, 2
0x180006d62  jnz     short loc_180006D6B
0x180006d64  xor     al, al
0x180006d66  jmp     loc_180006DF7
0x180006d6b  test    r9b, 2
0x180006d6f  jnz     short loc_180006DD7
0x180006d71  mov     [rsp+48h+arg_18], 1
0x180006d79  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180006d7e  mov     rcx, [rsp+48h+arg_20]
0x180006d83  mov     r14d, eax
0x180006d86  mov     [rsp+48h+var_20], rcx
0x180006d8b  lea     rax, [rsp+48h+arg_18]
0x180006d90  mov     rcx, rbp
0x180006d93  mov     [rsp+48h+var_28], rax
0x180006d98  mov     r8d, edi
0x180006d9b  mov     edx, esi
0x180006d9d  call    wil_QueryFeatureState
0x180006da2  mov     edx, [rsp+48h+arg_18]
0x180006da6  test    eax, eax
0x180006da8  mov     ecx, edx
0x180006daa  setnz   dil
0x180006dae  neg     ecx
0x180006db0  sbb     r8d, r8d
0x180006db3  neg     r8d
0x180006db6  add     r8d, 6
0x180006dba  xchg    r8d, [rbx]
0x180006dbd  test    edx, edx
0x180006dbf  jnz     short loc_180006DD2
0x180006dc1  test    r8b, 4
0x180006dc5  jnz     short loc_180006DD2
0x180006dc7  mov     r8d, r14d
0x180006dca  mov     rcx, rbx
0x180006dcd  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180006dd2  mov     al, dil
0x180006dd5  jmp     short loc_180006DF7
0x180006dd7  mov     rax, [rsp+48h+arg_20]
0x180006ddc  mov     r8d, edi
0x180006ddf  mov     [rsp+48h+var_20], rax
0x180006de4  mov     [rsp+48h+var_28], 0
0x180006ded  call    wil_QueryFeatureState
0x180006df2  test    eax, eax
0x180006df4  setnz   al
0x180006df7  mov     rbx, [rsp+48h+arg_0]
0x180006dfc  mov     rbp, [rsp+48h+arg_8]
0x180006e01  add     rsp, 30h
0x180006e05  pop     r14
0x180006e07  pop     rdi
0x180006e08  pop     rsi
0x180006e09  retn
```
