# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180029308`
- end: `0x1800293e1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c928`

## callees

- `0x180028ab4`
- `0x180029308`
- `0x180029bb8`
- `0x18002d7b8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_02_NonSec__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180029308  mov     [rsp+arg_10], rbx
0x18002930d  mov     [rsp+arg_0], rcx
0x180029312  push    rbp
0x180029313  push    rsi
0x180029314  push    rdi
0x180029315  sub     rsp, 20h
0x180029319  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180029320  mov     rdi, rdx
0x180029323  mov     qword ptr [rdx], 0
0x18002932a  mov     eax, [rsi]
0x18002932c  mov     [rdx], eax
0x18002932e  and     eax, 6
0x180029331  cmp     al, 6
0x180029333  jz      loc_1800293D1
0x180029339  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002933e  lea     r8, [rsp+38h+arg_0]
0x180029343  mov     dword ptr [rsp+38h+arg_0], 0
0x18002934b  lea     rdx, [rsp+38h+arg_8]
0x180029350  mov     ebp, eax
0x180029352  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180029357  mov     eax, [rdi]
0x180029359  mov     rbx, [rsp+38h+arg_8]
0x18002935e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180029363  mov     edx, eax
0x180029365  mov     [rdi], eax
0x180029367  mov     ecx, eax
0x180029369  jz      short loc_180029384
0x18002936b  test    dl, 2
0x18002936e  jnz     short loc_180029384
0x180029370  and     ecx, 0FFFFF63Eh
0x180029376  mov     eax, ebx
0x180029378  and     eax, 9C1h
0x18002937d  or      ecx, eax
0x18002937f  or      ecx, 2
0x180029382  mov     [rdi], ecx
0x180029384  mov     r8d, edx
0x180029387  and     r8d, 4
0x18002938b  jnz     short loc_18002939F
0x18002938d  btr     ecx, 0Ah
0x180029391  mov     eax, ebx
0x180029393  and     eax, 400h
0x180029398  or      ecx, eax
0x18002939a  or      ecx, 4
0x18002939d  mov     [rdi], ecx
0x18002939f  mov     eax, edx
0x1800293a1  lock cmpxchg [rsi], ecx
0x1800293a5  jnz     short loc_18002935E
0x1800293a7  test    r8d, r8d
0x1800293aa  jnz     short loc_1800293BC
0x1800293ac  mov     r8d, ebp
0x1800293af  mov     edx, 3
0x1800293b4  mov     rcx, rsi
0x1800293b7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800293bc  mov     eax, [rdi]
0x1800293be  test    al, 2
0x1800293c0  jnz     short loc_1800293D1
0x1800293c2  and     eax, 0FFFFF63Eh
0x1800293c7  and     ebx, 9C1h
0x1800293cd  or      eax, ebx
0x1800293cf  mov     [rdi], eax
0x1800293d1  mov     rbx, [rsp+38h+arg_10]
0x1800293d6  mov     rax, rdi
0x1800293d9  add     rsp, 20h
0x1800293dd  pop     rdi
0x1800293de  pop     rsi
0x1800293df  pop     rbp
0x1800293e0  retn
```
