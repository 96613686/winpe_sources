# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CDSFlatBuffers>::GetCachedFeatureEnabledState(void)

- ea: `0x1800263a8`
- end: `0x180026481`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CDSFlatBuffers@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028bfc`
- `0x18002907c`

## callees

- `0x1800086f8`
- `0x18000bb98`
- `0x1800263a8`
- `0x1800270b8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CDSFlatBuffers>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CDSFlatBuffers__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CDSFlatBuffers__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CDSFlatBuffers>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CDSFlatBuffers__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_CDSFlatBuffers__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800263a8  mov     [rsp+arg_10], rbx
0x1800263ad  mov     [rsp+arg_0], rcx
0x1800263b2  push    rbp
0x1800263b3  push    rsi
0x1800263b4  push    rdi
0x1800263b5  sub     rsp, 20h
0x1800263b9  mov     rsi, cs:Feature_CDSFlatBuffers__descriptor
0x1800263c0  mov     rdi, rdx
0x1800263c3  mov     qword ptr [rdx], 0
0x1800263ca  mov     eax, [rsi]
0x1800263cc  mov     [rdx], eax
0x1800263ce  and     eax, 6
0x1800263d1  cmp     al, 6
0x1800263d3  jz      loc_180026471
0x1800263d9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800263de  lea     r8, [rsp+38h+arg_0]
0x1800263e3  mov     dword ptr [rsp+38h+arg_0], 0
0x1800263eb  lea     rdx, [rsp+38h+arg_8]
0x1800263f0  mov     ebp, eax
0x1800263f2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CDSFlatBuffers@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CDSFlatBuffers>::GetCurrentFeatureEnabledState(int *)
0x1800263f7  mov     eax, [rdi]
0x1800263f9  mov     rbx, [rsp+38h+arg_8]
0x1800263fe  cmp     dword ptr [rsp+38h+arg_0], 0
0x180026403  mov     edx, eax
0x180026405  mov     [rdi], eax
0x180026407  mov     ecx, eax
0x180026409  jz      short loc_180026424
0x18002640b  test    dl, 2
0x18002640e  jnz     short loc_180026424
0x180026410  and     ecx, 0FFFFF63Eh
0x180026416  mov     eax, ebx
0x180026418  and     eax, 9C1h
0x18002641d  or      ecx, eax
0x18002641f  or      ecx, 2
0x180026422  mov     [rdi], ecx
0x180026424  mov     r8d, edx
0x180026427  and     r8d, 4
0x18002642b  jnz     short loc_18002643F
0x18002642d  btr     ecx, 0Ah
0x180026431  mov     eax, ebx
0x180026433  and     eax, 400h
0x180026438  or      ecx, eax
0x18002643a  or      ecx, 4
0x18002643d  mov     [rdi], ecx
0x18002643f  mov     eax, edx
0x180026441  lock cmpxchg [rsi], ecx
0x180026445  jnz     short loc_1800263FE
0x180026447  test    r8d, r8d
0x18002644a  jnz     short loc_18002645C
0x18002644c  mov     r8d, ebp
0x18002644f  mov     edx, 3
0x180026454  mov     rcx, rsi
0x180026457  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002645c  mov     eax, [rdi]
0x18002645e  test    al, 2
0x180026460  jnz     short loc_180026471
0x180026462  and     eax, 0FFFFF63Eh
0x180026467  and     ebx, 9C1h
0x18002646d  or      eax, ebx
0x18002646f  mov     [rdi], eax
0x180026471  mov     rbx, [rsp+38h+arg_10]
0x180026476  mov     rax, rdi
0x180026479  add     rsp, 20h
0x18002647d  pop     rdi
0x18002647e  pop     rsi
0x18002647f  pop     rbp
0x180026480  retn
```
