# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x140015638`
- end: `0x140015760`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `296`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017598`
- `0x140017f40`

## callees

- `0x14000a020`
- `0x140014c90`
- `0x140015638`
- `0x140016344`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400156ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400156ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015735`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015735`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_140029DD8);
      if ( !v5
        || v5 != dword_140029DEC
        || (v14[0] = 3,
            v14[1] = Feature_TestAccPerf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140029E10, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_TestAccPerf__descriptor, 0xFFFFFFFB);
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
0x140015638  mov     [rsp+arg_10], rbx
0x14001563d  mov     [rsp+arg_0], rcx
0x140015642  push    rbp
0x140015643  push    rsi
0x140015644  push    rdi
0x140015645  sub     rsp, 30h
0x140015649  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x140015650  mov     rdi, rdx
0x140015653  mov     qword ptr [rdx], 0
0x14001565a  mov     eax, [rsi]
0x14001565c  mov     [rdx], eax
0x14001565e  and     eax, 6
0x140015661  cmp     al, 6
0x140015663  jz      loc_140015750
0x140015669  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14001566e  lea     r8, [rsp+48h+arg_0]
0x140015673  mov     dword ptr [rsp+48h+arg_0], 0
0x14001567b  lea     rdx, [rsp+48h+arg_8]
0x140015680  mov     ebp, eax
0x140015682  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x140015687  mov     eax, [rdi]
0x140015689  mov     rbx, [rsp+48h+arg_8]
0x14001568e  cmp     dword ptr [rsp+48h+arg_0], 0
0x140015693  mov     edx, eax
0x140015695  mov     [rdi], eax
0x140015697  mov     ecx, eax
0x140015699  jz      short loc_1400156B4
0x14001569b  test    dl, 2
0x14001569e  jnz     short loc_1400156B4
0x1400156a0  and     ecx, 0FFFFF63Eh
0x1400156a6  mov     eax, ebx
0x1400156a8  and     eax, 9C1h
0x1400156ad  or      ecx, eax
0x1400156af  or      ecx, 2
0x1400156b2  mov     [rdi], ecx
0x1400156b4  mov     r8d, edx
0x1400156b7  and     r8d, 4
0x1400156bb  jnz     short loc_1400156CF
0x1400156bd  btr     ecx, 0Ah
0x1400156c1  mov     eax, ebx
0x1400156c3  and     eax, 400h
0x1400156c8  or      ecx, eax
0x1400156ca  or      ecx, 4
0x1400156cd  mov     [rdi], ecx
0x1400156cf  mov     eax, edx
0x1400156d1  lock cmpxchg [rsi], ecx
0x1400156d5  jnz     short loc_14001568E
0x1400156d7  test    r8d, r8d
0x1400156da  jnz     short loc_14001573B
0x1400156dc  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400156e2  test    eax, eax
0x1400156e4  jz      short loc_14001573B
0x1400156e6  lea     rcx, stru_140029DD8; SRWLock
0x1400156ed  call    cs:__imp_AcquireSRWLockExclusive
0x1400156f3  mov     eax, cs:dword_140029DEC
0x1400156f9  test    ebp, ebp
0x1400156fb  jz      short loc_14001572A
0x1400156fd  cmp     ebp, eax
0x1400156ff  jnz     short loc_14001572A
0x140015701  mov     r8d, 10h; unsigned __int64
0x140015707  mov     [rsp+48h+var_28], 3
0x140015710  lea     rdx, [rsp+48h+var_28]; void *
0x140015715  mov     [rsp+48h+var_20], rsi
0x14001571a  lea     rcx, qword_140029E10; this
0x140015721  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140015726  test    al, al
0x140015728  jnz     short loc_14001572E
0x14001572a  lock and dword ptr [rsi], 0FFFFFFFBh
0x14001572e  lea     rcx, stru_140029DD8; SRWLock
0x140015735  call    cs:__imp_ReleaseSRWLockExclusive
0x14001573b  mov     eax, [rdi]
0x14001573d  test    al, 2
0x14001573f  jnz     short loc_140015750
0x140015741  and     eax, 0FFFFF63Eh
0x140015746  and     ebx, 9C1h
0x14001574c  or      eax, ebx
0x14001574e  mov     [rdi], eax
0x140015750  mov     rbx, [rsp+48h+arg_10]
0x140015755  mov     rax, rdi
0x140015758  add     rsp, 30h
0x14001575c  pop     rdi
0x14001575d  pop     rsi
0x14001575e  pop     rbp
0x14001575f  retn
```
