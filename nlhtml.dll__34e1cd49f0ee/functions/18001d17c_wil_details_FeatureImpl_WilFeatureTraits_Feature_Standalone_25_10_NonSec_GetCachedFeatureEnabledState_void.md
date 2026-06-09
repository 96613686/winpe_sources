# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001d17c`
- end: `0x18001d255`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e90c`

## callees

- `0x180016c14`
- `0x180019b00`
- `0x18001d17c`
- `0x18001dc84`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
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
0x18001d17c  mov     [rsp+arg_10], rbx
0x18001d181  mov     [rsp+arg_0], rcx
0x18001d186  push    rbp
0x18001d187  push    rsi
0x18001d188  push    rdi
0x18001d189  sub     rsp, 20h
0x18001d18d  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18001d194  mov     rdi, rdx
0x18001d197  mov     qword ptr [rdx], 0
0x18001d19e  mov     eax, [rsi]
0x18001d1a0  mov     [rdx], eax
0x18001d1a2  and     eax, 6
0x18001d1a5  cmp     al, 6
0x18001d1a7  jz      loc_18001D245
0x18001d1ad  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d1b2  lea     r8, [rsp+38h+arg_0]
0x18001d1b7  mov     dword ptr [rsp+38h+arg_0], 0
0x18001d1bf  lea     rdx, [rsp+38h+arg_8]
0x18001d1c4  mov     ebp, eax
0x18001d1c6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18001d1cb  mov     eax, [rdi]
0x18001d1cd  mov     rbx, [rsp+38h+arg_8]
0x18001d1d2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001d1d7  mov     edx, eax
0x18001d1d9  mov     [rdi], eax
0x18001d1db  mov     ecx, eax
0x18001d1dd  jz      short loc_18001D1F8
0x18001d1df  test    dl, 2
0x18001d1e2  jnz     short loc_18001D1F8
0x18001d1e4  and     ecx, 0FFFFF63Eh
0x18001d1ea  mov     eax, ebx
0x18001d1ec  and     eax, 9C1h
0x18001d1f1  or      ecx, eax
0x18001d1f3  or      ecx, 2
0x18001d1f6  mov     [rdi], ecx
0x18001d1f8  mov     r8d, edx
0x18001d1fb  and     r8d, 4
0x18001d1ff  jnz     short loc_18001D213
0x18001d201  btr     ecx, 0Ah
0x18001d205  mov     eax, ebx
0x18001d207  and     eax, 400h
0x18001d20c  or      ecx, eax
0x18001d20e  or      ecx, 4
0x18001d211  mov     [rdi], ecx
0x18001d213  mov     eax, edx
0x18001d215  lock cmpxchg [rsi], ecx
0x18001d219  jnz     short loc_18001D1D2
0x18001d21b  test    r8d, r8d
0x18001d21e  jnz     short loc_18001D230
0x18001d220  mov     r8d, ebp
0x18001d223  mov     edx, 3
0x18001d228  mov     rcx, rsi
0x18001d22b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001d230  mov     eax, [rdi]
0x18001d232  test    al, 2
0x18001d234  jnz     short loc_18001D245
0x18001d236  and     eax, 0FFFFF63Eh
0x18001d23b  and     ebx, 9C1h
0x18001d241  or      eax, ebx
0x18001d243  mov     [rdi], eax
0x18001d245  mov     rbx, [rsp+38h+arg_10]
0x18001d24a  mov     rax, rdi
0x18001d24d  add     rsp, 20h
0x18001d251  pop     rdi
0x18001d252  pop     rsi
0x18001d253  pop     rbp
0x18001d254  retn
```
