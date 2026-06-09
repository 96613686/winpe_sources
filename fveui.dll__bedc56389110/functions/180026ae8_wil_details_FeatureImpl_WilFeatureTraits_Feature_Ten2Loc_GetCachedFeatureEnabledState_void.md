# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x180026ae8`
- end: `0x180026bc1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028d0c`
- `0x1800290f4`

## callees

- `0x1800086f8`
- `0x18000bb98`
- `0x180026ae8`
- `0x180027250`

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
0x180026ae8  mov     [rsp+arg_10], rbx
0x180026aed  mov     [rsp+arg_0], rcx
0x180026af2  push    rbp
0x180026af3  push    rsi
0x180026af4  push    rdi
0x180026af5  sub     rsp, 20h
0x180026af9  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x180026b00  mov     rdi, rdx
0x180026b03  mov     qword ptr [rdx], 0
0x180026b0a  mov     eax, [rsi]
0x180026b0c  mov     [rdx], eax
0x180026b0e  and     eax, 6
0x180026b11  cmp     al, 6
0x180026b13  jz      loc_180026BB1
0x180026b19  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180026b1e  lea     r8, [rsp+38h+arg_0]
0x180026b23  mov     dword ptr [rsp+38h+arg_0], 0
0x180026b2b  lea     rdx, [rsp+38h+arg_8]
0x180026b30  mov     ebp, eax
0x180026b32  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x180026b37  mov     eax, [rdi]
0x180026b39  mov     rbx, [rsp+38h+arg_8]
0x180026b3e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180026b43  mov     edx, eax
0x180026b45  mov     [rdi], eax
0x180026b47  mov     ecx, eax
0x180026b49  jz      short loc_180026B64
0x180026b4b  test    dl, 2
0x180026b4e  jnz     short loc_180026B64
0x180026b50  and     ecx, 0FFFFF63Eh
0x180026b56  mov     eax, ebx
0x180026b58  and     eax, 9C1h
0x180026b5d  or      ecx, eax
0x180026b5f  or      ecx, 2
0x180026b62  mov     [rdi], ecx
0x180026b64  mov     r8d, edx
0x180026b67  and     r8d, 4
0x180026b6b  jnz     short loc_180026B7F
0x180026b6d  btr     ecx, 0Ah
0x180026b71  mov     eax, ebx
0x180026b73  and     eax, 400h
0x180026b78  or      ecx, eax
0x180026b7a  or      ecx, 4
0x180026b7d  mov     [rdi], ecx
0x180026b7f  mov     eax, edx
0x180026b81  lock cmpxchg [rsi], ecx
0x180026b85  jnz     short loc_180026B3E
0x180026b87  test    r8d, r8d
0x180026b8a  jnz     short loc_180026B9C
0x180026b8c  mov     r8d, ebp
0x180026b8f  mov     edx, 3
0x180026b94  mov     rcx, rsi
0x180026b97  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180026b9c  mov     eax, [rdi]
0x180026b9e  test    al, 2
0x180026ba0  jnz     short loc_180026BB1
0x180026ba2  and     eax, 0FFFFF63Eh
0x180026ba7  and     ebx, 9C1h
0x180026bad  or      eax, ebx
0x180026baf  mov     [rdi], eax
0x180026bb1  mov     rbx, [rsp+38h+arg_10]
0x180026bb6  mov     rax, rdi
0x180026bb9  add     rsp, 20h
0x180026bbd  pop     rdi
0x180026bbe  pop     rsi
0x180026bbf  pop     rbp
0x180026bc0  retn
```
