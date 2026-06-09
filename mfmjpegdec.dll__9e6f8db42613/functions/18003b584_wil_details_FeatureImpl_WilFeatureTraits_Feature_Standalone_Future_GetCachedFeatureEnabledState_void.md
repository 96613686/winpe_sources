# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18003b584`
- end: `0x18003b6b7`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003ced0`

## callees

- `0x18003af20`
- `0x18003b30c`
- `0x18003b584`
- `0x18003baac`
- `0x18003dc50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b642`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b642`

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
  unsigned __int64 v13; // r8
  _QWORD Source[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v16; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v17; // [rsp+58h] [rbp+10h] BYREF

  v16 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCurrentFeatureEnabledState(
      v6,
      &v17,
      &v16);
    v7 = *(_DWORD *)a2;
    v8 = (__int16)v17;
    do
    {
      v9 = (_DWORD)v16 == 0;
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
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_18009D90C
        || (Source[0] = 3,
            Source[1] = Feature_Standalone_Future__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18009D930, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_Future__descriptor, 0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18003b584  mov     [rsp+arg_10], rbx
0x18003b589  mov     [rsp+arg_18], rbp
0x18003b58e  mov     [rsp+arg_0], rcx
0x18003b593  push    rsi
0x18003b594  push    rdi
0x18003b595  push    r14
0x18003b597  sub     rsp, 30h
0x18003b59b  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x18003b5a2  mov     rdi, rdx
0x18003b5a5  mov     qword ptr [rdx], 0
0x18003b5ac  mov     eax, [rsi]
0x18003b5ae  mov     [rdx], eax
0x18003b5b0  and     eax, 6
0x18003b5b3  cmp     al, 6
0x18003b5b5  jz      loc_18003B6A1
0x18003b5bb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18003b5c0  lea     r8, [rsp+48h+arg_0]
0x18003b5c5  mov     dword ptr [rsp+48h+arg_0], 0
0x18003b5cd  lea     rdx, [rsp+48h+arg_8]
0x18003b5d2  mov     ebp, eax
0x18003b5d4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCurrentFeatureEnabledState(int *)
0x18003b5d9  mov     eax, [rdi]
0x18003b5db  mov     rbx, [rsp+48h+arg_8]
0x18003b5e0  cmp     dword ptr [rsp+48h+arg_0], 0
0x18003b5e5  mov     edx, eax
0x18003b5e7  mov     [rdi], eax
0x18003b5e9  mov     ecx, eax
0x18003b5eb  jz      short loc_18003B606
0x18003b5ed  test    dl, 2
0x18003b5f0  jnz     short loc_18003B606
0x18003b5f2  and     ecx, 0FFFFF63Eh
0x18003b5f8  mov     eax, ebx
0x18003b5fa  and     eax, 9C1h
0x18003b5ff  or      ecx, eax
0x18003b601  or      ecx, 2
0x18003b604  mov     [rdi], ecx
0x18003b606  mov     r8d, edx
0x18003b609  and     r8d, 4
0x18003b60d  jnz     short loc_18003B621
0x18003b60f  btr     ecx, 0Ah
0x18003b613  mov     eax, ebx
0x18003b615  and     eax, 400h
0x18003b61a  or      ecx, eax
0x18003b61c  or      ecx, 4
0x18003b61f  mov     [rdi], ecx
0x18003b621  mov     eax, edx
0x18003b623  lock cmpxchg [rsi], ecx
0x18003b627  jnz     short loc_18003B5E0
0x18003b629  test    r8d, r8d
0x18003b62c  jnz     short loc_18003B68C
0x18003b62e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18003b634  test    eax, eax
0x18003b636  jz      short loc_18003B68C
0x18003b638  lea     r14, SRWLock
0x18003b63f  mov     rcx, r14; SRWLock
0x18003b642  call    cs:__imp_AcquireSRWLockExclusive
0x18003b648  mov     eax, cs:dword_18009D90C
0x18003b64e  mov     [rsp+48h+arg_8], r14
0x18003b653  test    ebp, ebp
0x18003b655  jz      short loc_18003B67E
0x18003b657  cmp     ebp, eax
0x18003b659  jnz     short loc_18003B67E
0x18003b65b  lea     rdx, [rsp+48h+Source]; Source
0x18003b660  mov     [rsp+48h+Source], 3
0x18003b669  lea     rcx, qword_18009D930; this
0x18003b670  mov     [rsp+48h+var_20], rsi
0x18003b675  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003b67a  test    al, al
0x18003b67c  jnz     short loc_18003B682
0x18003b67e  lock and dword ptr [rsi], 0FFFFFFFBh
0x18003b682  lea     rcx, [rsp+48h+arg_8]
0x18003b687  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003b68c  mov     eax, [rdi]
0x18003b68e  test    al, 2
0x18003b690  jnz     short loc_18003B6A1
0x18003b692  and     eax, 0FFFFF63Eh
0x18003b697  and     ebx, 9C1h
0x18003b69d  or      eax, ebx
0x18003b69f  mov     [rdi], eax
0x18003b6a1  mov     rbx, [rsp+48h+arg_10]
0x18003b6a6  mov     rax, rdi
0x18003b6a9  mov     rbp, [rsp+48h+arg_18]
0x18003b6ae  add     rsp, 30h
0x18003b6b2  pop     r14
0x18003b6b4  pop     rdi
0x18003b6b5  pop     rsi
0x18003b6b6  retn
```
