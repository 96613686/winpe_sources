# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x14000cf84`
- end: `0x14000d05d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e6f8`

## callees

- `0x140007508`
- `0x1400096d0`
- `0x14000cf84`
- `0x14000d860`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_03_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_03_NonSec__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x14000cf84  mov     [rsp+arg_10], rbx
0x14000cf89  mov     [rsp+arg_0], rcx
0x14000cf8e  push    rbp
0x14000cf8f  push    rsi
0x14000cf90  push    rdi
0x14000cf91  sub     rsp, 20h
0x14000cf95  mov     rsi, cs:Feature_Standalone_26_03_NonSec__descriptor
0x14000cf9c  mov     rdi, rdx
0x14000cf9f  mov     qword ptr [rdx], 0
0x14000cfa6  mov     eax, [rsi]
0x14000cfa8  mov     [rdx], eax
0x14000cfaa  and     eax, 6
0x14000cfad  cmp     al, 6
0x14000cfaf  jz      loc_14000D04D
0x14000cfb5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000cfba  lea     r8, [rsp+38h+arg_0]
0x14000cfbf  mov     dword ptr [rsp+38h+arg_0], 0
0x14000cfc7  lea     rdx, [rsp+38h+arg_8]
0x14000cfcc  mov     ebp, eax
0x14000cfce  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCurrentFeatureEnabledState(int *)
0x14000cfd3  mov     eax, [rdi]
0x14000cfd5  mov     rbx, [rsp+38h+arg_8]
0x14000cfda  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000cfdf  mov     edx, eax
0x14000cfe1  mov     [rdi], eax
0x14000cfe3  mov     ecx, eax
0x14000cfe5  jz      short loc_14000D000
0x14000cfe7  test    dl, 2
0x14000cfea  jnz     short loc_14000D000
0x14000cfec  and     ecx, 0FFFFF63Eh
0x14000cff2  mov     eax, ebx
0x14000cff4  and     eax, 9C1h
0x14000cff9  or      ecx, eax
0x14000cffb  or      ecx, 2
0x14000cffe  mov     [rdi], ecx
0x14000d000  mov     r8d, edx
0x14000d003  and     r8d, 4
0x14000d007  jnz     short loc_14000D01B
0x14000d009  btr     ecx, 0Ah
0x14000d00d  mov     eax, ebx
0x14000d00f  and     eax, 400h
0x14000d014  or      ecx, eax
0x14000d016  or      ecx, 4
0x14000d019  mov     [rdi], ecx
0x14000d01b  mov     eax, edx
0x14000d01d  lock cmpxchg [rsi], ecx
0x14000d021  jnz     short loc_14000CFDA
0x14000d023  test    r8d, r8d
0x14000d026  jnz     short loc_14000D038
0x14000d028  mov     r8d, ebp
0x14000d02b  mov     edx, 3
0x14000d030  mov     rcx, rsi
0x14000d033  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000d038  mov     eax, [rdi]
0x14000d03a  test    al, 2
0x14000d03c  jnz     short loc_14000D04D
0x14000d03e  and     eax, 0FFFFF63Eh
0x14000d043  and     ebx, 9C1h
0x14000d049  or      eax, ebx
0x14000d04b  mov     [rdi], eax
0x14000d04d  mov     rbx, [rsp+38h+arg_10]
0x14000d052  mov     rax, rdi
0x14000d055  add     rsp, 20h
0x14000d059  pop     rdi
0x14000d05a  pop     rsi
0x14000d05b  pop     rbp
0x14000d05c  retn
```
