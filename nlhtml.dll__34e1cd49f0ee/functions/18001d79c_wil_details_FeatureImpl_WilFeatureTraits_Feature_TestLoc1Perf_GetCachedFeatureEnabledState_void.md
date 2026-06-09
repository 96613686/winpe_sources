# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x18001d79c`
- end: `0x18001d875`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ecb0`
- `0x18001efc8`

## callees

- `0x180016c14`
- `0x180019b00`
- `0x18001d79c`
- `0x18001e090`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestLoc1Perf__descriptor,
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
0x18001d79c  mov     [rsp+arg_10], rbx
0x18001d7a1  mov     [rsp+arg_0], rcx
0x18001d7a6  push    rbp
0x18001d7a7  push    rsi
0x18001d7a8  push    rdi
0x18001d7a9  sub     rsp, 20h
0x18001d7ad  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x18001d7b4  mov     rdi, rdx
0x18001d7b7  mov     qword ptr [rdx], 0
0x18001d7be  mov     eax, [rsi]
0x18001d7c0  mov     [rdx], eax
0x18001d7c2  and     eax, 6
0x18001d7c5  cmp     al, 6
0x18001d7c7  jz      loc_18001D865
0x18001d7cd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d7d2  lea     r8, [rsp+38h+arg_0]
0x18001d7d7  mov     dword ptr [rsp+38h+arg_0], 0
0x18001d7df  lea     rdx, [rsp+38h+arg_8]
0x18001d7e4  mov     ebp, eax
0x18001d7e6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x18001d7eb  mov     eax, [rdi]
0x18001d7ed  mov     rbx, [rsp+38h+arg_8]
0x18001d7f2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001d7f7  mov     edx, eax
0x18001d7f9  mov     [rdi], eax
0x18001d7fb  mov     ecx, eax
0x18001d7fd  jz      short loc_18001D818
0x18001d7ff  test    dl, 2
0x18001d802  jnz     short loc_18001D818
0x18001d804  and     ecx, 0FFFFF63Eh
0x18001d80a  mov     eax, ebx
0x18001d80c  and     eax, 9C1h
0x18001d811  or      ecx, eax
0x18001d813  or      ecx, 2
0x18001d816  mov     [rdi], ecx
0x18001d818  mov     r8d, edx
0x18001d81b  and     r8d, 4
0x18001d81f  jnz     short loc_18001D833
0x18001d821  btr     ecx, 0Ah
0x18001d825  mov     eax, ebx
0x18001d827  and     eax, 400h
0x18001d82c  or      ecx, eax
0x18001d82e  or      ecx, 4
0x18001d831  mov     [rdi], ecx
0x18001d833  mov     eax, edx
0x18001d835  lock cmpxchg [rsi], ecx
0x18001d839  jnz     short loc_18001D7F2
0x18001d83b  test    r8d, r8d
0x18001d83e  jnz     short loc_18001D850
0x18001d840  mov     r8d, ebp
0x18001d843  mov     edx, 3
0x18001d848  mov     rcx, rsi
0x18001d84b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001d850  mov     eax, [rdi]
0x18001d852  test    al, 2
0x18001d854  jnz     short loc_18001D865
0x18001d856  and     eax, 0FFFFF63Eh
0x18001d85b  and     ebx, 9C1h
0x18001d861  or      eax, ebx
0x18001d863  mov     [rdi], eax
0x18001d865  mov     rbx, [rsp+38h+arg_10]
0x18001d86a  mov     rax, rdi
0x18001d86d  add     rsp, 20h
0x18001d871  pop     rdi
0x18001d872  pop     rsi
0x18001d873  pop     rbp
0x18001d874  retn
```
