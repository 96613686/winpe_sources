# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f338`
- end: `0x18000f411`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800116e8`

## callees

- `0x18000426c`
- `0x180005e58`
- `0x18000f338`
- `0x18000f9e8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValAccTest__descriptor,
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
0x18000f338  mov     [rsp+arg_10], rbx
0x18000f33d  mov     [rsp+arg_0], rcx
0x18000f342  push    rbp
0x18000f343  push    rsi
0x18000f344  push    rdi
0x18000f345  sub     rsp, 20h
0x18000f349  mov     rsi, cs:Feature_ValAccTest__descriptor
0x18000f350  mov     rdi, rdx
0x18000f353  mov     qword ptr [rdx], 0
0x18000f35a  mov     eax, [rsi]
0x18000f35c  mov     [rdx], eax
0x18000f35e  and     eax, 6
0x18000f361  cmp     al, 6
0x18000f363  jz      loc_18000F401
0x18000f369  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f36e  lea     r8, [rsp+38h+arg_0]
0x18000f373  mov     dword ptr [rsp+38h+arg_0], 0
0x18000f37b  lea     rdx, [rsp+38h+arg_8]
0x18000f380  mov     ebp, eax
0x18000f382  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x18000f387  mov     eax, [rdi]
0x18000f389  mov     rbx, [rsp+38h+arg_8]
0x18000f38e  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000f393  mov     edx, eax
0x18000f395  mov     [rdi], eax
0x18000f397  mov     ecx, eax
0x18000f399  jz      short loc_18000F3B4
0x18000f39b  test    dl, 2
0x18000f39e  jnz     short loc_18000F3B4
0x18000f3a0  and     ecx, 0FFFFF63Eh
0x18000f3a6  mov     eax, ebx
0x18000f3a8  and     eax, 9C1h
0x18000f3ad  or      ecx, eax
0x18000f3af  or      ecx, 2
0x18000f3b2  mov     [rdi], ecx
0x18000f3b4  mov     r8d, edx
0x18000f3b7  and     r8d, 4
0x18000f3bb  jnz     short loc_18000F3CF
0x18000f3bd  btr     ecx, 0Ah
0x18000f3c1  mov     eax, ebx
0x18000f3c3  and     eax, 400h
0x18000f3c8  or      ecx, eax
0x18000f3ca  or      ecx, 4
0x18000f3cd  mov     [rdi], ecx
0x18000f3cf  mov     eax, edx
0x18000f3d1  lock cmpxchg [rsi], ecx
0x18000f3d5  jnz     short loc_18000F38E
0x18000f3d7  test    r8d, r8d
0x18000f3da  jnz     short loc_18000F3EC
0x18000f3dc  mov     r8d, ebp
0x18000f3df  mov     edx, 3
0x18000f3e4  mov     rcx, rsi
0x18000f3e7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000f3ec  mov     eax, [rdi]
0x18000f3ee  test    al, 2
0x18000f3f0  jnz     short loc_18000F401
0x18000f3f2  and     eax, 0FFFFF63Eh
0x18000f3f7  and     ebx, 9C1h
0x18000f3fd  or      eax, ebx
0x18000f3ff  mov     [rdi], eax
0x18000f401  mov     rbx, [rsp+38h+arg_10]
0x18000f406  mov     rax, rdi
0x18000f409  add     rsp, 20h
0x18000f40d  pop     rdi
0x18000f40e  pop     rsi
0x18000f40f  pop     rbp
0x18000f410  retn
```
