# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x140015898`
- end: `0x1400159c0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `296`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400176a8`
- `0x140017fb8`

## callees

- `0x14000a020`
- `0x140014c90`
- `0x140015898`
- `0x14001650c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001594d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001594d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015995`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015995`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_140029DD8);
      if ( !v5
        || v5 != dword_140029DEC
        || (v14[0] = 3,
            v14[1] = Feature_UxAccOptimization__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140029E10, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, 0xFFFFFFFB);
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
0x140015898  mov     [rsp+arg_10], rbx
0x14001589d  mov     [rsp+arg_0], rcx
0x1400158a2  push    rbp
0x1400158a3  push    rsi
0x1400158a4  push    rdi
0x1400158a5  sub     rsp, 30h
0x1400158a9  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x1400158b0  mov     rdi, rdx
0x1400158b3  mov     qword ptr [rdx], 0
0x1400158ba  mov     eax, [rsi]
0x1400158bc  mov     [rdx], eax
0x1400158be  and     eax, 6
0x1400158c1  cmp     al, 6
0x1400158c3  jz      loc_1400159B0
0x1400158c9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400158ce  lea     r8, [rsp+48h+arg_0]
0x1400158d3  mov     dword ptr [rsp+48h+arg_0], 0
0x1400158db  lea     rdx, [rsp+48h+arg_8]
0x1400158e0  mov     ebp, eax
0x1400158e2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x1400158e7  mov     eax, [rdi]
0x1400158e9  mov     rbx, [rsp+48h+arg_8]
0x1400158ee  cmp     dword ptr [rsp+48h+arg_0], 0
0x1400158f3  mov     edx, eax
0x1400158f5  mov     [rdi], eax
0x1400158f7  mov     ecx, eax
0x1400158f9  jz      short loc_140015914
0x1400158fb  test    dl, 2
0x1400158fe  jnz     short loc_140015914
0x140015900  and     ecx, 0FFFFF63Eh
0x140015906  mov     eax, ebx
0x140015908  and     eax, 9C1h
0x14001590d  or      ecx, eax
0x14001590f  or      ecx, 2
0x140015912  mov     [rdi], ecx
0x140015914  mov     r8d, edx
0x140015917  and     r8d, 4
0x14001591b  jnz     short loc_14001592F
0x14001591d  btr     ecx, 0Ah
0x140015921  mov     eax, ebx
0x140015923  and     eax, 400h
0x140015928  or      ecx, eax
0x14001592a  or      ecx, 4
0x14001592d  mov     [rdi], ecx
0x14001592f  mov     eax, edx
0x140015931  lock cmpxchg [rsi], ecx
0x140015935  jnz     short loc_1400158EE
0x140015937  test    r8d, r8d
0x14001593a  jnz     short loc_14001599B
0x14001593c  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140015942  test    eax, eax
0x140015944  jz      short loc_14001599B
0x140015946  lea     rcx, stru_140029DD8; SRWLock
0x14001594d  call    cs:__imp_AcquireSRWLockExclusive
0x140015953  mov     eax, cs:dword_140029DEC
0x140015959  test    ebp, ebp
0x14001595b  jz      short loc_14001598A
0x14001595d  cmp     ebp, eax
0x14001595f  jnz     short loc_14001598A
0x140015961  mov     r8d, 10h; unsigned __int64
0x140015967  mov     [rsp+48h+var_28], 3
0x140015970  lea     rdx, [rsp+48h+var_28]; void *
0x140015975  mov     [rsp+48h+var_20], rsi
0x14001597a  lea     rcx, qword_140029E10; this
0x140015981  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140015986  test    al, al
0x140015988  jnz     short loc_14001598E
0x14001598a  lock and dword ptr [rsi], 0FFFFFFFBh
0x14001598e  lea     rcx, stru_140029DD8; SRWLock
0x140015995  call    cs:__imp_ReleaseSRWLockExclusive
0x14001599b  mov     eax, [rdi]
0x14001599d  test    al, 2
0x14001599f  jnz     short loc_1400159B0
0x1400159a1  and     eax, 0FFFFF63Eh
0x1400159a6  and     ebx, 9C1h
0x1400159ac  or      eax, ebx
0x1400159ae  mov     [rdi], eax
0x1400159b0  mov     rbx, [rsp+48h+arg_10]
0x1400159b5  mov     rax, rdi
0x1400159b8  add     rsp, 30h
0x1400159bc  pop     rdi
0x1400159bd  pop     rsi
0x1400159be  pop     rbp
0x1400159bf  retn
```
