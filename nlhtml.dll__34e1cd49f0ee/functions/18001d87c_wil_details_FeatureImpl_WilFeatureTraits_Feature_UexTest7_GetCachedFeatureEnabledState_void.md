# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x18001d87c`
- end: `0x18001d955`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ed38`
- `0x18001f004`

## callees

- `0x180016c14`
- `0x180019b00`
- `0x18001d87c`
- `0x18001e174`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_UexTest7__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001d87c  mov     [rsp+arg_10], rbx
0x18001d881  mov     [rsp+arg_0], rcx
0x18001d886  push    rbp
0x18001d887  push    rsi
0x18001d888  push    rdi
0x18001d889  sub     rsp, 20h
0x18001d88d  mov     rsi, cs:Feature_UexTest7__descriptor
0x18001d894  mov     rdi, rdx
0x18001d897  mov     qword ptr [rdx], 0
0x18001d89e  mov     eax, [rsi]
0x18001d8a0  mov     [rdx], eax
0x18001d8a2  and     eax, 6
0x18001d8a5  cmp     al, 6
0x18001d8a7  jz      loc_18001D945
0x18001d8ad  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d8b2  lea     r8, [rsp+38h+arg_0]
0x18001d8b7  mov     dword ptr [rsp+38h+arg_0], 0
0x18001d8bf  lea     rdx, [rsp+38h+arg_8]
0x18001d8c4  mov     ebp, eax
0x18001d8c6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x18001d8cb  mov     eax, [rdi]
0x18001d8cd  mov     rbx, [rsp+38h+arg_8]
0x18001d8d2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001d8d7  mov     edx, eax
0x18001d8d9  mov     [rdi], eax
0x18001d8db  mov     ecx, eax
0x18001d8dd  jz      short loc_18001D8F8
0x18001d8df  test    dl, 2
0x18001d8e2  jnz     short loc_18001D8F8
0x18001d8e4  and     ecx, 0FFFFF63Eh
0x18001d8ea  mov     eax, ebx
0x18001d8ec  and     eax, 9C1h
0x18001d8f1  or      ecx, eax
0x18001d8f3  or      ecx, 2
0x18001d8f6  mov     [rdi], ecx
0x18001d8f8  mov     r8d, edx
0x18001d8fb  and     r8d, 4
0x18001d8ff  jnz     short loc_18001D913
0x18001d901  btr     ecx, 0Ah
0x18001d905  mov     eax, ebx
0x18001d907  and     eax, 400h
0x18001d90c  or      ecx, eax
0x18001d90e  or      ecx, 4
0x18001d911  mov     [rdi], ecx
0x18001d913  mov     eax, edx
0x18001d915  lock cmpxchg [rsi], ecx
0x18001d919  jnz     short loc_18001D8D2
0x18001d91b  test    r8d, r8d
0x18001d91e  jnz     short loc_18001D930
0x18001d920  mov     r8d, ebp
0x18001d923  mov     edx, 3
0x18001d928  mov     rcx, rsi
0x18001d92b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001d930  mov     eax, [rdi]
0x18001d932  test    al, 2
0x18001d934  jnz     short loc_18001D945
0x18001d936  and     eax, 0FFFFF63Eh
0x18001d93b  and     ebx, 9C1h
0x18001d941  or      eax, ebx
0x18001d943  mov     [rdi], eax
0x18001d945  mov     rbx, [rsp+38h+arg_10]
0x18001d94a  mov     rax, rdi
0x18001d94d  add     rsp, 20h
0x18001d951  pop     rdi
0x18001d952  pop     rsi
0x18001d953  pop     rbp
0x18001d954  retn
```
