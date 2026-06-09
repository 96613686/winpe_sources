# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x1800129b0`
- end: `0x180012a89`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013814`

## callees

- `0x180005c18`
- `0x180009714`
- `0x1800129b0`
- `0x1800130b0`

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
0x1800129b0  mov     [rsp+arg_10], rbx
0x1800129b5  mov     [rsp+arg_0], rcx
0x1800129ba  push    rbp
0x1800129bb  push    rsi
0x1800129bc  push    rdi
0x1800129bd  sub     rsp, 20h
0x1800129c1  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x1800129c8  mov     rdi, rdx
0x1800129cb  mov     qword ptr [rdx], 0
0x1800129d2  mov     eax, [rsi]
0x1800129d4  mov     [rdx], eax
0x1800129d6  and     eax, 6
0x1800129d9  cmp     al, 6
0x1800129db  jz      loc_180012A79
0x1800129e1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800129e6  lea     r8, [rsp+38h+arg_0]
0x1800129eb  mov     dword ptr [rsp+38h+arg_0], 0
0x1800129f3  lea     rdx, [rsp+38h+arg_8]
0x1800129f8  mov     ebp, eax
0x1800129fa  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x1800129ff  mov     eax, [rdi]
0x180012a01  mov     rbx, [rsp+38h+arg_8]
0x180012a06  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012a0b  mov     edx, eax
0x180012a0d  mov     [rdi], eax
0x180012a0f  mov     ecx, eax
0x180012a11  jz      short loc_180012A2C
0x180012a13  test    dl, 2
0x180012a16  jnz     short loc_180012A2C
0x180012a18  and     ecx, 0FFFFF63Eh
0x180012a1e  mov     eax, ebx
0x180012a20  and     eax, 9C1h
0x180012a25  or      ecx, eax
0x180012a27  or      ecx, 2
0x180012a2a  mov     [rdi], ecx
0x180012a2c  mov     r8d, edx
0x180012a2f  and     r8d, 4
0x180012a33  jnz     short loc_180012A47
0x180012a35  btr     ecx, 0Ah
0x180012a39  mov     eax, ebx
0x180012a3b  and     eax, 400h
0x180012a40  or      ecx, eax
0x180012a42  or      ecx, 4
0x180012a45  mov     [rdi], ecx
0x180012a47  mov     eax, edx
0x180012a49  lock cmpxchg [rsi], ecx
0x180012a4d  jnz     short loc_180012A06
0x180012a4f  test    r8d, r8d
0x180012a52  jnz     short loc_180012A64
0x180012a54  mov     r8d, ebp
0x180012a57  mov     edx, 3
0x180012a5c  mov     rcx, rsi
0x180012a5f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012a64  mov     eax, [rdi]
0x180012a66  test    al, 2
0x180012a68  jnz     short loc_180012A79
0x180012a6a  and     eax, 0FFFFF63Eh
0x180012a6f  and     ebx, 9C1h
0x180012a75  or      eax, ebx
0x180012a77  mov     [rdi], eax
0x180012a79  mov     rbx, [rsp+38h+arg_10]
0x180012a7e  mov     rax, rdi
0x180012a81  add     rsp, 20h
0x180012a85  pop     rdi
0x180012a86  pop     rsi
0x180012a87  pop     rbp
0x180012a88  retn
```
