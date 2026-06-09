# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x14000d304`
- end: `0x14000d3dd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e914`
- `0x14000ecd4`

## callees

- `0x140007508`
- `0x1400096d0`
- `0x14000d304`
- `0x14000dba0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UexTest7__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UexTest7__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UexTest7__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UexTest7__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x14000d304  mov     [rsp+arg_10], rbx
0x14000d309  mov     [rsp+arg_0], rcx
0x14000d30e  push    rbp
0x14000d30f  push    rsi
0x14000d310  push    rdi
0x14000d311  sub     rsp, 20h
0x14000d315  mov     rsi, cs:Feature_UexTest7__descriptor
0x14000d31c  mov     rdi, rdx
0x14000d31f  mov     qword ptr [rdx], 0
0x14000d326  mov     eax, [rsi]
0x14000d328  mov     [rdx], eax
0x14000d32a  and     eax, 6
0x14000d32d  cmp     al, 6
0x14000d32f  jz      loc_14000D3CD
0x14000d335  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000d33a  lea     r8, [rsp+38h+arg_0]
0x14000d33f  mov     dword ptr [rsp+38h+arg_0], 0
0x14000d347  lea     rdx, [rsp+38h+arg_8]
0x14000d34c  mov     ebp, eax
0x14000d34e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x14000d353  mov     eax, [rdi]
0x14000d355  mov     rbx, [rsp+38h+arg_8]
0x14000d35a  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000d35f  mov     edx, eax
0x14000d361  mov     [rdi], eax
0x14000d363  mov     ecx, eax
0x14000d365  jz      short loc_14000D380
0x14000d367  test    dl, 2
0x14000d36a  jnz     short loc_14000D380
0x14000d36c  and     ecx, 0FFFFF63Eh
0x14000d372  mov     eax, ebx
0x14000d374  and     eax, 9C1h
0x14000d379  or      ecx, eax
0x14000d37b  or      ecx, 2
0x14000d37e  mov     [rdi], ecx
0x14000d380  mov     r8d, edx
0x14000d383  and     r8d, 4
0x14000d387  jnz     short loc_14000D39B
0x14000d389  btr     ecx, 0Ah
0x14000d38d  mov     eax, ebx
0x14000d38f  and     eax, 400h
0x14000d394  or      ecx, eax
0x14000d396  or      ecx, 4
0x14000d399  mov     [rdi], ecx
0x14000d39b  mov     eax, edx
0x14000d39d  lock cmpxchg [rsi], ecx
0x14000d3a1  jnz     short loc_14000D35A
0x14000d3a3  test    r8d, r8d
0x14000d3a6  jnz     short loc_14000D3B8
0x14000d3a8  mov     r8d, ebp
0x14000d3ab  mov     edx, 3
0x14000d3b0  mov     rcx, rsi
0x14000d3b3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000d3b8  mov     eax, [rdi]
0x14000d3ba  test    al, 2
0x14000d3bc  jnz     short loc_14000D3CD
0x14000d3be  and     eax, 0FFFFF63Eh
0x14000d3c3  and     ebx, 9C1h
0x14000d3c9  or      eax, ebx
0x14000d3cb  mov     [rdi], eax
0x14000d3cd  mov     rbx, [rsp+38h+arg_10]
0x14000d3d2  mov     rax, rdi
0x14000d3d5  add     rsp, 20h
0x14000d3d9  pop     rdi
0x14000d3da  pop     rsi
0x14000d3db  pop     rbp
0x14000d3dc  retn
```
