# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::GetCachedFeatureEnabledState(void)

- ea: `0x140015090`
- end: `0x140015171`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e9c4`
- `0x14000fc2c`

## callees

- `0x140014c90`
- `0x140015090`
- `0x140016090`
- `0x140017a74`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ShadowAdmin__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ShadowAdmin__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ShadowAdmin__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_ShadowAdmin__descriptor,
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
0x140015090  mov     [rsp+arg_10], rbx
0x140015095  mov     [rsp+arg_0], rcx
0x14001509a  push    rbp
0x14001509b  push    rsi
0x14001509c  push    rdi
0x14001509d  sub     rsp, 20h
0x1400150a1  mov     rsi, cs:Feature_ShadowAdmin__descriptor
0x1400150a8  mov     rdi, rdx
0x1400150ab  mov     qword ptr [rdx], 0
0x1400150b2  mov     eax, [rsi]
0x1400150b4  mov     [rdx], eax
0x1400150b6  and     eax, 6
0x1400150b9  cmp     al, 6
0x1400150bb  jz      loc_140015161
0x1400150c1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400150c6  lea     r8, [rsp+38h+arg_0]
0x1400150cb  mov     dword ptr [rsp+38h+arg_0], 0
0x1400150d3  lea     rdx, [rsp+38h+arg_8]
0x1400150d8  mov     ebp, eax
0x1400150da  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::GetCurrentFeatureEnabledState(int *)
0x1400150df  mov     eax, [rdi]
0x1400150e1  mov     rbx, [rsp+38h+arg_8]
0x1400150e6  cmp     dword ptr [rsp+38h+arg_0], 0
0x1400150eb  mov     edx, eax
0x1400150ed  mov     [rdi], eax
0x1400150ef  mov     ecx, eax
0x1400150f1  jz      short loc_14001510C
0x1400150f3  test    dl, 2
0x1400150f6  jnz     short loc_14001510C
0x1400150f8  and     ecx, 0FFFFF63Eh
0x1400150fe  mov     eax, ebx
0x140015100  and     eax, 9C1h
0x140015105  or      ecx, eax
0x140015107  or      ecx, 2
0x14001510a  mov     [rdi], ecx
0x14001510c  mov     r8d, edx
0x14001510f  and     r8d, 4
0x140015113  jnz     short loc_140015127
0x140015115  btr     ecx, 0Ah
0x140015119  mov     eax, ebx
0x14001511b  and     eax, 400h
0x140015120  or      ecx, eax
0x140015122  or      ecx, 4
0x140015125  mov     [rdi], ecx
0x140015127  mov     eax, edx
0x140015129  lock cmpxchg [rsi], ecx
0x14001512d  jnz     short loc_1400150E6
0x14001512f  test    r8d, r8d
0x140015132  jnz     short loc_14001514C
0x140015134  mov     r9d, ebp
0x140015137  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14001513e  mov     r8d, 3
0x140015144  mov     rdx, rsi
0x140015147  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14001514c  mov     eax, [rdi]
0x14001514e  test    al, 2
0x140015150  jnz     short loc_140015161
0x140015152  and     eax, 0FFFFF63Eh
0x140015157  and     ebx, 9C1h
0x14001515d  or      eax, ebx
0x14001515f  mov     [rdi], eax
0x140015161  mov     rbx, [rsp+38h+arg_10]
0x140015166  mov     rax, rdi
0x140015169  add     rsp, 20h
0x14001516d  pop     rdi
0x14001516e  pop     rsi
0x14001516f  pop     rbp
0x140015170  retn
```
