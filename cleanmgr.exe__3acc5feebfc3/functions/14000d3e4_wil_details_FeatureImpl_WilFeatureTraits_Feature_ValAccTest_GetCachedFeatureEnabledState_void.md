# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x14000d3e4`
- end: `0x14000d4bd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e99c`
- `0x14000ed10`

## callees

- `0x140007508`
- `0x1400096d0`
- `0x14000d3e4`
- `0x14000dc8c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValAccTest__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x14000d3e4  mov     [rsp+arg_10], rbx
0x14000d3e9  mov     [rsp+arg_0], rcx
0x14000d3ee  push    rbp
0x14000d3ef  push    rsi
0x14000d3f0  push    rdi
0x14000d3f1  sub     rsp, 20h
0x14000d3f5  mov     rsi, cs:Feature_ValAccTest__descriptor
0x14000d3fc  mov     rdi, rdx
0x14000d3ff  mov     qword ptr [rdx], 0
0x14000d406  mov     eax, [rsi]
0x14000d408  mov     [rdx], eax
0x14000d40a  and     eax, 6
0x14000d40d  cmp     al, 6
0x14000d40f  jz      loc_14000D4AD
0x14000d415  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000d41a  lea     r8, [rsp+38h+arg_0]
0x14000d41f  mov     dword ptr [rsp+38h+arg_0], 0
0x14000d427  lea     rdx, [rsp+38h+arg_8]
0x14000d42c  mov     ebp, eax
0x14000d42e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x14000d433  mov     eax, [rdi]
0x14000d435  mov     rbx, [rsp+38h+arg_8]
0x14000d43a  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000d43f  mov     edx, eax
0x14000d441  mov     [rdi], eax
0x14000d443  mov     ecx, eax
0x14000d445  jz      short loc_14000D460
0x14000d447  test    dl, 2
0x14000d44a  jnz     short loc_14000D460
0x14000d44c  and     ecx, 0FFFFF63Eh
0x14000d452  mov     eax, ebx
0x14000d454  and     eax, 9C1h
0x14000d459  or      ecx, eax
0x14000d45b  or      ecx, 2
0x14000d45e  mov     [rdi], ecx
0x14000d460  mov     r8d, edx
0x14000d463  and     r8d, 4
0x14000d467  jnz     short loc_14000D47B
0x14000d469  btr     ecx, 0Ah
0x14000d46d  mov     eax, ebx
0x14000d46f  and     eax, 400h
0x14000d474  or      ecx, eax
0x14000d476  or      ecx, 4
0x14000d479  mov     [rdi], ecx
0x14000d47b  mov     eax, edx
0x14000d47d  lock cmpxchg [rsi], ecx
0x14000d481  jnz     short loc_14000D43A
0x14000d483  test    r8d, r8d
0x14000d486  jnz     short loc_14000D498
0x14000d488  mov     r8d, ebp
0x14000d48b  mov     edx, 3
0x14000d490  mov     rcx, rsi
0x14000d493  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000d498  mov     eax, [rdi]
0x14000d49a  test    al, 2
0x14000d49c  jnz     short loc_14000D4AD
0x14000d49e  and     eax, 0FFFFF63Eh
0x14000d4a3  and     ebx, 9C1h
0x14000d4a9  or      eax, ebx
0x14000d4ab  mov     [rdi], eax
0x14000d4ad  mov     rbx, [rsp+38h+arg_10]
0x14000d4b2  mov     rax, rdi
0x14000d4b5  add     rsp, 20h
0x14000d4b9  pop     rdi
0x14000d4ba  pop     rsi
0x14000d4bb  pop     rbp
0x14000d4bc  retn
```
