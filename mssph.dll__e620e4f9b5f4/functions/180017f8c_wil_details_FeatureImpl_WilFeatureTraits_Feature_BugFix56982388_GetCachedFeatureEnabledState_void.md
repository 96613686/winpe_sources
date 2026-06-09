# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix56982388>::GetCachedFeatureEnabledState(void)

- ea: `0x180017f8c`
- end: `0x1800180c5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix56982388@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b1b0`
- `0x18001c100`

## callees

- `0x18000d118`
- `0x180012908`
- `0x180015b28`
- `0x180017f8c`
- `0x180018fcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001804a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001804a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix56982388>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_BugFix56982388__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BugFix56982388__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix56982388>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_BugFix56982388__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_1800367E8);
      v16 = &stru_1800367E8;
      if ( !v5
        || v5 != dword_1800367FC
        || (v14[0] = 3,
            v14[1] = Feature_BugFix56982388__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180036820, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_BugFix56982388__descriptor, 0xFFFFFFFB);
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
0x180017f8c  mov     [rsp+arg_10], rbx
0x180017f91  mov     [rsp+arg_18], rbp
0x180017f96  mov     [rsp+arg_0], rcx
0x180017f9b  push    rsi
0x180017f9c  push    rdi
0x180017f9d  push    r14
0x180017f9f  sub     rsp, 30h
0x180017fa3  mov     rsi, cs:Feature_BugFix56982388__descriptor
0x180017faa  mov     rdi, rdx
0x180017fad  mov     qword ptr [rdx], 0
0x180017fb4  mov     eax, [rsi]
0x180017fb6  mov     [rdx], eax
0x180017fb8  and     eax, 6
0x180017fbb  cmp     al, 6
0x180017fbd  jz      loc_1800180AF
0x180017fc3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180017fc8  lea     r8, [rsp+48h+arg_0]
0x180017fcd  mov     dword ptr [rsp+48h+arg_0], 0
0x180017fd5  lea     rdx, [rsp+48h+arg_8]
0x180017fda  mov     ebp, eax
0x180017fdc  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix56982388@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix56982388>::GetCurrentFeatureEnabledState(int *)
0x180017fe1  mov     eax, [rdi]
0x180017fe3  mov     rbx, [rsp+48h+arg_8]
0x180017fe8  cmp     dword ptr [rsp+48h+arg_0], 0
0x180017fed  mov     edx, eax
0x180017fef  mov     [rdi], eax
0x180017ff1  mov     ecx, eax
0x180017ff3  jz      short loc_18001800E
0x180017ff5  test    dl, 2
0x180017ff8  jnz     short loc_18001800E
0x180017ffa  and     ecx, 0FFFFF63Eh
0x180018000  mov     eax, ebx
0x180018002  and     eax, 9C1h
0x180018007  or      ecx, eax
0x180018009  or      ecx, 2
0x18001800c  mov     [rdi], ecx
0x18001800e  mov     r8d, edx
0x180018011  and     r8d, 4
0x180018015  jnz     short loc_180018029
0x180018017  btr     ecx, 0Ah
0x18001801b  mov     eax, ebx
0x18001801d  and     eax, 400h
0x180018022  or      ecx, eax
0x180018024  or      ecx, 4
0x180018027  mov     [rdi], ecx
0x180018029  mov     eax, edx
0x18001802b  lock cmpxchg [rsi], ecx
0x18001802f  jnz     short loc_180017FE8
0x180018031  test    r8d, r8d
0x180018034  jnz     short loc_18001809A
0x180018036  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001803c  test    eax, eax
0x18001803e  jz      short loc_18001809A
0x180018040  lea     r14, stru_1800367E8
0x180018047  mov     rcx, r14; SRWLock
0x18001804a  call    cs:__imp_AcquireSRWLockExclusive
0x180018050  mov     eax, cs:dword_1800367FC
0x180018056  mov     [rsp+48h+arg_8], r14
0x18001805b  test    ebp, ebp
0x18001805d  jz      short loc_18001808C
0x18001805f  cmp     ebp, eax
0x180018061  jnz     short loc_18001808C
0x180018063  mov     r8d, 10h; unsigned __int64
0x180018069  mov     [rsp+48h+var_28], 3
0x180018072  lea     rdx, [rsp+48h+var_28]; void *
0x180018077  mov     [rsp+48h+var_20], rsi
0x18001807c  lea     rcx, qword_180036820; this
0x180018083  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180018088  test    al, al
0x18001808a  jnz     short loc_180018090
0x18001808c  lock and dword ptr [rsi], 0FFFFFFFBh
0x180018090  lea     rcx, [rsp+48h+arg_8]
0x180018095  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001809a  mov     eax, [rdi]
0x18001809c  test    al, 2
0x18001809e  jnz     short loc_1800180AF
0x1800180a0  and     eax, 0FFFFF63Eh
0x1800180a5  and     ebx, 9C1h
0x1800180ab  or      eax, ebx
0x1800180ad  mov     [rdi], eax
0x1800180af  mov     rbx, [rsp+48h+arg_10]
0x1800180b4  mov     rax, rdi
0x1800180b7  mov     rbp, [rsp+48h+arg_18]
0x1800180bc  add     rsp, 30h
0x1800180c0  pop     r14
0x1800180c2  pop     rdi
0x1800180c3  pop     rsi
0x1800180c4  retn
```
