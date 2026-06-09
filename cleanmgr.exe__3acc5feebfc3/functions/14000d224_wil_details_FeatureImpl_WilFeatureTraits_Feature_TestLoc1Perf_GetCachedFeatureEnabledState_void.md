# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x14000d224`
- end: `0x14000d2fd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e88c`
- `0x14000ec98`

## callees

- `0x140007508`
- `0x1400096d0`
- `0x14000d224`
- `0x14000dab4`

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
0x14000d224  mov     [rsp+arg_10], rbx
0x14000d229  mov     [rsp+arg_0], rcx
0x14000d22e  push    rbp
0x14000d22f  push    rsi
0x14000d230  push    rdi
0x14000d231  sub     rsp, 20h
0x14000d235  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x14000d23c  mov     rdi, rdx
0x14000d23f  mov     qword ptr [rdx], 0
0x14000d246  mov     eax, [rsi]
0x14000d248  mov     [rdx], eax
0x14000d24a  and     eax, 6
0x14000d24d  cmp     al, 6
0x14000d24f  jz      loc_14000D2ED
0x14000d255  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000d25a  lea     r8, [rsp+38h+arg_0]
0x14000d25f  mov     dword ptr [rsp+38h+arg_0], 0
0x14000d267  lea     rdx, [rsp+38h+arg_8]
0x14000d26c  mov     ebp, eax
0x14000d26e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x14000d273  mov     eax, [rdi]
0x14000d275  mov     rbx, [rsp+38h+arg_8]
0x14000d27a  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000d27f  mov     edx, eax
0x14000d281  mov     [rdi], eax
0x14000d283  mov     ecx, eax
0x14000d285  jz      short loc_14000D2A0
0x14000d287  test    dl, 2
0x14000d28a  jnz     short loc_14000D2A0
0x14000d28c  and     ecx, 0FFFFF63Eh
0x14000d292  mov     eax, ebx
0x14000d294  and     eax, 9C1h
0x14000d299  or      ecx, eax
0x14000d29b  or      ecx, 2
0x14000d29e  mov     [rdi], ecx
0x14000d2a0  mov     r8d, edx
0x14000d2a3  and     r8d, 4
0x14000d2a7  jnz     short loc_14000D2BB
0x14000d2a9  btr     ecx, 0Ah
0x14000d2ad  mov     eax, ebx
0x14000d2af  and     eax, 400h
0x14000d2b4  or      ecx, eax
0x14000d2b6  or      ecx, 4
0x14000d2b9  mov     [rdi], ecx
0x14000d2bb  mov     eax, edx
0x14000d2bd  lock cmpxchg [rsi], ecx
0x14000d2c1  jnz     short loc_14000D27A
0x14000d2c3  test    r8d, r8d
0x14000d2c6  jnz     short loc_14000D2D8
0x14000d2c8  mov     r8d, ebp
0x14000d2cb  mov     edx, 3
0x14000d2d0  mov     rcx, rsi
0x14000d2d3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000d2d8  mov     eax, [rdi]
0x14000d2da  test    al, 2
0x14000d2dc  jnz     short loc_14000D2ED
0x14000d2de  and     eax, 0FFFFF63Eh
0x14000d2e3  and     ebx, 9C1h
0x14000d2e9  or      eax, ebx
0x14000d2eb  mov     [rdi], eax
0x14000d2ed  mov     rbx, [rsp+38h+arg_10]
0x14000d2f2  mov     rax, rdi
0x14000d2f5  add     rsp, 20h
0x14000d2f9  pop     rdi
0x14000d2fa  pop     rsi
0x14000d2fb  pop     rbp
0x14000d2fc  retn
```
