# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000a374`
- end: `0x18000a456`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000bfe0`
- `0x18000c050`

## callees

- `0x180009e0c`
- `0x18000a374`
- `0x18000bbb0`
- `0x18000cb14`

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
0x18000a374  mov     [rsp+arg_0], rbx
0x18000a379  mov     [rsp+arg_8], rbp
0x18000a37e  push    rsi
0x18000a37f  push    rdi
0x18000a380  push    r14
0x18000a382  sub     rsp, 30h
0x18000a386  test    r9d, r9d
0x18000a389  movzx   edi, r8b
0x18000a38d  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000a394  mov     esi, edx
0x18000a396  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18000a39d  mov     rbp, rcx
0x18000a3a0  cmovnz  rbx, rax
0x18000a3a4  mov     r9d, [rbx]
0x18000a3a7  mov     eax, r9d
0x18000a3aa  and     al, 3
0x18000a3ac  cmp     al, 2
0x18000a3ae  jnz     short loc_18000A3B7
0x18000a3b0  xor     al, al
0x18000a3b2  jmp     loc_18000A443
0x18000a3b7  test    r9b, 2
0x18000a3bb  jnz     short loc_18000A423
0x18000a3bd  mov     [rsp+48h+arg_18], 1
0x18000a3c5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000a3ca  mov     rcx, [rsp+48h+arg_20]
0x18000a3cf  mov     r14d, eax
0x18000a3d2  mov     [rsp+48h+var_20], rcx
0x18000a3d7  lea     rax, [rsp+48h+arg_18]
0x18000a3dc  mov     rcx, rbp
0x18000a3df  mov     [rsp+48h+var_28], rax
0x18000a3e4  mov     r8d, edi
0x18000a3e7  mov     edx, esi
0x18000a3e9  call    wil_QueryFeatureState
0x18000a3ee  mov     edx, [rsp+48h+arg_18]
0x18000a3f2  test    eax, eax
0x18000a3f4  mov     ecx, edx
0x18000a3f6  setnz   dil
0x18000a3fa  neg     ecx
0x18000a3fc  sbb     r8d, r8d
0x18000a3ff  neg     r8d
0x18000a402  add     r8d, 6
0x18000a406  xchg    r8d, [rbx]
0x18000a409  test    edx, edx
0x18000a40b  jnz     short loc_18000A41E
0x18000a40d  test    r8b, 4
0x18000a411  jnz     short loc_18000A41E
0x18000a413  mov     r8d, r14d
0x18000a416  mov     rcx, rbx
0x18000a419  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000a41e  mov     al, dil
0x18000a421  jmp     short loc_18000A443
0x18000a423  mov     rax, [rsp+48h+arg_20]
0x18000a428  mov     r8d, edi
0x18000a42b  mov     [rsp+48h+var_20], rax
0x18000a430  mov     [rsp+48h+var_28], 0
0x18000a439  call    wil_QueryFeatureState
0x18000a43e  test    eax, eax
0x18000a440  setnz   al
0x18000a443  mov     rbx, [rsp+48h+arg_0]
0x18000a448  mov     rbp, [rsp+48h+arg_8]
0x18000a44d  add     rsp, 30h
0x18000a451  pop     r14
0x18000a453  pop     rdi
0x18000a454  pop     rsi
0x18000a455  retn
```
