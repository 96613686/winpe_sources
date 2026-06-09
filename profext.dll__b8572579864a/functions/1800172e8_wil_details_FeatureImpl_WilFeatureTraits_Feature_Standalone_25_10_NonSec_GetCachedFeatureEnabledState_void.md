# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800172e8`
- end: `0x180017428`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800187d8`

## callees

- `0x180013750`
- `0x180016c90`
- `0x1800172e8`
- `0x1800181c0`
- `0x18001c040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800173a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800173a6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800316D4
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_10_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180031708, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, 0xFFFFFFFB);
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
0x1800172e8  mov     [rsp+arg_10], rbx
0x1800172ed  mov     [rsp+arg_18], rbp
0x1800172f2  mov     [rsp+arg_0], rcx
0x1800172f7  push    rsi
0x1800172f8  push    rdi
0x1800172f9  push    r14
0x1800172fb  sub     rsp, 30h
0x1800172ff  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180017306  mov     rdi, rdx
0x180017309  mov     qword ptr [rdx], 0
0x180017310  mov     eax, [rsi]
0x180017312  mov     [rdx], eax
0x180017314  and     eax, 6
0x180017317  cmp     al, 6
0x180017319  jz      loc_180017411
0x18001731f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180017324  lea     r8, [rsp+48h+arg_0]
0x180017329  mov     dword ptr [rsp+48h+arg_0], 0
0x180017331  lea     rdx, [rsp+48h+arg_8]
0x180017336  mov     ebp, eax
0x180017338  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18001733d  mov     eax, [rdi]
0x18001733f  mov     rbx, [rsp+48h+arg_8]
0x180017344  cmp     dword ptr [rsp+48h+arg_0], 0
0x180017349  mov     edx, eax
0x18001734b  mov     [rdi], eax
0x18001734d  mov     ecx, eax
0x18001734f  jz      short loc_18001736A
0x180017351  test    dl, 2
0x180017354  jnz     short loc_18001736A
0x180017356  and     ecx, 0FFFFF63Eh
0x18001735c  mov     eax, ebx
0x18001735e  and     eax, 9C1h
0x180017363  or      ecx, eax
0x180017365  or      ecx, 2
0x180017368  mov     [rdi], ecx
0x18001736a  mov     r8d, edx
0x18001736d  and     r8d, 4
0x180017371  jnz     short loc_180017385
0x180017373  btr     ecx, 0Ah
0x180017377  mov     eax, ebx
0x180017379  and     eax, 400h
0x18001737e  or      ecx, eax
0x180017380  or      ecx, 4
0x180017383  mov     [rdi], ecx
0x180017385  mov     eax, edx
0x180017387  lock cmpxchg [rsi], ecx
0x18001738b  jnz     short loc_180017344
0x18001738d  test    r8d, r8d
0x180017390  jnz     short loc_1800173FC
0x180017392  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180017398  test    eax, eax
0x18001739a  jz      short loc_1800173FC
0x18001739c  lea     r14, SRWLock
0x1800173a3  mov     rcx, r14; SRWLock
0x1800173a6  call    cs:__imp_AcquireSRWLockExclusive
0x1800173ad  nop     dword ptr [rax+rax+00h]
0x1800173b2  mov     eax, cs:dword_1800316D4
0x1800173b8  mov     [rsp+48h+arg_8], r14
0x1800173bd  test    ebp, ebp
0x1800173bf  jz      short loc_1800173EE
0x1800173c1  cmp     ebp, eax
0x1800173c3  jnz     short loc_1800173EE
0x1800173c5  mov     r8d, 10h; unsigned __int64
0x1800173cb  mov     [rsp+48h+var_28], 3
0x1800173d4  lea     rdx, [rsp+48h+var_28]; void *
0x1800173d9  mov     [rsp+48h+var_20], rsi
0x1800173de  lea     rcx, qword_180031708; this
0x1800173e5  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800173ea  test    al, al
0x1800173ec  jnz     short loc_1800173F2
0x1800173ee  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800173f2  lea     rcx, [rsp+48h+arg_8]
0x1800173f7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800173fc  mov     eax, [rdi]
0x1800173fe  test    al, 2
0x180017400  jnz     short loc_180017411
0x180017402  and     eax, 0FFFFF63Eh
0x180017407  and     ebx, 9C1h
0x18001740d  or      eax, ebx
0x18001740f  mov     [rdi], eax
0x180017411  mov     rbx, [rsp+48h+arg_10]
0x180017416  mov     rax, rdi
0x180017419  mov     rbp, [rsp+48h+arg_18]
0x18001741e  add     rsp, 30h
0x180017422  pop     r14
0x180017424  pop     rdi
0x180017425  pop     rsi
0x180017426  retn
```
