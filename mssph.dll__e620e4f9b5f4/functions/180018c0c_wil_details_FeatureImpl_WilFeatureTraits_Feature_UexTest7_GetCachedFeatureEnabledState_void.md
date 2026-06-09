# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x180018c0c`
- end: `0x180018d45`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b6f4`
- `0x18001c22c`

## callees

- `0x18000d118`
- `0x180012908`
- `0x180015b28`
- `0x180018c0c`
- `0x180019658`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018cca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018cca`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UexTest7__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UexTest7__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UexTest7__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_1800367E8);
      v16 = &stru_1800367E8;
      if ( !v5
        || v5 != dword_1800367FC
        || (v14[0] = 3,
            v14[1] = Feature_UexTest7__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180036820, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_UexTest7__descriptor, 0xFFFFFFFB);
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
0x180018c0c  mov     [rsp+arg_10], rbx
0x180018c11  mov     [rsp+arg_18], rbp
0x180018c16  mov     [rsp+arg_0], rcx
0x180018c1b  push    rsi
0x180018c1c  push    rdi
0x180018c1d  push    r14
0x180018c1f  sub     rsp, 30h
0x180018c23  mov     rsi, cs:Feature_UexTest7__descriptor
0x180018c2a  mov     rdi, rdx
0x180018c2d  mov     qword ptr [rdx], 0
0x180018c34  mov     eax, [rsi]
0x180018c36  mov     [rdx], eax
0x180018c38  and     eax, 6
0x180018c3b  cmp     al, 6
0x180018c3d  jz      loc_180018D2F
0x180018c43  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180018c48  lea     r8, [rsp+48h+arg_0]
0x180018c4d  mov     dword ptr [rsp+48h+arg_0], 0
0x180018c55  lea     rdx, [rsp+48h+arg_8]
0x180018c5a  mov     ebp, eax
0x180018c5c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x180018c61  mov     eax, [rdi]
0x180018c63  mov     rbx, [rsp+48h+arg_8]
0x180018c68  cmp     dword ptr [rsp+48h+arg_0], 0
0x180018c6d  mov     edx, eax
0x180018c6f  mov     [rdi], eax
0x180018c71  mov     ecx, eax
0x180018c73  jz      short loc_180018C8E
0x180018c75  test    dl, 2
0x180018c78  jnz     short loc_180018C8E
0x180018c7a  and     ecx, 0FFFFF63Eh
0x180018c80  mov     eax, ebx
0x180018c82  and     eax, 9C1h
0x180018c87  or      ecx, eax
0x180018c89  or      ecx, 2
0x180018c8c  mov     [rdi], ecx
0x180018c8e  mov     r8d, edx
0x180018c91  and     r8d, 4
0x180018c95  jnz     short loc_180018CA9
0x180018c97  btr     ecx, 0Ah
0x180018c9b  mov     eax, ebx
0x180018c9d  and     eax, 400h
0x180018ca2  or      ecx, eax
0x180018ca4  or      ecx, 4
0x180018ca7  mov     [rdi], ecx
0x180018ca9  mov     eax, edx
0x180018cab  lock cmpxchg [rsi], ecx
0x180018caf  jnz     short loc_180018C68
0x180018cb1  test    r8d, r8d
0x180018cb4  jnz     short loc_180018D1A
0x180018cb6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180018cbc  test    eax, eax
0x180018cbe  jz      short loc_180018D1A
0x180018cc0  lea     r14, stru_1800367E8
0x180018cc7  mov     rcx, r14; SRWLock
0x180018cca  call    cs:__imp_AcquireSRWLockExclusive
0x180018cd0  mov     eax, cs:dword_1800367FC
0x180018cd6  mov     [rsp+48h+arg_8], r14
0x180018cdb  test    ebp, ebp
0x180018cdd  jz      short loc_180018D0C
0x180018cdf  cmp     ebp, eax
0x180018ce1  jnz     short loc_180018D0C
0x180018ce3  mov     r8d, 10h; unsigned __int64
0x180018ce9  mov     [rsp+48h+var_28], 3
0x180018cf2  lea     rdx, [rsp+48h+var_28]; void *
0x180018cf7  mov     [rsp+48h+var_20], rsi
0x180018cfc  lea     rcx, qword_180036820; this
0x180018d03  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180018d08  test    al, al
0x180018d0a  jnz     short loc_180018D10
0x180018d0c  lock and dword ptr [rsi], 0FFFFFFFBh
0x180018d10  lea     rcx, [rsp+48h+arg_8]
0x180018d15  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180018d1a  mov     eax, [rdi]
0x180018d1c  test    al, 2
0x180018d1e  jnz     short loc_180018D2F
0x180018d20  and     eax, 0FFFFF63Eh
0x180018d25  and     ebx, 9C1h
0x180018d2b  or      eax, ebx
0x180018d2d  mov     [rdi], eax
0x180018d2f  mov     rbx, [rsp+48h+arg_10]
0x180018d34  mov     rax, rdi
0x180018d37  mov     rbp, [rsp+48h+arg_18]
0x180018d3c  add     rsp, 30h
0x180018d40  pop     r14
0x180018d42  pop     rdi
0x180018d43  pop     rsi
0x180018d44  retn
```
