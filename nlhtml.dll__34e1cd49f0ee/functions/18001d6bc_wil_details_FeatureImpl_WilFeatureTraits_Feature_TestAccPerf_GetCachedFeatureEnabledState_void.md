# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x18001d6bc`
- end: `0x18001d795`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ec28`
- `0x18001ef8c`

## callees

- `0x180016c14`
- `0x180019b00`
- `0x18001d6bc`
- `0x18001dfac`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestAccPerf__descriptor,
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
0x18001d6bc  mov     [rsp+arg_10], rbx
0x18001d6c1  mov     [rsp+arg_0], rcx
0x18001d6c6  push    rbp
0x18001d6c7  push    rsi
0x18001d6c8  push    rdi
0x18001d6c9  sub     rsp, 20h
0x18001d6cd  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x18001d6d4  mov     rdi, rdx
0x18001d6d7  mov     qword ptr [rdx], 0
0x18001d6de  mov     eax, [rsi]
0x18001d6e0  mov     [rdx], eax
0x18001d6e2  and     eax, 6
0x18001d6e5  cmp     al, 6
0x18001d6e7  jz      loc_18001D785
0x18001d6ed  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d6f2  lea     r8, [rsp+38h+arg_0]
0x18001d6f7  mov     dword ptr [rsp+38h+arg_0], 0
0x18001d6ff  lea     rdx, [rsp+38h+arg_8]
0x18001d704  mov     ebp, eax
0x18001d706  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18001d70b  mov     eax, [rdi]
0x18001d70d  mov     rbx, [rsp+38h+arg_8]
0x18001d712  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001d717  mov     edx, eax
0x18001d719  mov     [rdi], eax
0x18001d71b  mov     ecx, eax
0x18001d71d  jz      short loc_18001D738
0x18001d71f  test    dl, 2
0x18001d722  jnz     short loc_18001D738
0x18001d724  and     ecx, 0FFFFF63Eh
0x18001d72a  mov     eax, ebx
0x18001d72c  and     eax, 9C1h
0x18001d731  or      ecx, eax
0x18001d733  or      ecx, 2
0x18001d736  mov     [rdi], ecx
0x18001d738  mov     r8d, edx
0x18001d73b  and     r8d, 4
0x18001d73f  jnz     short loc_18001D753
0x18001d741  btr     ecx, 0Ah
0x18001d745  mov     eax, ebx
0x18001d747  and     eax, 400h
0x18001d74c  or      ecx, eax
0x18001d74e  or      ecx, 4
0x18001d751  mov     [rdi], ecx
0x18001d753  mov     eax, edx
0x18001d755  lock cmpxchg [rsi], ecx
0x18001d759  jnz     short loc_18001D712
0x18001d75b  test    r8d, r8d
0x18001d75e  jnz     short loc_18001D770
0x18001d760  mov     r8d, ebp
0x18001d763  mov     edx, 3
0x18001d768  mov     rcx, rsi
0x18001d76b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001d770  mov     eax, [rdi]
0x18001d772  test    al, 2
0x18001d774  jnz     short loc_18001D785
0x18001d776  and     eax, 0FFFFF63Eh
0x18001d77b  and     ebx, 9C1h
0x18001d781  or      eax, ebx
0x18001d783  mov     [rdi], eax
0x18001d785  mov     rbx, [rsp+38h+arg_10]
0x18001d78a  mov     rax, rdi
0x18001d78d  add     rsp, 20h
0x18001d791  pop     rdi
0x18001d792  pop     rsi
0x18001d793  pop     rbp
0x18001d794  retn
```
