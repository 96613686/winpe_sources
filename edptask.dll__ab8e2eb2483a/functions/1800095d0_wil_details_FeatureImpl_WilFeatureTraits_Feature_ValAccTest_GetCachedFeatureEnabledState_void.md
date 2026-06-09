# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x1800095d0`
- end: `0x1800096a9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012304`

## callees

- `0x1800084b4`
- `0x1800095d0`
- `0x180009d5c`
- `0x1800113c4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValAccTest__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800095d0  mov     [rsp+arg_10], rbx
0x1800095d5  mov     [rsp+arg_0], rcx
0x1800095da  push    rbp
0x1800095db  push    rsi
0x1800095dc  push    rdi
0x1800095dd  sub     rsp, 20h
0x1800095e1  mov     rsi, cs:Feature_ValAccTest__descriptor
0x1800095e8  mov     rdi, rdx
0x1800095eb  mov     qword ptr [rdx], 0
0x1800095f2  mov     eax, [rsi]
0x1800095f4  mov     [rdx], eax
0x1800095f6  and     eax, 6
0x1800095f9  cmp     al, 6
0x1800095fb  jz      loc_180009699
0x180009601  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180009606  lea     r8, [rsp+38h+arg_0]
0x18000960b  mov     dword ptr [rsp+38h+arg_0], 0
0x180009613  lea     rdx, [rsp+38h+arg_8]
0x180009618  mov     ebp, eax
0x18000961a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x18000961f  mov     eax, [rdi]
0x180009621  mov     rbx, [rsp+38h+arg_8]
0x180009626  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000962b  mov     edx, eax
0x18000962d  mov     [rdi], eax
0x18000962f  mov     ecx, eax
0x180009631  jz      short loc_18000964C
0x180009633  test    dl, 2
0x180009636  jnz     short loc_18000964C
0x180009638  and     ecx, 0FFFFF63Eh
0x18000963e  mov     eax, ebx
0x180009640  and     eax, 9C1h
0x180009645  or      ecx, eax
0x180009647  or      ecx, 2
0x18000964a  mov     [rdi], ecx
0x18000964c  mov     r8d, edx
0x18000964f  and     r8d, 4
0x180009653  jnz     short loc_180009667
0x180009655  btr     ecx, 0Ah
0x180009659  mov     eax, ebx
0x18000965b  and     eax, 400h
0x180009660  or      ecx, eax
0x180009662  or      ecx, 4
0x180009665  mov     [rdi], ecx
0x180009667  mov     eax, edx
0x180009669  lock cmpxchg [rsi], ecx
0x18000966d  jnz     short loc_180009626
0x18000966f  test    r8d, r8d
0x180009672  jnz     short loc_180009684
0x180009674  mov     r8d, ebp
0x180009677  mov     edx, 3
0x18000967c  mov     rcx, rsi
0x18000967f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180009684  mov     eax, [rdi]
0x180009686  test    al, 2
0x180009688  jnz     short loc_180009699
0x18000968a  and     eax, 0FFFFF63Eh
0x18000968f  and     ebx, 9C1h
0x180009695  or      eax, ebx
0x180009697  mov     [rdi], eax
0x180009699  mov     rbx, [rsp+38h+arg_10]
0x18000969e  mov     rax, rdi
0x1800096a1  add     rsp, 20h
0x1800096a5  pop     rdi
0x1800096a6  pop     rsi
0x1800096a7  pop     rbp
0x1800096a8  retn
```
