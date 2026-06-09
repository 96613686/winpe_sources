# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::GetCachedFeatureEnabledState(void)

- ea: `0x1800252e8`
- end: `0x180025421`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Eaphost_TVS_Fixes@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028c90`
- `0x18002afc4`

## callees

- `0x18000a7a0`
- `0x18000b408`
- `0x18000d640`
- `0x1800252e8`
- `0x180025568`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800253a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800253a6`

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
      AcquireSRWLockExclusive(&stru_18004D520);
      v16 = &stru_18004D520;
      if ( !v5
        || v5 != dword_18004D534
        || (v14[0] = 3,
            v14[1] = Feature_Eaphost_TVS_Fixes__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18004D558, v14, 0x10u)) )
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
0x1800252e8  mov     [rsp+arg_10], rbx
0x1800252ed  mov     [rsp+arg_18], rbp
0x1800252f2  mov     [rsp+arg_0], rcx
0x1800252f7  push    rsi
0x1800252f8  push    rdi
0x1800252f9  push    r14
0x1800252fb  sub     rsp, 30h
0x1800252ff  mov     rsi, cs:Feature_Eaphost_TVS_Fixes__descriptor
0x180025306  mov     rdi, rdx
0x180025309  mov     qword ptr [rdx], 0
0x180025310  mov     eax, [rsi]
0x180025312  mov     [rdx], eax
0x180025314  and     eax, 6
0x180025317  cmp     al, 6
0x180025319  jz      loc_18002540B
0x18002531f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180025324  lea     r8, [rsp+48h+arg_0]
0x180025329  mov     dword ptr [rsp+48h+arg_0], 0
0x180025331  lea     rdx, [rsp+48h+arg_8]
0x180025336  mov     ebp, eax
0x180025338  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Eaphost_TVS_Fixes@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::GetCurrentFeatureEnabledState(int *)
0x18002533d  mov     eax, [rdi]
0x18002533f  mov     rbx, [rsp+48h+arg_8]
0x180025344  cmp     dword ptr [rsp+48h+arg_0], 0
0x180025349  mov     edx, eax
0x18002534b  mov     [rdi], eax
0x18002534d  mov     ecx, eax
0x18002534f  jz      short loc_18002536A
0x180025351  test    dl, 2
0x180025354  jnz     short loc_18002536A
0x180025356  and     ecx, 0FFFFF63Eh
0x18002535c  mov     eax, ebx
0x18002535e  and     eax, 9C1h
0x180025363  or      ecx, eax
0x180025365  or      ecx, 2
0x180025368  mov     [rdi], ecx
0x18002536a  mov     r8d, edx
0x18002536d  and     r8d, 4
0x180025371  jnz     short loc_180025385
0x180025373  btr     ecx, 0Ah
0x180025377  mov     eax, ebx
0x180025379  and     eax, 400h
0x18002537e  or      ecx, eax
0x180025380  or      ecx, 4
0x180025383  mov     [rdi], ecx
0x180025385  mov     eax, edx
0x180025387  lock cmpxchg [rsi], ecx
0x18002538b  jnz     short loc_180025344
0x18002538d  test    r8d, r8d
0x180025390  jnz     short loc_1800253F6
0x180025392  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180025398  test    eax, eax
0x18002539a  jz      short loc_1800253F6
0x18002539c  lea     r14, stru_18004D520
0x1800253a3  mov     rcx, r14; SRWLock
0x1800253a6  call    cs:__imp_AcquireSRWLockExclusive
0x1800253ac  mov     eax, cs:dword_18004D534
0x1800253b2  mov     [rsp+48h+arg_8], r14
0x1800253b7  test    ebp, ebp
0x1800253b9  jz      short loc_1800253E8
0x1800253bb  cmp     ebp, eax
0x1800253bd  jnz     short loc_1800253E8
0x1800253bf  mov     r8d, 10h; unsigned __int64
0x1800253c5  mov     [rsp+48h+var_28], 3
0x1800253ce  lea     rdx, [rsp+48h+var_28]; void *
0x1800253d3  mov     [rsp+48h+var_20], rsi
0x1800253d8  lea     rcx, qword_18004D558; this
0x1800253df  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800253e4  test    al, al
0x1800253e6  jnz     short loc_1800253EC
0x1800253e8  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800253ec  lea     rcx, [rsp+48h+arg_8]
0x1800253f1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800253f6  mov     eax, [rdi]
0x1800253f8  test    al, 2
0x1800253fa  jnz     short loc_18002540B
0x1800253fc  and     eax, 0FFFFF63Eh
0x180025401  and     ebx, 9C1h
0x180025407  or      eax, ebx
0x180025409  mov     [rdi], eax
0x18002540b  mov     rbx, [rsp+48h+arg_10]
0x180025410  mov     rax, rdi
0x180025413  mov     rbp, [rsp+48h+arg_18]
0x180025418  add     rsp, 30h
0x18002541c  pop     r14
0x18002541e  pop     rdi
0x18002541f  pop     rsi
0x180025420  retn
```
