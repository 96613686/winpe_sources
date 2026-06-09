# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180013c28`
- end: `0x180013d61`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001442c`

## callees

- `0x18000f11c`
- `0x180012c54`
- `0x180013c28`
- `0x180014520`
- `0x180015b2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013ce6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013ce6`

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
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800226CC
        || (v14[0] = 3,
            v14[1] = Feature_ValLabTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800226F0, v14, 0x10u)) )
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
0x180013c28  mov     [rsp+arg_10], rbx
0x180013c2d  mov     [rsp+arg_18], rbp
0x180013c32  mov     [rsp+arg_0], rcx
0x180013c37  push    rsi
0x180013c38  push    rdi
0x180013c39  push    r14
0x180013c3b  sub     rsp, 30h
0x180013c3f  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180013c46  mov     rdi, rdx
0x180013c49  mov     qword ptr [rdx], 0
0x180013c50  mov     eax, [rsi]
0x180013c52  mov     [rdx], eax
0x180013c54  and     eax, 6
0x180013c57  cmp     al, 6
0x180013c59  jz      loc_180013D4B
0x180013c5f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013c64  lea     r8, [rsp+48h+arg_0]
0x180013c69  mov     dword ptr [rsp+48h+arg_0], 0
0x180013c71  lea     rdx, [rsp+48h+arg_8]
0x180013c76  mov     ebp, eax
0x180013c78  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x180013c7d  mov     eax, [rdi]
0x180013c7f  mov     rbx, [rsp+48h+arg_8]
0x180013c84  cmp     dword ptr [rsp+48h+arg_0], 0
0x180013c89  mov     edx, eax
0x180013c8b  mov     [rdi], eax
0x180013c8d  mov     ecx, eax
0x180013c8f  jz      short loc_180013CAA
0x180013c91  test    dl, 2
0x180013c94  jnz     short loc_180013CAA
0x180013c96  and     ecx, 0FFFFF63Eh
0x180013c9c  mov     eax, ebx
0x180013c9e  and     eax, 9C1h
0x180013ca3  or      ecx, eax
0x180013ca5  or      ecx, 2
0x180013ca8  mov     [rdi], ecx
0x180013caa  mov     r8d, edx
0x180013cad  and     r8d, 4
0x180013cb1  jnz     short loc_180013CC5
0x180013cb3  btr     ecx, 0Ah
0x180013cb7  mov     eax, ebx
0x180013cb9  and     eax, 400h
0x180013cbe  or      ecx, eax
0x180013cc0  or      ecx, 4
0x180013cc3  mov     [rdi], ecx
0x180013cc5  mov     eax, edx
0x180013cc7  lock cmpxchg [rsi], ecx
0x180013ccb  jnz     short loc_180013C84
0x180013ccd  test    r8d, r8d
0x180013cd0  jnz     short loc_180013D36
0x180013cd2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013cd8  test    eax, eax
0x180013cda  jz      short loc_180013D36
0x180013cdc  lea     r14, SRWLock
0x180013ce3  mov     rcx, r14; SRWLock
0x180013ce6  call    cs:__imp_AcquireSRWLockExclusive
0x180013cec  mov     eax, cs:dword_1800226CC
0x180013cf2  mov     [rsp+48h+arg_8], r14
0x180013cf7  test    ebp, ebp
0x180013cf9  jz      short loc_180013D28
0x180013cfb  cmp     ebp, eax
0x180013cfd  jnz     short loc_180013D28
0x180013cff  mov     r8d, 10h; unsigned __int64
0x180013d05  mov     [rsp+48h+var_28], 3
0x180013d0e  lea     rdx, [rsp+48h+var_28]; void *
0x180013d13  mov     [rsp+48h+var_20], rsi
0x180013d18  lea     rcx, qword_1800226F0; this
0x180013d1f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180013d24  test    al, al
0x180013d26  jnz     short loc_180013D2C
0x180013d28  lock and dword ptr [rsi], 0FFFFFFFBh
0x180013d2c  lea     rcx, [rsp+48h+arg_8]
0x180013d31  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013d36  mov     eax, [rdi]
0x180013d38  test    al, 2
0x180013d3a  jnz     short loc_180013D4B
0x180013d3c  and     eax, 0FFFFF63Eh
0x180013d41  and     ebx, 9C1h
0x180013d47  or      eax, ebx
0x180013d49  mov     [rdi], eax
0x180013d4b  mov     rbx, [rsp+48h+arg_10]
0x180013d50  mov     rax, rdi
0x180013d53  mov     rbp, [rsp+48h+arg_18]
0x180013d58  add     rsp, 30h
0x180013d5c  pop     r14
0x180013d5e  pop     rdi
0x180013d5f  pop     rsi
0x180013d60  retn
```
