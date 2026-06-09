# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b634`
- end: `0x18001b70d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bc1c`

## callees

- `0x180016c14`
- `0x180019b00`
- `0x18001b634`
- `0x18001b8b4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_Future__descriptor,
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
0x18001b634  mov     [rsp+arg_10], rbx
0x18001b639  mov     [rsp+arg_0], rcx
0x18001b63e  push    rbp
0x18001b63f  push    rsi
0x18001b640  push    rdi
0x18001b641  sub     rsp, 20h
0x18001b645  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x18001b64c  mov     rdi, rdx
0x18001b64f  mov     qword ptr [rdx], 0
0x18001b656  mov     eax, [rsi]
0x18001b658  mov     [rdx], eax
0x18001b65a  and     eax, 6
0x18001b65d  cmp     al, 6
0x18001b65f  jz      loc_18001B6FD
0x18001b665  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b66a  lea     r8, [rsp+38h+arg_0]
0x18001b66f  mov     dword ptr [rsp+38h+arg_0], 0
0x18001b677  lea     rdx, [rsp+38h+arg_8]
0x18001b67c  mov     ebp, eax
0x18001b67e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCurrentFeatureEnabledState(int *)
0x18001b683  mov     eax, [rdi]
0x18001b685  mov     rbx, [rsp+38h+arg_8]
0x18001b68a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001b68f  mov     edx, eax
0x18001b691  mov     [rdi], eax
0x18001b693  mov     ecx, eax
0x18001b695  jz      short loc_18001B6B0
0x18001b697  test    dl, 2
0x18001b69a  jnz     short loc_18001B6B0
0x18001b69c  and     ecx, 0FFFFF63Eh
0x18001b6a2  mov     eax, ebx
0x18001b6a4  and     eax, 9C1h
0x18001b6a9  or      ecx, eax
0x18001b6ab  or      ecx, 2
0x18001b6ae  mov     [rdi], ecx
0x18001b6b0  mov     r8d, edx
0x18001b6b3  and     r8d, 4
0x18001b6b7  jnz     short loc_18001B6CB
0x18001b6b9  btr     ecx, 0Ah
0x18001b6bd  mov     eax, ebx
0x18001b6bf  and     eax, 400h
0x18001b6c4  or      ecx, eax
0x18001b6c6  or      ecx, 4
0x18001b6c9  mov     [rdi], ecx
0x18001b6cb  mov     eax, edx
0x18001b6cd  lock cmpxchg [rsi], ecx
0x18001b6d1  jnz     short loc_18001B68A
0x18001b6d3  test    r8d, r8d
0x18001b6d6  jnz     short loc_18001B6E8
0x18001b6d8  mov     r8d, ebp
0x18001b6db  mov     edx, 3
0x18001b6e0  mov     rcx, rsi
0x18001b6e3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b6e8  mov     eax, [rdi]
0x18001b6ea  test    al, 2
0x18001b6ec  jnz     short loc_18001B6FD
0x18001b6ee  and     eax, 0FFFFF63Eh
0x18001b6f3  and     ebx, 9C1h
0x18001b6f9  or      eax, ebx
0x18001b6fb  mov     [rdi], eax
0x18001b6fd  mov     rbx, [rsp+38h+arg_10]
0x18001b702  mov     rax, rdi
0x18001b705  add     rsp, 20h
0x18001b709  pop     rdi
0x18001b70a  pop     rsi
0x18001b70b  pop     rbp
0x18001b70c  retn
```
