# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x180013868`
- end: `0x1800139a1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015064`
- `0x180015a78`

## callees

- `0x18000f11c`
- `0x180012c54`
- `0x180013868`
- `0x18001424c`
- `0x180015b2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013926`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013926`

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
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+10h] BYREF

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
    v8 = (__int16)v16;
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
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800226CC
        || (v14[0] = 3,
            v14[1] = Feature_TestLoc1Perf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800226F0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, 0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180013868  mov     [rsp+arg_10], rbx
0x18001386d  mov     [rsp+arg_18], rbp
0x180013872  mov     [rsp+arg_0], rcx
0x180013877  push    rsi
0x180013878  push    rdi
0x180013879  push    r14
0x18001387b  sub     rsp, 30h
0x18001387f  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x180013886  mov     rdi, rdx
0x180013889  mov     qword ptr [rdx], 0
0x180013890  mov     eax, [rsi]
0x180013892  mov     [rdx], eax
0x180013894  and     eax, 6
0x180013897  cmp     al, 6
0x180013899  jz      loc_18001398B
0x18001389f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800138a4  lea     r8, [rsp+48h+arg_0]
0x1800138a9  mov     dword ptr [rsp+48h+arg_0], 0
0x1800138b1  lea     rdx, [rsp+48h+arg_8]
0x1800138b6  mov     ebp, eax
0x1800138b8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x1800138bd  mov     eax, [rdi]
0x1800138bf  mov     rbx, [rsp+48h+arg_8]
0x1800138c4  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800138c9  mov     edx, eax
0x1800138cb  mov     [rdi], eax
0x1800138cd  mov     ecx, eax
0x1800138cf  jz      short loc_1800138EA
0x1800138d1  test    dl, 2
0x1800138d4  jnz     short loc_1800138EA
0x1800138d6  and     ecx, 0FFFFF63Eh
0x1800138dc  mov     eax, ebx
0x1800138de  and     eax, 9C1h
0x1800138e3  or      ecx, eax
0x1800138e5  or      ecx, 2
0x1800138e8  mov     [rdi], ecx
0x1800138ea  mov     r8d, edx
0x1800138ed  and     r8d, 4
0x1800138f1  jnz     short loc_180013905
0x1800138f3  btr     ecx, 0Ah
0x1800138f7  mov     eax, ebx
0x1800138f9  and     eax, 400h
0x1800138fe  or      ecx, eax
0x180013900  or      ecx, 4
0x180013903  mov     [rdi], ecx
0x180013905  mov     eax, edx
0x180013907  lock cmpxchg [rsi], ecx
0x18001390b  jnz     short loc_1800138C4
0x18001390d  test    r8d, r8d
0x180013910  jnz     short loc_180013976
0x180013912  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013918  test    eax, eax
0x18001391a  jz      short loc_180013976
0x18001391c  lea     r14, SRWLock
0x180013923  mov     rcx, r14; SRWLock
0x180013926  call    cs:__imp_AcquireSRWLockExclusive
0x18001392c  mov     eax, cs:dword_1800226CC
0x180013932  mov     [rsp+48h+arg_8], r14
0x180013937  test    ebp, ebp
0x180013939  jz      short loc_180013968
0x18001393b  cmp     ebp, eax
0x18001393d  jnz     short loc_180013968
0x18001393f  mov     r8d, 10h; unsigned __int64
0x180013945  mov     [rsp+48h+var_28], 3
0x18001394e  lea     rdx, [rsp+48h+var_28]; void *
0x180013953  mov     [rsp+48h+var_20], rsi
0x180013958  lea     rcx, qword_1800226F0; this
0x18001395f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180013964  test    al, al
0x180013966  jnz     short loc_18001396C
0x180013968  lock and dword ptr [rsi], 0FFFFFFFBh
0x18001396c  lea     rcx, [rsp+48h+arg_8]
0x180013971  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013976  mov     eax, [rdi]
0x180013978  test    al, 2
0x18001397a  jnz     short loc_18001398B
0x18001397c  and     eax, 0FFFFF63Eh
0x180013981  and     ebx, 9C1h
0x180013987  or      eax, ebx
0x180013989  mov     [rdi], eax
0x18001398b  mov     rbx, [rsp+48h+arg_10]
0x180013990  mov     rax, rdi
0x180013993  mov     rbp, [rsp+48h+arg_18]
0x180013998  add     rsp, 30h
0x18001399c  pop     r14
0x18001399e  pop     rdi
0x18001399f  pop     rsi
0x1800139a0  retn
```
