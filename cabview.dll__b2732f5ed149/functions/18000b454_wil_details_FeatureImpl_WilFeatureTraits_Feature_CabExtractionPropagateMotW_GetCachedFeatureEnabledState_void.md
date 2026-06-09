# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CabExtractionPropagateMotW>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b454`
- end: `0x18000b5a8`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CabExtractionPropagateMotW@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `340`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c894`
- `0x18000d048`

## callees

- `0x180002620`
- `0x180003fd8`
- `0x180005510`
- `0x180009e8c`
- `0x18000b454`
- `0x18000b8a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b51c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b51c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CabExtractionPropagateMotW>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  int v11; // r8d
  RTL_SRWLOCK *v13; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v14[2]; // [rsp+28h] [rbp-40h] BYREF
  int v15; // [rsp+38h] [rbp-30h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_CabExtractionPropagateMotW__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CabExtractionPropagateMotW__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v15 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CabExtractionPropagateMotW>::GetCurrentFeatureEnabledState(
      v5,
      &v13,
      &v15);
    v6 = *(_DWORD *)a2;
    v7 = (__int16)v13;
    do
    {
      v8 = v15 == 0;
      v9 = v6;
      *(_DWORD *)a2 = v6;
      v10 = v6;
      if ( !v8 && (v6 & 2) == 0 )
      {
        v10 = v7 & 0x9C1 | v6 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v10;
      }
      v11 = v6 & 4;
      if ( (v6 & 4) == 0 )
      {
        v10 = v7 & 0x400 | v10 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v10;
      }
      v6 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_CabExtractionPropagateMotW__descriptor,
             v10,
             v6);
    }
    while ( v9 != v6 );
    if ( !v11 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_18001A190);
      v13 = &stru_18001A190;
      if ( !v4
        || v4 != dword_18001A1A4
        || (v14[0] = 3,
            v14[1] = Feature_CabExtractionPropagateMotW__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18001A1C8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_CabExtractionPropagateMotW__descriptor, 0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000b454  mov     [rsp+arg_0], rbx
0x18000b459  mov     [rsp+arg_10], rbp
0x18000b45e  push    rsi
0x18000b45f  push    rdi
0x18000b460  push    r14
0x18000b462  sub     rsp, 50h
0x18000b466  mov     rax, cs:__security_cookie
0x18000b46d  xor     rax, rsp
0x18000b470  mov     [rsp+68h+var_28], rax
0x18000b475  mov     rsi, cs:Feature_CabExtractionPropagateMotW__descriptor
0x18000b47c  mov     rdi, rdx
0x18000b47f  mov     qword ptr [rdx], 0
0x18000b486  mov     eax, [rsi]
0x18000b488  mov     [rdx], eax
0x18000b48a  and     eax, 6
0x18000b48d  cmp     al, 6
0x18000b48f  jz      loc_18000B583
0x18000b495  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000b49a  lea     r8, [rsp+68h+var_30]
0x18000b49f  mov     [rsp+68h+var_30], 0
0x18000b4a7  lea     rdx, [rsp+68h+var_48]
0x18000b4ac  mov     ebp, eax
0x18000b4ae  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CabExtractionPropagateMotW@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CabExtractionPropagateMotW>::GetCurrentFeatureEnabledState(int *)
0x18000b4b3  mov     eax, [rdi]
0x18000b4b5  mov     rbx, [rsp+68h+var_48]
0x18000b4ba  cmp     [rsp+68h+var_30], 0
0x18000b4bf  mov     edx, eax
0x18000b4c1  mov     [rdi], eax
0x18000b4c3  mov     ecx, eax
0x18000b4c5  jz      short loc_18000B4E0
0x18000b4c7  test    dl, 2
0x18000b4ca  jnz     short loc_18000B4E0
0x18000b4cc  and     ecx, 0FFFFF63Eh
0x18000b4d2  mov     eax, ebx
0x18000b4d4  and     eax, 9C1h
0x18000b4d9  or      ecx, eax
0x18000b4db  or      ecx, 2
0x18000b4de  mov     [rdi], ecx
0x18000b4e0  mov     r8d, edx
0x18000b4e3  and     r8d, 4
0x18000b4e7  jnz     short loc_18000B4FB
0x18000b4e9  btr     ecx, 0Ah
0x18000b4ed  mov     eax, ebx
0x18000b4ef  and     eax, 400h
0x18000b4f4  or      ecx, eax
0x18000b4f6  or      ecx, 4
0x18000b4f9  mov     [rdi], ecx
0x18000b4fb  mov     eax, edx
0x18000b4fd  lock cmpxchg [rsi], ecx
0x18000b501  jnz     short loc_18000B4BA
0x18000b503  test    r8d, r8d
0x18000b506  jnz     short loc_18000B56C
0x18000b508  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000b50e  test    eax, eax
0x18000b510  jz      short loc_18000B56C
0x18000b512  lea     r14, stru_18001A190
0x18000b519  mov     rcx, r14; SRWLock
0x18000b51c  call    cs:__imp_AcquireSRWLockExclusive
0x18000b522  mov     eax, cs:dword_18001A1A4
0x18000b528  mov     [rsp+68h+var_48], r14
0x18000b52d  test    ebp, ebp
0x18000b52f  jz      short loc_18000B55E
0x18000b531  cmp     ebp, eax
0x18000b533  jnz     short loc_18000B55E
0x18000b535  mov     r8d, 10h; unsigned __int64
0x18000b53b  mov     [rsp+68h+var_40], 3
0x18000b544  lea     rdx, [rsp+68h+var_40]; void *
0x18000b549  mov     [rsp+68h+var_38], rsi
0x18000b54e  lea     rcx, qword_18001A1C8; this
0x18000b555  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000b55a  test    al, al
0x18000b55c  jnz     short loc_18000B562
0x18000b55e  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000b562  lea     rcx, [rsp+68h+var_48]
0x18000b567  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b56c  mov     ecx, [rdi]
0x18000b56e  test    cl, 2
0x18000b571  jnz     short loc_18000B583
0x18000b573  and     ecx, 0FFFFF63Eh
0x18000b579  and     ebx, 9C1h
0x18000b57f  or      ecx, ebx
0x18000b581  mov     [rdi], ecx
0x18000b583  mov     rax, rdi
0x18000b586  mov     rcx, [rsp+68h+var_28]
0x18000b58b  xor     rcx, rsp; StackCookie
0x18000b58e  call    __security_check_cookie
0x18000b593  lea     r11, [rsp+68h+var_18]
0x18000b598  mov     rbx, [r11+20h]
0x18000b59c  mov     rbp, [r11+30h]
0x18000b5a0  mov     rsp, r11
0x18000b5a3  pop     r14
0x18000b5a5  pop     rdi
0x18000b5a6  pop     rsi
0x18000b5a7  retn
```
