# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505>::GetCachedFeatureEnabledState(void)

- ea: `0x180059afc`
- end: `0x180059bdd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2505@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005f2a8`
- `0x18005fc50`

## callees

- `0x18003b30c`
- `0x18003d6a0`
- `0x180059afc`
- `0x180059f1c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_MediaQI2505__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_MediaQI2505__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_MediaQI2505__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_MediaQI2505__descriptor,
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
0x180059afc  mov     [rsp+arg_10], rbx
0x180059b01  mov     [rsp+arg_0], rcx
0x180059b06  push    rbp
0x180059b07  push    rsi
0x180059b08  push    rdi
0x180059b09  sub     rsp, 20h
0x180059b0d  mov     rsi, cs:Feature_MediaQI2505__descriptor
0x180059b14  mov     rdi, rdx
0x180059b17  mov     qword ptr [rdx], 0
0x180059b1e  mov     eax, [rsi]
0x180059b20  mov     [rdx], eax
0x180059b22  and     eax, 6
0x180059b25  cmp     al, 6
0x180059b27  jz      loc_180059BCD
0x180059b2d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180059b32  lea     r8, [rsp+38h+arg_0]
0x180059b37  mov     dword ptr [rsp+38h+arg_0], 0
0x180059b3f  lea     rdx, [rsp+38h+arg_8]
0x180059b44  mov     ebp, eax
0x180059b46  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2505@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505>::GetCurrentFeatureEnabledState(int *)
0x180059b4b  mov     eax, [rdi]
0x180059b4d  mov     rbx, [rsp+38h+arg_8]
0x180059b52  cmp     dword ptr [rsp+38h+arg_0], 0
0x180059b57  mov     edx, eax
0x180059b59  mov     [rdi], eax
0x180059b5b  mov     ecx, eax
0x180059b5d  jz      short loc_180059B78
0x180059b5f  test    dl, 2
0x180059b62  jnz     short loc_180059B78
0x180059b64  and     ecx, 0FFFFF63Eh
0x180059b6a  mov     eax, ebx
0x180059b6c  and     eax, 9C1h
0x180059b71  or      ecx, eax
0x180059b73  or      ecx, 2
0x180059b76  mov     [rdi], ecx
0x180059b78  mov     r8d, edx
0x180059b7b  and     r8d, 4
0x180059b7f  jnz     short loc_180059B93
0x180059b81  btr     ecx, 0Ah
0x180059b85  mov     eax, ebx
0x180059b87  and     eax, 400h
0x180059b8c  or      ecx, eax
0x180059b8e  or      ecx, 4
0x180059b91  mov     [rdi], ecx
0x180059b93  mov     eax, edx
0x180059b95  lock cmpxchg [rsi], ecx
0x180059b99  jnz     short loc_180059B52
0x180059b9b  test    r8d, r8d
0x180059b9e  jnz     short loc_180059BB8
0x180059ba0  mov     r9d, ebp
0x180059ba3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180059baa  mov     r8d, 3
0x180059bb0  mov     rdx, rsi
0x180059bb3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180059bb8  mov     eax, [rdi]
0x180059bba  test    al, 2
0x180059bbc  jnz     short loc_180059BCD
0x180059bbe  and     eax, 0FFFFF63Eh
0x180059bc3  and     ebx, 9C1h
0x180059bc9  or      eax, ebx
0x180059bcb  mov     [rdi], eax
0x180059bcd  mov     rbx, [rsp+38h+arg_10]
0x180059bd2  mov     rax, rdi
0x180059bd5  add     rsp, 20h
0x180059bd9  pop     rdi
0x180059bda  pop     rsi
0x180059bdb  pop     rbp
0x180059bdc  retn
```
