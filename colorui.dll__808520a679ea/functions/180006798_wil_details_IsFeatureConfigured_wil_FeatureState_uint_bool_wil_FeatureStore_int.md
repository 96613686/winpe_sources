# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180006798`
- end: `0x18000687a`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ae30`

## callees

- `0x1800054b4`
- `0x180006798`
- `0x18000a080`
- `0x18000bab8`

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
0x180006798  mov     [rsp+arg_0], rbx
0x18000679d  mov     [rsp+arg_8], rbp
0x1800067a2  push    rsi
0x1800067a3  push    rdi
0x1800067a4  push    r14
0x1800067a6  sub     rsp, 30h
0x1800067aa  test    r9d, r9d
0x1800067ad  movzx   edi, r8b
0x1800067b1  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1800067b8  mov     esi, edx
0x1800067ba  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1800067c1  mov     rbp, rcx
0x1800067c4  cmovnz  rbx, rax
0x1800067c8  mov     r9d, [rbx]
0x1800067cb  mov     eax, r9d
0x1800067ce  and     al, 3
0x1800067d0  cmp     al, 2
0x1800067d2  jnz     short loc_1800067DB
0x1800067d4  xor     al, al
0x1800067d6  jmp     loc_180006867
0x1800067db  test    r9b, 2
0x1800067df  jnz     short loc_180006847
0x1800067e1  mov     [rsp+48h+arg_18], 1
0x1800067e9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800067ee  mov     rcx, [rsp+48h+arg_20]
0x1800067f3  mov     r14d, eax
0x1800067f6  mov     [rsp+48h+var_20], rcx
0x1800067fb  lea     rax, [rsp+48h+arg_18]
0x180006800  mov     rcx, rbp
0x180006803  mov     [rsp+48h+var_28], rax
0x180006808  mov     r8d, edi
0x18000680b  mov     edx, esi
0x18000680d  call    wil_QueryFeatureState
0x180006812  mov     edx, [rsp+48h+arg_18]
0x180006816  test    eax, eax
0x180006818  mov     ecx, edx
0x18000681a  setnz   dil
0x18000681e  neg     ecx
0x180006820  sbb     r8d, r8d
0x180006823  neg     r8d
0x180006826  add     r8d, 6
0x18000682a  xchg    r8d, [rbx]
0x18000682d  test    edx, edx
0x18000682f  jnz     short loc_180006842
0x180006831  test    r8b, 4
0x180006835  jnz     short loc_180006842
0x180006837  mov     r8d, r14d
0x18000683a  mov     rcx, rbx
0x18000683d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180006842  mov     al, dil
0x180006845  jmp     short loc_180006867
0x180006847  mov     rax, [rsp+48h+arg_20]
0x18000684c  mov     r8d, edi
0x18000684f  mov     [rsp+48h+var_20], rax
0x180006854  mov     [rsp+48h+var_28], 0
0x18000685d  call    wil_QueryFeatureState
0x180006862  test    eax, eax
0x180006864  setnz   al
0x180006867  mov     rbx, [rsp+48h+arg_0]
0x18000686c  mov     rbp, [rsp+48h+arg_8]
0x180006871  add     rsp, 30h
0x180006875  pop     r14
0x180006877  pop     rdi
0x180006878  pop     rsi
0x180006879  retn
```
