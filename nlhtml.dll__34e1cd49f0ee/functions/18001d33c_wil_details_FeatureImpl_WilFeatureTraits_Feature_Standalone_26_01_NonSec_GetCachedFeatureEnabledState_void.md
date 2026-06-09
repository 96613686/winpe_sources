# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001d33c`
- end: `0x18001d415`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ea14`

## callees

- `0x180016c14`
- `0x180019b00`
- `0x18001d33c`
- `0x18001dd6c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
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
0x18001d33c  mov     [rsp+arg_10], rbx
0x18001d341  mov     [rsp+arg_0], rcx
0x18001d346  push    rbp
0x18001d347  push    rsi
0x18001d348  push    rdi
0x18001d349  sub     rsp, 20h
0x18001d34d  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18001d354  mov     rdi, rdx
0x18001d357  mov     qword ptr [rdx], 0
0x18001d35e  mov     eax, [rsi]
0x18001d360  mov     [rdx], eax
0x18001d362  and     eax, 6
0x18001d365  cmp     al, 6
0x18001d367  jz      loc_18001D405
0x18001d36d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d372  lea     r8, [rsp+38h+arg_0]
0x18001d377  mov     dword ptr [rsp+38h+arg_0], 0
0x18001d37f  lea     rdx, [rsp+38h+arg_8]
0x18001d384  mov     ebp, eax
0x18001d386  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18001d38b  mov     eax, [rdi]
0x18001d38d  mov     rbx, [rsp+38h+arg_8]
0x18001d392  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001d397  mov     edx, eax
0x18001d399  mov     [rdi], eax
0x18001d39b  mov     ecx, eax
0x18001d39d  jz      short loc_18001D3B8
0x18001d39f  test    dl, 2
0x18001d3a2  jnz     short loc_18001D3B8
0x18001d3a4  and     ecx, 0FFFFF63Eh
0x18001d3aa  mov     eax, ebx
0x18001d3ac  and     eax, 9C1h
0x18001d3b1  or      ecx, eax
0x18001d3b3  or      ecx, 2
0x18001d3b6  mov     [rdi], ecx
0x18001d3b8  mov     r8d, edx
0x18001d3bb  and     r8d, 4
0x18001d3bf  jnz     short loc_18001D3D3
0x18001d3c1  btr     ecx, 0Ah
0x18001d3c5  mov     eax, ebx
0x18001d3c7  and     eax, 400h
0x18001d3cc  or      ecx, eax
0x18001d3ce  or      ecx, 4
0x18001d3d1  mov     [rdi], ecx
0x18001d3d3  mov     eax, edx
0x18001d3d5  lock cmpxchg [rsi], ecx
0x18001d3d9  jnz     short loc_18001D392
0x18001d3db  test    r8d, r8d
0x18001d3de  jnz     short loc_18001D3F0
0x18001d3e0  mov     r8d, ebp
0x18001d3e3  mov     edx, 3
0x18001d3e8  mov     rcx, rsi
0x18001d3eb  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001d3f0  mov     eax, [rdi]
0x18001d3f2  test    al, 2
0x18001d3f4  jnz     short loc_18001D405
0x18001d3f6  and     eax, 0FFFFF63Eh
0x18001d3fb  and     ebx, 9C1h
0x18001d401  or      eax, ebx
0x18001d403  mov     [rdi], eax
0x18001d405  mov     rbx, [rsp+38h+arg_10]
0x18001d40a  mov     rax, rdi
0x18001d40d  add     rsp, 20h
0x18001d411  pop     rdi
0x18001d412  pop     rsi
0x18001d413  pop     rbp
0x18001d414  retn
```
