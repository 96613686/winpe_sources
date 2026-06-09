# wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b554`
- end: `0x18001b62d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bb90`
- `0x18001bf18`

## callees

- `0x180016c14`
- `0x180019b00`
- `0x18001b554`
- `0x18001b7f4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
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
  v3 = *(_DWORD *)Feature_56494824__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_56494824__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_56494824__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_56494824__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001b554  mov     [rsp+arg_10], rbx
0x18001b559  mov     [rsp+arg_0], rcx
0x18001b55e  push    rbp
0x18001b55f  push    rsi
0x18001b560  push    rdi
0x18001b561  sub     rsp, 20h
0x18001b565  mov     rsi, cs:Feature_56494824__descriptor
0x18001b56c  mov     rdi, rdx
0x18001b56f  mov     qword ptr [rdx], 0
0x18001b576  mov     eax, [rsi]
0x18001b578  mov     [rdx], eax
0x18001b57a  and     eax, 6
0x18001b57d  cmp     al, 6
0x18001b57f  jz      loc_18001B61D
0x18001b585  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b58a  lea     r8, [rsp+38h+arg_0]
0x18001b58f  mov     dword ptr [rsp+38h+arg_0], 0
0x18001b597  lea     rdx, [rsp+38h+arg_8]
0x18001b59c  mov     ebp, eax
0x18001b59e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCurrentFeatureEnabledState(int *)
0x18001b5a3  mov     eax, [rdi]
0x18001b5a5  mov     rbx, [rsp+38h+arg_8]
0x18001b5aa  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001b5af  mov     edx, eax
0x18001b5b1  mov     [rdi], eax
0x18001b5b3  mov     ecx, eax
0x18001b5b5  jz      short loc_18001B5D0
0x18001b5b7  test    dl, 2
0x18001b5ba  jnz     short loc_18001B5D0
0x18001b5bc  and     ecx, 0FFFFF63Eh
0x18001b5c2  mov     eax, ebx
0x18001b5c4  and     eax, 9C1h
0x18001b5c9  or      ecx, eax
0x18001b5cb  or      ecx, 2
0x18001b5ce  mov     [rdi], ecx
0x18001b5d0  mov     r8d, edx
0x18001b5d3  and     r8d, 4
0x18001b5d7  jnz     short loc_18001B5EB
0x18001b5d9  btr     ecx, 0Ah
0x18001b5dd  mov     eax, ebx
0x18001b5df  and     eax, 400h
0x18001b5e4  or      ecx, eax
0x18001b5e6  or      ecx, 4
0x18001b5e9  mov     [rdi], ecx
0x18001b5eb  mov     eax, edx
0x18001b5ed  lock cmpxchg [rsi], ecx
0x18001b5f1  jnz     short loc_18001B5AA
0x18001b5f3  test    r8d, r8d
0x18001b5f6  jnz     short loc_18001B608
0x18001b5f8  mov     r8d, ebp
0x18001b5fb  mov     edx, 3
0x18001b600  mov     rcx, rsi
0x18001b603  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b608  mov     eax, [rdi]
0x18001b60a  test    al, 2
0x18001b60c  jnz     short loc_18001B61D
0x18001b60e  and     eax, 0FFFFF63Eh
0x18001b613  and     ebx, 9C1h
0x18001b619  or      eax, ebx
0x18001b61b  mov     [rdi], eax
0x18001b61d  mov     rbx, [rsp+38h+arg_10]
0x18001b622  mov     rax, rdi
0x18001b625  add     rsp, 20h
0x18001b629  pop     rdi
0x18001b62a  pop     rsi
0x18001b62b  pop     rbp
0x18001b62c  retn
```
