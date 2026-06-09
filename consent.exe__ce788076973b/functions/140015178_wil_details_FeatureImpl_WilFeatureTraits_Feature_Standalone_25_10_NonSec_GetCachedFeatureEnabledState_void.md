# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x140015178`
- end: `0x1400152a0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `296`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017388`

## callees

- `0x14000a020`
- `0x140014c90`
- `0x140015178`
- `0x140016174`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001522d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001522d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015275`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015275`

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
  int v12; // r8d
  _QWORD v14[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v15; // [rsp+50h] [rbp+8h] BYREF
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
      v6,
      &v16,
      &v15);
    v7 = *(_DWORD *)a2;
    v8 = v16;
    do
    {
      v9 = (_DWORD)v15 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      v12 = v7 & 4;
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_140029DD8);
      if ( !v5
        || v5 != dword_140029DEC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_10_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140029E10, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, 0xFFFFFFFB);
      }
      ReleaseSRWLockExclusive(&stru_140029DD8);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x140015178  mov     [rsp+arg_10], rbx
0x14001517d  mov     [rsp+arg_0], rcx
0x140015182  push    rbp
0x140015183  push    rsi
0x140015184  push    rdi
0x140015185  sub     rsp, 30h
0x140015189  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x140015190  mov     rdi, rdx
0x140015193  mov     qword ptr [rdx], 0
0x14001519a  mov     eax, [rsi]
0x14001519c  mov     [rdx], eax
0x14001519e  and     eax, 6
0x1400151a1  cmp     al, 6
0x1400151a3  jz      loc_140015290
0x1400151a9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400151ae  lea     r8, [rsp+48h+arg_0]
0x1400151b3  mov     dword ptr [rsp+48h+arg_0], 0
0x1400151bb  lea     rdx, [rsp+48h+arg_8]
0x1400151c0  mov     ebp, eax
0x1400151c2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x1400151c7  mov     eax, [rdi]
0x1400151c9  mov     rbx, [rsp+48h+arg_8]
0x1400151ce  cmp     dword ptr [rsp+48h+arg_0], 0
0x1400151d3  mov     edx, eax
0x1400151d5  mov     [rdi], eax
0x1400151d7  mov     ecx, eax
0x1400151d9  jz      short loc_1400151F4
0x1400151db  test    dl, 2
0x1400151de  jnz     short loc_1400151F4
0x1400151e0  and     ecx, 0FFFFF63Eh
0x1400151e6  mov     eax, ebx
0x1400151e8  and     eax, 9C1h
0x1400151ed  or      ecx, eax
0x1400151ef  or      ecx, 2
0x1400151f2  mov     [rdi], ecx
0x1400151f4  mov     r8d, edx
0x1400151f7  and     r8d, 4
0x1400151fb  jnz     short loc_14001520F
0x1400151fd  btr     ecx, 0Ah
0x140015201  mov     eax, ebx
0x140015203  and     eax, 400h
0x140015208  or      ecx, eax
0x14001520a  or      ecx, 4
0x14001520d  mov     [rdi], ecx
0x14001520f  mov     eax, edx
0x140015211  lock cmpxchg [rsi], ecx
0x140015215  jnz     short loc_1400151CE
0x140015217  test    r8d, r8d
0x14001521a  jnz     short loc_14001527B
0x14001521c  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140015222  test    eax, eax
0x140015224  jz      short loc_14001527B
0x140015226  lea     rcx, stru_140029DD8; SRWLock
0x14001522d  call    cs:__imp_AcquireSRWLockExclusive
0x140015233  mov     eax, cs:dword_140029DEC
0x140015239  test    ebp, ebp
0x14001523b  jz      short loc_14001526A
0x14001523d  cmp     ebp, eax
0x14001523f  jnz     short loc_14001526A
0x140015241  mov     r8d, 10h; unsigned __int64
0x140015247  mov     [rsp+48h+var_28], 3
0x140015250  lea     rdx, [rsp+48h+var_28]; void *
0x140015255  mov     [rsp+48h+var_20], rsi
0x14001525a  lea     rcx, qword_140029E10; this
0x140015261  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140015266  test    al, al
0x140015268  jnz     short loc_14001526E
0x14001526a  lock and dword ptr [rsi], 0FFFFFFFBh
0x14001526e  lea     rcx, stru_140029DD8; SRWLock
0x140015275  call    cs:__imp_ReleaseSRWLockExclusive
0x14001527b  mov     eax, [rdi]
0x14001527d  test    al, 2
0x14001527f  jnz     short loc_140015290
0x140015281  and     eax, 0FFFFF63Eh
0x140015286  and     ebx, 9C1h
0x14001528c  or      eax, ebx
0x14001528e  mov     [rdi], eax
0x140015290  mov     rbx, [rsp+48h+arg_10]
0x140015295  mov     rax, rdi
0x140015298  add     rsp, 30h
0x14001529c  pop     rdi
0x14001529d  pop     rsi
0x14001529e  pop     rbp
0x14001529f  retn
```
