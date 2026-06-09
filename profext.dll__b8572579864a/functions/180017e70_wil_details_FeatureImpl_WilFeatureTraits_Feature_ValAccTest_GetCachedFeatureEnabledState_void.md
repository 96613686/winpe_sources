# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180017e70`
- end: `0x180017fb0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a594`
- `0x18001bb10`

## callees

- `0x180013750`
- `0x180016c90`
- `0x180017e70`
- `0x1800187d8`
- `0x18001c040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017f2e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017f2e`

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
        || v5 != dword_1800316D4
        || (v14[0] = 3,
            v14[1] = Feature_ValAccTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180031708, v14, 0x10u)) )
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
0x180017e70  mov     [rsp+arg_10], rbx
0x180017e75  mov     [rsp+arg_18], rbp
0x180017e7a  mov     [rsp+arg_0], rcx
0x180017e7f  push    rsi
0x180017e80  push    rdi
0x180017e81  push    r14
0x180017e83  sub     rsp, 30h
0x180017e87  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180017e8e  mov     rdi, rdx
0x180017e91  mov     qword ptr [rdx], 0
0x180017e98  mov     eax, [rsi]
0x180017e9a  mov     [rdx], eax
0x180017e9c  and     eax, 6
0x180017e9f  cmp     al, 6
0x180017ea1  jz      loc_180017F99
0x180017ea7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180017eac  lea     r8, [rsp+48h+arg_0]
0x180017eb1  mov     dword ptr [rsp+48h+arg_0], 0
0x180017eb9  lea     rdx, [rsp+48h+arg_8]
0x180017ebe  mov     ebp, eax
0x180017ec0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180017ec5  mov     eax, [rdi]
0x180017ec7  mov     rbx, [rsp+48h+arg_8]
0x180017ecc  cmp     dword ptr [rsp+48h+arg_0], 0
0x180017ed1  mov     edx, eax
0x180017ed3  mov     [rdi], eax
0x180017ed5  mov     ecx, eax
0x180017ed7  jz      short loc_180017EF2
0x180017ed9  test    dl, 2
0x180017edc  jnz     short loc_180017EF2
0x180017ede  and     ecx, 0FFFFF63Eh
0x180017ee4  mov     eax, ebx
0x180017ee6  and     eax, 9C1h
0x180017eeb  or      ecx, eax
0x180017eed  or      ecx, 2
0x180017ef0  mov     [rdi], ecx
0x180017ef2  mov     r8d, edx
0x180017ef5  and     r8d, 4
0x180017ef9  jnz     short loc_180017F0D
0x180017efb  btr     ecx, 0Ah
0x180017eff  mov     eax, ebx
0x180017f01  and     eax, 400h
0x180017f06  or      ecx, eax
0x180017f08  or      ecx, 4
0x180017f0b  mov     [rdi], ecx
0x180017f0d  mov     eax, edx
0x180017f0f  lock cmpxchg [rsi], ecx
0x180017f13  jnz     short loc_180017ECC
0x180017f15  test    r8d, r8d
0x180017f18  jnz     short loc_180017F84
0x180017f1a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180017f20  test    eax, eax
0x180017f22  jz      short loc_180017F84
0x180017f24  lea     r14, SRWLock
0x180017f2b  mov     rcx, r14; SRWLock
0x180017f2e  call    cs:__imp_AcquireSRWLockExclusive
0x180017f35  nop     dword ptr [rax+rax+00h]
0x180017f3a  mov     eax, cs:dword_1800316D4
0x180017f40  mov     [rsp+48h+arg_8], r14
0x180017f45  test    ebp, ebp
0x180017f47  jz      short loc_180017F76
0x180017f49  cmp     ebp, eax
0x180017f4b  jnz     short loc_180017F76
0x180017f4d  mov     r8d, 10h; unsigned __int64
0x180017f53  mov     [rsp+48h+var_28], 3
0x180017f5c  lea     rdx, [rsp+48h+var_28]; void *
0x180017f61  mov     [rsp+48h+var_20], rsi
0x180017f66  lea     rcx, qword_180031708; this
0x180017f6d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180017f72  test    al, al
0x180017f74  jnz     short loc_180017F7A
0x180017f76  lock and dword ptr [rsi], 0FFFFFFFBh
0x180017f7a  lea     rcx, [rsp+48h+arg_8]
0x180017f7f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017f84  mov     eax, [rdi]
0x180017f86  test    al, 2
0x180017f88  jnz     short loc_180017F99
0x180017f8a  and     eax, 0FFFFF63Eh
0x180017f8f  and     ebx, 9C1h
0x180017f95  or      eax, ebx
0x180017f97  mov     [rdi], eax
0x180017f99  mov     rbx, [rsp+48h+arg_10]
0x180017f9e  mov     rax, rdi
0x180017fa1  mov     rbp, [rsp+48h+arg_18]
0x180017fa6  add     rsp, 30h
0x180017faa  pop     r14
0x180017fac  pop     rdi
0x180017fad  pop     rsi
0x180017fae  retn
```
