# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180010334`
- end: `0x18001046d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011b1c`
- `0x1800123b8`

## callees

- `0x180007c28`
- `0x180008684`
- `0x18000c930`
- `0x180010334`
- `0x180010864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800103f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800103f2`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180035B78);
      v16 = &stru_180035B78;
      if ( !v5
        || v5 != dword_180035B8C
        || (v14[0] = 3,
            v14[1] = Feature_ValAccTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180035BB0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ValAccTest__descriptor, 0xFFFFFFFB);
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
0x180010334  mov     [rsp+arg_10], rbx
0x180010339  mov     [rsp+arg_18], rbp
0x18001033e  mov     [rsp+arg_0], rcx
0x180010343  push    rsi
0x180010344  push    rdi
0x180010345  push    r14
0x180010347  sub     rsp, 30h
0x18001034b  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180010352  mov     rdi, rdx
0x180010355  mov     qword ptr [rdx], 0
0x18001035c  mov     eax, [rsi]
0x18001035e  mov     [rdx], eax
0x180010360  and     eax, 6
0x180010363  cmp     al, 6
0x180010365  jz      loc_180010457
0x18001036b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180010370  lea     r8, [rsp+48h+arg_0]
0x180010375  mov     dword ptr [rsp+48h+arg_0], 0
0x18001037d  lea     rdx, [rsp+48h+arg_8]
0x180010382  mov     ebp, eax
0x180010384  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180010389  mov     eax, [rdi]
0x18001038b  mov     rbx, [rsp+48h+arg_8]
0x180010390  cmp     dword ptr [rsp+48h+arg_0], 0
0x180010395  mov     edx, eax
0x180010397  mov     [rdi], eax
0x180010399  mov     ecx, eax
0x18001039b  jz      short loc_1800103B6
0x18001039d  test    dl, 2
0x1800103a0  jnz     short loc_1800103B6
0x1800103a2  and     ecx, 0FFFFF63Eh
0x1800103a8  mov     eax, ebx
0x1800103aa  and     eax, 9C1h
0x1800103af  or      ecx, eax
0x1800103b1  or      ecx, 2
0x1800103b4  mov     [rdi], ecx
0x1800103b6  mov     r8d, edx
0x1800103b9  and     r8d, 4
0x1800103bd  jnz     short loc_1800103D1
0x1800103bf  btr     ecx, 0Ah
0x1800103c3  mov     eax, ebx
0x1800103c5  and     eax, 400h
0x1800103ca  or      ecx, eax
0x1800103cc  or      ecx, 4
0x1800103cf  mov     [rdi], ecx
0x1800103d1  mov     eax, edx
0x1800103d3  lock cmpxchg [rsi], ecx
0x1800103d7  jnz     short loc_180010390
0x1800103d9  test    r8d, r8d
0x1800103dc  jnz     short loc_180010442
0x1800103de  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800103e4  test    eax, eax
0x1800103e6  jz      short loc_180010442
0x1800103e8  lea     r14, stru_180035B78
0x1800103ef  mov     rcx, r14; SRWLock
0x1800103f2  call    cs:__imp_AcquireSRWLockExclusive
0x1800103f8  mov     eax, cs:dword_180035B8C
0x1800103fe  mov     [rsp+48h+arg_8], r14
0x180010403  test    ebp, ebp
0x180010405  jz      short loc_180010434
0x180010407  cmp     ebp, eax
0x180010409  jnz     short loc_180010434
0x18001040b  mov     r8d, 10h; unsigned __int64
0x180010411  mov     [rsp+48h+var_28], 3
0x18001041a  lea     rdx, [rsp+48h+var_28]; void *
0x18001041f  mov     [rsp+48h+var_20], rsi
0x180010424  lea     rcx, qword_180035BB0; this
0x18001042b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180010430  test    al, al
0x180010432  jnz     short loc_180010438
0x180010434  lock and dword ptr [rsi], 0FFFFFFFBh
0x180010438  lea     rcx, [rsp+48h+arg_8]
0x18001043d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180010442  mov     eax, [rdi]
0x180010444  test    al, 2
0x180010446  jnz     short loc_180010457
0x180010448  and     eax, 0FFFFF63Eh
0x18001044d  and     ebx, 9C1h
0x180010453  or      eax, ebx
0x180010455  mov     [rdi], eax
0x180010457  mov     rbx, [rsp+48h+arg_10]
0x18001045c  mov     rax, rdi
0x18001045f  mov     rbp, [rsp+48h+arg_18]
0x180010464  add     rsp, 30h
0x180010468  pop     r14
0x18001046a  pop     rdi
0x18001046b  pop     rsi
0x18001046c  retn
```
