# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x140015508`
- end: `0x140015630`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `296`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017514`

## callees

- `0x14000a020`
- `0x140014c90`
- `0x140015508`
- `0x1400162d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400155bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400155bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015605`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015605`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_140029DD8);
      if ( !v5
        || v5 != dword_140029DEC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_Future__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140029E10, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_Future__descriptor, 0xFFFFFFFB);
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
0x140015508  mov     [rsp+arg_10], rbx
0x14001550d  mov     [rsp+arg_0], rcx
0x140015512  push    rbp
0x140015513  push    rsi
0x140015514  push    rdi
0x140015515  sub     rsp, 30h
0x140015519  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x140015520  mov     rdi, rdx
0x140015523  mov     qword ptr [rdx], 0
0x14001552a  mov     eax, [rsi]
0x14001552c  mov     [rdx], eax
0x14001552e  and     eax, 6
0x140015531  cmp     al, 6
0x140015533  jz      loc_140015620
0x140015539  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14001553e  lea     r8, [rsp+48h+arg_0]
0x140015543  mov     dword ptr [rsp+48h+arg_0], 0
0x14001554b  lea     rdx, [rsp+48h+arg_8]
0x140015550  mov     ebp, eax
0x140015552  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCurrentFeatureEnabledState(int *)
0x140015557  mov     eax, [rdi]
0x140015559  mov     rbx, [rsp+48h+arg_8]
0x14001555e  cmp     dword ptr [rsp+48h+arg_0], 0
0x140015563  mov     edx, eax
0x140015565  mov     [rdi], eax
0x140015567  mov     ecx, eax
0x140015569  jz      short loc_140015584
0x14001556b  test    dl, 2
0x14001556e  jnz     short loc_140015584
0x140015570  and     ecx, 0FFFFF63Eh
0x140015576  mov     eax, ebx
0x140015578  and     eax, 9C1h
0x14001557d  or      ecx, eax
0x14001557f  or      ecx, 2
0x140015582  mov     [rdi], ecx
0x140015584  mov     r8d, edx
0x140015587  and     r8d, 4
0x14001558b  jnz     short loc_14001559F
0x14001558d  btr     ecx, 0Ah
0x140015591  mov     eax, ebx
0x140015593  and     eax, 400h
0x140015598  or      ecx, eax
0x14001559a  or      ecx, 4
0x14001559d  mov     [rdi], ecx
0x14001559f  mov     eax, edx
0x1400155a1  lock cmpxchg [rsi], ecx
0x1400155a5  jnz     short loc_14001555E
0x1400155a7  test    r8d, r8d
0x1400155aa  jnz     short loc_14001560B
0x1400155ac  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400155b2  test    eax, eax
0x1400155b4  jz      short loc_14001560B
0x1400155b6  lea     rcx, stru_140029DD8; SRWLock
0x1400155bd  call    cs:__imp_AcquireSRWLockExclusive
0x1400155c3  mov     eax, cs:dword_140029DEC
0x1400155c9  test    ebp, ebp
0x1400155cb  jz      short loc_1400155FA
0x1400155cd  cmp     ebp, eax
0x1400155cf  jnz     short loc_1400155FA
0x1400155d1  mov     r8d, 10h; unsigned __int64
0x1400155d7  mov     [rsp+48h+var_28], 3
0x1400155e0  lea     rdx, [rsp+48h+var_28]; void *
0x1400155e5  mov     [rsp+48h+var_20], rsi
0x1400155ea  lea     rcx, qword_140029E10; this
0x1400155f1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1400155f6  test    al, al
0x1400155f8  jnz     short loc_1400155FE
0x1400155fa  lock and dword ptr [rsi], 0FFFFFFFBh
0x1400155fe  lea     rcx, stru_140029DD8; SRWLock
0x140015605  call    cs:__imp_ReleaseSRWLockExclusive
0x14001560b  mov     eax, [rdi]
0x14001560d  test    al, 2
0x14001560f  jnz     short loc_140015620
0x140015611  and     eax, 0FFFFF63Eh
0x140015616  and     ebx, 9C1h
0x14001561c  or      eax, ebx
0x14001561e  mov     [rdi], eax
0x140015620  mov     rbx, [rsp+48h+arg_10]
0x140015625  mov     rax, rdi
0x140015628  add     rsp, 30h
0x14001562c  pop     rdi
0x14001562d  pop     rsi
0x14001562e  pop     rbp
0x14001562f  retn
```
