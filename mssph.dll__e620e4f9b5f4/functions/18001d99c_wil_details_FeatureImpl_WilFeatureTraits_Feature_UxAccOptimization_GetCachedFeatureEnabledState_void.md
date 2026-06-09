# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x18001d99c`
- end: `0x18001dad5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e0b8`
- `0x18001e298`

## callees

- `0x18000d118`
- `0x180012908`
- `0x180015b28`
- `0x18001d99c`
- `0x18001dcbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001da5a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001da5a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_1800367E8);
      v16 = &stru_1800367E8;
      if ( !v5
        || v5 != dword_1800367FC
        || (v14[0] = 3,
            v14[1] = Feature_UxAccOptimization__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180036820, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, 0xFFFFFFFB);
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
0x18001d99c  mov     [rsp+arg_10], rbx
0x18001d9a1  mov     [rsp+arg_18], rbp
0x18001d9a6  mov     [rsp+arg_0], rcx
0x18001d9ab  push    rsi
0x18001d9ac  push    rdi
0x18001d9ad  push    r14
0x18001d9af  sub     rsp, 30h
0x18001d9b3  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x18001d9ba  mov     rdi, rdx
0x18001d9bd  mov     qword ptr [rdx], 0
0x18001d9c4  mov     eax, [rsi]
0x18001d9c6  mov     [rdx], eax
0x18001d9c8  and     eax, 6
0x18001d9cb  cmp     al, 6
0x18001d9cd  jz      loc_18001DABF
0x18001d9d3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d9d8  lea     r8, [rsp+48h+arg_0]
0x18001d9dd  mov     dword ptr [rsp+48h+arg_0], 0
0x18001d9e5  lea     rdx, [rsp+48h+arg_8]
0x18001d9ea  mov     ebp, eax
0x18001d9ec  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18001d9f1  mov     eax, [rdi]
0x18001d9f3  mov     rbx, [rsp+48h+arg_8]
0x18001d9f8  cmp     dword ptr [rsp+48h+arg_0], 0
0x18001d9fd  mov     edx, eax
0x18001d9ff  mov     [rdi], eax
0x18001da01  mov     ecx, eax
0x18001da03  jz      short loc_18001DA1E
0x18001da05  test    dl, 2
0x18001da08  jnz     short loc_18001DA1E
0x18001da0a  and     ecx, 0FFFFF63Eh
0x18001da10  mov     eax, ebx
0x18001da12  and     eax, 9C1h
0x18001da17  or      ecx, eax
0x18001da19  or      ecx, 2
0x18001da1c  mov     [rdi], ecx
0x18001da1e  mov     r8d, edx
0x18001da21  and     r8d, 4
0x18001da25  jnz     short loc_18001DA39
0x18001da27  btr     ecx, 0Ah
0x18001da2b  mov     eax, ebx
0x18001da2d  and     eax, 400h
0x18001da32  or      ecx, eax
0x18001da34  or      ecx, 4
0x18001da37  mov     [rdi], ecx
0x18001da39  mov     eax, edx
0x18001da3b  lock cmpxchg [rsi], ecx
0x18001da3f  jnz     short loc_18001D9F8
0x18001da41  test    r8d, r8d
0x18001da44  jnz     short loc_18001DAAA
0x18001da46  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001da4c  test    eax, eax
0x18001da4e  jz      short loc_18001DAAA
0x18001da50  lea     r14, stru_1800367E8
0x18001da57  mov     rcx, r14; SRWLock
0x18001da5a  call    cs:__imp_AcquireSRWLockExclusive
0x18001da60  mov     eax, cs:dword_1800367FC
0x18001da66  mov     [rsp+48h+arg_8], r14
0x18001da6b  test    ebp, ebp
0x18001da6d  jz      short loc_18001DA9C
0x18001da6f  cmp     ebp, eax
0x18001da71  jnz     short loc_18001DA9C
0x18001da73  mov     r8d, 10h; unsigned __int64
0x18001da79  mov     [rsp+48h+var_28], 3
0x18001da82  lea     rdx, [rsp+48h+var_28]; void *
0x18001da87  mov     [rsp+48h+var_20], rsi
0x18001da8c  lea     rcx, qword_180036820; this
0x18001da93  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001da98  test    al, al
0x18001da9a  jnz     short loc_18001DAA0
0x18001da9c  lock and dword ptr [rsi], 0FFFFFFFBh
0x18001daa0  lea     rcx, [rsp+48h+arg_8]
0x18001daa5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001daaa  mov     eax, [rdi]
0x18001daac  test    al, 2
0x18001daae  jnz     short loc_18001DABF
0x18001dab0  and     eax, 0FFFFF63Eh
0x18001dab5  and     ebx, 9C1h
0x18001dabb  or      eax, ebx
0x18001dabd  mov     [rdi], eax
0x18001dabf  mov     rbx, [rsp+48h+arg_10]
0x18001dac4  mov     rax, rdi
0x18001dac7  mov     rbp, [rsp+48h+arg_18]
0x18001dacc  add     rsp, 30h
0x18001dad0  pop     r14
0x18001dad2  pop     rdi
0x18001dad3  pop     rsi
0x18001dad4  retn
```
