# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x180009410`
- end: `0x1800094e9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800121cc`

## callees

- `0x1800084b4`
- `0x180009410`
- `0x180009aa4`
- `0x1800113c4`

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
0x180009410  mov     [rsp+arg_10], rbx
0x180009415  mov     [rsp+arg_0], rcx
0x18000941a  push    rbp
0x18000941b  push    rsi
0x18000941c  push    rdi
0x18000941d  sub     rsp, 20h
0x180009421  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x180009428  mov     rdi, rdx
0x18000942b  mov     qword ptr [rdx], 0
0x180009432  mov     eax, [rsi]
0x180009434  mov     [rdx], eax
0x180009436  and     eax, 6
0x180009439  cmp     al, 6
0x18000943b  jz      loc_1800094D9
0x180009441  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180009446  lea     r8, [rsp+38h+arg_0]
0x18000944b  mov     dword ptr [rsp+38h+arg_0], 0
0x180009453  lea     rdx, [rsp+38h+arg_8]
0x180009458  mov     ebp, eax
0x18000945a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x18000945f  mov     eax, [rdi]
0x180009461  mov     rbx, [rsp+38h+arg_8]
0x180009466  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000946b  mov     edx, eax
0x18000946d  mov     [rdi], eax
0x18000946f  mov     ecx, eax
0x180009471  jz      short loc_18000948C
0x180009473  test    dl, 2
0x180009476  jnz     short loc_18000948C
0x180009478  and     ecx, 0FFFFF63Eh
0x18000947e  mov     eax, ebx
0x180009480  and     eax, 9C1h
0x180009485  or      ecx, eax
0x180009487  or      ecx, 2
0x18000948a  mov     [rdi], ecx
0x18000948c  mov     r8d, edx
0x18000948f  and     r8d, 4
0x180009493  jnz     short loc_1800094A7
0x180009495  btr     ecx, 0Ah
0x180009499  mov     eax, ebx
0x18000949b  and     eax, 400h
0x1800094a0  or      ecx, eax
0x1800094a2  or      ecx, 4
0x1800094a5  mov     [rdi], ecx
0x1800094a7  mov     eax, edx
0x1800094a9  lock cmpxchg [rsi], ecx
0x1800094ad  jnz     short loc_180009466
0x1800094af  test    r8d, r8d
0x1800094b2  jnz     short loc_1800094C4
0x1800094b4  mov     r8d, ebp
0x1800094b7  mov     edx, 3
0x1800094bc  mov     rcx, rsi
0x1800094bf  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800094c4  mov     eax, [rdi]
0x1800094c6  test    al, 2
0x1800094c8  jnz     short loc_1800094D9
0x1800094ca  and     eax, 0FFFFF63Eh
0x1800094cf  and     ebx, 9C1h
0x1800094d5  or      eax, ebx
0x1800094d7  mov     [rdi], eax
0x1800094d9  mov     rbx, [rsp+38h+arg_10]
0x1800094de  mov     rax, rdi
0x1800094e1  add     rsp, 20h
0x1800094e5  pop     rdi
0x1800094e6  pop     rsi
0x1800094e7  pop     rbp
0x1800094e8  retn
```
