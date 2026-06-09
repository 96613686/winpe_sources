# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024>::GetCachedFeatureEnabledState(void)

- ea: `0x180023038`
- end: `0x180023171`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID45522024@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023680`
- `0x18002410c`

## callees

- `0x180007c28`
- `0x180008684`
- `0x18000c930`
- `0x180023038`
- `0x180023388`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800230f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800230f6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ID45522024__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID45522024__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID45522024__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180035B78);
      v16 = &stru_180035B78;
      if ( !v5
        || v5 != dword_180035B8C
        || (v14[0] = 3,
            v14[1] = Feature_ID45522024__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180035BB0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ID45522024__descriptor, 0xFFFFFFFB);
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
0x180023038  mov     [rsp+arg_10], rbx
0x18002303d  mov     [rsp+arg_18], rbp
0x180023042  mov     [rsp+arg_0], rcx
0x180023047  push    rsi
0x180023048  push    rdi
0x180023049  push    r14
0x18002304b  sub     rsp, 30h
0x18002304f  mov     rsi, cs:Feature_ID45522024__descriptor
0x180023056  mov     rdi, rdx
0x180023059  mov     qword ptr [rdx], 0
0x180023060  mov     eax, [rsi]
0x180023062  mov     [rdx], eax
0x180023064  and     eax, 6
0x180023067  cmp     al, 6
0x180023069  jz      loc_18002315B
0x18002306f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180023074  lea     r8, [rsp+48h+arg_0]
0x180023079  mov     dword ptr [rsp+48h+arg_0], 0
0x180023081  lea     rdx, [rsp+48h+arg_8]
0x180023086  mov     ebp, eax
0x180023088  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID45522024@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024>::GetCurrentFeatureEnabledState(int *)
0x18002308d  mov     eax, [rdi]
0x18002308f  mov     rbx, [rsp+48h+arg_8]
0x180023094  cmp     dword ptr [rsp+48h+arg_0], 0
0x180023099  mov     edx, eax
0x18002309b  mov     [rdi], eax
0x18002309d  mov     ecx, eax
0x18002309f  jz      short loc_1800230BA
0x1800230a1  test    dl, 2
0x1800230a4  jnz     short loc_1800230BA
0x1800230a6  and     ecx, 0FFFFF63Eh
0x1800230ac  mov     eax, ebx
0x1800230ae  and     eax, 9C1h
0x1800230b3  or      ecx, eax
0x1800230b5  or      ecx, 2
0x1800230b8  mov     [rdi], ecx
0x1800230ba  mov     r8d, edx
0x1800230bd  and     r8d, 4
0x1800230c1  jnz     short loc_1800230D5
0x1800230c3  btr     ecx, 0Ah
0x1800230c7  mov     eax, ebx
0x1800230c9  and     eax, 400h
0x1800230ce  or      ecx, eax
0x1800230d0  or      ecx, 4
0x1800230d3  mov     [rdi], ecx
0x1800230d5  mov     eax, edx
0x1800230d7  lock cmpxchg [rsi], ecx
0x1800230db  jnz     short loc_180023094
0x1800230dd  test    r8d, r8d
0x1800230e0  jnz     short loc_180023146
0x1800230e2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800230e8  test    eax, eax
0x1800230ea  jz      short loc_180023146
0x1800230ec  lea     r14, stru_180035B78
0x1800230f3  mov     rcx, r14; SRWLock
0x1800230f6  call    cs:__imp_AcquireSRWLockExclusive
0x1800230fc  mov     eax, cs:dword_180035B8C
0x180023102  mov     [rsp+48h+arg_8], r14
0x180023107  test    ebp, ebp
0x180023109  jz      short loc_180023138
0x18002310b  cmp     ebp, eax
0x18002310d  jnz     short loc_180023138
0x18002310f  mov     r8d, 10h; unsigned __int64
0x180023115  mov     [rsp+48h+var_28], 3
0x18002311e  lea     rdx, [rsp+48h+var_28]; void *
0x180023123  mov     [rsp+48h+var_20], rsi
0x180023128  lea     rcx, qword_180035BB0; this
0x18002312f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180023134  test    al, al
0x180023136  jnz     short loc_18002313C
0x180023138  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002313c  lea     rcx, [rsp+48h+arg_8]
0x180023141  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180023146  mov     eax, [rdi]
0x180023148  test    al, 2
0x18002314a  jnz     short loc_18002315B
0x18002314c  and     eax, 0FFFFF63Eh
0x180023151  and     ebx, 9C1h
0x180023157  or      eax, ebx
0x180023159  mov     [rdi], eax
0x18002315b  mov     rbx, [rsp+48h+arg_10]
0x180023160  mov     rax, rdi
0x180023163  mov     rbp, [rsp+48h+arg_18]
0x180023168  add     rsp, 30h
0x18002316c  pop     r14
0x18002316e  pop     rdi
0x18002316f  pop     rsi
0x180023170  retn
```
