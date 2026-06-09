# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180018e8c`
- end: `0x180018fc5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b804`

## callees

- `0x18000d118`
- `0x180012908`
- `0x180015b28`
- `0x180018e8c`
- `0x180019820`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018f4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018f4a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_1800367E8);
      v16 = &stru_1800367E8;
      if ( !v5
        || v5 != dword_1800367FC
        || (v14[0] = 3,
            v14[1] = Feature_ValLabTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180036820, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ValLabTest__descriptor, 0xFFFFFFFB);
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
0x180018e8c  mov     [rsp+arg_10], rbx
0x180018e91  mov     [rsp+arg_18], rbp
0x180018e96  mov     [rsp+arg_0], rcx
0x180018e9b  push    rsi
0x180018e9c  push    rdi
0x180018e9d  push    r14
0x180018e9f  sub     rsp, 30h
0x180018ea3  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180018eaa  mov     rdi, rdx
0x180018ead  mov     qword ptr [rdx], 0
0x180018eb4  mov     eax, [rsi]
0x180018eb6  mov     [rdx], eax
0x180018eb8  and     eax, 6
0x180018ebb  cmp     al, 6
0x180018ebd  jz      loc_180018FAF
0x180018ec3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180018ec8  lea     r8, [rsp+48h+arg_0]
0x180018ecd  mov     dword ptr [rsp+48h+arg_0], 0
0x180018ed5  lea     rdx, [rsp+48h+arg_8]
0x180018eda  mov     ebp, eax
0x180018edc  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x180018ee1  mov     eax, [rdi]
0x180018ee3  mov     rbx, [rsp+48h+arg_8]
0x180018ee8  cmp     dword ptr [rsp+48h+arg_0], 0
0x180018eed  mov     edx, eax
0x180018eef  mov     [rdi], eax
0x180018ef1  mov     ecx, eax
0x180018ef3  jz      short loc_180018F0E
0x180018ef5  test    dl, 2
0x180018ef8  jnz     short loc_180018F0E
0x180018efa  and     ecx, 0FFFFF63Eh
0x180018f00  mov     eax, ebx
0x180018f02  and     eax, 9C1h
0x180018f07  or      ecx, eax
0x180018f09  or      ecx, 2
0x180018f0c  mov     [rdi], ecx
0x180018f0e  mov     r8d, edx
0x180018f11  and     r8d, 4
0x180018f15  jnz     short loc_180018F29
0x180018f17  btr     ecx, 0Ah
0x180018f1b  mov     eax, ebx
0x180018f1d  and     eax, 400h
0x180018f22  or      ecx, eax
0x180018f24  or      ecx, 4
0x180018f27  mov     [rdi], ecx
0x180018f29  mov     eax, edx
0x180018f2b  lock cmpxchg [rsi], ecx
0x180018f2f  jnz     short loc_180018EE8
0x180018f31  test    r8d, r8d
0x180018f34  jnz     short loc_180018F9A
0x180018f36  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180018f3c  test    eax, eax
0x180018f3e  jz      short loc_180018F9A
0x180018f40  lea     r14, stru_1800367E8
0x180018f47  mov     rcx, r14; SRWLock
0x180018f4a  call    cs:__imp_AcquireSRWLockExclusive
0x180018f50  mov     eax, cs:dword_1800367FC
0x180018f56  mov     [rsp+48h+arg_8], r14
0x180018f5b  test    ebp, ebp
0x180018f5d  jz      short loc_180018F8C
0x180018f5f  cmp     ebp, eax
0x180018f61  jnz     short loc_180018F8C
0x180018f63  mov     r8d, 10h; unsigned __int64
0x180018f69  mov     [rsp+48h+var_28], 3
0x180018f72  lea     rdx, [rsp+48h+var_28]; void *
0x180018f77  mov     [rsp+48h+var_20], rsi
0x180018f7c  lea     rcx, qword_180036820; this
0x180018f83  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180018f88  test    al, al
0x180018f8a  jnz     short loc_180018F90
0x180018f8c  lock and dword ptr [rsi], 0FFFFFFFBh
0x180018f90  lea     rcx, [rsp+48h+arg_8]
0x180018f95  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180018f9a  mov     eax, [rdi]
0x180018f9c  test    al, 2
0x180018f9e  jnz     short loc_180018FAF
0x180018fa0  and     eax, 0FFFFF63Eh
0x180018fa5  and     ebx, 9C1h
0x180018fab  or      eax, ebx
0x180018fad  mov     [rdi], eax
0x180018faf  mov     rbx, [rsp+48h+arg_10]
0x180018fb4  mov     rax, rdi
0x180018fb7  mov     rbp, [rsp+48h+arg_18]
0x180018fbc  add     rsp, 30h
0x180018fc0  pop     r14
0x180018fc2  pop     rdi
0x180018fc3  pop     rsi
0x180018fc4  retn
```
