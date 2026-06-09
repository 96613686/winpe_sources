# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MJPEG_DXVA_IMP_2409>::GetCachedFeatureEnabledState(void)

- ea: `0x18003b49c`
- end: `0x18003b57d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MJPEG_DXVA_IMP_2409@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003ce48`
- `0x18003db28`

## callees

- `0x18003b30c`
- `0x18003b49c`
- `0x18003b9ec`
- `0x18003d6a0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MJPEG_DXVA_IMP_2409>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_MJPEG_DXVA_IMP_2409__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_MJPEG_DXVA_IMP_2409__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_MJPEG_DXVA_IMP_2409>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_MJPEG_DXVA_IMP_2409__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_MJPEG_DXVA_IMP_2409__descriptor,
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
0x18003b49c  mov     [rsp+arg_10], rbx
0x18003b4a1  mov     [rsp+arg_0], rcx
0x18003b4a6  push    rbp
0x18003b4a7  push    rsi
0x18003b4a8  push    rdi
0x18003b4a9  sub     rsp, 20h
0x18003b4ad  mov     rsi, cs:Feature_MJPEG_DXVA_IMP_2409__descriptor
0x18003b4b4  mov     rdi, rdx
0x18003b4b7  mov     qword ptr [rdx], 0
0x18003b4be  mov     eax, [rsi]
0x18003b4c0  mov     [rdx], eax
0x18003b4c2  and     eax, 6
0x18003b4c5  cmp     al, 6
0x18003b4c7  jz      loc_18003B56D
0x18003b4cd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18003b4d2  lea     r8, [rsp+38h+arg_0]
0x18003b4d7  mov     dword ptr [rsp+38h+arg_0], 0
0x18003b4df  lea     rdx, [rsp+38h+arg_8]
0x18003b4e4  mov     ebp, eax
0x18003b4e6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MJPEG_DXVA_IMP_2409@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MJPEG_DXVA_IMP_2409>::GetCurrentFeatureEnabledState(int *)
0x18003b4eb  mov     eax, [rdi]
0x18003b4ed  mov     rbx, [rsp+38h+arg_8]
0x18003b4f2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18003b4f7  mov     edx, eax
0x18003b4f9  mov     [rdi], eax
0x18003b4fb  mov     ecx, eax
0x18003b4fd  jz      short loc_18003B518
0x18003b4ff  test    dl, 2
0x18003b502  jnz     short loc_18003B518
0x18003b504  and     ecx, 0FFFFF63Eh
0x18003b50a  mov     eax, ebx
0x18003b50c  and     eax, 9C1h
0x18003b511  or      ecx, eax
0x18003b513  or      ecx, 2
0x18003b516  mov     [rdi], ecx
0x18003b518  mov     r8d, edx
0x18003b51b  and     r8d, 4
0x18003b51f  jnz     short loc_18003B533
0x18003b521  btr     ecx, 0Ah
0x18003b525  mov     eax, ebx
0x18003b527  and     eax, 400h
0x18003b52c  or      ecx, eax
0x18003b52e  or      ecx, 4
0x18003b531  mov     [rdi], ecx
0x18003b533  mov     eax, edx
0x18003b535  lock cmpxchg [rsi], ecx
0x18003b539  jnz     short loc_18003B4F2
0x18003b53b  test    r8d, r8d
0x18003b53e  jnz     short loc_18003B558
0x18003b540  mov     r9d, ebp
0x18003b543  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18003b54a  mov     r8d, 3
0x18003b550  mov     rdx, rsi
0x18003b553  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18003b558  mov     eax, [rdi]
0x18003b55a  test    al, 2
0x18003b55c  jnz     short loc_18003B56D
0x18003b55e  and     eax, 0FFFFF63Eh
0x18003b563  and     ebx, 9C1h
0x18003b569  or      eax, ebx
0x18003b56b  mov     [rdi], eax
0x18003b56d  mov     rbx, [rsp+38h+arg_10]
0x18003b572  mov     rax, rdi
0x18003b575  add     rsp, 20h
0x18003b579  pop     rdi
0x18003b57a  pop     rsi
0x18003b57b  pop     rbp
0x18003b57c  retn
```
