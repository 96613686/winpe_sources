# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001834c`
- end: `0x180018485`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b34c`

## callees

- `0x18000d118`
- `0x180012908`
- `0x180015b28`
- `0x18001834c`
- `0x1800191a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001840a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001840a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_1800367E8);
      v16 = &stru_1800367E8;
      if ( !v5
        || v5 != dword_1800367FC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_11_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180036820, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, 0xFFFFFFFB);
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
0x18001834c  mov     [rsp+arg_10], rbx
0x180018351  mov     [rsp+arg_18], rbp
0x180018356  mov     [rsp+arg_0], rcx
0x18001835b  push    rsi
0x18001835c  push    rdi
0x18001835d  push    r14
0x18001835f  sub     rsp, 30h
0x180018363  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18001836a  mov     rdi, rdx
0x18001836d  mov     qword ptr [rdx], 0
0x180018374  mov     eax, [rsi]
0x180018376  mov     [rdx], eax
0x180018378  and     eax, 6
0x18001837b  cmp     al, 6
0x18001837d  jz      loc_18001846F
0x180018383  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180018388  lea     r8, [rsp+48h+arg_0]
0x18001838d  mov     dword ptr [rsp+48h+arg_0], 0
0x180018395  lea     rdx, [rsp+48h+arg_8]
0x18001839a  mov     ebp, eax
0x18001839c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)
0x1800183a1  mov     eax, [rdi]
0x1800183a3  mov     rbx, [rsp+48h+arg_8]
0x1800183a8  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800183ad  mov     edx, eax
0x1800183af  mov     [rdi], eax
0x1800183b1  mov     ecx, eax
0x1800183b3  jz      short loc_1800183CE
0x1800183b5  test    dl, 2
0x1800183b8  jnz     short loc_1800183CE
0x1800183ba  and     ecx, 0FFFFF63Eh
0x1800183c0  mov     eax, ebx
0x1800183c2  and     eax, 9C1h
0x1800183c7  or      ecx, eax
0x1800183c9  or      ecx, 2
0x1800183cc  mov     [rdi], ecx
0x1800183ce  mov     r8d, edx
0x1800183d1  and     r8d, 4
0x1800183d5  jnz     short loc_1800183E9
0x1800183d7  btr     ecx, 0Ah
0x1800183db  mov     eax, ebx
0x1800183dd  and     eax, 400h
0x1800183e2  or      ecx, eax
0x1800183e4  or      ecx, 4
0x1800183e7  mov     [rdi], ecx
0x1800183e9  mov     eax, edx
0x1800183eb  lock cmpxchg [rsi], ecx
0x1800183ef  jnz     short loc_1800183A8
0x1800183f1  test    r8d, r8d
0x1800183f4  jnz     short loc_18001845A
0x1800183f6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800183fc  test    eax, eax
0x1800183fe  jz      short loc_18001845A
0x180018400  lea     r14, stru_1800367E8
0x180018407  mov     rcx, r14; SRWLock
0x18001840a  call    cs:__imp_AcquireSRWLockExclusive
0x180018410  mov     eax, cs:dword_1800367FC
0x180018416  mov     [rsp+48h+arg_8], r14
0x18001841b  test    ebp, ebp
0x18001841d  jz      short loc_18001844C
0x18001841f  cmp     ebp, eax
0x180018421  jnz     short loc_18001844C
0x180018423  mov     r8d, 10h; unsigned __int64
0x180018429  mov     [rsp+48h+var_28], 3
0x180018432  lea     rdx, [rsp+48h+var_28]; void *
0x180018437  mov     [rsp+48h+var_20], rsi
0x18001843c  lea     rcx, qword_180036820; this
0x180018443  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180018448  test    al, al
0x18001844a  jnz     short loc_180018450
0x18001844c  lock and dword ptr [rsi], 0FFFFFFFBh
0x180018450  lea     rcx, [rsp+48h+arg_8]
0x180018455  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001845a  mov     eax, [rdi]
0x18001845c  test    al, 2
0x18001845e  jnz     short loc_18001846F
0x180018460  and     eax, 0FFFFF63Eh
0x180018465  and     ebx, 9C1h
0x18001846b  or      eax, ebx
0x18001846d  mov     [rdi], eax
0x18001846f  mov     rbx, [rsp+48h+arg_10]
0x180018474  mov     rax, rdi
0x180018477  mov     rbp, [rsp+48h+arg_18]
0x18001847c  add     rsp, 30h
0x180018480  pop     r14
0x180018482  pop     rdi
0x180018483  pop     rsi
0x180018484  retn
```
