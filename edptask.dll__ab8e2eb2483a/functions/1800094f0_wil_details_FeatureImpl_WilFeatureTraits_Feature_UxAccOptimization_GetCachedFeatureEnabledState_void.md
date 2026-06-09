# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x1800094f0`
- end: `0x1800095c9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012268`

## callees

- `0x1800084b4`
- `0x1800094f0`
- `0x180009c14`
- `0x1800113c4`

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
0x1800094f0  mov     [rsp+arg_10], rbx
0x1800094f5  mov     [rsp+arg_0], rcx
0x1800094fa  push    rbp
0x1800094fb  push    rsi
0x1800094fc  push    rdi
0x1800094fd  sub     rsp, 20h
0x180009501  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x180009508  mov     rdi, rdx
0x18000950b  mov     qword ptr [rdx], 0
0x180009512  mov     eax, [rsi]
0x180009514  mov     [rdx], eax
0x180009516  and     eax, 6
0x180009519  cmp     al, 6
0x18000951b  jz      loc_1800095B9
0x180009521  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180009526  lea     r8, [rsp+38h+arg_0]
0x18000952b  mov     dword ptr [rsp+38h+arg_0], 0
0x180009533  lea     rdx, [rsp+38h+arg_8]
0x180009538  mov     ebp, eax
0x18000953a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18000953f  mov     eax, [rdi]
0x180009541  mov     rbx, [rsp+38h+arg_8]
0x180009546  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000954b  mov     edx, eax
0x18000954d  mov     [rdi], eax
0x18000954f  mov     ecx, eax
0x180009551  jz      short loc_18000956C
0x180009553  test    dl, 2
0x180009556  jnz     short loc_18000956C
0x180009558  and     ecx, 0FFFFF63Eh
0x18000955e  mov     eax, ebx
0x180009560  and     eax, 9C1h
0x180009565  or      ecx, eax
0x180009567  or      ecx, 2
0x18000956a  mov     [rdi], ecx
0x18000956c  mov     r8d, edx
0x18000956f  and     r8d, 4
0x180009573  jnz     short loc_180009587
0x180009575  btr     ecx, 0Ah
0x180009579  mov     eax, ebx
0x18000957b  and     eax, 400h
0x180009580  or      ecx, eax
0x180009582  or      ecx, 4
0x180009585  mov     [rdi], ecx
0x180009587  mov     eax, edx
0x180009589  lock cmpxchg [rsi], ecx
0x18000958d  jnz     short loc_180009546
0x18000958f  test    r8d, r8d
0x180009592  jnz     short loc_1800095A4
0x180009594  mov     r8d, ebp
0x180009597  mov     edx, 3
0x18000959c  mov     rcx, rsi
0x18000959f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800095a4  mov     eax, [rdi]
0x1800095a6  test    al, 2
0x1800095a8  jnz     short loc_1800095B9
0x1800095aa  and     eax, 0FFFFF63Eh
0x1800095af  and     ebx, 9C1h
0x1800095b5  or      eax, ebx
0x1800095b7  mov     [rdi], eax
0x1800095b9  mov     rbx, [rsp+38h+arg_10]
0x1800095be  mov     rax, rdi
0x1800095c1  add     rsp, 20h
0x1800095c5  pop     rdi
0x1800095c6  pop     rsi
0x1800095c7  pop     rbp
0x1800095c8  retn
```
