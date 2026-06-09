# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180025428`
- end: `0x180025561`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028d1c`

## callees

- `0x18000a7a0`
- `0x18000b408`
- `0x18000d640`
- `0x180025428`
- `0x180025630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800254e6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800254e6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_18004D520);
      v16 = &stru_18004D520;
      if ( !v5
        || v5 != dword_18004D534
        || (v14[0] = 3,
            v14[1] = Feature_ValLabTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18004D558, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ValLabTest__descriptor, 0xFFFFFFFB);
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
0x180025428  mov     [rsp+arg_10], rbx
0x18002542d  mov     [rsp+arg_18], rbp
0x180025432  mov     [rsp+arg_0], rcx
0x180025437  push    rsi
0x180025438  push    rdi
0x180025439  push    r14
0x18002543b  sub     rsp, 30h
0x18002543f  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180025446  mov     rdi, rdx
0x180025449  mov     qword ptr [rdx], 0
0x180025450  mov     eax, [rsi]
0x180025452  mov     [rdx], eax
0x180025454  and     eax, 6
0x180025457  cmp     al, 6
0x180025459  jz      loc_18002554B
0x18002545f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180025464  lea     r8, [rsp+48h+arg_0]
0x180025469  mov     dword ptr [rsp+48h+arg_0], 0
0x180025471  lea     rdx, [rsp+48h+arg_8]
0x180025476  mov     ebp, eax
0x180025478  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x18002547d  mov     eax, [rdi]
0x18002547f  mov     rbx, [rsp+48h+arg_8]
0x180025484  cmp     dword ptr [rsp+48h+arg_0], 0
0x180025489  mov     edx, eax
0x18002548b  mov     [rdi], eax
0x18002548d  mov     ecx, eax
0x18002548f  jz      short loc_1800254AA
0x180025491  test    dl, 2
0x180025494  jnz     short loc_1800254AA
0x180025496  and     ecx, 0FFFFF63Eh
0x18002549c  mov     eax, ebx
0x18002549e  and     eax, 9C1h
0x1800254a3  or      ecx, eax
0x1800254a5  or      ecx, 2
0x1800254a8  mov     [rdi], ecx
0x1800254aa  mov     r8d, edx
0x1800254ad  and     r8d, 4
0x1800254b1  jnz     short loc_1800254C5
0x1800254b3  btr     ecx, 0Ah
0x1800254b7  mov     eax, ebx
0x1800254b9  and     eax, 400h
0x1800254be  or      ecx, eax
0x1800254c0  or      ecx, 4
0x1800254c3  mov     [rdi], ecx
0x1800254c5  mov     eax, edx
0x1800254c7  lock cmpxchg [rsi], ecx
0x1800254cb  jnz     short loc_180025484
0x1800254cd  test    r8d, r8d
0x1800254d0  jnz     short loc_180025536
0x1800254d2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800254d8  test    eax, eax
0x1800254da  jz      short loc_180025536
0x1800254dc  lea     r14, stru_18004D520
0x1800254e3  mov     rcx, r14; SRWLock
0x1800254e6  call    cs:__imp_AcquireSRWLockExclusive
0x1800254ec  mov     eax, cs:dword_18004D534
0x1800254f2  mov     [rsp+48h+arg_8], r14
0x1800254f7  test    ebp, ebp
0x1800254f9  jz      short loc_180025528
0x1800254fb  cmp     ebp, eax
0x1800254fd  jnz     short loc_180025528
0x1800254ff  mov     r8d, 10h; unsigned __int64
0x180025505  mov     [rsp+48h+var_28], 3
0x18002550e  lea     rdx, [rsp+48h+var_28]; void *
0x180025513  mov     [rsp+48h+var_20], rsi
0x180025518  lea     rcx, qword_18004D558; this
0x18002551f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180025524  test    al, al
0x180025526  jnz     short loc_18002552C
0x180025528  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002552c  lea     rcx, [rsp+48h+arg_8]
0x180025531  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180025536  mov     eax, [rdi]
0x180025538  test    al, 2
0x18002553a  jnz     short loc_18002554B
0x18002553c  and     eax, 0FFFFF63Eh
0x180025541  and     ebx, 9C1h
0x180025547  or      eax, ebx
0x180025549  mov     [rdi], eax
0x18002554b  mov     rbx, [rsp+48h+arg_10]
0x180025550  mov     rax, rdi
0x180025553  mov     rbp, [rsp+48h+arg_18]
0x180025558  add     rsp, 30h
0x18002555c  pop     r14
0x18002555e  pop     rdi
0x18002555f  pop     rsi
0x180025560  retn
```
