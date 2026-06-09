# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x140015768`
- end: `0x140015890`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `296`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017620`
- `0x140017f7c`

## callees

- `0x14000a020`
- `0x140014c90`
- `0x140015768`
- `0x140016428`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001581d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001581d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015865`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015865`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_140029DD8);
      if ( !v5
        || v5 != dword_140029DEC
        || (v14[0] = 3,
            v14[1] = Feature_TestLoc1Perf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140029E10, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, 0xFFFFFFFB);
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
0x140015768  mov     [rsp+arg_10], rbx
0x14001576d  mov     [rsp+arg_0], rcx
0x140015772  push    rbp
0x140015773  push    rsi
0x140015774  push    rdi
0x140015775  sub     rsp, 30h
0x140015779  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x140015780  mov     rdi, rdx
0x140015783  mov     qword ptr [rdx], 0
0x14001578a  mov     eax, [rsi]
0x14001578c  mov     [rdx], eax
0x14001578e  and     eax, 6
0x140015791  cmp     al, 6
0x140015793  jz      loc_140015880
0x140015799  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14001579e  lea     r8, [rsp+48h+arg_0]
0x1400157a3  mov     dword ptr [rsp+48h+arg_0], 0
0x1400157ab  lea     rdx, [rsp+48h+arg_8]
0x1400157b0  mov     ebp, eax
0x1400157b2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x1400157b7  mov     eax, [rdi]
0x1400157b9  mov     rbx, [rsp+48h+arg_8]
0x1400157be  cmp     dword ptr [rsp+48h+arg_0], 0
0x1400157c3  mov     edx, eax
0x1400157c5  mov     [rdi], eax
0x1400157c7  mov     ecx, eax
0x1400157c9  jz      short loc_1400157E4
0x1400157cb  test    dl, 2
0x1400157ce  jnz     short loc_1400157E4
0x1400157d0  and     ecx, 0FFFFF63Eh
0x1400157d6  mov     eax, ebx
0x1400157d8  and     eax, 9C1h
0x1400157dd  or      ecx, eax
0x1400157df  or      ecx, 2
0x1400157e2  mov     [rdi], ecx
0x1400157e4  mov     r8d, edx
0x1400157e7  and     r8d, 4
0x1400157eb  jnz     short loc_1400157FF
0x1400157ed  btr     ecx, 0Ah
0x1400157f1  mov     eax, ebx
0x1400157f3  and     eax, 400h
0x1400157f8  or      ecx, eax
0x1400157fa  or      ecx, 4
0x1400157fd  mov     [rdi], ecx
0x1400157ff  mov     eax, edx
0x140015801  lock cmpxchg [rsi], ecx
0x140015805  jnz     short loc_1400157BE
0x140015807  test    r8d, r8d
0x14001580a  jnz     short loc_14001586B
0x14001580c  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140015812  test    eax, eax
0x140015814  jz      short loc_14001586B
0x140015816  lea     rcx, stru_140029DD8; SRWLock
0x14001581d  call    cs:__imp_AcquireSRWLockExclusive
0x140015823  mov     eax, cs:dword_140029DEC
0x140015829  test    ebp, ebp
0x14001582b  jz      short loc_14001585A
0x14001582d  cmp     ebp, eax
0x14001582f  jnz     short loc_14001585A
0x140015831  mov     r8d, 10h; unsigned __int64
0x140015837  mov     [rsp+48h+var_28], 3
0x140015840  lea     rdx, [rsp+48h+var_28]; void *
0x140015845  mov     [rsp+48h+var_20], rsi
0x14001584a  lea     rcx, qword_140029E10; this
0x140015851  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140015856  test    al, al
0x140015858  jnz     short loc_14001585E
0x14001585a  lock and dword ptr [rsi], 0FFFFFFFBh
0x14001585e  lea     rcx, stru_140029DD8; SRWLock
0x140015865  call    cs:__imp_ReleaseSRWLockExclusive
0x14001586b  mov     eax, [rdi]
0x14001586d  test    al, 2
0x14001586f  jnz     short loc_140015880
0x140015871  and     eax, 0FFFFF63Eh
0x140015876  and     ebx, 9C1h
0x14001587c  or      eax, ebx
0x14001587e  mov     [rdi], eax
0x140015880  mov     rbx, [rsp+48h+arg_10]
0x140015885  mov     rax, rdi
0x140015888  add     rsp, 30h
0x14001588c  pop     rdi
0x14001588d  pop     rsi
0x14001588e  pop     rbp
0x14001588f  retn
```
