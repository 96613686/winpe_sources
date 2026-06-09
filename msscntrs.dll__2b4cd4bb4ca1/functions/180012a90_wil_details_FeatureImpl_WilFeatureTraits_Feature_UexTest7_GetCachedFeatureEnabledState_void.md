# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x180012a90`
- end: `0x180012b69`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800138b0`

## callees

- `0x180005c18`
- `0x180009714`
- `0x180012a90`
- `0x180013220`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UexTest7__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UexTest7__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UexTest7__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UexTest7__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180012a90  mov     [rsp+arg_10], rbx
0x180012a95  mov     [rsp+arg_0], rcx
0x180012a9a  push    rbp
0x180012a9b  push    rsi
0x180012a9c  push    rdi
0x180012a9d  sub     rsp, 20h
0x180012aa1  mov     rsi, cs:Feature_UexTest7__descriptor
0x180012aa8  mov     rdi, rdx
0x180012aab  mov     qword ptr [rdx], 0
0x180012ab2  mov     eax, [rsi]
0x180012ab4  mov     [rdx], eax
0x180012ab6  and     eax, 6
0x180012ab9  cmp     al, 6
0x180012abb  jz      loc_180012B59
0x180012ac1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012ac6  lea     r8, [rsp+38h+arg_0]
0x180012acb  mov     dword ptr [rsp+38h+arg_0], 0
0x180012ad3  lea     rdx, [rsp+38h+arg_8]
0x180012ad8  mov     ebp, eax
0x180012ada  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x180012adf  mov     eax, [rdi]
0x180012ae1  mov     rbx, [rsp+38h+arg_8]
0x180012ae6  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012aeb  mov     edx, eax
0x180012aed  mov     [rdi], eax
0x180012aef  mov     ecx, eax
0x180012af1  jz      short loc_180012B0C
0x180012af3  test    dl, 2
0x180012af6  jnz     short loc_180012B0C
0x180012af8  and     ecx, 0FFFFF63Eh
0x180012afe  mov     eax, ebx
0x180012b00  and     eax, 9C1h
0x180012b05  or      ecx, eax
0x180012b07  or      ecx, 2
0x180012b0a  mov     [rdi], ecx
0x180012b0c  mov     r8d, edx
0x180012b0f  and     r8d, 4
0x180012b13  jnz     short loc_180012B27
0x180012b15  btr     ecx, 0Ah
0x180012b19  mov     eax, ebx
0x180012b1b  and     eax, 400h
0x180012b20  or      ecx, eax
0x180012b22  or      ecx, 4
0x180012b25  mov     [rdi], ecx
0x180012b27  mov     eax, edx
0x180012b29  lock cmpxchg [rsi], ecx
0x180012b2d  jnz     short loc_180012AE6
0x180012b2f  test    r8d, r8d
0x180012b32  jnz     short loc_180012B44
0x180012b34  mov     r8d, ebp
0x180012b37  mov     edx, 3
0x180012b3c  mov     rcx, rsi
0x180012b3f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012b44  mov     eax, [rdi]
0x180012b46  test    al, 2
0x180012b48  jnz     short loc_180012B59
0x180012b4a  and     eax, 0FFFFF63Eh
0x180012b4f  and     ebx, 9C1h
0x180012b55  or      eax, ebx
0x180012b57  mov     [rdi], eax
0x180012b59  mov     rbx, [rsp+38h+arg_10]
0x180012b5e  mov     rax, rdi
0x180012b61  add     rsp, 20h
0x180012b65  pop     rdi
0x180012b66  pop     rsi
0x180012b67  pop     rbp
0x180012b68  retn
```
