# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmersiveColorFight>::GetCachedFeatureEnabledState(void)

- ea: `0x140014f60`
- end: `0x140015088`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ImmersiveColorFight@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `296`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017300`
- `0x140017f04`

## callees

- `0x14000a020`
- `0x140014c90`
- `0x140014f60`
- `0x140015fc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140015015`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140015015`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001505d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001505d`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmersiveColorFight>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ImmersiveColorFight__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ImmersiveColorFight__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmersiveColorFight>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ImmersiveColorFight__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_140029DD8);
      if ( !v5
        || v5 != dword_140029DEC
        || (v14[0] = 3,
            v14[1] = Feature_ImmersiveColorFight__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140029E10, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ImmersiveColorFight__descriptor, 0xFFFFFFFB);
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
0x140014f60  mov     [rsp+arg_10], rbx
0x140014f65  mov     [rsp+arg_0], rcx
0x140014f6a  push    rbp
0x140014f6b  push    rsi
0x140014f6c  push    rdi
0x140014f6d  sub     rsp, 30h
0x140014f71  mov     rsi, cs:Feature_ImmersiveColorFight__descriptor
0x140014f78  mov     rdi, rdx
0x140014f7b  mov     qword ptr [rdx], 0
0x140014f82  mov     eax, [rsi]
0x140014f84  mov     [rdx], eax
0x140014f86  and     eax, 6
0x140014f89  cmp     al, 6
0x140014f8b  jz      loc_140015078
0x140014f91  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140014f96  lea     r8, [rsp+48h+arg_0]
0x140014f9b  mov     dword ptr [rsp+48h+arg_0], 0
0x140014fa3  lea     rdx, [rsp+48h+arg_8]
0x140014fa8  mov     ebp, eax
0x140014faa  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ImmersiveColorFight@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmersiveColorFight>::GetCurrentFeatureEnabledState(int *)
0x140014faf  mov     eax, [rdi]
0x140014fb1  mov     rbx, [rsp+48h+arg_8]
0x140014fb6  cmp     dword ptr [rsp+48h+arg_0], 0
0x140014fbb  mov     edx, eax
0x140014fbd  mov     [rdi], eax
0x140014fbf  mov     ecx, eax
0x140014fc1  jz      short loc_140014FDC
0x140014fc3  test    dl, 2
0x140014fc6  jnz     short loc_140014FDC
0x140014fc8  and     ecx, 0FFFFF63Eh
0x140014fce  mov     eax, ebx
0x140014fd0  and     eax, 9C1h
0x140014fd5  or      ecx, eax
0x140014fd7  or      ecx, 2
0x140014fda  mov     [rdi], ecx
0x140014fdc  mov     r8d, edx
0x140014fdf  and     r8d, 4
0x140014fe3  jnz     short loc_140014FF7
0x140014fe5  btr     ecx, 0Ah
0x140014fe9  mov     eax, ebx
0x140014feb  and     eax, 400h
0x140014ff0  or      ecx, eax
0x140014ff2  or      ecx, 4
0x140014ff5  mov     [rdi], ecx
0x140014ff7  mov     eax, edx
0x140014ff9  lock cmpxchg [rsi], ecx
0x140014ffd  jnz     short loc_140014FB6
0x140014fff  test    r8d, r8d
0x140015002  jnz     short loc_140015063
0x140015004  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14001500a  test    eax, eax
0x14001500c  jz      short loc_140015063
0x14001500e  lea     rcx, stru_140029DD8; SRWLock
0x140015015  call    cs:__imp_AcquireSRWLockExclusive
0x14001501b  mov     eax, cs:dword_140029DEC
0x140015021  test    ebp, ebp
0x140015023  jz      short loc_140015052
0x140015025  cmp     ebp, eax
0x140015027  jnz     short loc_140015052
0x140015029  mov     r8d, 10h; unsigned __int64
0x14001502f  mov     [rsp+48h+var_28], 3
0x140015038  lea     rdx, [rsp+48h+var_28]; void *
0x14001503d  mov     [rsp+48h+var_20], rsi
0x140015042  lea     rcx, qword_140029E10; this
0x140015049  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14001504e  test    al, al
0x140015050  jnz     short loc_140015056
0x140015052  lock and dword ptr [rsi], 0FFFFFFFBh
0x140015056  lea     rcx, stru_140029DD8; SRWLock
0x14001505d  call    cs:__imp_ReleaseSRWLockExclusive
0x140015063  mov     eax, [rdi]
0x140015065  test    al, 2
0x140015067  jnz     short loc_140015078
0x140015069  and     eax, 0FFFFF63Eh
0x14001506e  and     ebx, 9C1h
0x140015074  or      eax, ebx
0x140015076  mov     [rdi], eax
0x140015078  mov     rbx, [rsp+48h+arg_10]
0x14001507d  mov     rax, rdi
0x140015080  add     rsp, 30h
0x140015084  pop     rdi
0x140015085  pop     rsi
0x140015086  pop     rbp
0x140015087  retn
```
