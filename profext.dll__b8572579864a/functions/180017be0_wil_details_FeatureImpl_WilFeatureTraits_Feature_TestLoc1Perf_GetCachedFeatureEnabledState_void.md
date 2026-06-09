# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x180017be0`
- end: `0x180017d20`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a534`
- `0x18001bab8`

## callees

- `0x180013750`
- `0x180016c90`
- `0x180017be0`
- `0x1800185f8`
- `0x18001c040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017c9e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017c9e`

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
        || v5 != dword_1800316D4
        || (v14[0] = 3,
            v14[1] = Feature_TestLoc1Perf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180031708, v14, 0x10u)) )
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
0x180017be0  mov     [rsp+arg_10], rbx
0x180017be5  mov     [rsp+arg_18], rbp
0x180017bea  mov     [rsp+arg_0], rcx
0x180017bef  push    rsi
0x180017bf0  push    rdi
0x180017bf1  push    r14
0x180017bf3  sub     rsp, 30h
0x180017bf7  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x180017bfe  mov     rdi, rdx
0x180017c01  mov     qword ptr [rdx], 0
0x180017c08  mov     eax, [rsi]
0x180017c0a  mov     [rdx], eax
0x180017c0c  and     eax, 6
0x180017c0f  cmp     al, 6
0x180017c11  jz      loc_180017D09
0x180017c17  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180017c1c  lea     r8, [rsp+48h+arg_0]
0x180017c21  mov     dword ptr [rsp+48h+arg_0], 0
0x180017c29  lea     rdx, [rsp+48h+arg_8]
0x180017c2e  mov     ebp, eax
0x180017c30  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x180017c35  mov     eax, [rdi]
0x180017c37  mov     rbx, [rsp+48h+arg_8]
0x180017c3c  cmp     dword ptr [rsp+48h+arg_0], 0
0x180017c41  mov     edx, eax
0x180017c43  mov     [rdi], eax
0x180017c45  mov     ecx, eax
0x180017c47  jz      short loc_180017C62
0x180017c49  test    dl, 2
0x180017c4c  jnz     short loc_180017C62
0x180017c4e  and     ecx, 0FFFFF63Eh
0x180017c54  mov     eax, ebx
0x180017c56  and     eax, 9C1h
0x180017c5b  or      ecx, eax
0x180017c5d  or      ecx, 2
0x180017c60  mov     [rdi], ecx
0x180017c62  mov     r8d, edx
0x180017c65  and     r8d, 4
0x180017c69  jnz     short loc_180017C7D
0x180017c6b  btr     ecx, 0Ah
0x180017c6f  mov     eax, ebx
0x180017c71  and     eax, 400h
0x180017c76  or      ecx, eax
0x180017c78  or      ecx, 4
0x180017c7b  mov     [rdi], ecx
0x180017c7d  mov     eax, edx
0x180017c7f  lock cmpxchg [rsi], ecx
0x180017c83  jnz     short loc_180017C3C
0x180017c85  test    r8d, r8d
0x180017c88  jnz     short loc_180017CF4
0x180017c8a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180017c90  test    eax, eax
0x180017c92  jz      short loc_180017CF4
0x180017c94  lea     r14, SRWLock
0x180017c9b  mov     rcx, r14; SRWLock
0x180017c9e  call    cs:__imp_AcquireSRWLockExclusive
0x180017ca5  nop     dword ptr [rax+rax+00h]
0x180017caa  mov     eax, cs:dword_1800316D4
0x180017cb0  mov     [rsp+48h+arg_8], r14
0x180017cb5  test    ebp, ebp
0x180017cb7  jz      short loc_180017CE6
0x180017cb9  cmp     ebp, eax
0x180017cbb  jnz     short loc_180017CE6
0x180017cbd  mov     r8d, 10h; unsigned __int64
0x180017cc3  mov     [rsp+48h+var_28], 3
0x180017ccc  lea     rdx, [rsp+48h+var_28]; void *
0x180017cd1  mov     [rsp+48h+var_20], rsi
0x180017cd6  lea     rcx, qword_180031708; this
0x180017cdd  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180017ce2  test    al, al
0x180017ce4  jnz     short loc_180017CEA
0x180017ce6  lock and dword ptr [rsi], 0FFFFFFFBh
0x180017cea  lea     rcx, [rsp+48h+arg_8]
0x180017cef  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017cf4  mov     eax, [rdi]
0x180017cf6  test    al, 2
0x180017cf8  jnz     short loc_180017D09
0x180017cfa  and     eax, 0FFFFF63Eh
0x180017cff  and     ebx, 9C1h
0x180017d05  or      eax, ebx
0x180017d07  mov     [rdi], eax
0x180017d09  mov     rbx, [rsp+48h+arg_10]
0x180017d0e  mov     rax, rdi
0x180017d11  mov     rbp, [rsp+48h+arg_18]
0x180017d16  add     rsp, 30h
0x180017d1a  pop     r14
0x180017d1c  pop     rdi
0x180017d1d  pop     rsi
0x180017d1e  retn
```
