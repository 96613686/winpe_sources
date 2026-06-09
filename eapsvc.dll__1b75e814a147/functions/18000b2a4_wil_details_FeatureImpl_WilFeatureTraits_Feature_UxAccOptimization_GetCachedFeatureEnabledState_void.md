# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b2a4`
- end: `0x18000b37d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bec0`

## callees

- `0x180004f18`
- `0x180008dc0`
- `0x18000b2a4`
- `0x18000b384`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UxAccOptimization__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000b2a4  mov     [rsp+arg_10], rbx
0x18000b2a9  mov     [rsp+arg_0], rcx
0x18000b2ae  push    rbp
0x18000b2af  push    rsi
0x18000b2b0  push    rdi
0x18000b2b1  sub     rsp, 20h
0x18000b2b5  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x18000b2bc  mov     rdi, rdx
0x18000b2bf  mov     qword ptr [rdx], 0
0x18000b2c6  mov     eax, [rsi]
0x18000b2c8  mov     [rdx], eax
0x18000b2ca  and     eax, 6
0x18000b2cd  cmp     al, 6
0x18000b2cf  jz      loc_18000B36D
0x18000b2d5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000b2da  lea     r8, [rsp+38h+arg_0]
0x18000b2df  mov     dword ptr [rsp+38h+arg_0], 0
0x18000b2e7  lea     rdx, [rsp+38h+arg_8]
0x18000b2ec  mov     ebp, eax
0x18000b2ee  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18000b2f3  mov     eax, [rdi]
0x18000b2f5  mov     rbx, [rsp+38h+arg_8]
0x18000b2fa  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000b2ff  mov     edx, eax
0x18000b301  mov     [rdi], eax
0x18000b303  mov     ecx, eax
0x18000b305  jz      short loc_18000B320
0x18000b307  test    dl, 2
0x18000b30a  jnz     short loc_18000B320
0x18000b30c  and     ecx, 0FFFFF63Eh
0x18000b312  mov     eax, ebx
0x18000b314  and     eax, 9C1h
0x18000b319  or      ecx, eax
0x18000b31b  or      ecx, 2
0x18000b31e  mov     [rdi], ecx
0x18000b320  mov     r8d, edx
0x18000b323  and     r8d, 4
0x18000b327  jnz     short loc_18000B33B
0x18000b329  btr     ecx, 0Ah
0x18000b32d  mov     eax, ebx
0x18000b32f  and     eax, 400h
0x18000b334  or      ecx, eax
0x18000b336  or      ecx, 4
0x18000b339  mov     [rdi], ecx
0x18000b33b  mov     eax, edx
0x18000b33d  lock cmpxchg [rsi], ecx
0x18000b341  jnz     short loc_18000B2FA
0x18000b343  test    r8d, r8d
0x18000b346  jnz     short loc_18000B358
0x18000b348  mov     r8d, ebp
0x18000b34b  mov     edx, 3
0x18000b350  mov     rcx, rsi
0x18000b353  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000b358  mov     eax, [rdi]
0x18000b35a  test    al, 2
0x18000b35c  jnz     short loc_18000B36D
0x18000b35e  and     eax, 0FFFFF63Eh
0x18000b363  and     ebx, 9C1h
0x18000b369  or      eax, ebx
0x18000b36b  mov     [rdi], eax
0x18000b36d  mov     rbx, [rsp+38h+arg_10]
0x18000b372  mov     rax, rdi
0x18000b375  add     rsp, 20h
0x18000b379  pop     rdi
0x18000b37a  pop     rsi
0x18000b37b  pop     rbp
0x18000b37c  retn
```
