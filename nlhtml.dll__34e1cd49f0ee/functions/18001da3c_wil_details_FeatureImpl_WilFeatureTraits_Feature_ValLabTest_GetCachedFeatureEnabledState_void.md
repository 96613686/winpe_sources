# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18001da3c`
- end: `0x18001db15`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ee48`

## callees

- `0x180016c14`
- `0x180019b00`
- `0x18001da3c`
- `0x18001e32c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValLabTest__descriptor,
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
0x18001da3c  mov     [rsp+arg_10], rbx
0x18001da41  mov     [rsp+arg_0], rcx
0x18001da46  push    rbp
0x18001da47  push    rsi
0x18001da48  push    rdi
0x18001da49  sub     rsp, 20h
0x18001da4d  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18001da54  mov     rdi, rdx
0x18001da57  mov     qword ptr [rdx], 0
0x18001da5e  mov     eax, [rsi]
0x18001da60  mov     [rdx], eax
0x18001da62  and     eax, 6
0x18001da65  cmp     al, 6
0x18001da67  jz      loc_18001DB05
0x18001da6d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001da72  lea     r8, [rsp+38h+arg_0]
0x18001da77  mov     dword ptr [rsp+38h+arg_0], 0
0x18001da7f  lea     rdx, [rsp+38h+arg_8]
0x18001da84  mov     ebp, eax
0x18001da86  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x18001da8b  mov     eax, [rdi]
0x18001da8d  mov     rbx, [rsp+38h+arg_8]
0x18001da92  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001da97  mov     edx, eax
0x18001da99  mov     [rdi], eax
0x18001da9b  mov     ecx, eax
0x18001da9d  jz      short loc_18001DAB8
0x18001da9f  test    dl, 2
0x18001daa2  jnz     short loc_18001DAB8
0x18001daa4  and     ecx, 0FFFFF63Eh
0x18001daaa  mov     eax, ebx
0x18001daac  and     eax, 9C1h
0x18001dab1  or      ecx, eax
0x18001dab3  or      ecx, 2
0x18001dab6  mov     [rdi], ecx
0x18001dab8  mov     r8d, edx
0x18001dabb  and     r8d, 4
0x18001dabf  jnz     short loc_18001DAD3
0x18001dac1  btr     ecx, 0Ah
0x18001dac5  mov     eax, ebx
0x18001dac7  and     eax, 400h
0x18001dacc  or      ecx, eax
0x18001dace  or      ecx, 4
0x18001dad1  mov     [rdi], ecx
0x18001dad3  mov     eax, edx
0x18001dad5  lock cmpxchg [rsi], ecx
0x18001dad9  jnz     short loc_18001DA92
0x18001dadb  test    r8d, r8d
0x18001dade  jnz     short loc_18001DAF0
0x18001dae0  mov     r8d, ebp
0x18001dae3  mov     edx, 3
0x18001dae8  mov     rcx, rsi
0x18001daeb  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001daf0  mov     eax, [rdi]
0x18001daf2  test    al, 2
0x18001daf4  jnz     short loc_18001DB05
0x18001daf6  and     eax, 0FFFFF63Eh
0x18001dafb  and     ebx, 9C1h
0x18001db01  or      eax, ebx
0x18001db03  mov     [rdi], eax
0x18001db05  mov     rbx, [rsp+38h+arg_10]
0x18001db0a  mov     rax, rdi
0x18001db0d  add     rsp, 20h
0x18001db11  pop     rdi
0x18001db12  pop     rsi
0x18001db13  pop     rbp
0x18001db14  retn
```
