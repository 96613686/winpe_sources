# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f258`
- end: `0x18000f331`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800116a4`

## callees

- `0x18000426c`
- `0x180005e58`
- `0x18000f258`
- `0x18000f8d4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  signed __int32 v8; // edx
  unsigned int v9; // ecx
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_UexTest7__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UexTest7__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(v5, &v11);
    v6 = *(_DWORD *)a2;
    v7 = v11;
    do
    {
      v8 = v6;
      *(_DWORD *)a2 = v6;
      v9 = v6;
      if ( (v6 & 4) == 0 )
      {
        v9 = v7 & 0x400 | v6 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v9;
      }
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UexTest7__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_UexTest7__descriptor,
        3,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000f258  mov     [rsp+arg_10], rbx
0x18000f25d  mov     [rsp+arg_0], rcx
0x18000f262  push    rbp
0x18000f263  push    rsi
0x18000f264  push    rdi
0x18000f265  sub     rsp, 20h
0x18000f269  mov     rsi, cs:Feature_UexTest7__descriptor
0x18000f270  mov     rdi, rdx
0x18000f273  mov     qword ptr [rdx], 0
0x18000f27a  mov     eax, [rsi]
0x18000f27c  mov     [rdx], eax
0x18000f27e  and     eax, 6
0x18000f281  cmp     al, 6
0x18000f283  jz      loc_18000F321
0x18000f289  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f28e  lea     r8, [rsp+38h+arg_0]
0x18000f293  mov     dword ptr [rsp+38h+arg_0], 0
0x18000f29b  lea     rdx, [rsp+38h+arg_8]
0x18000f2a0  mov     ebp, eax
0x18000f2a2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x18000f2a7  mov     eax, [rdi]
0x18000f2a9  mov     rbx, [rsp+38h+arg_8]
0x18000f2ae  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000f2b3  mov     edx, eax
0x18000f2b5  mov     [rdi], eax
0x18000f2b7  mov     ecx, eax
0x18000f2b9  jz      short loc_18000F2D4
0x18000f2bb  test    dl, 2
0x18000f2be  jnz     short loc_18000F2D4
0x18000f2c0  and     ecx, 0FFFFF63Eh
0x18000f2c6  mov     eax, ebx
0x18000f2c8  and     eax, 9C1h
0x18000f2cd  or      ecx, eax
0x18000f2cf  or      ecx, 2
0x18000f2d2  mov     [rdi], ecx
0x18000f2d4  mov     r8d, edx
0x18000f2d7  and     r8d, 4
0x18000f2db  jnz     short loc_18000F2EF
0x18000f2dd  btr     ecx, 0Ah
0x18000f2e1  mov     eax, ebx
0x18000f2e3  and     eax, 400h
0x18000f2e8  or      ecx, eax
0x18000f2ea  or      ecx, 4
0x18000f2ed  mov     [rdi], ecx
0x18000f2ef  mov     eax, edx
0x18000f2f1  lock cmpxchg [rsi], ecx
0x18000f2f5  jnz     short loc_18000F2AE
0x18000f2f7  test    r8d, r8d
0x18000f2fa  jnz     short loc_18000F30C
0x18000f2fc  mov     r8d, ebp
0x18000f2ff  mov     edx, 3
0x18000f304  mov     rcx, rsi
0x18000f307  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000f30c  mov     eax, [rdi]
0x18000f30e  test    al, 2
0x18000f310  jnz     short loc_18000F321
0x18000f312  and     eax, 0FFFFF63Eh
0x18000f317  and     ebx, 9C1h
0x18000f31d  or      eax, ebx
0x18000f31f  mov     [rdi], eax
0x18000f321  mov     rbx, [rsp+38h+arg_10]
0x18000f326  mov     rax, rdi
0x18000f329  add     rsp, 20h
0x18000f32d  pop     rdi
0x18000f32e  pop     rsi
0x18000f32f  pop     rbp
0x18000f330  retn
```
