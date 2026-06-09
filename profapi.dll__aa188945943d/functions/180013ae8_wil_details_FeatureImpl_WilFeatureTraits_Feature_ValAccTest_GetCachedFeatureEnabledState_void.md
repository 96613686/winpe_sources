# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180013ae8`
- end: `0x180013c21`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800150bc`
- `0x180015ad0`

## callees

- `0x18000f11c`
- `0x180012c54`
- `0x180013ae8`
- `0x18001442c`
- `0x180015b2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013ba6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013ba6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800226CC
        || (v14[0] = 3,
            v14[1] = Feature_ValAccTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800226F0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ValAccTest__descriptor, 0xFFFFFFFB);
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
0x180013ae8  mov     [rsp+arg_10], rbx
0x180013aed  mov     [rsp+arg_18], rbp
0x180013af2  mov     [rsp+arg_0], rcx
0x180013af7  push    rsi
0x180013af8  push    rdi
0x180013af9  push    r14
0x180013afb  sub     rsp, 30h
0x180013aff  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180013b06  mov     rdi, rdx
0x180013b09  mov     qword ptr [rdx], 0
0x180013b10  mov     eax, [rsi]
0x180013b12  mov     [rdx], eax
0x180013b14  and     eax, 6
0x180013b17  cmp     al, 6
0x180013b19  jz      loc_180013C0B
0x180013b1f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013b24  lea     r8, [rsp+48h+arg_0]
0x180013b29  mov     dword ptr [rsp+48h+arg_0], 0
0x180013b31  lea     rdx, [rsp+48h+arg_8]
0x180013b36  mov     ebp, eax
0x180013b38  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180013b3d  mov     eax, [rdi]
0x180013b3f  mov     rbx, [rsp+48h+arg_8]
0x180013b44  cmp     dword ptr [rsp+48h+arg_0], 0
0x180013b49  mov     edx, eax
0x180013b4b  mov     [rdi], eax
0x180013b4d  mov     ecx, eax
0x180013b4f  jz      short loc_180013B6A
0x180013b51  test    dl, 2
0x180013b54  jnz     short loc_180013B6A
0x180013b56  and     ecx, 0FFFFF63Eh
0x180013b5c  mov     eax, ebx
0x180013b5e  and     eax, 9C1h
0x180013b63  or      ecx, eax
0x180013b65  or      ecx, 2
0x180013b68  mov     [rdi], ecx
0x180013b6a  mov     r8d, edx
0x180013b6d  and     r8d, 4
0x180013b71  jnz     short loc_180013B85
0x180013b73  btr     ecx, 0Ah
0x180013b77  mov     eax, ebx
0x180013b79  and     eax, 400h
0x180013b7e  or      ecx, eax
0x180013b80  or      ecx, 4
0x180013b83  mov     [rdi], ecx
0x180013b85  mov     eax, edx
0x180013b87  lock cmpxchg [rsi], ecx
0x180013b8b  jnz     short loc_180013B44
0x180013b8d  test    r8d, r8d
0x180013b90  jnz     short loc_180013BF6
0x180013b92  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013b98  test    eax, eax
0x180013b9a  jz      short loc_180013BF6
0x180013b9c  lea     r14, SRWLock
0x180013ba3  mov     rcx, r14; SRWLock
0x180013ba6  call    cs:__imp_AcquireSRWLockExclusive
0x180013bac  mov     eax, cs:dword_1800226CC
0x180013bb2  mov     [rsp+48h+arg_8], r14
0x180013bb7  test    ebp, ebp
0x180013bb9  jz      short loc_180013BE8
0x180013bbb  cmp     ebp, eax
0x180013bbd  jnz     short loc_180013BE8
0x180013bbf  mov     r8d, 10h; unsigned __int64
0x180013bc5  mov     [rsp+48h+var_28], 3
0x180013bce  lea     rdx, [rsp+48h+var_28]; void *
0x180013bd3  mov     [rsp+48h+var_20], rsi
0x180013bd8  lea     rcx, qword_1800226F0; this
0x180013bdf  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180013be4  test    al, al
0x180013be6  jnz     short loc_180013BEC
0x180013be8  lock and dword ptr [rsi], 0FFFFFFFBh
0x180013bec  lea     rcx, [rsp+48h+arg_8]
0x180013bf1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013bf6  mov     eax, [rdi]
0x180013bf8  test    al, 2
0x180013bfa  jnz     short loc_180013C0B
0x180013bfc  and     eax, 0FFFFF63Eh
0x180013c01  and     ebx, 9C1h
0x180013c07  or      eax, ebx
0x180013c09  mov     [rdi], eax
0x180013c0b  mov     rbx, [rsp+48h+arg_10]
0x180013c10  mov     rax, rdi
0x180013c13  mov     rbp, [rsp+48h+arg_18]
0x180013c18  add     rsp, 30h
0x180013c1c  pop     r14
0x180013c1e  pop     rdi
0x180013c1f  pop     rsi
0x180013c20  retn
```
