# wil::details::FeatureImpl<__WilFeatureTraits_Feature_59116012>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ce08`
- end: `0x18000cef0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_59116012@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800164a4`

## callees

- `0x18000ae90`
- `0x18000ce08`
- `0x18000d32c`
- `0x1800140e0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_59116012>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // eax
  int v5; // esi
  __int64 v6; // rcx
  signed __int32 i; // r8d
  __int16 v8; // ax
  bool v9; // zf
  signed __int32 v10; // edx
  signed __int32 v11; // eax
  int v13; // [rsp+38h] [rbp+10h] BYREF
  __int64 v14; // [rsp+40h] [rbp+18h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_59116012__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_59116012__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v13 = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_59116012>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v11 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_59116012__descriptor, v10, i);
      if ( i == v11 )
        break;
    }
    if ( (i & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_59116012__descriptor,
        0,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v14 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000ce08  mov     [rsp+arg_0], rbx
0x18000ce0d  mov     [rsp+arg_18], rsi
0x18000ce12  push    rdi
0x18000ce13  sub     rsp, 20h
0x18000ce17  and     qword ptr [rdx], 0
0x18000ce1b  mov     rbx, rdx
0x18000ce1e  mov     rdi, cs:Feature_59116012__descriptor
0x18000ce25  mov     eax, [rdi]
0x18000ce27  mov     [rdx], eax
0x18000ce29  and     eax, 6
0x18000ce2c  cmp     al, 6
0x18000ce2e  jz      loc_18000CEDC
0x18000ce34  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ce39  and     [rsp+28h+arg_8], 0
0x18000ce3e  lea     r8, [rsp+28h+arg_8]
0x18000ce43  lea     rdx, [rsp+28h+arg_10]
0x18000ce48  mov     esi, eax
0x18000ce4a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_59116012@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59116012>::GetCurrentFeatureEnabledState(int *)
0x18000ce4f  test    esi, esi
0x18000ce51  jnz     short loc_18000CE57
0x18000ce53  and     [rsp+28h+arg_8], esi
0x18000ce57  mov     r8d, [rbx]
0x18000ce5a  mov     rax, [rsp+28h+arg_10]
0x18000ce5f  mov     ecx, r8d
0x18000ce62  bts     ecx, 12h
0x18000ce66  cmp     [rsp+28h+arg_8], 0
0x18000ce6b  mov     edx, ecx
0x18000ce6d  mov     [rbx], ecx
0x18000ce6f  jz      short loc_18000CE8B
0x18000ce71  test    cl, 2
0x18000ce74  jnz     short loc_18000CE8B
0x18000ce76  and     edx, 0FFFFF63Eh
0x18000ce7c  mov     ecx, eax
0x18000ce7e  and     ecx, 9C1h
0x18000ce84  or      edx, ecx
0x18000ce86  or      edx, 2
0x18000ce89  mov     [rbx], edx
0x18000ce8b  test    r8b, 4
0x18000ce8f  jnz     short loc_18000CEA1
0x18000ce91  btr     edx, 0Ah
0x18000ce95  and     eax, 400h
0x18000ce9a  or      edx, eax
0x18000ce9c  or      edx, 4
0x18000ce9f  mov     [rbx], edx
0x18000cea1  mov     eax, r8d
0x18000cea4  lock cmpxchg [rdi], edx
0x18000cea8  jz      short loc_18000CEAF
0x18000ceaa  mov     r8d, eax
0x18000cead  jmp     short loc_18000CE5A
0x18000ceaf  test    r8b, 4
0x18000ceb3  jnz     short loc_18000CEC2
0x18000ceb5  mov     r8d, esi
0x18000ceb8  xor     edx, edx
0x18000ceba  mov     rcx, rdi
0x18000cebd  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000cec2  mov     ecx, [rbx]
0x18000cec4  test    cl, 2
0x18000cec7  jnz     short loc_18000CEDC
0x18000cec9  mov     eax, dword ptr [rsp+28h+arg_10]
0x18000cecd  and     ecx, 0FFFFF63Eh
0x18000ced3  and     eax, 9C1h
0x18000ced8  or      ecx, eax
0x18000ceda  mov     [rbx], ecx
0x18000cedc  mov     rsi, [rsp+28h+arg_18]
0x18000cee1  mov     rax, rbx
0x18000cee4  mov     rbx, [rsp+28h+arg_0]
0x18000cee9  add     rsp, 20h
0x18000ceed  pop     rdi
0x18000ceee  retn
```
