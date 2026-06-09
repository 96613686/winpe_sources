# wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcInVsm>::GetCachedFeatureEnabledState(void)

- ea: `0x18001beec`
- end: `0x18001c029`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NgcInVsm@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `317`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c5b8`

## callees

- `0x180008c94`
- `0x18000ee40`
- `0x180017f9c`
- `0x18001ac44`
- `0x18001beec`
- `0x18001c030`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcInVsm>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // r14d
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  int v12; // r8d
  _QWORD v14[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details *v15; // [rsp+50h] [rbp+20h] BYREF
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+28h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_NgcInVsm__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_NgcInVsm__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcInVsm>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
    if ( !v5 )
      LODWORD(v15) = 0;
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_NgcInVsm__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      wil::srwlock::lock_exclusive(qword_180031820, &v16);
      if ( !v5
        || v5 != dword_180031834
        || (v14[0] = 0,
            v14[1] = Feature_NgcInVsm__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180031858, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_NgcInVsm__descriptor, 0xFFFFF7C1);
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
0x18001beec  mov     [rsp-18h+arg_10], rbx
0x18001bef1  mov     [rsp-18h+arg_18], rsi
0x18001bef6  mov     [rsp-18h+arg_0], rcx
0x18001befb  push    rbp
0x18001befc  push    rdi
0x18001befd  push    r14
0x18001beff  mov     rbp, rsp
0x18001bf02  sub     rsp, 30h
0x18001bf06  mov     rsi, cs:Feature_NgcInVsm__descriptor
0x18001bf0d  mov     rdi, rdx
0x18001bf10  mov     qword ptr [rdx], 0
0x18001bf17  mov     eax, [rsi]
0x18001bf19  mov     [rdx], eax
0x18001bf1b  and     eax, 6
0x18001bf1e  cmp     al, 6
0x18001bf20  jz      loc_18001C013
0x18001bf26  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001bf2b  lea     r8, [rbp+arg_0]
0x18001bf2f  mov     dword ptr [rbp+arg_0], 0
0x18001bf36  lea     rdx, [rbp+arg_8]
0x18001bf3a  mov     r14d, eax
0x18001bf3d  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NgcInVsm@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcInVsm>::GetCurrentFeatureEnabledState(int *)
0x18001bf42  test    r14d, r14d
0x18001bf45  jnz     short loc_18001BF4B
0x18001bf47  mov     dword ptr [rbp+arg_0], r14d
0x18001bf4b  mov     eax, [rdi]
0x18001bf4d  mov     rbx, [rbp+arg_8]
0x18001bf51  cmp     dword ptr [rbp+arg_0], 0
0x18001bf55  mov     edx, eax
0x18001bf57  mov     [rdi], eax
0x18001bf59  mov     ecx, eax
0x18001bf5b  jz      short loc_18001BF76
0x18001bf5d  test    dl, 2
0x18001bf60  jnz     short loc_18001BF76
0x18001bf62  and     ecx, 0FFFFF63Eh
0x18001bf68  mov     eax, ebx
0x18001bf6a  and     eax, 9C1h
0x18001bf6f  or      ecx, eax
0x18001bf71  or      ecx, 2
0x18001bf74  mov     [rdi], ecx
0x18001bf76  mov     r8d, edx
0x18001bf79  and     r8d, 4
0x18001bf7d  jnz     short loc_18001BF91
0x18001bf7f  btr     ecx, 0Ah
0x18001bf83  mov     eax, ebx
0x18001bf85  and     eax, 400h
0x18001bf8a  or      ecx, eax
0x18001bf8c  or      ecx, 4
0x18001bf8f  mov     [rdi], ecx
0x18001bf91  mov     eax, edx
0x18001bf93  lock cmpxchg [rsi], ecx
0x18001bf97  jnz     short loc_18001BF51
0x18001bf99  test    r8d, r8d
0x18001bf9c  jnz     short loc_18001BFFE
0x18001bf9e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001bfa4  test    eax, eax
0x18001bfa6  jz      short loc_18001BFFE
0x18001bfa8  lea     rdx, [rbp+arg_8]
0x18001bfac  lea     rcx, qword_180031820
0x18001bfb3  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x18001bfb8  mov     eax, cs:dword_180031834
0x18001bfbe  test    r14d, r14d
0x18001bfc1  jz      short loc_18001BFEE
0x18001bfc3  cmp     r14d, eax
0x18001bfc6  jnz     short loc_18001BFEE
0x18001bfc8  mov     r8d, 10h; unsigned __int64
0x18001bfce  mov     [rbp+var_10], 0
0x18001bfd6  lea     rdx, [rbp+var_10]; void *
0x18001bfda  mov     [rbp+var_8], rsi
0x18001bfde  lea     rcx, qword_180031858; this
0x18001bfe5  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001bfea  test    al, al
0x18001bfec  jnz     short loc_18001BFF5
0x18001bfee  lock and dword ptr [rsi], 0FFFFF7C1h
0x18001bff5  lea     rcx, [rbp+arg_8]
0x18001bff9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001bffe  mov     eax, [rdi]
0x18001c000  test    al, 2
0x18001c002  jnz     short loc_18001C013
0x18001c004  and     eax, 0FFFFF63Eh
0x18001c009  and     ebx, 9C1h
0x18001c00f  or      eax, ebx
0x18001c011  mov     [rdi], eax
0x18001c013  mov     rbx, [rsp+30h+arg_10]
0x18001c018  mov     rax, rdi
0x18001c01b  mov     rsi, [rsp+30h+arg_18]
0x18001c020  add     rsp, 30h
0x18001c024  pop     r14
0x18001c026  pop     rdi
0x18001c027  pop     rbp
0x18001c028  retn
```
