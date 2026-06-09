# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_08_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180014e44`
- end: `0x180014f98`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_08_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015a10`

## callees

- `0x18000b5ec`
- `0x18000be40`
- `0x18000e6c0`
- `0x18001201c`
- `0x180014e44`
- `0x180015138`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014f0c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014f0c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_08_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_08_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_08_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v15 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_08_NonSec>::GetCurrentFeatureEnabledState(
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_08_NonSec__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( !v11 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180032C98);
      v13 = &stru_180032C98;
      if ( !v4
        || v4 != dword_180032CAC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_08_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180032CD0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_08_NonSec__descriptor, 0xFFFFFFFB);
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
0x180014e44  mov     [rsp+arg_0], rbx
0x180014e49  mov     [rsp+arg_10], rbp
0x180014e4e  push    rsi
0x180014e4f  push    rdi
0x180014e50  push    r14
0x180014e52  sub     rsp, 50h
0x180014e56  mov     rax, cs:__security_cookie
0x180014e5d  xor     rax, rsp
0x180014e60  mov     [rsp+68h+var_28], rax
0x180014e65  mov     rsi, cs:Feature_Standalone_25_08_NonSec__descriptor
0x180014e6c  mov     rdi, rdx
0x180014e6f  mov     qword ptr [rdx], 0
0x180014e76  mov     eax, [rsi]
0x180014e78  mov     [rdx], eax
0x180014e7a  and     eax, 6
0x180014e7d  cmp     al, 6
0x180014e7f  jz      loc_180014F73
0x180014e85  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014e8a  lea     r8, [rsp+68h+var_30]
0x180014e8f  mov     [rsp+68h+var_30], 0
0x180014e97  lea     rdx, [rsp+68h+var_48]
0x180014e9c  mov     ebp, eax
0x180014e9e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_08_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_08_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180014ea3  mov     eax, [rdi]
0x180014ea5  mov     rbx, [rsp+68h+var_48]
0x180014eaa  cmp     [rsp+68h+var_30], 0
0x180014eaf  mov     edx, eax
0x180014eb1  mov     [rdi], eax
0x180014eb3  mov     ecx, eax
0x180014eb5  jz      short loc_180014ED0
0x180014eb7  test    dl, 2
0x180014eba  jnz     short loc_180014ED0
0x180014ebc  and     ecx, 0FFFFF63Eh
0x180014ec2  mov     eax, ebx
0x180014ec4  and     eax, 9C1h
0x180014ec9  or      ecx, eax
0x180014ecb  or      ecx, 2
0x180014ece  mov     [rdi], ecx
0x180014ed0  mov     r8d, edx
0x180014ed3  and     r8d, 4
0x180014ed7  jnz     short loc_180014EEB
0x180014ed9  btr     ecx, 0Ah
0x180014edd  mov     eax, ebx
0x180014edf  and     eax, 400h
0x180014ee4  or      ecx, eax
0x180014ee6  or      ecx, 4
0x180014ee9  mov     [rdi], ecx
0x180014eeb  mov     eax, edx
0x180014eed  lock cmpxchg [rsi], ecx
0x180014ef1  jnz     short loc_180014EAA
0x180014ef3  test    r8d, r8d
0x180014ef6  jnz     short loc_180014F5C
0x180014ef8  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180014efe  test    eax, eax
0x180014f00  jz      short loc_180014F5C
0x180014f02  lea     r14, stru_180032C98
0x180014f09  mov     rcx, r14; SRWLock
0x180014f0c  call    cs:__imp_AcquireSRWLockExclusive
0x180014f12  mov     eax, cs:dword_180032CAC
0x180014f18  mov     [rsp+68h+var_48], r14
0x180014f1d  test    ebp, ebp
0x180014f1f  jz      short loc_180014F4E
0x180014f21  cmp     ebp, eax
0x180014f23  jnz     short loc_180014F4E
0x180014f25  mov     r8d, 10h; unsigned __int64
0x180014f2b  mov     [rsp+68h+var_40], 3
0x180014f34  lea     rdx, [rsp+68h+var_40]; void *
0x180014f39  mov     [rsp+68h+var_38], rsi
0x180014f3e  lea     rcx, qword_180032CD0; this
0x180014f45  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180014f4a  test    al, al
0x180014f4c  jnz     short loc_180014F52
0x180014f4e  lock and dword ptr [rsi], 0FFFFFFFBh
0x180014f52  lea     rcx, [rsp+68h+var_48]
0x180014f57  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014f5c  mov     ecx, [rdi]
0x180014f5e  test    cl, 2
0x180014f61  jnz     short loc_180014F73
0x180014f63  and     ecx, 0FFFFF63Eh
0x180014f69  and     ebx, 9C1h
0x180014f6f  or      ecx, ebx
0x180014f71  mov     [rdi], ecx
0x180014f73  mov     rax, rdi
0x180014f76  mov     rcx, [rsp+68h+var_28]
0x180014f7b  xor     rcx, rsp; StackCookie
0x180014f7e  call    __security_check_cookie
0x180014f83  lea     r11, [rsp+68h+var_18]
0x180014f88  mov     rbx, [r11+20h]
0x180014f8c  mov     rbp, [r11+30h]
0x180014f90  mov     rsp, r11
0x180014f93  pop     r14
0x180014f95  pop     rdi
0x180014f96  pop     rsi
0x180014f97  retn
```
