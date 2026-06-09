# wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::GetCachedFeatureEnabledState(void)

- ea: `0x1800115c8`
- end: `0x180011701`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NegoLateFallback@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800138f0`
- `0x180015150`

## callees

- `0x18000df10`
- `0x1800110e8`
- `0x1800115c8`
- `0x1800118c4`
- `0x18001527c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011686`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011686`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_NegoLateFallback__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_NegoLateFallback__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_NegoLateFallback__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002731C
        || (v14[0] = 3,
            v14[1] = Feature_NegoLateFallback__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180027340, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_NegoLateFallback__descriptor, 0xFFFFFFFB);
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
0x1800115c8  mov     [rsp+arg_10], rbx
0x1800115cd  mov     [rsp+arg_18], rbp
0x1800115d2  mov     [rsp+arg_0], rcx
0x1800115d7  push    rsi
0x1800115d8  push    rdi
0x1800115d9  push    r14
0x1800115db  sub     rsp, 30h
0x1800115df  mov     rsi, cs:Feature_NegoLateFallback__descriptor
0x1800115e6  mov     rdi, rdx
0x1800115e9  mov     qword ptr [rdx], 0
0x1800115f0  mov     eax, [rsi]
0x1800115f2  mov     [rdx], eax
0x1800115f4  and     eax, 6
0x1800115f7  cmp     al, 6
0x1800115f9  jz      loc_1800116EB
0x1800115ff  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180011604  lea     r8, [rsp+48h+arg_0]
0x180011609  mov     dword ptr [rsp+48h+arg_0], 0
0x180011611  lea     rdx, [rsp+48h+arg_8]
0x180011616  mov     ebp, eax
0x180011618  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NegoLateFallback@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::GetCurrentFeatureEnabledState(int *)
0x18001161d  mov     eax, [rdi]
0x18001161f  mov     rbx, [rsp+48h+arg_8]
0x180011624  cmp     dword ptr [rsp+48h+arg_0], 0
0x180011629  mov     edx, eax
0x18001162b  mov     [rdi], eax
0x18001162d  mov     ecx, eax
0x18001162f  jz      short loc_18001164A
0x180011631  test    dl, 2
0x180011634  jnz     short loc_18001164A
0x180011636  and     ecx, 0FFFFF63Eh
0x18001163c  mov     eax, ebx
0x18001163e  and     eax, 9C1h
0x180011643  or      ecx, eax
0x180011645  or      ecx, 2
0x180011648  mov     [rdi], ecx
0x18001164a  mov     r8d, edx
0x18001164d  and     r8d, 4
0x180011651  jnz     short loc_180011665
0x180011653  btr     ecx, 0Ah
0x180011657  mov     eax, ebx
0x180011659  and     eax, 400h
0x18001165e  or      ecx, eax
0x180011660  or      ecx, 4
0x180011663  mov     [rdi], ecx
0x180011665  mov     eax, edx
0x180011667  lock cmpxchg [rsi], ecx
0x18001166b  jnz     short loc_180011624
0x18001166d  test    r8d, r8d
0x180011670  jnz     short loc_1800116D6
0x180011672  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180011678  test    eax, eax
0x18001167a  jz      short loc_1800116D6
0x18001167c  lea     r14, SRWLock
0x180011683  mov     rcx, r14; SRWLock
0x180011686  call    cs:__imp_AcquireSRWLockExclusive
0x18001168c  mov     eax, cs:dword_18002731C
0x180011692  mov     [rsp+48h+arg_8], r14
0x180011697  test    ebp, ebp
0x180011699  jz      short loc_1800116C8
0x18001169b  cmp     ebp, eax
0x18001169d  jnz     short loc_1800116C8
0x18001169f  mov     r8d, 10h; unsigned __int64
0x1800116a5  mov     [rsp+48h+var_28], 3
0x1800116ae  lea     rdx, [rsp+48h+var_28]; void *
0x1800116b3  mov     [rsp+48h+var_20], rsi
0x1800116b8  lea     rcx, qword_180027340; this
0x1800116bf  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800116c4  test    al, al
0x1800116c6  jnz     short loc_1800116CC
0x1800116c8  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800116cc  lea     rcx, [rsp+48h+arg_8]
0x1800116d1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800116d6  mov     eax, [rdi]
0x1800116d8  test    al, 2
0x1800116da  jnz     short loc_1800116EB
0x1800116dc  and     eax, 0FFFFF63Eh
0x1800116e1  and     ebx, 9C1h
0x1800116e7  or      eax, ebx
0x1800116e9  mov     [rdi], eax
0x1800116eb  mov     rbx, [rsp+48h+arg_10]
0x1800116f0  mov     rax, rdi
0x1800116f3  mov     rbp, [rsp+48h+arg_18]
0x1800116f8  add     rsp, 30h
0x1800116fc  pop     r14
0x1800116fe  pop     rdi
0x1800116ff  pop     rsi
0x180011700  retn
```
