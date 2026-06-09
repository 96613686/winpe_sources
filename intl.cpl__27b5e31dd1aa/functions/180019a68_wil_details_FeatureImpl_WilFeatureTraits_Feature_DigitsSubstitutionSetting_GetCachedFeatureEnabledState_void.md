# wil::details::FeatureImpl<__WilFeatureTraits_Feature_DigitsSubstitutionSetting>::GetCachedFeatureEnabledState(void)

- ea: `0x180019a68`
- end: `0x180019b4b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DigitsSubstitutionSetting@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c8f4`

## callees

- `0x180019778`
- `0x180019a68`
- `0x180019b54`
- `0x18001ccf4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_DigitsSubstitutionSetting>::GetCachedFeatureEnabledState(
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
  __int64 v12; // r8
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_DigitsSubstitutionSetting__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_DigitsSubstitutionSetting__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DigitsSubstitutionSetting>::GetCurrentFeatureEnabledState(
      v6,
      &v15,
      &v14);
    if ( !v5 )
      LODWORD(v14) = 0;
    v7 = *(_DWORD *)a2;
    v8 = v15;
    do
    {
      v9 = (_DWORD)v14 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      v12 = v7 & 4;
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_DigitsSubstitutionSetting__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !(_DWORD)v12 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_DigitsSubstitutionSetting__descriptor,
        v12,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180019a68  mov     [rsp+arg_10], rbx
0x180019a6d  mov     [rsp+arg_0], rcx
0x180019a72  push    rbp
0x180019a73  push    rsi
0x180019a74  push    rdi
0x180019a75  sub     rsp, 20h
0x180019a79  mov     rsi, cs:Feature_DigitsSubstitutionSetting__descriptor
0x180019a80  mov     rdi, rdx
0x180019a83  mov     qword ptr [rdx], 0
0x180019a8a  mov     eax, [rsi]
0x180019a8c  mov     [rdx], eax
0x180019a8e  and     eax, 6
0x180019a91  cmp     al, 6
0x180019a93  jz      loc_180019B3B
0x180019a99  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180019a9e  lea     r8, [rsp+38h+arg_0]
0x180019aa3  mov     dword ptr [rsp+38h+arg_0], 0
0x180019aab  lea     rdx, [rsp+38h+arg_8]
0x180019ab0  mov     ebp, eax
0x180019ab2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DigitsSubstitutionSetting@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DigitsSubstitutionSetting>::GetCurrentFeatureEnabledState(int *)
0x180019ab7  test    ebp, ebp
0x180019ab9  jnz     short loc_180019ABF
0x180019abb  mov     dword ptr [rsp+38h+arg_0], ebp
0x180019abf  mov     eax, [rdi]
0x180019ac1  mov     rbx, [rsp+38h+arg_8]
0x180019ac6  cmp     dword ptr [rsp+38h+arg_0], 0
0x180019acb  mov     edx, eax
0x180019acd  mov     [rdi], eax
0x180019acf  mov     ecx, eax
0x180019ad1  jz      short loc_180019AEC
0x180019ad3  test    dl, 2
0x180019ad6  jnz     short loc_180019AEC
0x180019ad8  and     ecx, 0FFFFF63Eh
0x180019ade  mov     eax, ebx
0x180019ae0  and     eax, 9C1h
0x180019ae5  or      ecx, eax
0x180019ae7  or      ecx, 2
0x180019aea  mov     [rdi], ecx
0x180019aec  mov     r8d, edx
0x180019aef  and     r8d, 4
0x180019af3  jnz     short loc_180019B07
0x180019af5  btr     ecx, 0Ah
0x180019af9  mov     eax, ebx
0x180019afb  and     eax, 400h
0x180019b00  or      ecx, eax
0x180019b02  or      ecx, 4
0x180019b05  mov     [rdi], ecx
0x180019b07  mov     eax, edx
0x180019b09  lock cmpxchg [rsi], ecx
0x180019b0d  jnz     short loc_180019AC6
0x180019b0f  test    r8d, r8d
0x180019b12  jnz     short loc_180019B26
0x180019b14  mov     r9d, ebp
0x180019b17  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180019b1e  mov     rdx, rsi
0x180019b21  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180019b26  mov     eax, [rdi]
0x180019b28  test    al, 2
0x180019b2a  jnz     short loc_180019B3B
0x180019b2c  and     eax, 0FFFFF63Eh
0x180019b31  and     ebx, 9C1h
0x180019b37  or      eax, ebx
0x180019b39  mov     [rdi], eax
0x180019b3b  mov     rbx, [rsp+38h+arg_10]
0x180019b40  mov     rax, rdi
0x180019b43  add     rsp, 20h
0x180019b47  pop     rdi
0x180019b48  pop     rsi
0x180019b49  pop     rbp
0x180019b4a  retn
```
