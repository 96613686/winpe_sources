# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180020730`
- end: `0x180020809`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800228b0`

## callees

- `0x180017fd8`
- `0x18001fc20`
- `0x180020730`
- `0x180022240`

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
  unsigned int v10; // eax
  unsigned int v11; // r14d
  int v12; // eax
  __int64 v13; // rdx
  bool v14; // di
  char v15; // r8
  unsigned int v16; // [rsp+58h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    *a5 = 1;
    return (unsigned int)wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, a3, 0) != 0;
  }
  else
  {
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v16 = 0;
    v11 = v10;
    *a5 = 1;
    v12 = wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, v5, &v16);
    v13 = v16;
    v14 = v12 != 0;
    v15 = _InterlockedExchange((volatile __int32 *)v7, (v16 != 0) + 6);
    if ( !(_DWORD)v13 && (v15 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, v13, v11);
    return v14;
  }
}

```

## disassembly

```asm
0x180020730  mov     [rsp+arg_0], rbx
0x180020735  mov     [rsp+arg_8], rbp
0x18002073a  push    rsi
0x18002073b  push    rdi
0x18002073c  push    r14
0x18002073e  sub     rsp, 20h
0x180020742  test    r9d, r9d
0x180020745  movzx   edi, r8b
0x180020749  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180020750  mov     esi, edx
0x180020752  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180020759  mov     rbp, rcx
0x18002075c  cmovnz  rbx, rax
0x180020760  mov     r9d, [rbx]
0x180020763  mov     eax, r9d
0x180020766  and     al, 3
0x180020768  cmp     al, 2
0x18002076a  jnz     short loc_180020773
0x18002076c  xor     al, al
0x18002076e  jmp     loc_1800207F6
0x180020773  test    r9b, 2
0x180020777  jnz     short loc_1800207DB
0x180020779  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002077e  mov     rcx, [rsp+38h+arg_20]
0x180020783  lea     r9, [rsp+38h+arg_18]
0x180020788  mov     r8d, edi
0x18002078b  mov     [rsp+38h+arg_18], 0
0x180020793  mov     edx, esi
0x180020795  mov     r14d, eax
0x180020798  mov     dword ptr [rcx], 1
0x18002079e  mov     rcx, rbp
0x1800207a1  call    wil_RtlStagingConfig_QueryFeatureState
0x1800207a6  mov     edx, [rsp+38h+arg_18]
0x1800207aa  test    eax, eax
0x1800207ac  mov     ecx, edx
0x1800207ae  setnz   dil
0x1800207b2  neg     ecx
0x1800207b4  sbb     r8d, r8d
0x1800207b7  neg     r8d
0x1800207ba  add     r8d, 6
0x1800207be  xchg    r8d, [rbx]
0x1800207c1  test    edx, edx
0x1800207c3  jnz     short loc_1800207D6
0x1800207c5  test    r8b, 4
0x1800207c9  jnz     short loc_1800207D6
0x1800207cb  mov     r8d, r14d
0x1800207ce  mov     rcx, rbx
0x1800207d1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800207d6  mov     al, dil
0x1800207d9  jmp     short loc_1800207F6
0x1800207db  mov     rax, [rsp+38h+arg_20]
0x1800207e0  mov     r8d, edi
0x1800207e3  xor     r9d, r9d
0x1800207e6  mov     dword ptr [rax], 1
0x1800207ec  call    wil_RtlStagingConfig_QueryFeatureState
0x1800207f1  test    eax, eax
0x1800207f3  setnz   al
0x1800207f6  mov     rbx, [rsp+38h+arg_0]
0x1800207fb  mov     rbp, [rsp+38h+arg_8]
0x180020800  add     rsp, 20h
0x180020804  pop     r14
0x180020806  pop     rdi
0x180020807  pop     rsi
0x180020808  retn
```
