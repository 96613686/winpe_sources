# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x18000d464`
- end: `0x18000d53d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010998`

## callees

- `0x180005c18`
- `0x180009714`
- `0x18000d464`
- `0x18000d7ec`

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
0x18000d464  mov     [rsp+arg_10], rbx
0x18000d469  mov     [rsp+arg_0], rcx
0x18000d46e  push    rbp
0x18000d46f  push    rsi
0x18000d470  push    rdi
0x18000d471  sub     rsp, 20h
0x18000d475  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x18000d47c  mov     rdi, rdx
0x18000d47f  mov     qword ptr [rdx], 0
0x18000d486  mov     eax, [rsi]
0x18000d488  mov     [rdx], eax
0x18000d48a  and     eax, 6
0x18000d48d  cmp     al, 6
0x18000d48f  jz      loc_18000D52D
0x18000d495  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000d49a  lea     r8, [rsp+38h+arg_0]
0x18000d49f  mov     dword ptr [rsp+38h+arg_0], 0
0x18000d4a7  lea     rdx, [rsp+38h+arg_8]
0x18000d4ac  mov     ebp, eax
0x18000d4ae  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18000d4b3  mov     eax, [rdi]
0x18000d4b5  mov     rbx, [rsp+38h+arg_8]
0x18000d4ba  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000d4bf  mov     edx, eax
0x18000d4c1  mov     [rdi], eax
0x18000d4c3  mov     ecx, eax
0x18000d4c5  jz      short loc_18000D4E0
0x18000d4c7  test    dl, 2
0x18000d4ca  jnz     short loc_18000D4E0
0x18000d4cc  and     ecx, 0FFFFF63Eh
0x18000d4d2  mov     eax, ebx
0x18000d4d4  and     eax, 9C1h
0x18000d4d9  or      ecx, eax
0x18000d4db  or      ecx, 2
0x18000d4de  mov     [rdi], ecx
0x18000d4e0  mov     r8d, edx
0x18000d4e3  and     r8d, 4
0x18000d4e7  jnz     short loc_18000D4FB
0x18000d4e9  btr     ecx, 0Ah
0x18000d4ed  mov     eax, ebx
0x18000d4ef  and     eax, 400h
0x18000d4f4  or      ecx, eax
0x18000d4f6  or      ecx, 4
0x18000d4f9  mov     [rdi], ecx
0x18000d4fb  mov     eax, edx
0x18000d4fd  lock cmpxchg [rsi], ecx
0x18000d501  jnz     short loc_18000D4BA
0x18000d503  test    r8d, r8d
0x18000d506  jnz     short loc_18000D518
0x18000d508  mov     r8d, ebp
0x18000d50b  mov     edx, 3
0x18000d510  mov     rcx, rsi
0x18000d513  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000d518  mov     eax, [rdi]
0x18000d51a  test    al, 2
0x18000d51c  jnz     short loc_18000D52D
0x18000d51e  and     eax, 0FFFFF63Eh
0x18000d523  and     ebx, 9C1h
0x18000d529  or      eax, ebx
0x18000d52b  mov     [rdi], eax
0x18000d52d  mov     rbx, [rsp+38h+arg_10]
0x18000d532  mov     rax, rdi
0x18000d535  add     rsp, 20h
0x18000d539  pop     rdi
0x18000d53a  pop     rsi
0x18000d53b  pop     rbp
0x18000d53c  retn
```
