# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT>::GetCachedFeatureEnabledState(void)

- ea: `0x180012f98`
- end: `0x180013079`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800150cc`
- `0x180016744`

## callees

- `0x180012bf0`
- `0x180012f98`
- `0x1800131ac`
- `0x180015be8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        wil::details::g_enabledStateManager,
        Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__descriptor,
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
0x180012f98  mov     [rsp+arg_10], rbx
0x180012f9d  mov     [rsp+arg_0], rcx
0x180012fa2  push    rbp
0x180012fa3  push    rsi
0x180012fa4  push    rdi
0x180012fa5  sub     rsp, 20h
0x180012fa9  mov     rsi, cs:Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__descriptor
0x180012fb0  mov     rdi, rdx
0x180012fb3  mov     qword ptr [rdx], 0
0x180012fba  mov     eax, [rsi]
0x180012fbc  mov     [rdx], eax
0x180012fbe  and     eax, 6
0x180012fc1  cmp     al, 6
0x180012fc3  jz      loc_180013069
0x180012fc9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012fce  lea     r8, [rsp+38h+arg_0]
0x180012fd3  mov     dword ptr [rsp+38h+arg_0], 0
0x180012fdb  lea     rdx, [rsp+38h+arg_8]
0x180012fe0  mov     ebp, eax
0x180012fe2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT>::GetCurrentFeatureEnabledState(int *)
0x180012fe7  mov     eax, [rdi]
0x180012fe9  mov     rbx, [rsp+38h+arg_8]
0x180012fee  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012ff3  mov     edx, eax
0x180012ff5  mov     [rdi], eax
0x180012ff7  mov     ecx, eax
0x180012ff9  jz      short loc_180013014
0x180012ffb  test    dl, 2
0x180012ffe  jnz     short loc_180013014
0x180013000  and     ecx, 0FFFFF63Eh
0x180013006  mov     eax, ebx
0x180013008  and     eax, 9C1h
0x18001300d  or      ecx, eax
0x18001300f  or      ecx, 2
0x180013012  mov     [rdi], ecx
0x180013014  mov     r8d, edx
0x180013017  and     r8d, 4
0x18001301b  jnz     short loc_18001302F
0x18001301d  btr     ecx, 0Ah
0x180013021  mov     eax, ebx
0x180013023  and     eax, 400h
0x180013028  or      ecx, eax
0x18001302a  or      ecx, 4
0x18001302d  mov     [rdi], ecx
0x18001302f  mov     eax, edx
0x180013031  lock cmpxchg [rsi], ecx
0x180013035  jnz     short loc_180012FEE
0x180013037  test    r8d, r8d
0x18001303a  jnz     short loc_180013054
0x18001303c  mov     r9d, ebp
0x18001303f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013046  mov     r8d, 3
0x18001304c  mov     rdx, rsi
0x18001304f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013054  mov     eax, [rdi]
0x180013056  test    al, 2
0x180013058  jnz     short loc_180013069
0x18001305a  and     eax, 0FFFFF63Eh
0x18001305f  and     ebx, 9C1h
0x180013065  or      eax, ebx
0x180013067  mov     [rdi], eax
0x180013069  mov     rbx, [rsp+38h+arg_10]
0x18001306e  mov     rax, rdi
0x180013071  add     rsp, 20h
0x180013075  pop     rdi
0x180013076  pop     rsi
0x180013077  pop     rbp
0x180013078  retn
```
