# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000dbf4`
- end: `0x18000dcd6`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180014aa0`

## callees

- `0x18000ad30`
- `0x18000dbf4`
- `0x1800135a0`
- `0x180019780`

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
0x18000dbf4  mov     [rsp+arg_0], rbx
0x18000dbf9  mov     [rsp+arg_8], rbp
0x18000dbfe  push    rsi
0x18000dbff  push    rdi
0x18000dc00  push    r14
0x18000dc02  sub     rsp, 30h
0x18000dc06  test    r9d, r9d
0x18000dc09  movzx   edi, r8b
0x18000dc0d  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000dc14  mov     esi, edx
0x18000dc16  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18000dc1d  mov     rbp, rcx
0x18000dc20  cmovnz  rbx, rax
0x18000dc24  mov     r9d, [rbx]
0x18000dc27  mov     eax, r9d
0x18000dc2a  and     al, 3
0x18000dc2c  cmp     al, 2
0x18000dc2e  jnz     short loc_18000DC37
0x18000dc30  xor     al, al
0x18000dc32  jmp     loc_18000DCC3
0x18000dc37  test    r9b, 2
0x18000dc3b  jnz     short loc_18000DCA3
0x18000dc3d  mov     [rsp+48h+arg_18], 1
0x18000dc45  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000dc4a  mov     rcx, [rsp+48h+arg_20]
0x18000dc4f  mov     r14d, eax
0x18000dc52  mov     [rsp+48h+var_20], rcx
0x18000dc57  lea     rax, [rsp+48h+arg_18]
0x18000dc5c  mov     rcx, rbp
0x18000dc5f  mov     [rsp+48h+var_28], rax
0x18000dc64  mov     r8d, edi
0x18000dc67  mov     edx, esi
0x18000dc69  call    wil_QueryFeatureState
0x18000dc6e  mov     edx, [rsp+48h+arg_18]
0x18000dc72  test    eax, eax
0x18000dc74  mov     ecx, edx
0x18000dc76  setnz   dil
0x18000dc7a  neg     ecx
0x18000dc7c  sbb     r8d, r8d
0x18000dc7f  neg     r8d
0x18000dc82  add     r8d, 6
0x18000dc86  xchg    r8d, [rbx]
0x18000dc89  test    edx, edx
0x18000dc8b  jnz     short loc_18000DC9E
0x18000dc8d  test    r8b, 4
0x18000dc91  jnz     short loc_18000DC9E
0x18000dc93  mov     r8d, r14d
0x18000dc96  mov     rcx, rbx
0x18000dc99  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000dc9e  mov     al, dil
0x18000dca1  jmp     short loc_18000DCC3
0x18000dca3  mov     rax, [rsp+48h+arg_20]
0x18000dca8  mov     r8d, edi
0x18000dcab  mov     [rsp+48h+var_20], rax
0x18000dcb0  mov     [rsp+48h+var_28], 0
0x18000dcb9  call    wil_QueryFeatureState
0x18000dcbe  test    eax, eax
0x18000dcc0  setnz   al
0x18000dcc3  mov     rbx, [rsp+48h+arg_0]
0x18000dcc8  mov     rbp, [rsp+48h+arg_8]
0x18000dccd  add     rsp, 30h
0x18000dcd1  pop     r14
0x18000dcd3  pop     rdi
0x18000dcd4  pop     rsi
0x18000dcd5  retn
```
