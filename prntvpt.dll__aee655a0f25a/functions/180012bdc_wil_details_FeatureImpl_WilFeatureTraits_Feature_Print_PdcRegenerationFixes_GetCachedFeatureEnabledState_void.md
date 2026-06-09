# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PdcRegenerationFixes>::GetCachedFeatureEnabledState(void)

- ea: `0x180012bdc`
- end: `0x180012d15`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PdcRegenerationFixes@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015de0`
- `0x1800174b4`

## callees

- `0x18000d66c`
- `0x180012744`
- `0x180012bdc`
- `0x180012e5c`
- `0x1800175ec`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180012c9a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180012c9a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PdcRegenerationFixes>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Print_PdcRegenerationFixes__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Print_PdcRegenerationFixes__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PdcRegenerationFixes>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Print_PdcRegenerationFixes__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18003237C
        || (v14[0] = 3,
            v14[1] = Feature_Print_PdcRegenerationFixes__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800323A0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Print_PdcRegenerationFixes__descriptor, 0xFFFFFFFB);
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
0x180012bdc  mov     [rsp+arg_10], rbx
0x180012be1  mov     [rsp+arg_18], rbp
0x180012be6  mov     [rsp+arg_0], rcx
0x180012beb  push    rsi
0x180012bec  push    rdi
0x180012bed  push    r14
0x180012bef  sub     rsp, 30h
0x180012bf3  mov     rsi, cs:Feature_Print_PdcRegenerationFixes__descriptor
0x180012bfa  mov     rdi, rdx
0x180012bfd  mov     qword ptr [rdx], 0
0x180012c04  mov     eax, [rsi]
0x180012c06  mov     [rdx], eax
0x180012c08  and     eax, 6
0x180012c0b  cmp     al, 6
0x180012c0d  jz      loc_180012CFF
0x180012c13  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012c18  lea     r8, [rsp+48h+arg_0]
0x180012c1d  mov     dword ptr [rsp+48h+arg_0], 0
0x180012c25  lea     rdx, [rsp+48h+arg_8]
0x180012c2a  mov     ebp, eax
0x180012c2c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PdcRegenerationFixes@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PdcRegenerationFixes>::GetCurrentFeatureEnabledState(int *)
0x180012c31  mov     eax, [rdi]
0x180012c33  mov     rbx, [rsp+48h+arg_8]
0x180012c38  cmp     dword ptr [rsp+48h+arg_0], 0
0x180012c3d  mov     edx, eax
0x180012c3f  mov     [rdi], eax
0x180012c41  mov     ecx, eax
0x180012c43  jz      short loc_180012C5E
0x180012c45  test    dl, 2
0x180012c48  jnz     short loc_180012C5E
0x180012c4a  and     ecx, 0FFFFF63Eh
0x180012c50  mov     eax, ebx
0x180012c52  and     eax, 9C1h
0x180012c57  or      ecx, eax
0x180012c59  or      ecx, 2
0x180012c5c  mov     [rdi], ecx
0x180012c5e  mov     r8d, edx
0x180012c61  and     r8d, 4
0x180012c65  jnz     short loc_180012C79
0x180012c67  btr     ecx, 0Ah
0x180012c6b  mov     eax, ebx
0x180012c6d  and     eax, 400h
0x180012c72  or      ecx, eax
0x180012c74  or      ecx, 4
0x180012c77  mov     [rdi], ecx
0x180012c79  mov     eax, edx
0x180012c7b  lock cmpxchg [rsi], ecx
0x180012c7f  jnz     short loc_180012C38
0x180012c81  test    r8d, r8d
0x180012c84  jnz     short loc_180012CEA
0x180012c86  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180012c8c  test    eax, eax
0x180012c8e  jz      short loc_180012CEA
0x180012c90  lea     r14, SRWLock
0x180012c97  mov     rcx, r14; SRWLock
0x180012c9a  call    cs:__imp_AcquireSRWLockExclusive
0x180012ca0  mov     eax, cs:dword_18003237C
0x180012ca6  mov     [rsp+48h+arg_8], r14
0x180012cab  test    ebp, ebp
0x180012cad  jz      short loc_180012CDC
0x180012caf  cmp     ebp, eax
0x180012cb1  jnz     short loc_180012CDC
0x180012cb3  mov     r8d, 10h; unsigned __int64
0x180012cb9  mov     [rsp+48h+var_28], 3
0x180012cc2  lea     rdx, [rsp+48h+var_28]; void *
0x180012cc7  mov     [rsp+48h+var_20], rsi
0x180012ccc  lea     rcx, qword_1800323A0; this
0x180012cd3  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180012cd8  test    al, al
0x180012cda  jnz     short loc_180012CE0
0x180012cdc  lock and dword ptr [rsi], 0FFFFFFFBh
0x180012ce0  lea     rcx, [rsp+48h+arg_8]
0x180012ce5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012cea  mov     eax, [rdi]
0x180012cec  test    al, 2
0x180012cee  jnz     short loc_180012CFF
0x180012cf0  and     eax, 0FFFFF63Eh
0x180012cf5  and     ebx, 9C1h
0x180012cfb  or      eax, ebx
0x180012cfd  mov     [rdi], eax
0x180012cff  mov     rbx, [rsp+48h+arg_10]
0x180012d04  mov     rax, rdi
0x180012d07  mov     rbp, [rsp+48h+arg_18]
0x180012d0c  add     rsp, 30h
0x180012d10  pop     r14
0x180012d12  pop     rdi
0x180012d13  pop     rsi
0x180012d14  retn
```
