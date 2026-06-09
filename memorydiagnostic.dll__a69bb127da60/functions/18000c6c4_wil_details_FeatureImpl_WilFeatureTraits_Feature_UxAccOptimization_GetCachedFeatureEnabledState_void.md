# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x18000c6c4`
- end: `0x18000c79d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015804`

## callees

- `0x18000ad30`
- `0x18000c6c4`
- `0x18000cbbc`
- `0x1800135a0`

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
0x18000c6c4  mov     [rsp+arg_10], rbx
0x18000c6c9  mov     [rsp+arg_0], rcx
0x18000c6ce  push    rbp
0x18000c6cf  push    rsi
0x18000c6d0  push    rdi
0x18000c6d1  sub     rsp, 20h
0x18000c6d5  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x18000c6dc  mov     rdi, rdx
0x18000c6df  mov     qword ptr [rdx], 0
0x18000c6e6  mov     eax, [rsi]
0x18000c6e8  mov     [rdx], eax
0x18000c6ea  and     eax, 6
0x18000c6ed  cmp     al, 6
0x18000c6ef  jz      loc_18000C78D
0x18000c6f5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000c6fa  lea     r8, [rsp+38h+arg_0]
0x18000c6ff  mov     dword ptr [rsp+38h+arg_0], 0
0x18000c707  lea     rdx, [rsp+38h+arg_8]
0x18000c70c  mov     ebp, eax
0x18000c70e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18000c713  mov     eax, [rdi]
0x18000c715  mov     rbx, [rsp+38h+arg_8]
0x18000c71a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000c71f  mov     edx, eax
0x18000c721  mov     [rdi], eax
0x18000c723  mov     ecx, eax
0x18000c725  jz      short loc_18000C740
0x18000c727  test    dl, 2
0x18000c72a  jnz     short loc_18000C740
0x18000c72c  and     ecx, 0FFFFF63Eh
0x18000c732  mov     eax, ebx
0x18000c734  and     eax, 9C1h
0x18000c739  or      ecx, eax
0x18000c73b  or      ecx, 2
0x18000c73e  mov     [rdi], ecx
0x18000c740  mov     r8d, edx
0x18000c743  and     r8d, 4
0x18000c747  jnz     short loc_18000C75B
0x18000c749  btr     ecx, 0Ah
0x18000c74d  mov     eax, ebx
0x18000c74f  and     eax, 400h
0x18000c754  or      ecx, eax
0x18000c756  or      ecx, 4
0x18000c759  mov     [rdi], ecx
0x18000c75b  mov     eax, edx
0x18000c75d  lock cmpxchg [rsi], ecx
0x18000c761  jnz     short loc_18000C71A
0x18000c763  test    r8d, r8d
0x18000c766  jnz     short loc_18000C778
0x18000c768  mov     r8d, ebp
0x18000c76b  mov     edx, 3
0x18000c770  mov     rcx, rsi
0x18000c773  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000c778  mov     eax, [rdi]
0x18000c77a  test    al, 2
0x18000c77c  jnz     short loc_18000C78D
0x18000c77e  and     eax, 0FFFFF63Eh
0x18000c783  and     ebx, 9C1h
0x18000c789  or      eax, ebx
0x18000c78b  mov     [rdi], eax
0x18000c78d  mov     rbx, [rsp+38h+arg_10]
0x18000c792  mov     rax, rdi
0x18000c795  add     rsp, 20h
0x18000c799  pop     rdi
0x18000c79a  pop     rsi
0x18000c79b  pop     rbp
0x18000c79c  retn
```
