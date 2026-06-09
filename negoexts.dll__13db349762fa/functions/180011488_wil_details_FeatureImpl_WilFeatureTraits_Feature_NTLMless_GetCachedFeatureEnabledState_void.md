# wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless>::GetCachedFeatureEnabledState(void)

- ea: `0x180011488`
- end: `0x1800115c1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013868`
- `0x180015114`

## callees

- `0x18000df10`
- `0x1800110e8`
- `0x180011488`
- `0x18001183c`
- `0x18001527c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011546`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011546`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_NTLMless__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_NTLMless__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_NTLMless__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002731C
        || (v14[0] = 3,
            v14[1] = Feature_NTLMless__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180027340, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_NTLMless__descriptor, 0xFFFFFFFB);
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
0x180011488  mov     [rsp+arg_10], rbx
0x18001148d  mov     [rsp+arg_18], rbp
0x180011492  mov     [rsp+arg_0], rcx
0x180011497  push    rsi
0x180011498  push    rdi
0x180011499  push    r14
0x18001149b  sub     rsp, 30h
0x18001149f  mov     rsi, cs:Feature_NTLMless__descriptor
0x1800114a6  mov     rdi, rdx
0x1800114a9  mov     qword ptr [rdx], 0
0x1800114b0  mov     eax, [rsi]
0x1800114b2  mov     [rdx], eax
0x1800114b4  and     eax, 6
0x1800114b7  cmp     al, 6
0x1800114b9  jz      loc_1800115AB
0x1800114bf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800114c4  lea     r8, [rsp+48h+arg_0]
0x1800114c9  mov     dword ptr [rsp+48h+arg_0], 0
0x1800114d1  lea     rdx, [rsp+48h+arg_8]
0x1800114d6  mov     ebp, eax
0x1800114d8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless>::GetCurrentFeatureEnabledState(int *)
0x1800114dd  mov     eax, [rdi]
0x1800114df  mov     rbx, [rsp+48h+arg_8]
0x1800114e4  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800114e9  mov     edx, eax
0x1800114eb  mov     [rdi], eax
0x1800114ed  mov     ecx, eax
0x1800114ef  jz      short loc_18001150A
0x1800114f1  test    dl, 2
0x1800114f4  jnz     short loc_18001150A
0x1800114f6  and     ecx, 0FFFFF63Eh
0x1800114fc  mov     eax, ebx
0x1800114fe  and     eax, 9C1h
0x180011503  or      ecx, eax
0x180011505  or      ecx, 2
0x180011508  mov     [rdi], ecx
0x18001150a  mov     r8d, edx
0x18001150d  and     r8d, 4
0x180011511  jnz     short loc_180011525
0x180011513  btr     ecx, 0Ah
0x180011517  mov     eax, ebx
0x180011519  and     eax, 400h
0x18001151e  or      ecx, eax
0x180011520  or      ecx, 4
0x180011523  mov     [rdi], ecx
0x180011525  mov     eax, edx
0x180011527  lock cmpxchg [rsi], ecx
0x18001152b  jnz     short loc_1800114E4
0x18001152d  test    r8d, r8d
0x180011530  jnz     short loc_180011596
0x180011532  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180011538  test    eax, eax
0x18001153a  jz      short loc_180011596
0x18001153c  lea     r14, SRWLock
0x180011543  mov     rcx, r14; SRWLock
0x180011546  call    cs:__imp_AcquireSRWLockExclusive
0x18001154c  mov     eax, cs:dword_18002731C
0x180011552  mov     [rsp+48h+arg_8], r14
0x180011557  test    ebp, ebp
0x180011559  jz      short loc_180011588
0x18001155b  cmp     ebp, eax
0x18001155d  jnz     short loc_180011588
0x18001155f  mov     r8d, 10h; unsigned __int64
0x180011565  mov     [rsp+48h+var_28], 3
0x18001156e  lea     rdx, [rsp+48h+var_28]; void *
0x180011573  mov     [rsp+48h+var_20], rsi
0x180011578  lea     rcx, qword_180027340; this
0x18001157f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180011584  test    al, al
0x180011586  jnz     short loc_18001158C
0x180011588  lock and dword ptr [rsi], 0FFFFFFFBh
0x18001158c  lea     rcx, [rsp+48h+arg_8]
0x180011591  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180011596  mov     eax, [rdi]
0x180011598  test    al, 2
0x18001159a  jnz     short loc_1800115AB
0x18001159c  and     eax, 0FFFFF63Eh
0x1800115a1  and     ebx, 9C1h
0x1800115a7  or      eax, ebx
0x1800115a9  mov     [rdi], eax
0x1800115ab  mov     rbx, [rsp+48h+arg_10]
0x1800115b0  mov     rax, rdi
0x1800115b3  mov     rbp, [rsp+48h+arg_18]
0x1800115b8  add     rsp, 30h
0x1800115bc  pop     r14
0x1800115be  pop     rdi
0x1800115bf  pop     rsi
0x1800115c0  retn
```
