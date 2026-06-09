# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x1800129a4`
- end: `0x180012add`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800147f4`

## callees

- `0x18000ab44`
- `0x18000c824`
- `0x18000d520`
- `0x1800129a4`
- `0x180012d5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012a62`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012a62`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180020758);
      v16 = &stru_180020758;
      if ( !v5
        || v5 != dword_18002076C
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_Future__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180020790, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_Future__descriptor, 0xFFFFFFFB);
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
0x1800129a4  mov     [rsp+arg_10], rbx
0x1800129a9  mov     [rsp+arg_18], rbp
0x1800129ae  mov     [rsp+arg_0], rcx
0x1800129b3  push    rsi
0x1800129b4  push    rdi
0x1800129b5  push    r14
0x1800129b7  sub     rsp, 30h
0x1800129bb  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x1800129c2  mov     rdi, rdx
0x1800129c5  mov     qword ptr [rdx], 0
0x1800129cc  mov     eax, [rsi]
0x1800129ce  mov     [rdx], eax
0x1800129d0  and     eax, 6
0x1800129d3  cmp     al, 6
0x1800129d5  jz      loc_180012AC7
0x1800129db  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800129e0  lea     r8, [rsp+48h+arg_0]
0x1800129e5  mov     dword ptr [rsp+48h+arg_0], 0
0x1800129ed  lea     rdx, [rsp+48h+arg_8]
0x1800129f2  mov     ebp, eax
0x1800129f4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCurrentFeatureEnabledState(int *)
0x1800129f9  mov     eax, [rdi]
0x1800129fb  mov     rbx, [rsp+48h+arg_8]
0x180012a00  cmp     dword ptr [rsp+48h+arg_0], 0
0x180012a05  mov     edx, eax
0x180012a07  mov     [rdi], eax
0x180012a09  mov     ecx, eax
0x180012a0b  jz      short loc_180012A26
0x180012a0d  test    dl, 2
0x180012a10  jnz     short loc_180012A26
0x180012a12  and     ecx, 0FFFFF63Eh
0x180012a18  mov     eax, ebx
0x180012a1a  and     eax, 9C1h
0x180012a1f  or      ecx, eax
0x180012a21  or      ecx, 2
0x180012a24  mov     [rdi], ecx
0x180012a26  mov     r8d, edx
0x180012a29  and     r8d, 4
0x180012a2d  jnz     short loc_180012A41
0x180012a2f  btr     ecx, 0Ah
0x180012a33  mov     eax, ebx
0x180012a35  and     eax, 400h
0x180012a3a  or      ecx, eax
0x180012a3c  or      ecx, 4
0x180012a3f  mov     [rdi], ecx
0x180012a41  mov     eax, edx
0x180012a43  lock cmpxchg [rsi], ecx
0x180012a47  jnz     short loc_180012A00
0x180012a49  test    r8d, r8d
0x180012a4c  jnz     short loc_180012AB2
0x180012a4e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180012a54  test    eax, eax
0x180012a56  jz      short loc_180012AB2
0x180012a58  lea     r14, stru_180020758
0x180012a5f  mov     rcx, r14; SRWLock
0x180012a62  call    cs:__imp_AcquireSRWLockExclusive
0x180012a68  mov     eax, cs:dword_18002076C
0x180012a6e  mov     [rsp+48h+arg_8], r14
0x180012a73  test    ebp, ebp
0x180012a75  jz      short loc_180012AA4
0x180012a77  cmp     ebp, eax
0x180012a79  jnz     short loc_180012AA4
0x180012a7b  mov     r8d, 10h; unsigned __int64
0x180012a81  mov     [rsp+48h+var_28], 3
0x180012a8a  lea     rdx, [rsp+48h+var_28]; void *
0x180012a8f  mov     [rsp+48h+var_20], rsi
0x180012a94  lea     rcx, qword_180020790; this
0x180012a9b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180012aa0  test    al, al
0x180012aa2  jnz     short loc_180012AA8
0x180012aa4  lock and dword ptr [rsi], 0FFFFFFFBh
0x180012aa8  lea     rcx, [rsp+48h+arg_8]
0x180012aad  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012ab2  mov     eax, [rdi]
0x180012ab4  test    al, 2
0x180012ab6  jnz     short loc_180012AC7
0x180012ab8  and     eax, 0FFFFF63Eh
0x180012abd  and     ebx, 9C1h
0x180012ac3  or      eax, ebx
0x180012ac5  mov     [rdi], eax
0x180012ac7  mov     rbx, [rsp+48h+arg_10]
0x180012acc  mov     rax, rdi
0x180012acf  mov     rbp, [rsp+48h+arg_18]
0x180012ad4  add     rsp, 30h
0x180012ad8  pop     r14
0x180012ada  pop     rdi
0x180012adb  pop     rsi
0x180012adc  retn
```
