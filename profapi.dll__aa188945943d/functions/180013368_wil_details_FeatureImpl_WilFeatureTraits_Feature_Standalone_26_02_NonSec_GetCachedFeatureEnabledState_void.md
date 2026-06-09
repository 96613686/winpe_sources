# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180013368`
- end: `0x1800134a1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001406c`

## callees

- `0x18000f11c`
- `0x180012c54`
- `0x180013368`
- `0x180013f84`
- `0x180015b2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013426`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013426`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800226CC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_26_02_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800226F0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, 0xFFFFFFFB);
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
0x180013368  mov     [rsp+arg_10], rbx
0x18001336d  mov     [rsp+arg_18], rbp
0x180013372  mov     [rsp+arg_0], rcx
0x180013377  push    rsi
0x180013378  push    rdi
0x180013379  push    r14
0x18001337b  sub     rsp, 30h
0x18001337f  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180013386  mov     rdi, rdx
0x180013389  mov     qword ptr [rdx], 0
0x180013390  mov     eax, [rsi]
0x180013392  mov     [rdx], eax
0x180013394  and     eax, 6
0x180013397  cmp     al, 6
0x180013399  jz      loc_18001348B
0x18001339f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800133a4  lea     r8, [rsp+48h+arg_0]
0x1800133a9  mov     dword ptr [rsp+48h+arg_0], 0
0x1800133b1  lea     rdx, [rsp+48h+arg_8]
0x1800133b6  mov     ebp, eax
0x1800133b8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(int *)
0x1800133bd  mov     eax, [rdi]
0x1800133bf  mov     rbx, [rsp+48h+arg_8]
0x1800133c4  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800133c9  mov     edx, eax
0x1800133cb  mov     [rdi], eax
0x1800133cd  mov     ecx, eax
0x1800133cf  jz      short loc_1800133EA
0x1800133d1  test    dl, 2
0x1800133d4  jnz     short loc_1800133EA
0x1800133d6  and     ecx, 0FFFFF63Eh
0x1800133dc  mov     eax, ebx
0x1800133de  and     eax, 9C1h
0x1800133e3  or      ecx, eax
0x1800133e5  or      ecx, 2
0x1800133e8  mov     [rdi], ecx
0x1800133ea  mov     r8d, edx
0x1800133ed  and     r8d, 4
0x1800133f1  jnz     short loc_180013405
0x1800133f3  btr     ecx, 0Ah
0x1800133f7  mov     eax, ebx
0x1800133f9  and     eax, 400h
0x1800133fe  or      ecx, eax
0x180013400  or      ecx, 4
0x180013403  mov     [rdi], ecx
0x180013405  mov     eax, edx
0x180013407  lock cmpxchg [rsi], ecx
0x18001340b  jnz     short loc_1800133C4
0x18001340d  test    r8d, r8d
0x180013410  jnz     short loc_180013476
0x180013412  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013418  test    eax, eax
0x18001341a  jz      short loc_180013476
0x18001341c  lea     r14, SRWLock
0x180013423  mov     rcx, r14; SRWLock
0x180013426  call    cs:__imp_AcquireSRWLockExclusive
0x18001342c  mov     eax, cs:dword_1800226CC
0x180013432  mov     [rsp+48h+arg_8], r14
0x180013437  test    ebp, ebp
0x180013439  jz      short loc_180013468
0x18001343b  cmp     ebp, eax
0x18001343d  jnz     short loc_180013468
0x18001343f  mov     r8d, 10h; unsigned __int64
0x180013445  mov     [rsp+48h+var_28], 3
0x18001344e  lea     rdx, [rsp+48h+var_28]; void *
0x180013453  mov     [rsp+48h+var_20], rsi
0x180013458  lea     rcx, qword_1800226F0; this
0x18001345f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180013464  test    al, al
0x180013466  jnz     short loc_18001346C
0x180013468  lock and dword ptr [rsi], 0FFFFFFFBh
0x18001346c  lea     rcx, [rsp+48h+arg_8]
0x180013471  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013476  mov     eax, [rdi]
0x180013478  test    al, 2
0x18001347a  jnz     short loc_18001348B
0x18001347c  and     eax, 0FFFFF63Eh
0x180013481  and     ebx, 9C1h
0x180013487  or      eax, ebx
0x180013489  mov     [rdi], eax
0x18001348b  mov     rbx, [rsp+48h+arg_10]
0x180013490  mov     rax, rdi
0x180013493  mov     rbp, [rsp+48h+arg_18]
0x180013498  add     rsp, 30h
0x18001349c  pop     r14
0x18001349e  pop     rdi
0x18001349f  pop     rsi
0x1800134a0  retn
```
