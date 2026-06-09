# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x18000efb8`
- end: `0x18000f091`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800115d8`

## callees

- `0x18000426c`
- `0x180005e58`
- `0x18000efb8`
- `0x18000f598`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Ten2Loc__descriptor,
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
0x18000efb8  mov     [rsp+arg_10], rbx
0x18000efbd  mov     [rsp+arg_0], rcx
0x18000efc2  push    rbp
0x18000efc3  push    rsi
0x18000efc4  push    rdi
0x18000efc5  sub     rsp, 20h
0x18000efc9  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18000efd0  mov     rdi, rdx
0x18000efd3  mov     qword ptr [rdx], 0
0x18000efda  mov     eax, [rsi]
0x18000efdc  mov     [rdx], eax
0x18000efde  and     eax, 6
0x18000efe1  cmp     al, 6
0x18000efe3  jz      loc_18000F081
0x18000efe9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000efee  lea     r8, [rsp+38h+arg_0]
0x18000eff3  mov     dword ptr [rsp+38h+arg_0], 0
0x18000effb  lea     rdx, [rsp+38h+arg_8]
0x18000f000  mov     ebp, eax
0x18000f002  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18000f007  mov     eax, [rdi]
0x18000f009  mov     rbx, [rsp+38h+arg_8]
0x18000f00e  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000f013  mov     edx, eax
0x18000f015  mov     [rdi], eax
0x18000f017  mov     ecx, eax
0x18000f019  jz      short loc_18000F034
0x18000f01b  test    dl, 2
0x18000f01e  jnz     short loc_18000F034
0x18000f020  and     ecx, 0FFFFF63Eh
0x18000f026  mov     eax, ebx
0x18000f028  and     eax, 9C1h
0x18000f02d  or      ecx, eax
0x18000f02f  or      ecx, 2
0x18000f032  mov     [rdi], ecx
0x18000f034  mov     r8d, edx
0x18000f037  and     r8d, 4
0x18000f03b  jnz     short loc_18000F04F
0x18000f03d  btr     ecx, 0Ah
0x18000f041  mov     eax, ebx
0x18000f043  and     eax, 400h
0x18000f048  or      ecx, eax
0x18000f04a  or      ecx, 4
0x18000f04d  mov     [rdi], ecx
0x18000f04f  mov     eax, edx
0x18000f051  lock cmpxchg [rsi], ecx
0x18000f055  jnz     short loc_18000F00E
0x18000f057  test    r8d, r8d
0x18000f05a  jnz     short loc_18000F06C
0x18000f05c  mov     r8d, ebp
0x18000f05f  mov     edx, 3
0x18000f064  mov     rcx, rsi
0x18000f067  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000f06c  mov     eax, [rdi]
0x18000f06e  test    al, 2
0x18000f070  jnz     short loc_18000F081
0x18000f072  and     eax, 0FFFFF63Eh
0x18000f077  and     ebx, 9C1h
0x18000f07d  or      eax, ebx
0x18000f07f  mov     [rdi], eax
0x18000f081  mov     rbx, [rsp+38h+arg_10]
0x18000f086  mov     rax, rdi
0x18000f089  add     rsp, 20h
0x18000f08d  pop     rdi
0x18000f08e  pop     rsi
0x18000f08f  pop     rbp
0x18000f090  retn
```
