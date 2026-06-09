# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18001d85c`
- end: `0x18001d995`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e034`

## callees

- `0x18000d118`
- `0x180012908`
- `0x180015b28`
- `0x18001d85c`
- `0x18001dc40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d91a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d91a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_1800367E8);
      v16 = &stru_1800367E8;
      if ( !v5
        || v5 != dword_1800367FC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_Future__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180036820, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_Future__descriptor, 0xFFFFFFFB);
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
0x18001d85c  mov     [rsp+arg_10], rbx
0x18001d861  mov     [rsp+arg_18], rbp
0x18001d866  mov     [rsp+arg_0], rcx
0x18001d86b  push    rsi
0x18001d86c  push    rdi
0x18001d86d  push    r14
0x18001d86f  sub     rsp, 30h
0x18001d873  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x18001d87a  mov     rdi, rdx
0x18001d87d  mov     qword ptr [rdx], 0
0x18001d884  mov     eax, [rsi]
0x18001d886  mov     [rdx], eax
0x18001d888  and     eax, 6
0x18001d88b  cmp     al, 6
0x18001d88d  jz      loc_18001D97F
0x18001d893  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d898  lea     r8, [rsp+48h+arg_0]
0x18001d89d  mov     dword ptr [rsp+48h+arg_0], 0
0x18001d8a5  lea     rdx, [rsp+48h+arg_8]
0x18001d8aa  mov     ebp, eax
0x18001d8ac  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCurrentFeatureEnabledState(int *)
0x18001d8b1  mov     eax, [rdi]
0x18001d8b3  mov     rbx, [rsp+48h+arg_8]
0x18001d8b8  cmp     dword ptr [rsp+48h+arg_0], 0
0x18001d8bd  mov     edx, eax
0x18001d8bf  mov     [rdi], eax
0x18001d8c1  mov     ecx, eax
0x18001d8c3  jz      short loc_18001D8DE
0x18001d8c5  test    dl, 2
0x18001d8c8  jnz     short loc_18001D8DE
0x18001d8ca  and     ecx, 0FFFFF63Eh
0x18001d8d0  mov     eax, ebx
0x18001d8d2  and     eax, 9C1h
0x18001d8d7  or      ecx, eax
0x18001d8d9  or      ecx, 2
0x18001d8dc  mov     [rdi], ecx
0x18001d8de  mov     r8d, edx
0x18001d8e1  and     r8d, 4
0x18001d8e5  jnz     short loc_18001D8F9
0x18001d8e7  btr     ecx, 0Ah
0x18001d8eb  mov     eax, ebx
0x18001d8ed  and     eax, 400h
0x18001d8f2  or      ecx, eax
0x18001d8f4  or      ecx, 4
0x18001d8f7  mov     [rdi], ecx
0x18001d8f9  mov     eax, edx
0x18001d8fb  lock cmpxchg [rsi], ecx
0x18001d8ff  jnz     short loc_18001D8B8
0x18001d901  test    r8d, r8d
0x18001d904  jnz     short loc_18001D96A
0x18001d906  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001d90c  test    eax, eax
0x18001d90e  jz      short loc_18001D96A
0x18001d910  lea     r14, stru_1800367E8
0x18001d917  mov     rcx, r14; SRWLock
0x18001d91a  call    cs:__imp_AcquireSRWLockExclusive
0x18001d920  mov     eax, cs:dword_1800367FC
0x18001d926  mov     [rsp+48h+arg_8], r14
0x18001d92b  test    ebp, ebp
0x18001d92d  jz      short loc_18001D95C
0x18001d92f  cmp     ebp, eax
0x18001d931  jnz     short loc_18001D95C
0x18001d933  mov     r8d, 10h; unsigned __int64
0x18001d939  mov     [rsp+48h+var_28], 3
0x18001d942  lea     rdx, [rsp+48h+var_28]; void *
0x18001d947  mov     [rsp+48h+var_20], rsi
0x18001d94c  lea     rcx, qword_180036820; this
0x18001d953  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001d958  test    al, al
0x18001d95a  jnz     short loc_18001D960
0x18001d95c  lock and dword ptr [rsi], 0FFFFFFFBh
0x18001d960  lea     rcx, [rsp+48h+arg_8]
0x18001d965  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d96a  mov     eax, [rdi]
0x18001d96c  test    al, 2
0x18001d96e  jnz     short loc_18001D97F
0x18001d970  and     eax, 0FFFFF63Eh
0x18001d975  and     ebx, 9C1h
0x18001d97b  or      eax, ebx
0x18001d97d  mov     [rdi], eax
0x18001d97f  mov     rbx, [rsp+48h+arg_10]
0x18001d984  mov     rax, rdi
0x18001d987  mov     rbp, [rsp+48h+arg_18]
0x18001d98c  add     rsp, 30h
0x18001d990  pop     r14
0x18001d992  pop     rdi
0x18001d993  pop     rsi
0x18001d994  retn
```
