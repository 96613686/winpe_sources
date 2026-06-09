# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x1800139a8`
- end: `0x180013ae1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015090`
- `0x180015aa4`

## callees

- `0x18000f11c`
- `0x180012c54`
- `0x1800139a8`
- `0x18001433c`
- `0x180015b2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013a66`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013a66`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UexTest7__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UexTest7__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UexTest7__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800226CC
        || (v14[0] = 3,
            v14[1] = Feature_UexTest7__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800226F0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_UexTest7__descriptor, 0xFFFFFFFB);
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
0x1800139a8  mov     [rsp+arg_10], rbx
0x1800139ad  mov     [rsp+arg_18], rbp
0x1800139b2  mov     [rsp+arg_0], rcx
0x1800139b7  push    rsi
0x1800139b8  push    rdi
0x1800139b9  push    r14
0x1800139bb  sub     rsp, 30h
0x1800139bf  mov     rsi, cs:Feature_UexTest7__descriptor
0x1800139c6  mov     rdi, rdx
0x1800139c9  mov     qword ptr [rdx], 0
0x1800139d0  mov     eax, [rsi]
0x1800139d2  mov     [rdx], eax
0x1800139d4  and     eax, 6
0x1800139d7  cmp     al, 6
0x1800139d9  jz      loc_180013ACB
0x1800139df  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800139e4  lea     r8, [rsp+48h+arg_0]
0x1800139e9  mov     dword ptr [rsp+48h+arg_0], 0
0x1800139f1  lea     rdx, [rsp+48h+arg_8]
0x1800139f6  mov     ebp, eax
0x1800139f8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x1800139fd  mov     eax, [rdi]
0x1800139ff  mov     rbx, [rsp+48h+arg_8]
0x180013a04  cmp     dword ptr [rsp+48h+arg_0], 0
0x180013a09  mov     edx, eax
0x180013a0b  mov     [rdi], eax
0x180013a0d  mov     ecx, eax
0x180013a0f  jz      short loc_180013A2A
0x180013a11  test    dl, 2
0x180013a14  jnz     short loc_180013A2A
0x180013a16  and     ecx, 0FFFFF63Eh
0x180013a1c  mov     eax, ebx
0x180013a1e  and     eax, 9C1h
0x180013a23  or      ecx, eax
0x180013a25  or      ecx, 2
0x180013a28  mov     [rdi], ecx
0x180013a2a  mov     r8d, edx
0x180013a2d  and     r8d, 4
0x180013a31  jnz     short loc_180013A45
0x180013a33  btr     ecx, 0Ah
0x180013a37  mov     eax, ebx
0x180013a39  and     eax, 400h
0x180013a3e  or      ecx, eax
0x180013a40  or      ecx, 4
0x180013a43  mov     [rdi], ecx
0x180013a45  mov     eax, edx
0x180013a47  lock cmpxchg [rsi], ecx
0x180013a4b  jnz     short loc_180013A04
0x180013a4d  test    r8d, r8d
0x180013a50  jnz     short loc_180013AB6
0x180013a52  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013a58  test    eax, eax
0x180013a5a  jz      short loc_180013AB6
0x180013a5c  lea     r14, SRWLock
0x180013a63  mov     rcx, r14; SRWLock
0x180013a66  call    cs:__imp_AcquireSRWLockExclusive
0x180013a6c  mov     eax, cs:dword_1800226CC
0x180013a72  mov     [rsp+48h+arg_8], r14
0x180013a77  test    ebp, ebp
0x180013a79  jz      short loc_180013AA8
0x180013a7b  cmp     ebp, eax
0x180013a7d  jnz     short loc_180013AA8
0x180013a7f  mov     r8d, 10h; unsigned __int64
0x180013a85  mov     [rsp+48h+var_28], 3
0x180013a8e  lea     rdx, [rsp+48h+var_28]; void *
0x180013a93  mov     [rsp+48h+var_20], rsi
0x180013a98  lea     rcx, qword_1800226F0; this
0x180013a9f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180013aa4  test    al, al
0x180013aa6  jnz     short loc_180013AAC
0x180013aa8  lock and dword ptr [rsi], 0FFFFFFFBh
0x180013aac  lea     rcx, [rsp+48h+arg_8]
0x180013ab1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013ab6  mov     eax, [rdi]
0x180013ab8  test    al, 2
0x180013aba  jnz     short loc_180013ACB
0x180013abc  and     eax, 0FFFFF63Eh
0x180013ac1  and     ebx, 9C1h
0x180013ac7  or      eax, ebx
0x180013ac9  mov     [rdi], eax
0x180013acb  mov     rbx, [rsp+48h+arg_10]
0x180013ad0  mov     rax, rdi
0x180013ad3  mov     rbp, [rsp+48h+arg_18]
0x180013ad8  add     rsp, 30h
0x180013adc  pop     r14
0x180013ade  pop     rdi
0x180013adf  pop     rsi
0x180013ae0  retn
```
