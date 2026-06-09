# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180012b88`
- end: `0x180012c61`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013bdc`

## callees

- `0x1800058f8`
- `0x18000b7c8`
- `0x180012b88`
- `0x180012f48`

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
0x180012b88  mov     [rsp+arg_10], rbx
0x180012b8d  mov     [rsp+arg_0], rcx
0x180012b92  push    rbp
0x180012b93  push    rsi
0x180012b94  push    rdi
0x180012b95  sub     rsp, 20h
0x180012b99  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180012ba0  mov     rdi, rdx
0x180012ba3  mov     qword ptr [rdx], 0
0x180012baa  mov     eax, [rsi]
0x180012bac  mov     [rdx], eax
0x180012bae  and     eax, 6
0x180012bb1  cmp     al, 6
0x180012bb3  jz      loc_180012C51
0x180012bb9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012bbe  lea     r8, [rsp+38h+arg_0]
0x180012bc3  mov     dword ptr [rsp+38h+arg_0], 0
0x180012bcb  lea     rdx, [rsp+38h+arg_8]
0x180012bd0  mov     ebp, eax
0x180012bd2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180012bd7  mov     eax, [rdi]
0x180012bd9  mov     rbx, [rsp+38h+arg_8]
0x180012bde  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012be3  mov     edx, eax
0x180012be5  mov     [rdi], eax
0x180012be7  mov     ecx, eax
0x180012be9  jz      short loc_180012C04
0x180012beb  test    dl, 2
0x180012bee  jnz     short loc_180012C04
0x180012bf0  and     ecx, 0FFFFF63Eh
0x180012bf6  mov     eax, ebx
0x180012bf8  and     eax, 9C1h
0x180012bfd  or      ecx, eax
0x180012bff  or      ecx, 2
0x180012c02  mov     [rdi], ecx
0x180012c04  mov     r8d, edx
0x180012c07  and     r8d, 4
0x180012c0b  jnz     short loc_180012C1F
0x180012c0d  btr     ecx, 0Ah
0x180012c11  mov     eax, ebx
0x180012c13  and     eax, 400h
0x180012c18  or      ecx, eax
0x180012c1a  or      ecx, 4
0x180012c1d  mov     [rdi], ecx
0x180012c1f  mov     eax, edx
0x180012c21  lock cmpxchg [rsi], ecx
0x180012c25  jnz     short loc_180012BDE
0x180012c27  test    r8d, r8d
0x180012c2a  jnz     short loc_180012C3C
0x180012c2c  mov     r8d, ebp
0x180012c2f  mov     edx, 3
0x180012c34  mov     rcx, rsi
0x180012c37  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012c3c  mov     eax, [rdi]
0x180012c3e  test    al, 2
0x180012c40  jnz     short loc_180012C51
0x180012c42  and     eax, 0FFFFF63Eh
0x180012c47  and     ebx, 9C1h
0x180012c4d  or      eax, ebx
0x180012c4f  mov     [rdi], eax
0x180012c51  mov     rbx, [rsp+38h+arg_10]
0x180012c56  mov     rax, rdi
0x180012c59  add     rsp, 20h
0x180012c5d  pop     rdi
0x180012c5e  pop     rsi
0x180012c5f  pop     rbp
0x180012c60  retn
```
