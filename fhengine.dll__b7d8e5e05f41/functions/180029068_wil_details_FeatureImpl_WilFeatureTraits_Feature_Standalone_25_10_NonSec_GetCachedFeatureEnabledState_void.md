# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180029068`
- end: `0x180029141`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c79c`

## callees

- `0x180028ab4`
- `0x180029068`
- `0x180029a44`
- `0x18002d7b8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_10_NonSec__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180029068  mov     [rsp+arg_10], rbx
0x18002906d  mov     [rsp+arg_0], rcx
0x180029072  push    rbp
0x180029073  push    rsi
0x180029074  push    rdi
0x180029075  sub     rsp, 20h
0x180029079  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180029080  mov     rdi, rdx
0x180029083  mov     qword ptr [rdx], 0
0x18002908a  mov     eax, [rsi]
0x18002908c  mov     [rdx], eax
0x18002908e  and     eax, 6
0x180029091  cmp     al, 6
0x180029093  jz      loc_180029131
0x180029099  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002909e  lea     r8, [rsp+38h+arg_0]
0x1800290a3  mov     dword ptr [rsp+38h+arg_0], 0
0x1800290ab  lea     rdx, [rsp+38h+arg_8]
0x1800290b0  mov     ebp, eax
0x1800290b2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x1800290b7  mov     eax, [rdi]
0x1800290b9  mov     rbx, [rsp+38h+arg_8]
0x1800290be  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800290c3  mov     edx, eax
0x1800290c5  mov     [rdi], eax
0x1800290c7  mov     ecx, eax
0x1800290c9  jz      short loc_1800290E4
0x1800290cb  test    dl, 2
0x1800290ce  jnz     short loc_1800290E4
0x1800290d0  and     ecx, 0FFFFF63Eh
0x1800290d6  mov     eax, ebx
0x1800290d8  and     eax, 9C1h
0x1800290dd  or      ecx, eax
0x1800290df  or      ecx, 2
0x1800290e2  mov     [rdi], ecx
0x1800290e4  mov     r8d, edx
0x1800290e7  and     r8d, 4
0x1800290eb  jnz     short loc_1800290FF
0x1800290ed  btr     ecx, 0Ah
0x1800290f1  mov     eax, ebx
0x1800290f3  and     eax, 400h
0x1800290f8  or      ecx, eax
0x1800290fa  or      ecx, 4
0x1800290fd  mov     [rdi], ecx
0x1800290ff  mov     eax, edx
0x180029101  lock cmpxchg [rsi], ecx
0x180029105  jnz     short loc_1800290BE
0x180029107  test    r8d, r8d
0x18002910a  jnz     short loc_18002911C
0x18002910c  mov     r8d, ebp
0x18002910f  mov     edx, 3
0x180029114  mov     rcx, rsi
0x180029117  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002911c  mov     eax, [rdi]
0x18002911e  test    al, 2
0x180029120  jnz     short loc_180029131
0x180029122  and     eax, 0FFFFF63Eh
0x180029127  and     ebx, 9C1h
0x18002912d  or      eax, ebx
0x18002912f  mov     [rdi], eax
0x180029131  mov     rbx, [rsp+38h+arg_10]
0x180029136  mov     rax, rdi
0x180029139  add     rsp, 20h
0x18002913d  pop     rdi
0x18002913e  pop     rsi
0x18002913f  pop     rbp
0x180029140  retn
```
