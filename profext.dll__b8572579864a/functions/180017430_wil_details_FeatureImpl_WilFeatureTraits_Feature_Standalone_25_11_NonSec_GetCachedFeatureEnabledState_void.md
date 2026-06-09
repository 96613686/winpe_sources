# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180017430`
- end: `0x180017570`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018508`

## callees

- `0x180013750`
- `0x180016c90`
- `0x180017430`
- `0x180018238`
- `0x18001c040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800174ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800174ee`

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
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800316D4
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_11_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180031708, v14, 0x10u)) )
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
0x180017430  mov     [rsp+arg_10], rbx
0x180017435  mov     [rsp+arg_18], rbp
0x18001743a  mov     [rsp+arg_0], rcx
0x18001743f  push    rsi
0x180017440  push    rdi
0x180017441  push    r14
0x180017443  sub     rsp, 30h
0x180017447  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18001744e  mov     rdi, rdx
0x180017451  mov     qword ptr [rdx], 0
0x180017458  mov     eax, [rsi]
0x18001745a  mov     [rdx], eax
0x18001745c  and     eax, 6
0x18001745f  cmp     al, 6
0x180017461  jz      loc_180017559
0x180017467  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001746c  lea     r8, [rsp+48h+arg_0]
0x180017471  mov     dword ptr [rsp+48h+arg_0], 0
0x180017479  lea     rdx, [rsp+48h+arg_8]
0x18001747e  mov     ebp, eax
0x180017480  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180017485  mov     eax, [rdi]
0x180017487  mov     rbx, [rsp+48h+arg_8]
0x18001748c  cmp     dword ptr [rsp+48h+arg_0], 0
0x180017491  mov     edx, eax
0x180017493  mov     [rdi], eax
0x180017495  mov     ecx, eax
0x180017497  jz      short loc_1800174B2
0x180017499  test    dl, 2
0x18001749c  jnz     short loc_1800174B2
0x18001749e  and     ecx, 0FFFFF63Eh
0x1800174a4  mov     eax, ebx
0x1800174a6  and     eax, 9C1h
0x1800174ab  or      ecx, eax
0x1800174ad  or      ecx, 2
0x1800174b0  mov     [rdi], ecx
0x1800174b2  mov     r8d, edx
0x1800174b5  and     r8d, 4
0x1800174b9  jnz     short loc_1800174CD
0x1800174bb  btr     ecx, 0Ah
0x1800174bf  mov     eax, ebx
0x1800174c1  and     eax, 400h
0x1800174c6  or      ecx, eax
0x1800174c8  or      ecx, 4
0x1800174cb  mov     [rdi], ecx
0x1800174cd  mov     eax, edx
0x1800174cf  lock cmpxchg [rsi], ecx
0x1800174d3  jnz     short loc_18001748C
0x1800174d5  test    r8d, r8d
0x1800174d8  jnz     short loc_180017544
0x1800174da  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800174e0  test    eax, eax
0x1800174e2  jz      short loc_180017544
0x1800174e4  lea     r14, SRWLock
0x1800174eb  mov     rcx, r14; SRWLock
0x1800174ee  call    cs:__imp_AcquireSRWLockExclusive
0x1800174f5  nop     dword ptr [rax+rax+00h]
0x1800174fa  mov     eax, cs:dword_1800316D4
0x180017500  mov     [rsp+48h+arg_8], r14
0x180017505  test    ebp, ebp
0x180017507  jz      short loc_180017536
0x180017509  cmp     ebp, eax
0x18001750b  jnz     short loc_180017536
0x18001750d  mov     r8d, 10h; unsigned __int64
0x180017513  mov     [rsp+48h+var_28], 3
0x18001751c  lea     rdx, [rsp+48h+var_28]; void *
0x180017521  mov     [rsp+48h+var_20], rsi
0x180017526  lea     rcx, qword_180031708; this
0x18001752d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180017532  test    al, al
0x180017534  jnz     short loc_18001753A
0x180017536  lock and dword ptr [rsi], 0FFFFFFFBh
0x18001753a  lea     rcx, [rsp+48h+arg_8]
0x18001753f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017544  mov     eax, [rdi]
0x180017546  test    al, 2
0x180017548  jnz     short loc_180017559
0x18001754a  and     eax, 0FFFFF63Eh
0x18001754f  and     ebx, 9C1h
0x180017555  or      eax, ebx
0x180017557  mov     [rdi], eax
0x180017559  mov     rbx, [rsp+48h+arg_10]
0x18001755e  mov     rax, rdi
0x180017561  mov     rbp, [rsp+48h+arg_18]
0x180017566  add     rsp, 30h
0x18001756a  pop     r14
0x18001756c  pop     rdi
0x18001756d  pop     rsi
0x18001756e  retn
```
