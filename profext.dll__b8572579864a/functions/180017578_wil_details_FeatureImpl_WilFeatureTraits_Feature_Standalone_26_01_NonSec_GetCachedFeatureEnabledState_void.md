# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180017578`
- end: `0x1800176b8`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800185f8`

## callees

- `0x180013750`
- `0x180016c90`
- `0x180017578`
- `0x1800182b0`
- `0x18001c040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017636`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017636`

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
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800316D4
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_26_01_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180031708, v14, 0x10u)) )
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
0x180017578  mov     [rsp+arg_10], rbx
0x18001757d  mov     [rsp+arg_18], rbp
0x180017582  mov     [rsp+arg_0], rcx
0x180017587  push    rsi
0x180017588  push    rdi
0x180017589  push    r14
0x18001758b  sub     rsp, 30h
0x18001758f  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180017596  mov     rdi, rdx
0x180017599  mov     qword ptr [rdx], 0
0x1800175a0  mov     eax, [rsi]
0x1800175a2  mov     [rdx], eax
0x1800175a4  and     eax, 6
0x1800175a7  cmp     al, 6
0x1800175a9  jz      loc_1800176A1
0x1800175af  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800175b4  lea     r8, [rsp+48h+arg_0]
0x1800175b9  mov     dword ptr [rsp+48h+arg_0], 0
0x1800175c1  lea     rdx, [rsp+48h+arg_8]
0x1800175c6  mov     ebp, eax
0x1800175c8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)
0x1800175cd  mov     eax, [rdi]
0x1800175cf  mov     rbx, [rsp+48h+arg_8]
0x1800175d4  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800175d9  mov     edx, eax
0x1800175db  mov     [rdi], eax
0x1800175dd  mov     ecx, eax
0x1800175df  jz      short loc_1800175FA
0x1800175e1  test    dl, 2
0x1800175e4  jnz     short loc_1800175FA
0x1800175e6  and     ecx, 0FFFFF63Eh
0x1800175ec  mov     eax, ebx
0x1800175ee  and     eax, 9C1h
0x1800175f3  or      ecx, eax
0x1800175f5  or      ecx, 2
0x1800175f8  mov     [rdi], ecx
0x1800175fa  mov     r8d, edx
0x1800175fd  and     r8d, 4
0x180017601  jnz     short loc_180017615
0x180017603  btr     ecx, 0Ah
0x180017607  mov     eax, ebx
0x180017609  and     eax, 400h
0x18001760e  or      ecx, eax
0x180017610  or      ecx, 4
0x180017613  mov     [rdi], ecx
0x180017615  mov     eax, edx
0x180017617  lock cmpxchg [rsi], ecx
0x18001761b  jnz     short loc_1800175D4
0x18001761d  test    r8d, r8d
0x180017620  jnz     short loc_18001768C
0x180017622  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180017628  test    eax, eax
0x18001762a  jz      short loc_18001768C
0x18001762c  lea     r14, SRWLock
0x180017633  mov     rcx, r14; SRWLock
0x180017636  call    cs:__imp_AcquireSRWLockExclusive
0x18001763d  nop     dword ptr [rax+rax+00h]
0x180017642  mov     eax, cs:dword_1800316D4
0x180017648  mov     [rsp+48h+arg_8], r14
0x18001764d  test    ebp, ebp
0x18001764f  jz      short loc_18001767E
0x180017651  cmp     ebp, eax
0x180017653  jnz     short loc_18001767E
0x180017655  mov     r8d, 10h; unsigned __int64
0x18001765b  mov     [rsp+48h+var_28], 3
0x180017664  lea     rdx, [rsp+48h+var_28]; void *
0x180017669  mov     [rsp+48h+var_20], rsi
0x18001766e  lea     rcx, qword_180031708; this
0x180017675  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001767a  test    al, al
0x18001767c  jnz     short loc_180017682
0x18001767e  lock and dword ptr [rsi], 0FFFFFFFBh
0x180017682  lea     rcx, [rsp+48h+arg_8]
0x180017687  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001768c  mov     eax, [rdi]
0x18001768e  test    al, 2
0x180017690  jnz     short loc_1800176A1
0x180017692  and     eax, 0FFFFF63Eh
0x180017697  and     ebx, 9C1h
0x18001769d  or      eax, ebx
0x18001769f  mov     [rdi], eax
0x1800176a1  mov     rbx, [rsp+48h+arg_10]
0x1800176a6  mov     rax, rdi
0x1800176a9  mov     rbp, [rsp+48h+arg_18]
0x1800176ae  add     rsp, 30h
0x1800176b2  pop     r14
0x1800176b4  pop     rdi
0x1800176b5  pop     rsi
0x1800176b6  retn
```
