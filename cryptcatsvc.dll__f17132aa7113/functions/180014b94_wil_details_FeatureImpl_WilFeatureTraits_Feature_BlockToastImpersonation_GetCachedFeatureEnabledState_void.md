# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BlockToastImpersonation>::GetCachedFeatureEnabledState(void)

- ea: `0x180014b94`
- end: `0x180014ce1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BlockToastImpersonation@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `333`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800158c4`
- `0x1800162a0`

## callees

- `0x18000b5ec`
- `0x18000be40`
- `0x18000e6c0`
- `0x18001201c`
- `0x180014b94`
- `0x180014fa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014c5e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014c5e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BlockToastImpersonation>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // r14d
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  int v11; // r8d
  RTL_SRWLOCK *v13; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v14[2]; // [rsp+28h] [rbp-30h] BYREF
  int v15; // [rsp+38h] [rbp-20h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_BlockToastImpersonation__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BlockToastImpersonation__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v15 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_BlockToastImpersonation>::GetCurrentFeatureEnabledState(
      v5,
      &v13,
      &v15);
    if ( !v4 )
      v15 = 0;
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_BlockToastImpersonation__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( !v11 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180032C98);
      v13 = &stru_180032C98;
      if ( !v4
        || v4 != dword_180032CAC
        || (v14[0] = 0,
            v14[1] = Feature_BlockToastImpersonation__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180032CD0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_BlockToastImpersonation__descriptor, 0xFFFFF7C1);
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
0x180014b94  push    rbp
0x180014b96  push    rbx
0x180014b97  push    rsi
0x180014b98  push    rdi
0x180014b99  push    r14
0x180014b9b  push    r15
0x180014b9d  mov     rbp, rsp
0x180014ba0  sub     rsp, 58h
0x180014ba4  mov     rax, cs:__security_cookie
0x180014bab  xor     rax, rsp
0x180014bae  mov     [rbp+var_18], rax
0x180014bb2  mov     rsi, cs:Feature_BlockToastImpersonation__descriptor
0x180014bb9  mov     rdi, rdx
0x180014bbc  mov     qword ptr [rdx], 0
0x180014bc3  mov     eax, [rsi]
0x180014bc5  mov     [rdx], eax
0x180014bc7  and     eax, 6
0x180014bca  cmp     al, 6
0x180014bcc  jz      loc_180014CC5
0x180014bd2  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014bd7  lea     r8, [rbp+var_20]
0x180014bdb  mov     [rbp+var_20], 0
0x180014be2  lea     rdx, [rbp+var_38]
0x180014be6  mov     r14d, eax
0x180014be9  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BlockToastImpersonation@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BlockToastImpersonation>::GetCurrentFeatureEnabledState(int *)
0x180014bee  test    r14d, r14d
0x180014bf1  jnz     short loc_180014BF7
0x180014bf3  mov     [rbp+var_20], r14d
0x180014bf7  mov     eax, [rdi]
0x180014bf9  mov     rbx, [rbp+var_38]
0x180014bfd  cmp     [rbp+var_20], 0
0x180014c01  mov     edx, eax
0x180014c03  mov     [rdi], eax
0x180014c05  mov     ecx, eax
0x180014c07  jz      short loc_180014C22
0x180014c09  test    dl, 2
0x180014c0c  jnz     short loc_180014C22
0x180014c0e  and     ecx, 0FFFFF63Eh
0x180014c14  mov     eax, ebx
0x180014c16  and     eax, 9C1h
0x180014c1b  or      ecx, eax
0x180014c1d  or      ecx, 2
0x180014c20  mov     [rdi], ecx
0x180014c22  mov     r8d, edx
0x180014c25  and     r8d, 4
0x180014c29  jnz     short loc_180014C3D
0x180014c2b  btr     ecx, 0Ah
0x180014c2f  mov     eax, ebx
0x180014c31  and     eax, 400h
0x180014c36  or      ecx, eax
0x180014c38  or      ecx, 4
0x180014c3b  mov     [rdi], ecx
0x180014c3d  mov     eax, edx
0x180014c3f  lock cmpxchg [rsi], ecx
0x180014c43  jnz     short loc_180014BFD
0x180014c45  test    r8d, r8d
0x180014c48  jnz     short loc_180014CAE
0x180014c4a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180014c50  test    eax, eax
0x180014c52  jz      short loc_180014CAE
0x180014c54  lea     r15, stru_180032C98
0x180014c5b  mov     rcx, r15; SRWLock
0x180014c5e  call    cs:__imp_AcquireSRWLockExclusive
0x180014c64  mov     eax, cs:dword_180032CAC
0x180014c6a  mov     [rbp+var_38], r15
0x180014c6e  test    r14d, r14d
0x180014c71  jz      short loc_180014C9E
0x180014c73  cmp     r14d, eax
0x180014c76  jnz     short loc_180014C9E
0x180014c78  mov     r8d, 10h; unsigned __int64
0x180014c7e  mov     [rbp+var_30], 0
0x180014c86  lea     rdx, [rbp+var_30]; void *
0x180014c8a  mov     [rbp+var_28], rsi
0x180014c8e  lea     rcx, qword_180032CD0; this
0x180014c95  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180014c9a  test    al, al
0x180014c9c  jnz     short loc_180014CA5
0x180014c9e  lock and dword ptr [rsi], 0FFFFF7C1h
0x180014ca5  lea     rcx, [rbp+var_38]
0x180014ca9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014cae  mov     ecx, [rdi]
0x180014cb0  test    cl, 2
0x180014cb3  jnz     short loc_180014CC5
0x180014cb5  and     ecx, 0FFFFF63Eh
0x180014cbb  and     ebx, 9C1h
0x180014cc1  or      ecx, ebx
0x180014cc3  mov     [rdi], ecx
0x180014cc5  mov     rax, rdi
0x180014cc8  mov     rcx, [rbp+var_18]
0x180014ccc  xor     rcx, rsp; StackCookie
0x180014ccf  call    __security_check_cookie
0x180014cd4  add     rsp, 58h
0x180014cd8  pop     r15
0x180014cda  pop     r14
0x180014cdc  pop     rdi
0x180014cdd  pop     rsi
0x180014cde  pop     rbx
0x180014cdf  pop     rbp
0x180014ce0  retn
```
