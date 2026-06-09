# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180011b3c`
- end: `0x180011c1d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012148`
- `0x180012488`

## callees

- `0x18000eb58`
- `0x18001011c`
- `0x180011b3c`
- `0x180011e50`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  __int64 v6; // rcx
  int *v7; // r9
  signed __int32 v8; // eax
  __int16 v9; // bx
  bool v10; // zf
  signed __int32 v11; // edx
  unsigned int v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
      v6,
      &v15,
      (enum FEATURE_CHANGE_TIME)&v14,
      v7);
    v8 = *(_DWORD *)a2;
    v9 = v15;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v8;
      *(_DWORD *)a2 = v8;
      v12 = v8;
      if ( !v10 && (v8 & 2) == 0 )
      {
        v12 = v9 & 0x9C1 | v8 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v12;
      }
      if ( (v8 & 4) == 0 )
      {
        v12 = v9 & 0x400 | v12 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v12;
      }
      v8 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v12, v8);
    }
    while ( v11 != v8 );
    if ( (v11 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_ValAccTest__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v9 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180011b3c  mov     [rsp+arg_10], rbx
0x180011b41  mov     [rsp+arg_0], rcx
0x180011b46  push    rbp
0x180011b47  push    rsi
0x180011b48  push    rdi
0x180011b49  sub     rsp, 20h
0x180011b4d  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180011b54  mov     rdi, rdx
0x180011b57  mov     qword ptr [rdx], 0
0x180011b5e  mov     eax, [rsi]
0x180011b60  mov     [rdx], eax
0x180011b62  and     eax, 6
0x180011b65  cmp     al, 6
0x180011b67  jz      loc_180011C0D
0x180011b6d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180011b72  lea     r8, [rsp+38h+arg_0]
0x180011b77  mov     dword ptr [rsp+38h+arg_0], 0
0x180011b7f  lea     rdx, [rsp+38h+arg_8]
0x180011b84  mov     ebp, eax
0x180011b86  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180011b8b  mov     eax, [rdi]
0x180011b8d  mov     rbx, [rsp+38h+arg_8]
0x180011b92  cmp     dword ptr [rsp+38h+arg_0], 0
0x180011b97  mov     edx, eax
0x180011b99  mov     [rdi], eax
0x180011b9b  mov     ecx, eax
0x180011b9d  jz      short loc_180011BB8
0x180011b9f  test    dl, 2
0x180011ba2  jnz     short loc_180011BB8
0x180011ba4  and     ecx, 0FFFFF63Eh
0x180011baa  mov     eax, ebx
0x180011bac  and     eax, 9C1h
0x180011bb1  or      ecx, eax
0x180011bb3  or      ecx, 2
0x180011bb6  mov     [rdi], ecx
0x180011bb8  mov     r8d, edx
0x180011bbb  and     r8d, 4
0x180011bbf  jnz     short loc_180011BD3
0x180011bc1  btr     ecx, 0Ah
0x180011bc5  mov     eax, ebx
0x180011bc7  and     eax, 400h
0x180011bcc  or      ecx, eax
0x180011bce  or      ecx, 4
0x180011bd1  mov     [rdi], ecx
0x180011bd3  mov     eax, edx
0x180011bd5  lock cmpxchg [rsi], ecx
0x180011bd9  jnz     short loc_180011B92
0x180011bdb  test    r8d, r8d
0x180011bde  jnz     short loc_180011BF8
0x180011be0  mov     r9d, ebp
0x180011be3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180011bea  mov     r8d, 3
0x180011bf0  mov     rdx, rsi
0x180011bf3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180011bf8  mov     eax, [rdi]
0x180011bfa  test    al, 2
0x180011bfc  jnz     short loc_180011C0D
0x180011bfe  and     eax, 0FFFFF63Eh
0x180011c03  and     ebx, 9C1h
0x180011c09  or      eax, ebx
0x180011c0b  mov     [rdi], eax
0x180011c0d  mov     rbx, [rsp+38h+arg_10]
0x180011c12  mov     rax, rdi
0x180011c15  add     rsp, 20h
0x180011c19  pop     rdi
0x180011c1a  pop     rsi
0x180011c1b  pop     rbp
0x180011c1c  retn
```
