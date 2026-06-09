# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f098`
- end: `0x18000f171`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001161c`

## callees

- `0x18000426c`
- `0x180005e58`
- `0x18000f098`
- `0x18000f6ac`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  signed __int32 v8; // edx
  unsigned int v9; // ecx
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v5, &v11);
    v6 = *(_DWORD *)a2;
    v7 = v11;
    do
    {
      v8 = v6;
      *(_DWORD *)a2 = v6;
      v9 = v6;
      if ( (v6 & 4) == 0 )
      {
        v9 = v7 & 0x400 | v6 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v9;
      }
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestAccPerf__descriptor,
        3,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000f098  mov     [rsp+arg_10], rbx
0x18000f09d  mov     [rsp+arg_0], rcx
0x18000f0a2  push    rbp
0x18000f0a3  push    rsi
0x18000f0a4  push    rdi
0x18000f0a5  sub     rsp, 20h
0x18000f0a9  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x18000f0b0  mov     rdi, rdx
0x18000f0b3  mov     qword ptr [rdx], 0
0x18000f0ba  mov     eax, [rsi]
0x18000f0bc  mov     [rdx], eax
0x18000f0be  and     eax, 6
0x18000f0c1  cmp     al, 6
0x18000f0c3  jz      loc_18000F161
0x18000f0c9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f0ce  lea     r8, [rsp+38h+arg_0]
0x18000f0d3  mov     dword ptr [rsp+38h+arg_0], 0
0x18000f0db  lea     rdx, [rsp+38h+arg_8]
0x18000f0e0  mov     ebp, eax
0x18000f0e2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18000f0e7  mov     eax, [rdi]
0x18000f0e9  mov     rbx, [rsp+38h+arg_8]
0x18000f0ee  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000f0f3  mov     edx, eax
0x18000f0f5  mov     [rdi], eax
0x18000f0f7  mov     ecx, eax
0x18000f0f9  jz      short loc_18000F114
0x18000f0fb  test    dl, 2
0x18000f0fe  jnz     short loc_18000F114
0x18000f100  and     ecx, 0FFFFF63Eh
0x18000f106  mov     eax, ebx
0x18000f108  and     eax, 9C1h
0x18000f10d  or      ecx, eax
0x18000f10f  or      ecx, 2
0x18000f112  mov     [rdi], ecx
0x18000f114  mov     r8d, edx
0x18000f117  and     r8d, 4
0x18000f11b  jnz     short loc_18000F12F
0x18000f11d  btr     ecx, 0Ah
0x18000f121  mov     eax, ebx
0x18000f123  and     eax, 400h
0x18000f128  or      ecx, eax
0x18000f12a  or      ecx, 4
0x18000f12d  mov     [rdi], ecx
0x18000f12f  mov     eax, edx
0x18000f131  lock cmpxchg [rsi], ecx
0x18000f135  jnz     short loc_18000F0EE
0x18000f137  test    r8d, r8d
0x18000f13a  jnz     short loc_18000F14C
0x18000f13c  mov     r8d, ebp
0x18000f13f  mov     edx, 3
0x18000f144  mov     rcx, rsi
0x18000f147  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000f14c  mov     eax, [rdi]
0x18000f14e  test    al, 2
0x18000f150  jnz     short loc_18000F161
0x18000f152  and     eax, 0FFFFF63Eh
0x18000f157  and     ebx, 9C1h
0x18000f15d  or      eax, ebx
0x18000f15f  mov     [rdi], eax
0x18000f161  mov     rbx, [rsp+38h+arg_10]
0x18000f166  mov     rax, rdi
0x18000f169  add     rsp, 20h
0x18000f16d  pop     rdi
0x18000f16e  pop     rsi
0x18000f16f  pop     rbp
0x18000f170  retn
```
