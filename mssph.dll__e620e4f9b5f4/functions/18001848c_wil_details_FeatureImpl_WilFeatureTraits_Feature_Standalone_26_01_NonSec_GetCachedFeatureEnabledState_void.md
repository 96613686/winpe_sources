# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001848c`
- end: `0x1800185c5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b3d0`

## callees

- `0x18000d118`
- `0x180012908`
- `0x180015b28`
- `0x18001848c`
- `0x180019220`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001854a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001854a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_1800367E8);
      v16 = &stru_1800367E8;
      if ( !v5
        || v5 != dword_1800367FC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_26_01_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180036820, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, 0xFFFFFFFB);
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
0x18001848c  mov     [rsp+arg_10], rbx
0x180018491  mov     [rsp+arg_18], rbp
0x180018496  mov     [rsp+arg_0], rcx
0x18001849b  push    rsi
0x18001849c  push    rdi
0x18001849d  push    r14
0x18001849f  sub     rsp, 30h
0x1800184a3  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x1800184aa  mov     rdi, rdx
0x1800184ad  mov     qword ptr [rdx], 0
0x1800184b4  mov     eax, [rsi]
0x1800184b6  mov     [rdx], eax
0x1800184b8  and     eax, 6
0x1800184bb  cmp     al, 6
0x1800184bd  jz      loc_1800185AF
0x1800184c3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800184c8  lea     r8, [rsp+48h+arg_0]
0x1800184cd  mov     dword ptr [rsp+48h+arg_0], 0
0x1800184d5  lea     rdx, [rsp+48h+arg_8]
0x1800184da  mov     ebp, eax
0x1800184dc  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)
0x1800184e1  mov     eax, [rdi]
0x1800184e3  mov     rbx, [rsp+48h+arg_8]
0x1800184e8  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800184ed  mov     edx, eax
0x1800184ef  mov     [rdi], eax
0x1800184f1  mov     ecx, eax
0x1800184f3  jz      short loc_18001850E
0x1800184f5  test    dl, 2
0x1800184f8  jnz     short loc_18001850E
0x1800184fa  and     ecx, 0FFFFF63Eh
0x180018500  mov     eax, ebx
0x180018502  and     eax, 9C1h
0x180018507  or      ecx, eax
0x180018509  or      ecx, 2
0x18001850c  mov     [rdi], ecx
0x18001850e  mov     r8d, edx
0x180018511  and     r8d, 4
0x180018515  jnz     short loc_180018529
0x180018517  btr     ecx, 0Ah
0x18001851b  mov     eax, ebx
0x18001851d  and     eax, 400h
0x180018522  or      ecx, eax
0x180018524  or      ecx, 4
0x180018527  mov     [rdi], ecx
0x180018529  mov     eax, edx
0x18001852b  lock cmpxchg [rsi], ecx
0x18001852f  jnz     short loc_1800184E8
0x180018531  test    r8d, r8d
0x180018534  jnz     short loc_18001859A
0x180018536  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001853c  test    eax, eax
0x18001853e  jz      short loc_18001859A
0x180018540  lea     r14, stru_1800367E8
0x180018547  mov     rcx, r14; SRWLock
0x18001854a  call    cs:__imp_AcquireSRWLockExclusive
0x180018550  mov     eax, cs:dword_1800367FC
0x180018556  mov     [rsp+48h+arg_8], r14
0x18001855b  test    ebp, ebp
0x18001855d  jz      short loc_18001858C
0x18001855f  cmp     ebp, eax
0x180018561  jnz     short loc_18001858C
0x180018563  mov     r8d, 10h; unsigned __int64
0x180018569  mov     [rsp+48h+var_28], 3
0x180018572  lea     rdx, [rsp+48h+var_28]; void *
0x180018577  mov     [rsp+48h+var_20], rsi
0x18001857c  lea     rcx, qword_180036820; this
0x180018583  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180018588  test    al, al
0x18001858a  jnz     short loc_180018590
0x18001858c  lock and dword ptr [rsi], 0FFFFFFFBh
0x180018590  lea     rcx, [rsp+48h+arg_8]
0x180018595  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001859a  mov     eax, [rdi]
0x18001859c  test    al, 2
0x18001859e  jnz     short loc_1800185AF
0x1800185a0  and     eax, 0FFFFF63Eh
0x1800185a5  and     ebx, 9C1h
0x1800185ab  or      eax, ebx
0x1800185ad  mov     [rdi], eax
0x1800185af  mov     rbx, [rsp+48h+arg_10]
0x1800185b4  mov     rax, rdi
0x1800185b7  mov     rbp, [rsp+48h+arg_18]
0x1800185bc  add     rsp, 30h
0x1800185c0  pop     r14
0x1800185c2  pop     rdi
0x1800185c3  pop     rsi
0x1800185c4  retn
```
