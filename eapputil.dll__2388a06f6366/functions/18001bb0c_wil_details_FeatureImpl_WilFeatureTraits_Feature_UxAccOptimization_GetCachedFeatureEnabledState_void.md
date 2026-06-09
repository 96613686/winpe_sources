# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x18001bb0c`
- end: `0x18001bbe5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023c34`

## callees

- `0x180009e0c`
- `0x18000bbb0`
- `0x18001bb0c`
- `0x18001bd78`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  wil::details *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
    v7 = *(_DWORD *)a2;
    v8 = v14;
    do
    {
      v9 = (_DWORD)v13 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UxAccOptimization__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001bb0c  mov     [rsp+arg_10], rbx
0x18001bb11  mov     [rsp+arg_0], rcx
0x18001bb16  push    rbp
0x18001bb17  push    rsi
0x18001bb18  push    rdi
0x18001bb19  sub     rsp, 20h
0x18001bb1d  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x18001bb24  mov     rdi, rdx
0x18001bb27  mov     qword ptr [rdx], 0
0x18001bb2e  mov     eax, [rsi]
0x18001bb30  mov     [rdx], eax
0x18001bb32  and     eax, 6
0x18001bb35  cmp     al, 6
0x18001bb37  jz      loc_18001BBD5
0x18001bb3d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001bb42  lea     r8, [rsp+38h+arg_0]
0x18001bb47  mov     dword ptr [rsp+38h+arg_0], 0
0x18001bb4f  lea     rdx, [rsp+38h+arg_8]
0x18001bb54  mov     ebp, eax
0x18001bb56  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18001bb5b  mov     eax, [rdi]
0x18001bb5d  mov     rbx, [rsp+38h+arg_8]
0x18001bb62  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001bb67  mov     edx, eax
0x18001bb69  mov     [rdi], eax
0x18001bb6b  mov     ecx, eax
0x18001bb6d  jz      short loc_18001BB88
0x18001bb6f  test    dl, 2
0x18001bb72  jnz     short loc_18001BB88
0x18001bb74  and     ecx, 0FFFFF63Eh
0x18001bb7a  mov     eax, ebx
0x18001bb7c  and     eax, 9C1h
0x18001bb81  or      ecx, eax
0x18001bb83  or      ecx, 2
0x18001bb86  mov     [rdi], ecx
0x18001bb88  mov     r8d, edx
0x18001bb8b  and     r8d, 4
0x18001bb8f  jnz     short loc_18001BBA3
0x18001bb91  btr     ecx, 0Ah
0x18001bb95  mov     eax, ebx
0x18001bb97  and     eax, 400h
0x18001bb9c  or      ecx, eax
0x18001bb9e  or      ecx, 4
0x18001bba1  mov     [rdi], ecx
0x18001bba3  mov     eax, edx
0x18001bba5  lock cmpxchg [rsi], ecx
0x18001bba9  jnz     short loc_18001BB62
0x18001bbab  test    r8d, r8d
0x18001bbae  jnz     short loc_18001BBC0
0x18001bbb0  mov     r8d, ebp
0x18001bbb3  mov     edx, 3
0x18001bbb8  mov     rcx, rsi
0x18001bbbb  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001bbc0  mov     eax, [rdi]
0x18001bbc2  test    al, 2
0x18001bbc4  jnz     short loc_18001BBD5
0x18001bbc6  and     eax, 0FFFFF63Eh
0x18001bbcb  and     ebx, 9C1h
0x18001bbd1  or      eax, ebx
0x18001bbd3  mov     [rdi], eax
0x18001bbd5  mov     rbx, [rsp+38h+arg_10]
0x18001bbda  mov     rax, rdi
0x18001bbdd  add     rsp, 20h
0x18001bbe1  pop     rdi
0x18001bbe2  pop     rsi
0x18001bbe3  pop     rbp
0x18001bbe4  retn
```
