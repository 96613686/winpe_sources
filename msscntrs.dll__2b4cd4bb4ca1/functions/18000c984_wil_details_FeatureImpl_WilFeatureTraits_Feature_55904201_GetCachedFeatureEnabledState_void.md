# wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::GetCachedFeatureEnabledState(void)

- ea: `0x18000c984`
- end: `0x18000ca5d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_55904201@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800107bc`

## callees

- `0x180005c18`
- `0x180009714`
- `0x18000c984`
- `0x18000d544`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_55904201__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_55904201__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_55904201__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_55904201__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000c984  mov     [rsp+arg_10], rbx
0x18000c989  mov     [rsp+arg_0], rcx
0x18000c98e  push    rbp
0x18000c98f  push    rsi
0x18000c990  push    rdi
0x18000c991  sub     rsp, 20h
0x18000c995  mov     rsi, cs:Feature_55904201__descriptor
0x18000c99c  mov     rdi, rdx
0x18000c99f  mov     qword ptr [rdx], 0
0x18000c9a6  mov     eax, [rsi]
0x18000c9a8  mov     [rdx], eax
0x18000c9aa  and     eax, 6
0x18000c9ad  cmp     al, 6
0x18000c9af  jz      loc_18000CA4D
0x18000c9b5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000c9ba  lea     r8, [rsp+38h+arg_0]
0x18000c9bf  mov     dword ptr [rsp+38h+arg_0], 0
0x18000c9c7  lea     rdx, [rsp+38h+arg_8]
0x18000c9cc  mov     ebp, eax
0x18000c9ce  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_55904201@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::GetCurrentFeatureEnabledState(int *)
0x18000c9d3  mov     eax, [rdi]
0x18000c9d5  mov     rbx, [rsp+38h+arg_8]
0x18000c9da  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000c9df  mov     edx, eax
0x18000c9e1  mov     [rdi], eax
0x18000c9e3  mov     ecx, eax
0x18000c9e5  jz      short loc_18000CA00
0x18000c9e7  test    dl, 2
0x18000c9ea  jnz     short loc_18000CA00
0x18000c9ec  and     ecx, 0FFFFF63Eh
0x18000c9f2  mov     eax, ebx
0x18000c9f4  and     eax, 9C1h
0x18000c9f9  or      ecx, eax
0x18000c9fb  or      ecx, 2
0x18000c9fe  mov     [rdi], ecx
0x18000ca00  mov     r8d, edx
0x18000ca03  and     r8d, 4
0x18000ca07  jnz     short loc_18000CA1B
0x18000ca09  btr     ecx, 0Ah
0x18000ca0d  mov     eax, ebx
0x18000ca0f  and     eax, 400h
0x18000ca14  or      ecx, eax
0x18000ca16  or      ecx, 4
0x18000ca19  mov     [rdi], ecx
0x18000ca1b  mov     eax, edx
0x18000ca1d  lock cmpxchg [rsi], ecx
0x18000ca21  jnz     short loc_18000C9DA
0x18000ca23  test    r8d, r8d
0x18000ca26  jnz     short loc_18000CA38
0x18000ca28  mov     r8d, ebp
0x18000ca2b  mov     edx, 3
0x18000ca30  mov     rcx, rsi
0x18000ca33  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000ca38  mov     eax, [rdi]
0x18000ca3a  test    al, 2
0x18000ca3c  jnz     short loc_18000CA4D
0x18000ca3e  and     eax, 0FFFFF63Eh
0x18000ca43  and     ebx, 9C1h
0x18000ca49  or      eax, ebx
0x18000ca4b  mov     [rdi], eax
0x18000ca4d  mov     rbx, [rsp+38h+arg_10]
0x18000ca52  mov     rax, rdi
0x18000ca55  add     rsp, 20h
0x18000ca59  pop     rdi
0x18000ca5a  pop     rsi
0x18000ca5b  pop     rbp
0x18000ca5c  retn
```
