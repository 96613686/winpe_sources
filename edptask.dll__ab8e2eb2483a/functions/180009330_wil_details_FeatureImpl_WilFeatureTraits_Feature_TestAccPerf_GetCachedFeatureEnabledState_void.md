# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x180009330`
- end: `0x180009409`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012130`

## callees

- `0x1800084b4`
- `0x180009330`
- `0x180009934`
- `0x1800113c4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TestAccPerf__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180009330  mov     [rsp+arg_10], rbx
0x180009335  mov     [rsp+arg_0], rcx
0x18000933a  push    rbp
0x18000933b  push    rsi
0x18000933c  push    rdi
0x18000933d  sub     rsp, 20h
0x180009341  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x180009348  mov     rdi, rdx
0x18000934b  mov     qword ptr [rdx], 0
0x180009352  mov     eax, [rsi]
0x180009354  mov     [rdx], eax
0x180009356  and     eax, 6
0x180009359  cmp     al, 6
0x18000935b  jz      loc_1800093F9
0x180009361  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180009366  lea     r8, [rsp+38h+arg_0]
0x18000936b  mov     dword ptr [rsp+38h+arg_0], 0
0x180009373  lea     rdx, [rsp+38h+arg_8]
0x180009378  mov     ebp, eax
0x18000937a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18000937f  mov     eax, [rdi]
0x180009381  mov     rbx, [rsp+38h+arg_8]
0x180009386  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000938b  mov     edx, eax
0x18000938d  mov     [rdi], eax
0x18000938f  mov     ecx, eax
0x180009391  jz      short loc_1800093AC
0x180009393  test    dl, 2
0x180009396  jnz     short loc_1800093AC
0x180009398  and     ecx, 0FFFFF63Eh
0x18000939e  mov     eax, ebx
0x1800093a0  and     eax, 9C1h
0x1800093a5  or      ecx, eax
0x1800093a7  or      ecx, 2
0x1800093aa  mov     [rdi], ecx
0x1800093ac  mov     r8d, edx
0x1800093af  and     r8d, 4
0x1800093b3  jnz     short loc_1800093C7
0x1800093b5  btr     ecx, 0Ah
0x1800093b9  mov     eax, ebx
0x1800093bb  and     eax, 400h
0x1800093c0  or      ecx, eax
0x1800093c2  or      ecx, 4
0x1800093c5  mov     [rdi], ecx
0x1800093c7  mov     eax, edx
0x1800093c9  lock cmpxchg [rsi], ecx
0x1800093cd  jnz     short loc_180009386
0x1800093cf  test    r8d, r8d
0x1800093d2  jnz     short loc_1800093E4
0x1800093d4  mov     r8d, ebp
0x1800093d7  mov     edx, 3
0x1800093dc  mov     rcx, rsi
0x1800093df  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800093e4  mov     eax, [rdi]
0x1800093e6  test    al, 2
0x1800093e8  jnz     short loc_1800093F9
0x1800093ea  and     eax, 0FFFFF63Eh
0x1800093ef  and     ebx, 9C1h
0x1800093f5  or      eax, ebx
0x1800093f7  mov     [rdi], eax
0x1800093f9  mov     rbx, [rsp+38h+arg_10]
0x1800093fe  mov     rax, rdi
0x180009401  add     rsp, 20h
0x180009405  pop     rdi
0x180009406  pop     rsi
0x180009407  pop     rbp
0x180009408  retn
```
