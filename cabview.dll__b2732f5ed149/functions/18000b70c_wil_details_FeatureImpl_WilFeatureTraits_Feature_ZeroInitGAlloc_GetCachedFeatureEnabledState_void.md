# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ZeroInitGAlloc>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b70c`
- end: `0x18000b860`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ZeroInitGAlloc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `340`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c9d4`
- `0x18000d0c0`

## callees

- `0x180002620`
- `0x180003fd8`
- `0x180005510`
- `0x180009e8c`
- `0x18000b70c`
- `0x18000b9b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b7d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b7d4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ZeroInitGAlloc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ZeroInitGAlloc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ZeroInitGAlloc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v15 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ZeroInitGAlloc>::GetCurrentFeatureEnabledState(v5, &v13, &v15);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ZeroInitGAlloc__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( !v11 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_18001A190);
      v13 = &stru_18001A190;
      if ( !v4
        || v4 != dword_18001A1A4
        || (v14[0] = 3,
            v14[1] = Feature_ZeroInitGAlloc__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18001A1C8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ZeroInitGAlloc__descriptor, 0xFFFFFFFB);
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
0x18000b70c  mov     [rsp+arg_0], rbx
0x18000b711  mov     [rsp+arg_10], rbp
0x18000b716  push    rsi
0x18000b717  push    rdi
0x18000b718  push    r14
0x18000b71a  sub     rsp, 50h
0x18000b71e  mov     rax, cs:__security_cookie
0x18000b725  xor     rax, rsp
0x18000b728  mov     [rsp+68h+var_28], rax
0x18000b72d  mov     rsi, cs:Feature_ZeroInitGAlloc__descriptor
0x18000b734  mov     rdi, rdx
0x18000b737  mov     qword ptr [rdx], 0
0x18000b73e  mov     eax, [rsi]
0x18000b740  mov     [rdx], eax
0x18000b742  and     eax, 6
0x18000b745  cmp     al, 6
0x18000b747  jz      loc_18000B83B
0x18000b74d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000b752  lea     r8, [rsp+68h+var_30]
0x18000b757  mov     [rsp+68h+var_30], 0
0x18000b75f  lea     rdx, [rsp+68h+var_48]
0x18000b764  mov     ebp, eax
0x18000b766  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ZeroInitGAlloc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ZeroInitGAlloc>::GetCurrentFeatureEnabledState(int *)
0x18000b76b  mov     eax, [rdi]
0x18000b76d  mov     rbx, [rsp+68h+var_48]
0x18000b772  cmp     [rsp+68h+var_30], 0
0x18000b777  mov     edx, eax
0x18000b779  mov     [rdi], eax
0x18000b77b  mov     ecx, eax
0x18000b77d  jz      short loc_18000B798
0x18000b77f  test    dl, 2
0x18000b782  jnz     short loc_18000B798
0x18000b784  and     ecx, 0FFFFF63Eh
0x18000b78a  mov     eax, ebx
0x18000b78c  and     eax, 9C1h
0x18000b791  or      ecx, eax
0x18000b793  or      ecx, 2
0x18000b796  mov     [rdi], ecx
0x18000b798  mov     r8d, edx
0x18000b79b  and     r8d, 4
0x18000b79f  jnz     short loc_18000B7B3
0x18000b7a1  btr     ecx, 0Ah
0x18000b7a5  mov     eax, ebx
0x18000b7a7  and     eax, 400h
0x18000b7ac  or      ecx, eax
0x18000b7ae  or      ecx, 4
0x18000b7b1  mov     [rdi], ecx
0x18000b7b3  mov     eax, edx
0x18000b7b5  lock cmpxchg [rsi], ecx
0x18000b7b9  jnz     short loc_18000B772
0x18000b7bb  test    r8d, r8d
0x18000b7be  jnz     short loc_18000B824
0x18000b7c0  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000b7c6  test    eax, eax
0x18000b7c8  jz      short loc_18000B824
0x18000b7ca  lea     r14, stru_18001A190
0x18000b7d1  mov     rcx, r14; SRWLock
0x18000b7d4  call    cs:__imp_AcquireSRWLockExclusive
0x18000b7da  mov     eax, cs:dword_18001A1A4
0x18000b7e0  mov     [rsp+68h+var_48], r14
0x18000b7e5  test    ebp, ebp
0x18000b7e7  jz      short loc_18000B816
0x18000b7e9  cmp     ebp, eax
0x18000b7eb  jnz     short loc_18000B816
0x18000b7ed  mov     r8d, 10h; unsigned __int64
0x18000b7f3  mov     [rsp+68h+var_40], 3
0x18000b7fc  lea     rdx, [rsp+68h+var_40]; void *
0x18000b801  mov     [rsp+68h+var_38], rsi
0x18000b806  lea     rcx, qword_18001A1C8; this
0x18000b80d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000b812  test    al, al
0x18000b814  jnz     short loc_18000B81A
0x18000b816  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000b81a  lea     rcx, [rsp+68h+var_48]
0x18000b81f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b824  mov     ecx, [rdi]
0x18000b826  test    cl, 2
0x18000b829  jnz     short loc_18000B83B
0x18000b82b  and     ecx, 0FFFFF63Eh
0x18000b831  and     ebx, 9C1h
0x18000b837  or      ecx, ebx
0x18000b839  mov     [rdi], ecx
0x18000b83b  mov     rax, rdi
0x18000b83e  mov     rcx, [rsp+68h+var_28]
0x18000b843  xor     rcx, rsp; StackCookie
0x18000b846  call    __security_check_cookie
0x18000b84b  lea     r11, [rsp+68h+var_18]
0x18000b850  mov     rbx, [r11+20h]
0x18000b854  mov     rbp, [r11+30h]
0x18000b858  mov     rsp, r11
0x18000b85b  pop     r14
0x18000b85d  pop     rdi
0x18000b85e  pop     rsi
0x18000b85f  retn
```
