# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::GetCachedFeatureEnabledState(void)

- ea: `0x1800180cc`
- end: `0x180018205`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_44936384@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b23c`
- `0x18001c13c`

## callees

- `0x18000d118`
- `0x180012908`
- `0x180015b28`
- `0x1800180cc`
- `0x18001905c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001818a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001818a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_BugFix_44936384__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BugFix_44936384__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_BugFix_44936384__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_1800367E8);
      v16 = &stru_1800367E8;
      if ( !v5
        || v5 != dword_1800367FC
        || (v14[0] = 3,
            v14[1] = Feature_BugFix_44936384__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180036820, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_BugFix_44936384__descriptor, 0xFFFFFFFB);
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
0x1800180cc  mov     [rsp+arg_10], rbx
0x1800180d1  mov     [rsp+arg_18], rbp
0x1800180d6  mov     [rsp+arg_0], rcx
0x1800180db  push    rsi
0x1800180dc  push    rdi
0x1800180dd  push    r14
0x1800180df  sub     rsp, 30h
0x1800180e3  mov     rsi, cs:Feature_BugFix_44936384__descriptor
0x1800180ea  mov     rdi, rdx
0x1800180ed  mov     qword ptr [rdx], 0
0x1800180f4  mov     eax, [rsi]
0x1800180f6  mov     [rdx], eax
0x1800180f8  and     eax, 6
0x1800180fb  cmp     al, 6
0x1800180fd  jz      loc_1800181EF
0x180018103  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180018108  lea     r8, [rsp+48h+arg_0]
0x18001810d  mov     dword ptr [rsp+48h+arg_0], 0
0x180018115  lea     rdx, [rsp+48h+arg_8]
0x18001811a  mov     ebp, eax
0x18001811c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_44936384@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::GetCurrentFeatureEnabledState(int *)
0x180018121  mov     eax, [rdi]
0x180018123  mov     rbx, [rsp+48h+arg_8]
0x180018128  cmp     dword ptr [rsp+48h+arg_0], 0
0x18001812d  mov     edx, eax
0x18001812f  mov     [rdi], eax
0x180018131  mov     ecx, eax
0x180018133  jz      short loc_18001814E
0x180018135  test    dl, 2
0x180018138  jnz     short loc_18001814E
0x18001813a  and     ecx, 0FFFFF63Eh
0x180018140  mov     eax, ebx
0x180018142  and     eax, 9C1h
0x180018147  or      ecx, eax
0x180018149  or      ecx, 2
0x18001814c  mov     [rdi], ecx
0x18001814e  mov     r8d, edx
0x180018151  and     r8d, 4
0x180018155  jnz     short loc_180018169
0x180018157  btr     ecx, 0Ah
0x18001815b  mov     eax, ebx
0x18001815d  and     eax, 400h
0x180018162  or      ecx, eax
0x180018164  or      ecx, 4
0x180018167  mov     [rdi], ecx
0x180018169  mov     eax, edx
0x18001816b  lock cmpxchg [rsi], ecx
0x18001816f  jnz     short loc_180018128
0x180018171  test    r8d, r8d
0x180018174  jnz     short loc_1800181DA
0x180018176  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001817c  test    eax, eax
0x18001817e  jz      short loc_1800181DA
0x180018180  lea     r14, stru_1800367E8
0x180018187  mov     rcx, r14; SRWLock
0x18001818a  call    cs:__imp_AcquireSRWLockExclusive
0x180018190  mov     eax, cs:dword_1800367FC
0x180018196  mov     [rsp+48h+arg_8], r14
0x18001819b  test    ebp, ebp
0x18001819d  jz      short loc_1800181CC
0x18001819f  cmp     ebp, eax
0x1800181a1  jnz     short loc_1800181CC
0x1800181a3  mov     r8d, 10h; unsigned __int64
0x1800181a9  mov     [rsp+48h+var_28], 3
0x1800181b2  lea     rdx, [rsp+48h+var_28]; void *
0x1800181b7  mov     [rsp+48h+var_20], rsi
0x1800181bc  lea     rcx, qword_180036820; this
0x1800181c3  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800181c8  test    al, al
0x1800181ca  jnz     short loc_1800181D0
0x1800181cc  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800181d0  lea     rcx, [rsp+48h+arg_8]
0x1800181d5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800181da  mov     eax, [rdi]
0x1800181dc  test    al, 2
0x1800181de  jnz     short loc_1800181EF
0x1800181e0  and     eax, 0FFFFF63Eh
0x1800181e5  and     ebx, 9C1h
0x1800181eb  or      eax, ebx
0x1800181ed  mov     [rdi], eax
0x1800181ef  mov     rbx, [rsp+48h+arg_10]
0x1800181f4  mov     rax, rdi
0x1800181f7  mov     rbp, [rsp+48h+arg_18]
0x1800181fc  add     rsp, 30h
0x180018200  pop     r14
0x180018202  pop     rdi
0x180018203  pop     rsi
0x180018204  retn
```
