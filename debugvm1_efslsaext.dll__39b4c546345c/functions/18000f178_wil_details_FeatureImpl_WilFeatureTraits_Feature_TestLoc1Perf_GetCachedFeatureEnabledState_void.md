# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f178`
- end: `0x18000f251`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011660`

## callees

- `0x18000426c`
- `0x180005e58`
- `0x18000f178`
- `0x18000f7c0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestLoc1Perf__descriptor,
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
0x18000f178  mov     [rsp+arg_10], rbx
0x18000f17d  mov     [rsp+arg_0], rcx
0x18000f182  push    rbp
0x18000f183  push    rsi
0x18000f184  push    rdi
0x18000f185  sub     rsp, 20h
0x18000f189  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x18000f190  mov     rdi, rdx
0x18000f193  mov     qword ptr [rdx], 0
0x18000f19a  mov     eax, [rsi]
0x18000f19c  mov     [rdx], eax
0x18000f19e  and     eax, 6
0x18000f1a1  cmp     al, 6
0x18000f1a3  jz      loc_18000F241
0x18000f1a9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f1ae  lea     r8, [rsp+38h+arg_0]
0x18000f1b3  mov     dword ptr [rsp+38h+arg_0], 0
0x18000f1bb  lea     rdx, [rsp+38h+arg_8]
0x18000f1c0  mov     ebp, eax
0x18000f1c2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x18000f1c7  mov     eax, [rdi]
0x18000f1c9  mov     rbx, [rsp+38h+arg_8]
0x18000f1ce  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000f1d3  mov     edx, eax
0x18000f1d5  mov     [rdi], eax
0x18000f1d7  mov     ecx, eax
0x18000f1d9  jz      short loc_18000F1F4
0x18000f1db  test    dl, 2
0x18000f1de  jnz     short loc_18000F1F4
0x18000f1e0  and     ecx, 0FFFFF63Eh
0x18000f1e6  mov     eax, ebx
0x18000f1e8  and     eax, 9C1h
0x18000f1ed  or      ecx, eax
0x18000f1ef  or      ecx, 2
0x18000f1f2  mov     [rdi], ecx
0x18000f1f4  mov     r8d, edx
0x18000f1f7  and     r8d, 4
0x18000f1fb  jnz     short loc_18000F20F
0x18000f1fd  btr     ecx, 0Ah
0x18000f201  mov     eax, ebx
0x18000f203  and     eax, 400h
0x18000f208  or      ecx, eax
0x18000f20a  or      ecx, 4
0x18000f20d  mov     [rdi], ecx
0x18000f20f  mov     eax, edx
0x18000f211  lock cmpxchg [rsi], ecx
0x18000f215  jnz     short loc_18000F1CE
0x18000f217  test    r8d, r8d
0x18000f21a  jnz     short loc_18000F22C
0x18000f21c  mov     r8d, ebp
0x18000f21f  mov     edx, 3
0x18000f224  mov     rcx, rsi
0x18000f227  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000f22c  mov     eax, [rdi]
0x18000f22e  test    al, 2
0x18000f230  jnz     short loc_18000F241
0x18000f232  and     eax, 0FFFFF63Eh
0x18000f237  and     ebx, 9C1h
0x18000f23d  or      eax, ebx
0x18000f23f  mov     [rdi], eax
0x18000f241  mov     rbx, [rsp+38h+arg_10]
0x18000f246  mov     rax, rdi
0x18000f249  add     rsp, 20h
0x18000f24d  pop     rdi
0x18000f24e  pop     rsi
0x18000f24f  pop     rbp
0x18000f250  retn
```
