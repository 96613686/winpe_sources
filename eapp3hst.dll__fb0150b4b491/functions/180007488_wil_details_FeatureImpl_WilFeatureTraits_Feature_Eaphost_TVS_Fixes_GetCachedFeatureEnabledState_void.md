# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::GetCachedFeatureEnabledState(void)

- ea: `0x180007488`
- end: `0x1800075c1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Eaphost_TVS_Fixes@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a410`
- `0x18000b9f4`

## callees

- `0x180005f54`
- `0x1800070c4`
- `0x180007488`
- `0x18000783c`
- `0x18000bbc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007546`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007546`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Eaphost_TVS_Fixes__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Eaphost_TVS_Fixes__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::GetCurrentFeatureEnabledState(
      v6,
      &v16,
      &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Eaphost_TVS_Fixes__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18004A23C
        || (v14[0] = 3,
            v14[1] = Feature_Eaphost_TVS_Fixes__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18004A260, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Eaphost_TVS_Fixes__descriptor, 0xFFFFFFFB);
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
0x180007488  mov     [rsp+arg_10], rbx
0x18000748d  mov     [rsp+arg_18], rbp
0x180007492  mov     [rsp+arg_0], rcx
0x180007497  push    rsi
0x180007498  push    rdi
0x180007499  push    r14
0x18000749b  sub     rsp, 30h
0x18000749f  mov     rsi, cs:Feature_Eaphost_TVS_Fixes__descriptor
0x1800074a6  mov     rdi, rdx
0x1800074a9  mov     qword ptr [rdx], 0
0x1800074b0  mov     eax, [rsi]
0x1800074b2  mov     [rdx], eax
0x1800074b4  and     eax, 6
0x1800074b7  cmp     al, 6
0x1800074b9  jz      loc_1800075AB
0x1800074bf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800074c4  lea     r8, [rsp+48h+arg_0]
0x1800074c9  mov     dword ptr [rsp+48h+arg_0], 0
0x1800074d1  lea     rdx, [rsp+48h+arg_8]
0x1800074d6  mov     ebp, eax
0x1800074d8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Eaphost_TVS_Fixes@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::GetCurrentFeatureEnabledState(int *)
0x1800074dd  mov     eax, [rdi]
0x1800074df  mov     rbx, [rsp+48h+arg_8]
0x1800074e4  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800074e9  mov     edx, eax
0x1800074eb  mov     [rdi], eax
0x1800074ed  mov     ecx, eax
0x1800074ef  jz      short loc_18000750A
0x1800074f1  test    dl, 2
0x1800074f4  jnz     short loc_18000750A
0x1800074f6  and     ecx, 0FFFFF63Eh
0x1800074fc  mov     eax, ebx
0x1800074fe  and     eax, 9C1h
0x180007503  or      ecx, eax
0x180007505  or      ecx, 2
0x180007508  mov     [rdi], ecx
0x18000750a  mov     r8d, edx
0x18000750d  and     r8d, 4
0x180007511  jnz     short loc_180007525
0x180007513  btr     ecx, 0Ah
0x180007517  mov     eax, ebx
0x180007519  and     eax, 400h
0x18000751e  or      ecx, eax
0x180007520  or      ecx, 4
0x180007523  mov     [rdi], ecx
0x180007525  mov     eax, edx
0x180007527  lock cmpxchg [rsi], ecx
0x18000752b  jnz     short loc_1800074E4
0x18000752d  test    r8d, r8d
0x180007530  jnz     short loc_180007596
0x180007532  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180007538  test    eax, eax
0x18000753a  jz      short loc_180007596
0x18000753c  lea     r14, SRWLock
0x180007543  mov     rcx, r14; SRWLock
0x180007546  call    cs:__imp_AcquireSRWLockExclusive
0x18000754c  mov     eax, cs:dword_18004A23C
0x180007552  mov     [rsp+48h+arg_8], r14
0x180007557  test    ebp, ebp
0x180007559  jz      short loc_180007588
0x18000755b  cmp     ebp, eax
0x18000755d  jnz     short loc_180007588
0x18000755f  mov     r8d, 10h; unsigned __int64
0x180007565  mov     [rsp+48h+var_28], 3
0x18000756e  lea     rdx, [rsp+48h+var_28]; void *
0x180007573  mov     [rsp+48h+var_20], rsi
0x180007578  lea     rcx, qword_18004A260; this
0x18000757f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180007584  test    al, al
0x180007586  jnz     short loc_18000758C
0x180007588  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000758c  lea     rcx, [rsp+48h+arg_8]
0x180007591  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180007596  mov     eax, [rdi]
0x180007598  test    al, 2
0x18000759a  jnz     short loc_1800075AB
0x18000759c  and     eax, 0FFFFF63Eh
0x1800075a1  and     ebx, 9C1h
0x1800075a7  or      eax, ebx
0x1800075a9  mov     [rdi], eax
0x1800075ab  mov     rbx, [rsp+48h+arg_10]
0x1800075b0  mov     rax, rdi
0x1800075b3  mov     rbp, [rsp+48h+arg_18]
0x1800075b8  add     rsp, 30h
0x1800075bc  pop     r14
0x1800075be  pop     rdi
0x1800075bf  pop     rsi
0x1800075c0  retn
```
