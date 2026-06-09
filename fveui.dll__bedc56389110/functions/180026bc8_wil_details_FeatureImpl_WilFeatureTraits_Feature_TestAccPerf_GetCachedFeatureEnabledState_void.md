# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x180026bc8`
- end: `0x180026ca1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028d94`
- `0x180029130`

## callees

- `0x1800086f8`
- `0x18000bb98`
- `0x180026bc8`
- `0x1800273a4`

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
0x180026bc8  mov     [rsp+arg_10], rbx
0x180026bcd  mov     [rsp+arg_0], rcx
0x180026bd2  push    rbp
0x180026bd3  push    rsi
0x180026bd4  push    rdi
0x180026bd5  sub     rsp, 20h
0x180026bd9  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x180026be0  mov     rdi, rdx
0x180026be3  mov     qword ptr [rdx], 0
0x180026bea  mov     eax, [rsi]
0x180026bec  mov     [rdx], eax
0x180026bee  and     eax, 6
0x180026bf1  cmp     al, 6
0x180026bf3  jz      loc_180026C91
0x180026bf9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180026bfe  lea     r8, [rsp+38h+arg_0]
0x180026c03  mov     dword ptr [rsp+38h+arg_0], 0
0x180026c0b  lea     rdx, [rsp+38h+arg_8]
0x180026c10  mov     ebp, eax
0x180026c12  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x180026c17  mov     eax, [rdi]
0x180026c19  mov     rbx, [rsp+38h+arg_8]
0x180026c1e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180026c23  mov     edx, eax
0x180026c25  mov     [rdi], eax
0x180026c27  mov     ecx, eax
0x180026c29  jz      short loc_180026C44
0x180026c2b  test    dl, 2
0x180026c2e  jnz     short loc_180026C44
0x180026c30  and     ecx, 0FFFFF63Eh
0x180026c36  mov     eax, ebx
0x180026c38  and     eax, 9C1h
0x180026c3d  or      ecx, eax
0x180026c3f  or      ecx, 2
0x180026c42  mov     [rdi], ecx
0x180026c44  mov     r8d, edx
0x180026c47  and     r8d, 4
0x180026c4b  jnz     short loc_180026C5F
0x180026c4d  btr     ecx, 0Ah
0x180026c51  mov     eax, ebx
0x180026c53  and     eax, 400h
0x180026c58  or      ecx, eax
0x180026c5a  or      ecx, 4
0x180026c5d  mov     [rdi], ecx
0x180026c5f  mov     eax, edx
0x180026c61  lock cmpxchg [rsi], ecx
0x180026c65  jnz     short loc_180026C1E
0x180026c67  test    r8d, r8d
0x180026c6a  jnz     short loc_180026C7C
0x180026c6c  mov     r8d, ebp
0x180026c6f  mov     edx, 3
0x180026c74  mov     rcx, rsi
0x180026c77  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180026c7c  mov     eax, [rdi]
0x180026c7e  test    al, 2
0x180026c80  jnz     short loc_180026C91
0x180026c82  and     eax, 0FFFFF63Eh
0x180026c87  and     ebx, 9C1h
0x180026c8d  or      eax, ebx
0x180026c8f  mov     [rdi], eax
0x180026c91  mov     rbx, [rsp+38h+arg_10]
0x180026c96  mov     rax, rdi
0x180026c99  add     rsp, 20h
0x180026c9d  pop     rdi
0x180026c9e  pop     rsi
0x180026c9f  pop     rbp
0x180026ca0  retn
```
