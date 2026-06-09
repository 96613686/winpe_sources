# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000612c`
- end: `0x18000620e`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800094a0`

## callees

- `0x180004f18`
- `0x18000612c`
- `0x180008dc0`
- `0x18000a078`

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
0x18000612c  mov     [rsp+arg_0], rbx
0x180006131  mov     [rsp+arg_8], rbp
0x180006136  push    rsi
0x180006137  push    rdi
0x180006138  push    r14
0x18000613a  sub     rsp, 30h
0x18000613e  test    r9d, r9d
0x180006141  movzx   edi, r8b
0x180006145  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000614c  mov     esi, edx
0x18000614e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180006155  mov     rbp, rcx
0x180006158  cmovnz  rbx, rax
0x18000615c  mov     r9d, [rbx]
0x18000615f  mov     eax, r9d
0x180006162  and     al, 3
0x180006164  cmp     al, 2
0x180006166  jnz     short loc_18000616F
0x180006168  xor     al, al
0x18000616a  jmp     loc_1800061FB
0x18000616f  test    r9b, 2
0x180006173  jnz     short loc_1800061DB
0x180006175  mov     [rsp+48h+arg_18], 1
0x18000617d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180006182  mov     rcx, [rsp+48h+arg_20]
0x180006187  mov     r14d, eax
0x18000618a  mov     [rsp+48h+var_20], rcx
0x18000618f  lea     rax, [rsp+48h+arg_18]
0x180006194  mov     rcx, rbp
0x180006197  mov     [rsp+48h+var_28], rax
0x18000619c  mov     r8d, edi
0x18000619f  mov     edx, esi
0x1800061a1  call    wil_QueryFeatureState
0x1800061a6  mov     edx, [rsp+48h+arg_18]
0x1800061aa  test    eax, eax
0x1800061ac  mov     ecx, edx
0x1800061ae  setnz   dil
0x1800061b2  neg     ecx
0x1800061b4  sbb     r8d, r8d
0x1800061b7  neg     r8d
0x1800061ba  add     r8d, 6
0x1800061be  xchg    r8d, [rbx]
0x1800061c1  test    edx, edx
0x1800061c3  jnz     short loc_1800061D6
0x1800061c5  test    r8b, 4
0x1800061c9  jnz     short loc_1800061D6
0x1800061cb  mov     r8d, r14d
0x1800061ce  mov     rcx, rbx
0x1800061d1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800061d6  mov     al, dil
0x1800061d9  jmp     short loc_1800061FB
0x1800061db  mov     rax, [rsp+48h+arg_20]
0x1800061e0  mov     r8d, edi
0x1800061e3  mov     [rsp+48h+var_20], rax
0x1800061e8  mov     [rsp+48h+var_28], 0
0x1800061f1  call    wil_QueryFeatureState
0x1800061f6  test    eax, eax
0x1800061f8  setnz   al
0x1800061fb  mov     rbx, [rsp+48h+arg_0]
0x180006200  mov     rbp, [rsp+48h+arg_8]
0x180006205  add     rsp, 30h
0x180006209  pop     r14
0x18000620b  pop     rdi
0x18000620c  pop     rsi
0x18000620d  retn
```
