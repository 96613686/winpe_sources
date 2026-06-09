# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x14000d144`
- end: `0x14000d21d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e804`
- `0x14000ec5c`

## callees

- `0x140007508`
- `0x1400096d0`
- `0x14000d144`
- `0x14000d9c8`

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
0x14000d144  mov     [rsp+arg_10], rbx
0x14000d149  mov     [rsp+arg_0], rcx
0x14000d14e  push    rbp
0x14000d14f  push    rsi
0x14000d150  push    rdi
0x14000d151  sub     rsp, 20h
0x14000d155  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x14000d15c  mov     rdi, rdx
0x14000d15f  mov     qword ptr [rdx], 0
0x14000d166  mov     eax, [rsi]
0x14000d168  mov     [rdx], eax
0x14000d16a  and     eax, 6
0x14000d16d  cmp     al, 6
0x14000d16f  jz      loc_14000D20D
0x14000d175  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000d17a  lea     r8, [rsp+38h+arg_0]
0x14000d17f  mov     dword ptr [rsp+38h+arg_0], 0
0x14000d187  lea     rdx, [rsp+38h+arg_8]
0x14000d18c  mov     ebp, eax
0x14000d18e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x14000d193  mov     eax, [rdi]
0x14000d195  mov     rbx, [rsp+38h+arg_8]
0x14000d19a  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000d19f  mov     edx, eax
0x14000d1a1  mov     [rdi], eax
0x14000d1a3  mov     ecx, eax
0x14000d1a5  jz      short loc_14000D1C0
0x14000d1a7  test    dl, 2
0x14000d1aa  jnz     short loc_14000D1C0
0x14000d1ac  and     ecx, 0FFFFF63Eh
0x14000d1b2  mov     eax, ebx
0x14000d1b4  and     eax, 9C1h
0x14000d1b9  or      ecx, eax
0x14000d1bb  or      ecx, 2
0x14000d1be  mov     [rdi], ecx
0x14000d1c0  mov     r8d, edx
0x14000d1c3  and     r8d, 4
0x14000d1c7  jnz     short loc_14000D1DB
0x14000d1c9  btr     ecx, 0Ah
0x14000d1cd  mov     eax, ebx
0x14000d1cf  and     eax, 400h
0x14000d1d4  or      ecx, eax
0x14000d1d6  or      ecx, 4
0x14000d1d9  mov     [rdi], ecx
0x14000d1db  mov     eax, edx
0x14000d1dd  lock cmpxchg [rsi], ecx
0x14000d1e1  jnz     short loc_14000D19A
0x14000d1e3  test    r8d, r8d
0x14000d1e6  jnz     short loc_14000D1F8
0x14000d1e8  mov     r8d, ebp
0x14000d1eb  mov     edx, 3
0x14000d1f0  mov     rcx, rsi
0x14000d1f3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000d1f8  mov     eax, [rdi]
0x14000d1fa  test    al, 2
0x14000d1fc  jnz     short loc_14000D20D
0x14000d1fe  and     eax, 0FFFFF63Eh
0x14000d203  and     ebx, 9C1h
0x14000d209  or      eax, ebx
0x14000d20b  mov     [rdi], eax
0x14000d20d  mov     rbx, [rsp+38h+arg_10]
0x14000d212  mov     rax, rdi
0x14000d215  add     rsp, 20h
0x14000d219  pop     rdi
0x14000d21a  pop     rsi
0x14000d21b  pop     rbp
0x14000d21c  retn
```
