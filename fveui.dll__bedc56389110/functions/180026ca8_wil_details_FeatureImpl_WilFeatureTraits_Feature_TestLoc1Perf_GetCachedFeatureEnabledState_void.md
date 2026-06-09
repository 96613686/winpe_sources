# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x180026ca8`
- end: `0x180026d81`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028e1c`
- `0x18002916c`

## callees

- `0x1800086f8`
- `0x18000bb98`
- `0x180026ca8`
- `0x1800274f8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TestLoc1Perf__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180026ca8  mov     [rsp+arg_10], rbx
0x180026cad  mov     [rsp+arg_0], rcx
0x180026cb2  push    rbp
0x180026cb3  push    rsi
0x180026cb4  push    rdi
0x180026cb5  sub     rsp, 20h
0x180026cb9  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x180026cc0  mov     rdi, rdx
0x180026cc3  mov     qword ptr [rdx], 0
0x180026cca  mov     eax, [rsi]
0x180026ccc  mov     [rdx], eax
0x180026cce  and     eax, 6
0x180026cd1  cmp     al, 6
0x180026cd3  jz      loc_180026D71
0x180026cd9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180026cde  lea     r8, [rsp+38h+arg_0]
0x180026ce3  mov     dword ptr [rsp+38h+arg_0], 0
0x180026ceb  lea     rdx, [rsp+38h+arg_8]
0x180026cf0  mov     ebp, eax
0x180026cf2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x180026cf7  mov     eax, [rdi]
0x180026cf9  mov     rbx, [rsp+38h+arg_8]
0x180026cfe  cmp     dword ptr [rsp+38h+arg_0], 0
0x180026d03  mov     edx, eax
0x180026d05  mov     [rdi], eax
0x180026d07  mov     ecx, eax
0x180026d09  jz      short loc_180026D24
0x180026d0b  test    dl, 2
0x180026d0e  jnz     short loc_180026D24
0x180026d10  and     ecx, 0FFFFF63Eh
0x180026d16  mov     eax, ebx
0x180026d18  and     eax, 9C1h
0x180026d1d  or      ecx, eax
0x180026d1f  or      ecx, 2
0x180026d22  mov     [rdi], ecx
0x180026d24  mov     r8d, edx
0x180026d27  and     r8d, 4
0x180026d2b  jnz     short loc_180026D3F
0x180026d2d  btr     ecx, 0Ah
0x180026d31  mov     eax, ebx
0x180026d33  and     eax, 400h
0x180026d38  or      ecx, eax
0x180026d3a  or      ecx, 4
0x180026d3d  mov     [rdi], ecx
0x180026d3f  mov     eax, edx
0x180026d41  lock cmpxchg [rsi], ecx
0x180026d45  jnz     short loc_180026CFE
0x180026d47  test    r8d, r8d
0x180026d4a  jnz     short loc_180026D5C
0x180026d4c  mov     r8d, ebp
0x180026d4f  mov     edx, 3
0x180026d54  mov     rcx, rsi
0x180026d57  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180026d5c  mov     eax, [rdi]
0x180026d5e  test    al, 2
0x180026d60  jnz     short loc_180026D71
0x180026d62  and     eax, 0FFFFF63Eh
0x180026d67  and     ebx, 9C1h
0x180026d6d  or      eax, ebx
0x180026d6f  mov     [rdi], eax
0x180026d71  mov     rbx, [rsp+38h+arg_10]
0x180026d76  mov     rax, rdi
0x180026d79  add     rsp, 20h
0x180026d7d  pop     rdi
0x180026d7e  pop     rsi
0x180026d7f  pop     rbp
0x180026d80  retn
```
