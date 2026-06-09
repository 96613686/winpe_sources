# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180017fb8`
- end: `0x1800180f8`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
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
- `0x180017fb8`
- `0x1800188cc`
- `0x18001c040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018076`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018076`

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
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800316D4
        || (v14[0] = 3,
            v14[1] = Feature_ValLabTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180031708, v14, 0x10u)) )
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
0x180017fb8  mov     [rsp+arg_10], rbx
0x180017fbd  mov     [rsp+arg_18], rbp
0x180017fc2  mov     [rsp+arg_0], rcx
0x180017fc7  push    rsi
0x180017fc8  push    rdi
0x180017fc9  push    r14
0x180017fcb  sub     rsp, 30h
0x180017fcf  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180017fd6  mov     rdi, rdx
0x180017fd9  mov     qword ptr [rdx], 0
0x180017fe0  mov     eax, [rsi]
0x180017fe2  mov     [rdx], eax
0x180017fe4  and     eax, 6
0x180017fe7  cmp     al, 6
0x180017fe9  jz      loc_1800180E1
0x180017fef  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180017ff4  lea     r8, [rsp+48h+arg_0]
0x180017ff9  mov     dword ptr [rsp+48h+arg_0], 0
0x180018001  lea     rdx, [rsp+48h+arg_8]
0x180018006  mov     ebp, eax
0x180018008  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x18001800d  mov     eax, [rdi]
0x18001800f  mov     rbx, [rsp+48h+arg_8]
0x180018014  cmp     dword ptr [rsp+48h+arg_0], 0
0x180018019  mov     edx, eax
0x18001801b  mov     [rdi], eax
0x18001801d  mov     ecx, eax
0x18001801f  jz      short loc_18001803A
0x180018021  test    dl, 2
0x180018024  jnz     short loc_18001803A
0x180018026  and     ecx, 0FFFFF63Eh
0x18001802c  mov     eax, ebx
0x18001802e  and     eax, 9C1h
0x180018033  or      ecx, eax
0x180018035  or      ecx, 2
0x180018038  mov     [rdi], ecx
0x18001803a  mov     r8d, edx
0x18001803d  and     r8d, 4
0x180018041  jnz     short loc_180018055
0x180018043  btr     ecx, 0Ah
0x180018047  mov     eax, ebx
0x180018049  and     eax, 400h
0x18001804e  or      ecx, eax
0x180018050  or      ecx, 4
0x180018053  mov     [rdi], ecx
0x180018055  mov     eax, edx
0x180018057  lock cmpxchg [rsi], ecx
0x18001805b  jnz     short loc_180018014
0x18001805d  test    r8d, r8d
0x180018060  jnz     short loc_1800180CC
0x180018062  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180018068  test    eax, eax
0x18001806a  jz      short loc_1800180CC
0x18001806c  lea     r14, SRWLock
0x180018073  mov     rcx, r14; SRWLock
0x180018076  call    cs:__imp_AcquireSRWLockExclusive
0x18001807d  nop     dword ptr [rax+rax+00h]
0x180018082  mov     eax, cs:dword_1800316D4
0x180018088  mov     [rsp+48h+arg_8], r14
0x18001808d  test    ebp, ebp
0x18001808f  jz      short loc_1800180BE
0x180018091  cmp     ebp, eax
0x180018093  jnz     short loc_1800180BE
0x180018095  mov     r8d, 10h; unsigned __int64
0x18001809b  mov     [rsp+48h+var_28], 3
0x1800180a4  lea     rdx, [rsp+48h+var_28]; void *
0x1800180a9  mov     [rsp+48h+var_20], rsi
0x1800180ae  lea     rcx, qword_180031708; this
0x1800180b5  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800180ba  test    al, al
0x1800180bc  jnz     short loc_1800180C2
0x1800180be  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800180c2  lea     rcx, [rsp+48h+arg_8]
0x1800180c7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800180cc  mov     eax, [rdi]
0x1800180ce  test    al, 2
0x1800180d0  jnz     short loc_1800180E1
0x1800180d2  and     eax, 0FFFFF63Eh
0x1800180d7  and     ebx, 9C1h
0x1800180dd  or      eax, ebx
0x1800180df  mov     [rdi], eax
0x1800180e1  mov     rbx, [rsp+48h+arg_10]
0x1800180e6  mov     rax, rdi
0x1800180e9  mov     rbp, [rsp+48h+arg_18]
0x1800180ee  add     rsp, 30h
0x1800180f2  pop     r14
0x1800180f4  pop     rdi
0x1800180f5  pop     rsi
0x1800180f6  retn
```
