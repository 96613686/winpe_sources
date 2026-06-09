# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180012b70`
- end: `0x180012c49`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001394c`

## callees

- `0x180005c18`
- `0x180009714`
- `0x180012b70`
- `0x180013390`

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
0x180012b70  mov     [rsp+arg_10], rbx
0x180012b75  mov     [rsp+arg_0], rcx
0x180012b7a  push    rbp
0x180012b7b  push    rsi
0x180012b7c  push    rdi
0x180012b7d  sub     rsp, 20h
0x180012b81  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180012b88  mov     rdi, rdx
0x180012b8b  mov     qword ptr [rdx], 0
0x180012b92  mov     eax, [rsi]
0x180012b94  mov     [rdx], eax
0x180012b96  and     eax, 6
0x180012b99  cmp     al, 6
0x180012b9b  jz      loc_180012C39
0x180012ba1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012ba6  lea     r8, [rsp+38h+arg_0]
0x180012bab  mov     dword ptr [rsp+38h+arg_0], 0
0x180012bb3  lea     rdx, [rsp+38h+arg_8]
0x180012bb8  mov     ebp, eax
0x180012bba  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180012bbf  mov     eax, [rdi]
0x180012bc1  mov     rbx, [rsp+38h+arg_8]
0x180012bc6  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012bcb  mov     edx, eax
0x180012bcd  mov     [rdi], eax
0x180012bcf  mov     ecx, eax
0x180012bd1  jz      short loc_180012BEC
0x180012bd3  test    dl, 2
0x180012bd6  jnz     short loc_180012BEC
0x180012bd8  and     ecx, 0FFFFF63Eh
0x180012bde  mov     eax, ebx
0x180012be0  and     eax, 9C1h
0x180012be5  or      ecx, eax
0x180012be7  or      ecx, 2
0x180012bea  mov     [rdi], ecx
0x180012bec  mov     r8d, edx
0x180012bef  and     r8d, 4
0x180012bf3  jnz     short loc_180012C07
0x180012bf5  btr     ecx, 0Ah
0x180012bf9  mov     eax, ebx
0x180012bfb  and     eax, 400h
0x180012c00  or      ecx, eax
0x180012c02  or      ecx, 4
0x180012c05  mov     [rdi], ecx
0x180012c07  mov     eax, edx
0x180012c09  lock cmpxchg [rsi], ecx
0x180012c0d  jnz     short loc_180012BC6
0x180012c0f  test    r8d, r8d
0x180012c12  jnz     short loc_180012C24
0x180012c14  mov     r8d, ebp
0x180012c17  mov     edx, 3
0x180012c1c  mov     rcx, rsi
0x180012c1f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012c24  mov     eax, [rdi]
0x180012c26  test    al, 2
0x180012c28  jnz     short loc_180012C39
0x180012c2a  and     eax, 0FFFFF63Eh
0x180012c2f  and     ebx, 9C1h
0x180012c35  or      eax, ebx
0x180012c37  mov     [rdi], eax
0x180012c39  mov     rbx, [rsp+38h+arg_10]
0x180012c3e  mov     rax, rdi
0x180012c41  add     rsp, 20h
0x180012c45  pop     rdi
0x180012c46  pop     rsi
0x180012c47  pop     rbp
0x180012c48  retn
```
