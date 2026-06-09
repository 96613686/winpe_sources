# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1400153d8`
- end: `0x140015500`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `296`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017490`

## callees

- `0x14000a020`
- `0x140014c90`
- `0x1400153d8`
- `0x14001625c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001548d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001548d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400154d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400154d5`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_140029DD8);
      if ( !v5
        || v5 != dword_140029DEC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_26_01_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140029E10, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, 0xFFFFFFFB);
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
0x1400153d8  mov     [rsp+arg_10], rbx
0x1400153dd  mov     [rsp+arg_0], rcx
0x1400153e2  push    rbp
0x1400153e3  push    rsi
0x1400153e4  push    rdi
0x1400153e5  sub     rsp, 30h
0x1400153e9  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x1400153f0  mov     rdi, rdx
0x1400153f3  mov     qword ptr [rdx], 0
0x1400153fa  mov     eax, [rsi]
0x1400153fc  mov     [rdx], eax
0x1400153fe  and     eax, 6
0x140015401  cmp     al, 6
0x140015403  jz      loc_1400154F0
0x140015409  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14001540e  lea     r8, [rsp+48h+arg_0]
0x140015413  mov     dword ptr [rsp+48h+arg_0], 0
0x14001541b  lea     rdx, [rsp+48h+arg_8]
0x140015420  mov     ebp, eax
0x140015422  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)
0x140015427  mov     eax, [rdi]
0x140015429  mov     rbx, [rsp+48h+arg_8]
0x14001542e  cmp     dword ptr [rsp+48h+arg_0], 0
0x140015433  mov     edx, eax
0x140015435  mov     [rdi], eax
0x140015437  mov     ecx, eax
0x140015439  jz      short loc_140015454
0x14001543b  test    dl, 2
0x14001543e  jnz     short loc_140015454
0x140015440  and     ecx, 0FFFFF63Eh
0x140015446  mov     eax, ebx
0x140015448  and     eax, 9C1h
0x14001544d  or      ecx, eax
0x14001544f  or      ecx, 2
0x140015452  mov     [rdi], ecx
0x140015454  mov     r8d, edx
0x140015457  and     r8d, 4
0x14001545b  jnz     short loc_14001546F
0x14001545d  btr     ecx, 0Ah
0x140015461  mov     eax, ebx
0x140015463  and     eax, 400h
0x140015468  or      ecx, eax
0x14001546a  or      ecx, 4
0x14001546d  mov     [rdi], ecx
0x14001546f  mov     eax, edx
0x140015471  lock cmpxchg [rsi], ecx
0x140015475  jnz     short loc_14001542E
0x140015477  test    r8d, r8d
0x14001547a  jnz     short loc_1400154DB
0x14001547c  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140015482  test    eax, eax
0x140015484  jz      short loc_1400154DB
0x140015486  lea     rcx, stru_140029DD8; SRWLock
0x14001548d  call    cs:__imp_AcquireSRWLockExclusive
0x140015493  mov     eax, cs:dword_140029DEC
0x140015499  test    ebp, ebp
0x14001549b  jz      short loc_1400154CA
0x14001549d  cmp     ebp, eax
0x14001549f  jnz     short loc_1400154CA
0x1400154a1  mov     r8d, 10h; unsigned __int64
0x1400154a7  mov     [rsp+48h+var_28], 3
0x1400154b0  lea     rdx, [rsp+48h+var_28]; void *
0x1400154b5  mov     [rsp+48h+var_20], rsi
0x1400154ba  lea     rcx, qword_140029E10; this
0x1400154c1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1400154c6  test    al, al
0x1400154c8  jnz     short loc_1400154CE
0x1400154ca  lock and dword ptr [rsi], 0FFFFFFFBh
0x1400154ce  lea     rcx, stru_140029DD8; SRWLock
0x1400154d5  call    cs:__imp_ReleaseSRWLockExclusive
0x1400154db  mov     eax, [rdi]
0x1400154dd  test    al, 2
0x1400154df  jnz     short loc_1400154F0
0x1400154e1  and     eax, 0FFFFF63Eh
0x1400154e6  and     ebx, 9C1h
0x1400154ec  or      eax, ebx
0x1400154ee  mov     [rdi], eax
0x1400154f0  mov     rbx, [rsp+48h+arg_10]
0x1400154f5  mov     rax, rdi
0x1400154f8  add     rsp, 30h
0x1400154fc  pop     rdi
0x1400154fd  pop     rsi
0x1400154fe  pop     rbp
0x1400154ff  retn
```
