# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x180012ae4`
- end: `0x180012c1d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014878`
- `0x1800157d4`

## callees

- `0x18000ab44`
- `0x18000c824`
- `0x18000d520`
- `0x180012ae4`
- `0x180012df0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012ba2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012ba2`

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
      AcquireSRWLockExclusive(&stru_180020758);
      v16 = &stru_180020758;
      if ( !v5
        || v5 != dword_18002076C
        || (v14[0] = 3,
            v14[1] = Feature_UxAccOptimization__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180020790, v14, 0x10u)) )
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
0x180012ae4  mov     [rsp+arg_10], rbx
0x180012ae9  mov     [rsp+arg_18], rbp
0x180012aee  mov     [rsp+arg_0], rcx
0x180012af3  push    rsi
0x180012af4  push    rdi
0x180012af5  push    r14
0x180012af7  sub     rsp, 30h
0x180012afb  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x180012b02  mov     rdi, rdx
0x180012b05  mov     qword ptr [rdx], 0
0x180012b0c  mov     eax, [rsi]
0x180012b0e  mov     [rdx], eax
0x180012b10  and     eax, 6
0x180012b13  cmp     al, 6
0x180012b15  jz      loc_180012C07
0x180012b1b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012b20  lea     r8, [rsp+48h+arg_0]
0x180012b25  mov     dword ptr [rsp+48h+arg_0], 0
0x180012b2d  lea     rdx, [rsp+48h+arg_8]
0x180012b32  mov     ebp, eax
0x180012b34  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x180012b39  mov     eax, [rdi]
0x180012b3b  mov     rbx, [rsp+48h+arg_8]
0x180012b40  cmp     dword ptr [rsp+48h+arg_0], 0
0x180012b45  mov     edx, eax
0x180012b47  mov     [rdi], eax
0x180012b49  mov     ecx, eax
0x180012b4b  jz      short loc_180012B66
0x180012b4d  test    dl, 2
0x180012b50  jnz     short loc_180012B66
0x180012b52  and     ecx, 0FFFFF63Eh
0x180012b58  mov     eax, ebx
0x180012b5a  and     eax, 9C1h
0x180012b5f  or      ecx, eax
0x180012b61  or      ecx, 2
0x180012b64  mov     [rdi], ecx
0x180012b66  mov     r8d, edx
0x180012b69  and     r8d, 4
0x180012b6d  jnz     short loc_180012B81
0x180012b6f  btr     ecx, 0Ah
0x180012b73  mov     eax, ebx
0x180012b75  and     eax, 400h
0x180012b7a  or      ecx, eax
0x180012b7c  or      ecx, 4
0x180012b7f  mov     [rdi], ecx
0x180012b81  mov     eax, edx
0x180012b83  lock cmpxchg [rsi], ecx
0x180012b87  jnz     short loc_180012B40
0x180012b89  test    r8d, r8d
0x180012b8c  jnz     short loc_180012BF2
0x180012b8e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180012b94  test    eax, eax
0x180012b96  jz      short loc_180012BF2
0x180012b98  lea     r14, stru_180020758
0x180012b9f  mov     rcx, r14; SRWLock
0x180012ba2  call    cs:__imp_AcquireSRWLockExclusive
0x180012ba8  mov     eax, cs:dword_18002076C
0x180012bae  mov     [rsp+48h+arg_8], r14
0x180012bb3  test    ebp, ebp
0x180012bb5  jz      short loc_180012BE4
0x180012bb7  cmp     ebp, eax
0x180012bb9  jnz     short loc_180012BE4
0x180012bbb  mov     r8d, 10h; unsigned __int64
0x180012bc1  mov     [rsp+48h+var_28], 3
0x180012bca  lea     rdx, [rsp+48h+var_28]; void *
0x180012bcf  mov     [rsp+48h+var_20], rsi
0x180012bd4  lea     rcx, qword_180020790; this
0x180012bdb  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180012be0  test    al, al
0x180012be2  jnz     short loc_180012BE8
0x180012be4  lock and dword ptr [rsi], 0FFFFFFFBh
0x180012be8  lea     rcx, [rsp+48h+arg_8]
0x180012bed  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012bf2  mov     eax, [rdi]
0x180012bf4  test    al, 2
0x180012bf6  jnz     short loc_180012C07
0x180012bf8  and     eax, 0FFFFF63Eh
0x180012bfd  and     ebx, 9C1h
0x180012c03  or      eax, ebx
0x180012c05  mov     [rdi], eax
0x180012c07  mov     rbx, [rsp+48h+arg_10]
0x180012c0c  mov     rax, rdi
0x180012c0f  mov     rbp, [rsp+48h+arg_18]
0x180012c14  add     rsp, 30h
0x180012c18  pop     r14
0x180012c1a  pop     rdi
0x180012c1b  pop     rsi
0x180012c1c  retn
```
