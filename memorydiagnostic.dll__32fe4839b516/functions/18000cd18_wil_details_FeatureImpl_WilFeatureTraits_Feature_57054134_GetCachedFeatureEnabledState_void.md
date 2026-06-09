# wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::GetCachedFeatureEnabledState(void)

- ea: `0x18000cd18`
- end: `0x18000ce00`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `232`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010f30`
- `0x180016464`
- `0x18001f10c`

## callees

- `0x18000ae90`
- `0x18000cd18`
- `0x18000d1e4`
- `0x1800140e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // esi
  __int64 v6; // rcx
  signed __int32 i; // r8d
  __int16 v8; // ax
  bool v9; // zf
  signed __int32 v10; // edx
  signed __int32 v11; // eax
  int v13; // [rsp+38h] [rbp+10h] BYREF
  __int64 v14; // [rsp+40h] [rbp+18h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_57054134__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_57054134__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v13 = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
    if ( !v5 )
      v13 = 0;
    for ( i = *(_DWORD *)a2; ; i = v11 )
    {
      v8 = v14;
      v9 = v13 == 0;
      v10 = i | 0x40000;
      *(_DWORD *)a2 = i | 0x40000;
      if ( !v9 && (i & 2) == 0 )
      {
        v10 = v8 & 0x9C1 | i & 0xFFFBF63E | 0x40000 | 2;
        *(_DWORD *)a2 = v10;
      }
      if ( (i & 4) == 0 )
      {
        v10 = v8 & 0x400 | v10 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v10;
      }
      v11 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_57054134__descriptor, v10, i);
      if ( i == v11 )
        break;
    }
    if ( (i & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_57054134__descriptor, 0, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v14 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000cd18  mov     [rsp+arg_0], rbx
0x18000cd1d  mov     [rsp+arg_18], rsi
0x18000cd22  push    rdi
0x18000cd23  sub     rsp, 20h
0x18000cd27  and     qword ptr [rdx], 0
0x18000cd2b  mov     rbx, rdx
0x18000cd2e  mov     rdi, cs:Feature_57054134__descriptor
0x18000cd35  mov     eax, [rdi]
0x18000cd37  mov     [rdx], eax
0x18000cd39  and     eax, 6
0x18000cd3c  cmp     al, 6
0x18000cd3e  jz      loc_18000CDEC
0x18000cd44  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000cd49  and     [rsp+28h+arg_8], 0
0x18000cd4e  lea     r8, [rsp+28h+arg_8]
0x18000cd53  lea     rdx, [rsp+28h+arg_10]
0x18000cd58  mov     esi, eax
0x18000cd5a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::GetCurrentFeatureEnabledState(int *)
0x18000cd5f  test    esi, esi
0x18000cd61  jnz     short loc_18000CD67
0x18000cd63  and     [rsp+28h+arg_8], esi
0x18000cd67  mov     r8d, [rbx]
0x18000cd6a  mov     rax, [rsp+28h+arg_10]
0x18000cd6f  mov     ecx, r8d
0x18000cd72  bts     ecx, 12h
0x18000cd76  cmp     [rsp+28h+arg_8], 0
0x18000cd7b  mov     edx, ecx
0x18000cd7d  mov     [rbx], ecx
0x18000cd7f  jz      short loc_18000CD9B
0x18000cd81  test    cl, 2
0x18000cd84  jnz     short loc_18000CD9B
0x18000cd86  and     edx, 0FFFFF63Eh
0x18000cd8c  mov     ecx, eax
0x18000cd8e  and     ecx, 9C1h
0x18000cd94  or      edx, ecx
0x18000cd96  or      edx, 2
0x18000cd99  mov     [rbx], edx
0x18000cd9b  test    r8b, 4
0x18000cd9f  jnz     short loc_18000CDB1
0x18000cda1  btr     edx, 0Ah
0x18000cda5  and     eax, 400h
0x18000cdaa  or      edx, eax
0x18000cdac  or      edx, 4
0x18000cdaf  mov     [rbx], edx
0x18000cdb1  mov     eax, r8d
0x18000cdb4  lock cmpxchg [rdi], edx
0x18000cdb8  jz      short loc_18000CDBF
0x18000cdba  mov     r8d, eax
0x18000cdbd  jmp     short loc_18000CD6A
0x18000cdbf  test    r8b, 4
0x18000cdc3  jnz     short loc_18000CDD2
0x18000cdc5  mov     r8d, esi
0x18000cdc8  xor     edx, edx
0x18000cdca  mov     rcx, rdi
0x18000cdcd  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000cdd2  mov     ecx, [rbx]
0x18000cdd4  test    cl, 2
0x18000cdd7  jnz     short loc_18000CDEC
0x18000cdd9  mov     eax, dword ptr [rsp+28h+arg_10]
0x18000cddd  and     ecx, 0FFFFF63Eh
0x18000cde3  and     eax, 9C1h
0x18000cde8  or      ecx, eax
0x18000cdea  mov     [rbx], ecx
0x18000cdec  mov     rsi, [rsp+28h+arg_18]
0x18000cdf1  mov     rax, rbx
0x18000cdf4  mov     rbx, [rsp+28h+arg_0]
0x18000cdf9  add     rsp, 20h
0x18000cdfd  pop     rdi
0x18000cdfe  retn
```
