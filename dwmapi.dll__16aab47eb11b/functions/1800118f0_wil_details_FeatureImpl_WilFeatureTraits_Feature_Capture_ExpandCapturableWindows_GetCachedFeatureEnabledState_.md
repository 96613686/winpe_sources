# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetCachedFeatureEnabledState(void)

- ea: `0x1800118f0`
- end: `0x1800119d1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800120bc`
- `0x18001244c`

## callees

- `0x18000eb58`
- `0x18001011c`
- `0x1800118f0`
- `0x180011d88`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Capture_ExpandCapturableWindows__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Capture_ExpandCapturableWindows__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Capture_ExpandCapturableWindows__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_Capture_ExpandCapturableWindows__descriptor,
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
0x1800118f0  mov     [rsp+arg_10], rbx
0x1800118f5  mov     [rsp+arg_0], rcx
0x1800118fa  push    rbp
0x1800118fb  push    rsi
0x1800118fc  push    rdi
0x1800118fd  sub     rsp, 20h
0x180011901  mov     rsi, cs:Feature_Capture_ExpandCapturableWindows__descriptor
0x180011908  mov     rdi, rdx
0x18001190b  mov     qword ptr [rdx], 0
0x180011912  mov     eax, [rsi]
0x180011914  mov     [rdx], eax
0x180011916  and     eax, 6
0x180011919  cmp     al, 6
0x18001191b  jz      loc_1800119C1
0x180011921  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180011926  lea     r8, [rsp+38h+arg_0]
0x18001192b  mov     dword ptr [rsp+38h+arg_0], 0
0x180011933  lea     rdx, [rsp+38h+arg_8]
0x180011938  mov     ebp, eax
0x18001193a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetCurrentFeatureEnabledState(int *)
0x18001193f  mov     eax, [rdi]
0x180011941  mov     rbx, [rsp+38h+arg_8]
0x180011946  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001194b  mov     edx, eax
0x18001194d  mov     [rdi], eax
0x18001194f  mov     ecx, eax
0x180011951  jz      short loc_18001196C
0x180011953  test    dl, 2
0x180011956  jnz     short loc_18001196C
0x180011958  and     ecx, 0FFFFF63Eh
0x18001195e  mov     eax, ebx
0x180011960  and     eax, 9C1h
0x180011965  or      ecx, eax
0x180011967  or      ecx, 2
0x18001196a  mov     [rdi], ecx
0x18001196c  mov     r8d, edx
0x18001196f  and     r8d, 4
0x180011973  jnz     short loc_180011987
0x180011975  btr     ecx, 0Ah
0x180011979  mov     eax, ebx
0x18001197b  and     eax, 400h
0x180011980  or      ecx, eax
0x180011982  or      ecx, 4
0x180011985  mov     [rdi], ecx
0x180011987  mov     eax, edx
0x180011989  lock cmpxchg [rsi], ecx
0x18001198d  jnz     short loc_180011946
0x18001198f  test    r8d, r8d
0x180011992  jnz     short loc_1800119AC
0x180011994  mov     r9d, ebp
0x180011997  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001199e  mov     r8d, 3
0x1800119a4  mov     rdx, rsi
0x1800119a7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800119ac  mov     eax, [rdi]
0x1800119ae  test    al, 2
0x1800119b0  jnz     short loc_1800119C1
0x1800119b2  and     eax, 0FFFFF63Eh
0x1800119b7  and     ebx, 9C1h
0x1800119bd  or      eax, ebx
0x1800119bf  mov     [rdi], eax
0x1800119c1  mov     rbx, [rsp+38h+arg_10]
0x1800119c6  mov     rax, rdi
0x1800119c9  add     rsp, 20h
0x1800119cd  pop     rdi
0x1800119ce  pop     rsi
0x1800119cf  pop     rbp
0x1800119d0  retn
```
