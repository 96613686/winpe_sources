# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x1800128d0`
- end: `0x1800129a9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013778`

## callees

- `0x180005c18`
- `0x180009714`
- `0x1800128d0`
- `0x180012f40`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TestAccPerf__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800128d0  mov     [rsp+arg_10], rbx
0x1800128d5  mov     [rsp+arg_0], rcx
0x1800128da  push    rbp
0x1800128db  push    rsi
0x1800128dc  push    rdi
0x1800128dd  sub     rsp, 20h
0x1800128e1  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x1800128e8  mov     rdi, rdx
0x1800128eb  mov     qword ptr [rdx], 0
0x1800128f2  mov     eax, [rsi]
0x1800128f4  mov     [rdx], eax
0x1800128f6  and     eax, 6
0x1800128f9  cmp     al, 6
0x1800128fb  jz      loc_180012999
0x180012901  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012906  lea     r8, [rsp+38h+arg_0]
0x18001290b  mov     dword ptr [rsp+38h+arg_0], 0
0x180012913  lea     rdx, [rsp+38h+arg_8]
0x180012918  mov     ebp, eax
0x18001291a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18001291f  mov     eax, [rdi]
0x180012921  mov     rbx, [rsp+38h+arg_8]
0x180012926  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001292b  mov     edx, eax
0x18001292d  mov     [rdi], eax
0x18001292f  mov     ecx, eax
0x180012931  jz      short loc_18001294C
0x180012933  test    dl, 2
0x180012936  jnz     short loc_18001294C
0x180012938  and     ecx, 0FFFFF63Eh
0x18001293e  mov     eax, ebx
0x180012940  and     eax, 9C1h
0x180012945  or      ecx, eax
0x180012947  or      ecx, 2
0x18001294a  mov     [rdi], ecx
0x18001294c  mov     r8d, edx
0x18001294f  and     r8d, 4
0x180012953  jnz     short loc_180012967
0x180012955  btr     ecx, 0Ah
0x180012959  mov     eax, ebx
0x18001295b  and     eax, 400h
0x180012960  or      ecx, eax
0x180012962  or      ecx, 4
0x180012965  mov     [rdi], ecx
0x180012967  mov     eax, edx
0x180012969  lock cmpxchg [rsi], ecx
0x18001296d  jnz     short loc_180012926
0x18001296f  test    r8d, r8d
0x180012972  jnz     short loc_180012984
0x180012974  mov     r8d, ebp
0x180012977  mov     edx, 3
0x18001297c  mov     rcx, rsi
0x18001297f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012984  mov     eax, [rdi]
0x180012986  test    al, 2
0x180012988  jnz     short loc_180012999
0x18001298a  and     eax, 0FFFFF63Eh
0x18001298f  and     ebx, 9C1h
0x180012995  or      eax, ebx
0x180012997  mov     [rdi], eax
0x180012999  mov     rbx, [rsp+38h+arg_10]
0x18001299e  mov     rax, rdi
0x1800129a1  add     rsp, 20h
0x1800129a5  pop     rdi
0x1800129a6  pop     rsi
0x1800129a7  pop     rbp
0x1800129a8  retn
```
