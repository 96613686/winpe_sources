# wil::details::FeatureImpl<__WilFeatureTraits_Feature_SMB2>::GetCachedFeatureEnabledState(void)

- ea: `0x180014ce8`
- end: `0x180014e3c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_SMB2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `340`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001596c`
- `0x1800162dc`

## callees

- `0x18000b5ec`
- `0x18000be40`
- `0x18000e6c0`
- `0x18001201c`
- `0x180014ce8`
- `0x180015068`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014db0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014db0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_SMB2>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_SMB2__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_SMB2__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v15 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SMB2>::GetCurrentFeatureEnabledState(v5, &v13, &v15);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_SMB2__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( !v11 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180032C98);
      v13 = &stru_180032C98;
      if ( !v4
        || v4 != dword_180032CAC
        || (v14[0] = 3,
            v14[1] = Feature_SMB2__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180032CD0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_SMB2__descriptor, 0xFFFFFFFB);
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
0x180014ce8  mov     [rsp+arg_0], rbx
0x180014ced  mov     [rsp+arg_10], rbp
0x180014cf2  push    rsi
0x180014cf3  push    rdi
0x180014cf4  push    r14
0x180014cf6  sub     rsp, 50h
0x180014cfa  mov     rax, cs:__security_cookie
0x180014d01  xor     rax, rsp
0x180014d04  mov     [rsp+68h+var_28], rax
0x180014d09  mov     rsi, cs:Feature_SMB2__descriptor
0x180014d10  mov     rdi, rdx
0x180014d13  mov     qword ptr [rdx], 0
0x180014d1a  mov     eax, [rsi]
0x180014d1c  mov     [rdx], eax
0x180014d1e  and     eax, 6
0x180014d21  cmp     al, 6
0x180014d23  jz      loc_180014E17
0x180014d29  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014d2e  lea     r8, [rsp+68h+var_30]
0x180014d33  mov     [rsp+68h+var_30], 0
0x180014d3b  lea     rdx, [rsp+68h+var_48]
0x180014d40  mov     ebp, eax
0x180014d42  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_SMB2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SMB2>::GetCurrentFeatureEnabledState(int *)
0x180014d47  mov     eax, [rdi]
0x180014d49  mov     rbx, [rsp+68h+var_48]
0x180014d4e  cmp     [rsp+68h+var_30], 0
0x180014d53  mov     edx, eax
0x180014d55  mov     [rdi], eax
0x180014d57  mov     ecx, eax
0x180014d59  jz      short loc_180014D74
0x180014d5b  test    dl, 2
0x180014d5e  jnz     short loc_180014D74
0x180014d60  and     ecx, 0FFFFF63Eh
0x180014d66  mov     eax, ebx
0x180014d68  and     eax, 9C1h
0x180014d6d  or      ecx, eax
0x180014d6f  or      ecx, 2
0x180014d72  mov     [rdi], ecx
0x180014d74  mov     r8d, edx
0x180014d77  and     r8d, 4
0x180014d7b  jnz     short loc_180014D8F
0x180014d7d  btr     ecx, 0Ah
0x180014d81  mov     eax, ebx
0x180014d83  and     eax, 400h
0x180014d88  or      ecx, eax
0x180014d8a  or      ecx, 4
0x180014d8d  mov     [rdi], ecx
0x180014d8f  mov     eax, edx
0x180014d91  lock cmpxchg [rsi], ecx
0x180014d95  jnz     short loc_180014D4E
0x180014d97  test    r8d, r8d
0x180014d9a  jnz     short loc_180014E00
0x180014d9c  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180014da2  test    eax, eax
0x180014da4  jz      short loc_180014E00
0x180014da6  lea     r14, stru_180032C98
0x180014dad  mov     rcx, r14; SRWLock
0x180014db0  call    cs:__imp_AcquireSRWLockExclusive
0x180014db6  mov     eax, cs:dword_180032CAC
0x180014dbc  mov     [rsp+68h+var_48], r14
0x180014dc1  test    ebp, ebp
0x180014dc3  jz      short loc_180014DF2
0x180014dc5  cmp     ebp, eax
0x180014dc7  jnz     short loc_180014DF2
0x180014dc9  mov     r8d, 10h; unsigned __int64
0x180014dcf  mov     [rsp+68h+var_40], 3
0x180014dd8  lea     rdx, [rsp+68h+var_40]; void *
0x180014ddd  mov     [rsp+68h+var_38], rsi
0x180014de2  lea     rcx, qword_180032CD0; this
0x180014de9  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180014dee  test    al, al
0x180014df0  jnz     short loc_180014DF6
0x180014df2  lock and dword ptr [rsi], 0FFFFFFFBh
0x180014df6  lea     rcx, [rsp+68h+var_48]
0x180014dfb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014e00  mov     ecx, [rdi]
0x180014e02  test    cl, 2
0x180014e05  jnz     short loc_180014E17
0x180014e07  and     ecx, 0FFFFF63Eh
0x180014e0d  and     ebx, 9C1h
0x180014e13  or      ecx, ebx
0x180014e15  mov     [rdi], ecx
0x180014e17  mov     rax, rdi
0x180014e1a  mov     rcx, [rsp+68h+var_28]
0x180014e1f  xor     rcx, rsp; StackCookie
0x180014e22  call    __security_check_cookie
0x180014e27  lea     r11, [rsp+68h+var_18]
0x180014e2c  mov     rbx, [r11+20h]
0x180014e30  mov     rbp, [r11+30h]
0x180014e34  mov     rsp, r11
0x180014e37  pop     r14
0x180014e39  pop     rdi
0x180014e3a  pop     rsi
0x180014e3b  retn
```
