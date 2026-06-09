# wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::GetCachedFeatureEnabledState(void)

- ea: `0x180018608`
- end: `0x180018731`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `297`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019d5c`
- `0x18001ab24`

## callees

- `0x180008c94`
- `0x18000ee40`
- `0x180017f9c`
- `0x180018608`
- `0x180018738`
- `0x18001ac44`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_EssFprPeripherals__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_EssFprPeripherals__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_EssFprPeripherals__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      wil::srwlock::lock_exclusive(qword_180031820, &v16);
      if ( !v5
        || v5 != dword_180031834
        || (v14[0] = 3,
            v14[1] = Feature_EssFprPeripherals__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180031858, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_EssFprPeripherals__descriptor, 0xFFFFFFFB);
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
0x180018608  mov     [rsp+arg_10], rbx
0x18001860d  mov     [rsp+arg_0], rcx
0x180018612  push    rbp
0x180018613  push    rsi
0x180018614  push    rdi
0x180018615  sub     rsp, 30h
0x180018619  mov     rsi, cs:Feature_EssFprPeripherals__descriptor
0x180018620  mov     rdi, rdx
0x180018623  mov     qword ptr [rdx], 0
0x18001862a  mov     eax, [rsi]
0x18001862c  mov     [rdx], eax
0x18001862e  and     eax, 6
0x180018631  cmp     al, 6
0x180018633  jz      loc_180018721
0x180018639  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001863e  lea     r8, [rsp+48h+arg_0]
0x180018643  mov     dword ptr [rsp+48h+arg_0], 0
0x18001864b  lea     rdx, [rsp+48h+arg_8]
0x180018650  mov     ebp, eax
0x180018652  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::GetCurrentFeatureEnabledState(int *)
0x180018657  mov     eax, [rdi]
0x180018659  mov     rbx, [rsp+48h+arg_8]
0x18001865e  cmp     dword ptr [rsp+48h+arg_0], 0
0x180018663  mov     edx, eax
0x180018665  mov     [rdi], eax
0x180018667  mov     ecx, eax
0x180018669  jz      short loc_180018684
0x18001866b  test    dl, 2
0x18001866e  jnz     short loc_180018684
0x180018670  and     ecx, 0FFFFF63Eh
0x180018676  mov     eax, ebx
0x180018678  and     eax, 9C1h
0x18001867d  or      ecx, eax
0x18001867f  or      ecx, 2
0x180018682  mov     [rdi], ecx
0x180018684  mov     r8d, edx
0x180018687  and     r8d, 4
0x18001868b  jnz     short loc_18001869F
0x18001868d  btr     ecx, 0Ah
0x180018691  mov     eax, ebx
0x180018693  and     eax, 400h
0x180018698  or      ecx, eax
0x18001869a  or      ecx, 4
0x18001869d  mov     [rdi], ecx
0x18001869f  mov     eax, edx
0x1800186a1  lock cmpxchg [rsi], ecx
0x1800186a5  jnz     short loc_18001865E
0x1800186a7  test    r8d, r8d
0x1800186aa  jnz     short loc_18001870C
0x1800186ac  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800186b2  test    eax, eax
0x1800186b4  jz      short loc_18001870C
0x1800186b6  lea     rdx, [rsp+48h+arg_8]
0x1800186bb  lea     rcx, qword_180031820
0x1800186c2  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x1800186c7  mov     eax, cs:dword_180031834
0x1800186cd  test    ebp, ebp
0x1800186cf  jz      short loc_1800186FE
0x1800186d1  cmp     ebp, eax
0x1800186d3  jnz     short loc_1800186FE
0x1800186d5  mov     r8d, 10h; unsigned __int64
0x1800186db  mov     [rsp+48h+var_28], 3
0x1800186e4  lea     rdx, [rsp+48h+var_28]; void *
0x1800186e9  mov     [rsp+48h+var_20], rsi
0x1800186ee  lea     rcx, qword_180031858; this
0x1800186f5  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800186fa  test    al, al
0x1800186fc  jnz     short loc_180018702
0x1800186fe  lock and dword ptr [rsi], 0FFFFFFFBh
0x180018702  lea     rcx, [rsp+48h+arg_8]
0x180018707  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001870c  mov     eax, [rdi]
0x18001870e  test    al, 2
0x180018710  jnz     short loc_180018721
0x180018712  and     eax, 0FFFFF63Eh
0x180018717  and     ebx, 9C1h
0x18001871d  or      eax, ebx
0x18001871f  mov     [rdi], eax
0x180018721  mov     rbx, [rsp+48h+arg_10]
0x180018726  mov     rax, rdi
0x180018729  add     rsp, 30h
0x18001872d  pop     rdi
0x18001872e  pop     rsi
0x18001872f  pop     rbp
0x180018730  retn
```
