# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x14000d064`
- end: `0x14000d13d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e77c`
- `0x14000ec20`

## callees

- `0x140007508`
- `0x1400096d0`
- `0x14000d064`
- `0x14000d8dc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Ten2Loc__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x14000d064  mov     [rsp+arg_10], rbx
0x14000d069  mov     [rsp+arg_0], rcx
0x14000d06e  push    rbp
0x14000d06f  push    rsi
0x14000d070  push    rdi
0x14000d071  sub     rsp, 20h
0x14000d075  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x14000d07c  mov     rdi, rdx
0x14000d07f  mov     qword ptr [rdx], 0
0x14000d086  mov     eax, [rsi]
0x14000d088  mov     [rdx], eax
0x14000d08a  and     eax, 6
0x14000d08d  cmp     al, 6
0x14000d08f  jz      loc_14000D12D
0x14000d095  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000d09a  lea     r8, [rsp+38h+arg_0]
0x14000d09f  mov     dword ptr [rsp+38h+arg_0], 0
0x14000d0a7  lea     rdx, [rsp+38h+arg_8]
0x14000d0ac  mov     ebp, eax
0x14000d0ae  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x14000d0b3  mov     eax, [rdi]
0x14000d0b5  mov     rbx, [rsp+38h+arg_8]
0x14000d0ba  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000d0bf  mov     edx, eax
0x14000d0c1  mov     [rdi], eax
0x14000d0c3  mov     ecx, eax
0x14000d0c5  jz      short loc_14000D0E0
0x14000d0c7  test    dl, 2
0x14000d0ca  jnz     short loc_14000D0E0
0x14000d0cc  and     ecx, 0FFFFF63Eh
0x14000d0d2  mov     eax, ebx
0x14000d0d4  and     eax, 9C1h
0x14000d0d9  or      ecx, eax
0x14000d0db  or      ecx, 2
0x14000d0de  mov     [rdi], ecx
0x14000d0e0  mov     r8d, edx
0x14000d0e3  and     r8d, 4
0x14000d0e7  jnz     short loc_14000D0FB
0x14000d0e9  btr     ecx, 0Ah
0x14000d0ed  mov     eax, ebx
0x14000d0ef  and     eax, 400h
0x14000d0f4  or      ecx, eax
0x14000d0f6  or      ecx, 4
0x14000d0f9  mov     [rdi], ecx
0x14000d0fb  mov     eax, edx
0x14000d0fd  lock cmpxchg [rsi], ecx
0x14000d101  jnz     short loc_14000D0BA
0x14000d103  test    r8d, r8d
0x14000d106  jnz     short loc_14000D118
0x14000d108  mov     r8d, ebp
0x14000d10b  mov     edx, 3
0x14000d110  mov     rcx, rsi
0x14000d113  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000d118  mov     eax, [rdi]
0x14000d11a  test    al, 2
0x14000d11c  jnz     short loc_14000D12D
0x14000d11e  and     eax, 0FFFFF63Eh
0x14000d123  and     ebx, 9C1h
0x14000d129  or      eax, ebx
0x14000d12b  mov     [rdi], eax
0x14000d12d  mov     rbx, [rsp+38h+arg_10]
0x14000d132  mov     rax, rdi
0x14000d135  add     rsp, 20h
0x14000d139  pop     rdi
0x14000d13a  pop     rsi
0x14000d13b  pop     rbp
0x14000d13c  retn
```
