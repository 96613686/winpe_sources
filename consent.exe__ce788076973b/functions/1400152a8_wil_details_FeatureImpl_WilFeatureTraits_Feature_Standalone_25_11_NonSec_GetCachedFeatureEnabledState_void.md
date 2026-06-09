# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1400152a8`
- end: `0x1400153d0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `296`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001740c`

## callees

- `0x14000a020`
- `0x140014c90`
- `0x1400152a8`
- `0x1400161e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001535d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001535d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400153a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400153a5`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_140029DD8);
      if ( !v5
        || v5 != dword_140029DEC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_11_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140029E10, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, 0xFFFFFFFB);
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
0x1400152a8  mov     [rsp+arg_10], rbx
0x1400152ad  mov     [rsp+arg_0], rcx
0x1400152b2  push    rbp
0x1400152b3  push    rsi
0x1400152b4  push    rdi
0x1400152b5  sub     rsp, 30h
0x1400152b9  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x1400152c0  mov     rdi, rdx
0x1400152c3  mov     qword ptr [rdx], 0
0x1400152ca  mov     eax, [rsi]
0x1400152cc  mov     [rdx], eax
0x1400152ce  and     eax, 6
0x1400152d1  cmp     al, 6
0x1400152d3  jz      loc_1400153C0
0x1400152d9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400152de  lea     r8, [rsp+48h+arg_0]
0x1400152e3  mov     dword ptr [rsp+48h+arg_0], 0
0x1400152eb  lea     rdx, [rsp+48h+arg_8]
0x1400152f0  mov     ebp, eax
0x1400152f2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)
0x1400152f7  mov     eax, [rdi]
0x1400152f9  mov     rbx, [rsp+48h+arg_8]
0x1400152fe  cmp     dword ptr [rsp+48h+arg_0], 0
0x140015303  mov     edx, eax
0x140015305  mov     [rdi], eax
0x140015307  mov     ecx, eax
0x140015309  jz      short loc_140015324
0x14001530b  test    dl, 2
0x14001530e  jnz     short loc_140015324
0x140015310  and     ecx, 0FFFFF63Eh
0x140015316  mov     eax, ebx
0x140015318  and     eax, 9C1h
0x14001531d  or      ecx, eax
0x14001531f  or      ecx, 2
0x140015322  mov     [rdi], ecx
0x140015324  mov     r8d, edx
0x140015327  and     r8d, 4
0x14001532b  jnz     short loc_14001533F
0x14001532d  btr     ecx, 0Ah
0x140015331  mov     eax, ebx
0x140015333  and     eax, 400h
0x140015338  or      ecx, eax
0x14001533a  or      ecx, 4
0x14001533d  mov     [rdi], ecx
0x14001533f  mov     eax, edx
0x140015341  lock cmpxchg [rsi], ecx
0x140015345  jnz     short loc_1400152FE
0x140015347  test    r8d, r8d
0x14001534a  jnz     short loc_1400153AB
0x14001534c  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140015352  test    eax, eax
0x140015354  jz      short loc_1400153AB
0x140015356  lea     rcx, stru_140029DD8; SRWLock
0x14001535d  call    cs:__imp_AcquireSRWLockExclusive
0x140015363  mov     eax, cs:dword_140029DEC
0x140015369  test    ebp, ebp
0x14001536b  jz      short loc_14001539A
0x14001536d  cmp     ebp, eax
0x14001536f  jnz     short loc_14001539A
0x140015371  mov     r8d, 10h; unsigned __int64
0x140015377  mov     [rsp+48h+var_28], 3
0x140015380  lea     rdx, [rsp+48h+var_28]; void *
0x140015385  mov     [rsp+48h+var_20], rsi
0x14001538a  lea     rcx, qword_140029E10; this
0x140015391  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140015396  test    al, al
0x140015398  jnz     short loc_14001539E
0x14001539a  lock and dword ptr [rsi], 0FFFFFFFBh
0x14001539e  lea     rcx, stru_140029DD8; SRWLock
0x1400153a5  call    cs:__imp_ReleaseSRWLockExclusive
0x1400153ab  mov     eax, [rdi]
0x1400153ad  test    al, 2
0x1400153af  jnz     short loc_1400153C0
0x1400153b1  and     eax, 0FFFFF63Eh
0x1400153b6  and     ebx, 9C1h
0x1400153bc  or      eax, ebx
0x1400153be  mov     [rdi], eax
0x1400153c0  mov     rbx, [rsp+48h+arg_10]
0x1400153c5  mov     rax, rdi
0x1400153c8  add     rsp, 30h
0x1400153cc  pop     rdi
0x1400153cd  pop     rsi
0x1400153ce  pop     rbp
0x1400153cf  retn
```
